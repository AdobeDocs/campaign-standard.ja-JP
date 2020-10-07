---
title: 暗号化されたデータの管理
description: 暗号化されたデータを管理する方法を説明します。
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 44%

---


# 暗号化されたデータの管理 {#managing-encrypted-data}

## 前処理ステージについて {#about-preprocessing-stages}

場合によっては、キャンペーンサーバーにPIIデータが含まれている場合など、暗号化サーバーを読み込むデータを暗号化する必要があります。

送信データを暗号化したり、受信データを復号化したりするには、 [Campaign コントロールパネルを使用してGPGキーを管理する必要があります](https://docs.adobe.com/content/help/ja-JP/control-panel/using/instances-settings/gpg-keys-management.html)。

>[!NOTE]
>
>Campaign コントロールパネルは、AWS でホストされるすべてのお客様が利用できます（自分のマーケティングインスタンスをオンプレミスでホストするお客様を除く）。

Campaign コントロールパネルを使用する資格がない場合は、Adobeカスタマーケアに連絡して、インスタンスに必要な暗号化/復号化コマンドを提供してもらう必要があります。 これを行うには、次のことを示すリクエストを送信します。

* コマンドを使用するためにキャンペーンインタフェースに表示される **ラベル** 。 例えば、「ファイルを暗号化」などです。
* インスタンスにインストールする **コマンド** 。

要求が処理されると、暗号化/復号化コマンドは、 **[!UICONTROL Pre-processing stage]** フィールド内の、およびの **[!UICONTROL Load file]****[!UICONTROL Extract file]** アクティビティから使用できます。 読み込みまたは書き出しを行うファイルは、それらを使用して復号化または暗号化できます。

![](assets/preprocessing-encryption.png)

**関連トピック：**

* [ファイル読み込み](../../automating/using/load-file.md)
* [ファイル抽出](../../automating/using/extract-file.md)

## ユースケース：コントロールパネルで生成されたキーを使用して暗号化されたデータのインポート {#use-case-gpg-decrypt}

このユースケースでは、外部システムで暗号化されたデータを Campaign コントロールパネルで生成された鍵を使用してインポートするためのワークフローを作成します。

GPG キーを使用してデータを復号化する方法を示すチュートリアルビデオについては、[こちら](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/control-panel/gpg-key-management/decrypting-data.html)を参照してください。

このユースケースを実行する手順は次のとおりです。

1. Campaign コントロールパネルを使用して、キーペア（公開鍵と秘密鍵）を生成します。詳細な手順については、[Campaign コントロールパネルのドキュメント](https://docs.adobe.com/content/help/ja-JP/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data)を参照してください。

   * 公開鍵は外部システムと共有され、外部システムはこのキーを使用して Campaign に送信するデータを暗号化します。
   * 秘密鍵は、受信する暗号化されたデータを復号化するために Campaign で使用されます。

   ![](assets/gpg_generate.png)

1. 外部システムでは、Campaign コントロールパネルからダウンロードした公開鍵を使用して、Campaign Standardにインポートするデータを暗号化します。

   ![](assets/do-not-localize/gpg_external.png)

1. Campaign Standardで、暗号化されたデータを読み込むワークフローを構築し、Campaign コントロールパネル経由でインストールされた秘密鍵を使用して復号化します。 これをおこなうには、次のようにワークフローを作成します。

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** アクティビティ:ファイルを外部ソースからキャンペーンに転送します。 この例では、SFTPサーバーからファイルを転送します。
   * **[!UICONTROL Load file]** アクティビティ:ファイルからデータベースにデータを読み込み、Campaign コントロールパネルで生成された秘密鍵を使用して復号化します。

1. Open the **[!UICONTROL Transfer file]** activity then configure it according to your needs. アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/load-file.md)を参照してください。

   「 **[!UICONTROL Protocol]** 」タブで、転送するsftpサーバーと暗号化された.gpgファイルに関する詳細を指定します。

   ![](assets/gpg_transfer.png)

1. Open the **[!UICONTROL Load file]** activity, then configure it according to your needs. アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/load-file.md)を参照してください。

   受信データを復号化するために、アクティビティに前処理ステージを追加します。これを行うには、リストから **[!UICONTROL Decryption GPG]** オプションを選択します。

   >[!NOTE]
   >
   >データの復号化に使用する秘密鍵を指定する必要はありません。 秘密鍵はCampaign コントロールパネルに保存され、ファイルの復号化に使用する鍵が自動的に検出されます。

   ![](assets/gpg_load.png)

1. 「**[!UICONTROL OK]**」をクリックして、アクティビティの設定を確定します。

1. これで、ワークフローを開始できます。

## ユースケース：コントロールパネルにインストールされたキーを使用したデータの暗号化および書き出し {#use-case-gpg-encrypt}

このユースケースでは、Campaign コントロールパネルにインストールされたキーを使用してデータを暗号化およびエクスポートするためのワークフローを作成します。

GPG キーを使用してデータを暗号化する方法を示すチュートリアルビデオについては、[こちら](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/control-panel/gpg-key-management/using-a-gpg-key-to-encrypt-data.html)を参照してください。

このユースケースを実行する手順は次のとおりです。

1. GPG ユーティリティを使用して GPG キーペア（公開鍵／秘密鍵）を生成し、公開キーを Campaign コントロールパネルにインストールします。詳細な手順については、[Campaign コントロールパネルのドキュメント](https://docs.adobe.com/content/help/ja-JP/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data)を参照してください。

   ![](assets/gpg_install.png)

1. Campaign Standardで、データを書き出すワークフローを作成し、Campaign コントロールパネル経由でインストールされた秘密鍵を使用してデータを書き出します。 これをおこなうには、次のようにワークフローを作成します。

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** アクティビティ:この例では、クエリを実行して、エクスポートするデータベースのデータをターゲットします。
   * **[!UICONTROL Extract file]** アクティビティ:データを暗号化し、ファイルに抽出します。
   * **[!UICONTROL Transfer file]** アクティビティ:暗号化されたデータを含むファイルをSFTPサーバーに転送します。

1. Configure the **[!UICONTROL Query]** activity to target the desired data from the database. 詳しくは、[この節](../../automating/using/query.md)を参照してください。

1. アクティビティを開き、必要に応じて設定します（出力ファイル、列、形式など）。 **[!UICONTROL Extract file]** アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/extract-file.md)を参照してください。

   抽出す追加るデータを暗号化するための、アクティビティへの事前処理段階。 これを行うには、データの暗号化に使用する暗号化GPGキーを選択します。

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >括弧内の値は、GPG暗号化ツールを使用してキーペアを生成する際に定義した **** コメントです。 正しい一致キーを選択していることを確認してください。選択していない場合、受信者はファイルを復号化できません。

1. Open the **[!UICONTROL Transfer file]** activity, then specify the SFTP server to which you want to send the file. アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/transfer-file.md)を参照してください。

   ![](assets/gpg-transfer-encrypt.png)

1. これで、ワークフローを開始できます。ワークフローを実行すると、クエリで選択された対象データが、暗号化された .gpg ファイルにエクスポートされ、SFTP サーバーに転送されます。

   ![](assets/do-not-localize/gpg-sftp-encrypt.png)
