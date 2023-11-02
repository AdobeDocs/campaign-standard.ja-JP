---
title: 暗号化されたデータの管理
description: 暗号化されたデータを管理する方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows, Encryption
role: Data Architect
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: 69c47c8f3cbb405acbef634aa1ebaef8e767f159
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 35%

---

# 暗号化されたデータの管理 {#managing-encrypted-data}

## 前処理ステージについて {#about-preprocessing-stages}

PII データを含む場合など、Campaign サーバーをインポートするデータが暗号化されている必要が生じる場合があります。

送信データを暗号化したり、受信データを復号化したりできるようにするには、 [Campaign コントロールパネル](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=ja).

>[!NOTE]
>
>コントロールパネルは、AWS でホストされるすべてのお客様が利用できます（自分のマーケティングインスタンスをオンプレミスでホストするお客様を除く）。

Campaign コントロールパネルを使用する資格がない場合は、Adobeカスタマーケアに連絡して、インスタンスに必要な暗号化/復号化コマンドを提供してもらう必要があります。 これをおこなうには、次の内容を示すリクエストを送信します。

* The **ラベル** これが Campaign インターフェイスに表示され、コマンドを使用します。 例：「ファイルを暗号化」。
* The **command** をクリックして、をインスタンスにインストールします。

リクエストが処理されると、 encryption / decryption コマンドは **[!UICONTROL Pre-processing stage]** フィールド **[!UICONTROL Load file]** および **[!UICONTROL Extract file]** アクティビティ。 これらを使用して、インポートまたはエクスポートするファイルを復号化または暗号化できます。

![](assets/preprocessing-encryption.png)

**関連トピック：**

* [ファイルを読み込み](../../automating/using/load-file.md)
* [ファイルを抽出](../../automating/using/extract-file.md)

## ユースケース：コントロールパネルで生成されたキーを使用して暗号化されたデータのインポート {#use-case-gpg-decrypt}

この使用例では、Campaign コントロールパネルで生成されたキーを使用して、外部システムで暗号化されたデータをインポートするためのワークフローを作成します。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

このユースケースを実行する手順は次のとおりです。

1. コントロールパネルを使用して、キーペア（公開鍵と秘密鍵）を生成します。詳細な手順については、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=ja#decrypting-data)を参照してください。

   * 公開鍵は外部システムと共有され、外部システムはこのキーを使用して Campaign に送信するデータを暗号化します。
   * 秘密鍵は、受信する暗号化されたデータを復号化するために Campaign で使用されます。

   ![](assets/gpg_generate.png)

1. 外部システムでは、Campaign コントロールパネルからダウンロードした公開鍵を使用して、Campaign Standardにインポートするデータを暗号化します。

1. Campaign Standardで、暗号化されたデータを読み込むワークフローを作成し、Campaign コントロールパネル経由でインストールされた秘密鍵を使用して復号化します。 これをおこなうには、次のようにワークフローを作成します。

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** アクティビティ：ファイルを外部ソースから Campaign に転送します。 この例では、SFTP サーバーからファイルを転送します。
   * **[!UICONTROL Load file]** activity：ファイルからデータベースにデータを読み込み、データベースで生成された秘密鍵を使用してCampaign コントロールパネルします。

1. を開きます。 **[!UICONTROL Transfer file]** アクティビティを設定し、必要に応じて設定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/load-file.md)を参照してください。

   Adobe Analytics の **[!UICONTROL Protocol]** 「 」タブで、sftp サーバーと、転送する暗号化された.gpg ファイルに関する詳細を指定します。

   ![](assets/gpg_transfer.png)

1. を開きます。 **[!UICONTROL Load file]** アクティビティを作成し、必要に応じて設定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/load-file.md)を参照してください。

   受信データを復号化するために、アクティビティに前処理ステージを追加します。これをおこなうには、「 **[!UICONTROL Decryption GPG]** 」オプションを選択します。

   >[!NOTE]
   >
   >データの復号化に使用する秘密鍵を指定する必要はありません。 秘密鍵はCampaign コントロールパネルに保存され、ファイルの復号化に使用する鍵が自動的に検出されます。

   ![](assets/gpg_load.png)

1. 「**[!UICONTROL OK]**」をクリックして、アクティビティの設定を確定します。

1. これで、ワークフローを開始できます。

## ユースケース：コントロールパネルにインストールされたキーを使用したデータの暗号化および書き出し {#use-case-gpg-encrypt}

この使用例では、Campaign コントロールパネルにインストールされたキーを使用してデータを暗号化およびエクスポートするためのワークフローを作成します。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

このユースケースを実行する手順は次のとおりです。

1. GPG ユーティリティを使用して GPG キーペア（公開鍵／秘密鍵）を生成し、公開キーを コントロールパネルにインストールします。詳細な手順については、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=ja#encrypting-data)を参照してください。

   ![](assets/gpg_install.png)

1. Campaign Standardで、データをエクスポートするワークフローを作成し、Campaign コントロールパネル経由でインストールされた秘密鍵を使用してデータを暗号化します。 これをおこなうには、次のようにワークフローを作成します。

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** アクティビティ：この例では、クエリを実行して、エクスポートするデータをデータベースから選択します。
   * **[!UICONTROL Extract file]** activity：データを暗号化してファイルに抽出します。
   * **[!UICONTROL Transfer file]** activity：暗号化されたデータを含むファイルを SFTP サーバーに転送します。

1. を設定します。 **[!UICONTROL Query]** 「 」アクティビティを使用して、目的のデータをデータベースから選択します。 詳しくは、[この節](../../automating/using/query.md)を参照してください。

1. を開きます。 **[!UICONTROL Extract file]** アクティビティを作成し、必要に応じて設定します（出力ファイル、列、形式など）。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/extract-file.md)を参照してください。

   抽出するデータを暗号化するために、アクティビティに前処理ステージを追加します。 これをおこなうには、データの暗号化に使用する暗号化 GPG キーを選択します。

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >括弧内の値は **コメント** GPG 暗号化ツールを使用してキーペアを生成する際に定義した値。 正しい一致キーを選択していることを確認してください。選択しないと、受信者はファイルを復号化できなくなります。

1. を開きます。 **[!UICONTROL Transfer file]** 「 」アクティビティを選択し、ファイルの送信先の SFTP サーバーを指定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/transfer-file.md)を参照してください。

   ![](assets/gpg-transfer-encrypt.png)

1. これで、ワークフローを開始できます。ワークフローを実行すると、クエリで選択された対象データが、暗号化された .gpg ファイルにエクスポートされ、SFTP サーバーに転送されます。

## チュートリアルビデオ {#video}

このビデオでは、GPG キーを使用してデータを復号化する方法を紹介します。

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

このビデオでは、GPG キーを使用してデータを暗号化する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

その他のCampaign Standardのハウツービデオも利用できます [ここ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja).
