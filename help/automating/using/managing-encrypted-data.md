---
title: 暗号化されたデータの管理
description: 暗号化されたデータを管理する方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 42%

---

# 暗号化されたデータの管理 {#managing-encrypted-data}

## 前処理ステージについて {#about-preprocessing-stages}

PIIデータを含む場合など、Campaignサーバーをインポートするデータを暗号化する必要が生じる場合があります。

送信データを暗号化または受信データを復号化するには、[Campaign コントロールパネル](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=ja)を使用してGPGキーを管理する必要があります。

>[!NOTE]
>
>Campaign コントロールパネルは、AWS でホストされるすべてのお客様が利用できます（自分のマーケティングインスタンスをオンプレミスでホストするお客様を除く）。

Campaign コントロールパネルを使用する資格がない場合は、Adobeカスタマーケアに連絡して、インスタンスに必要な暗号化/復号化コマンドを提供してもらう必要があります。 これをおこなうには、次を示すリクエストを送信します。

* コマンドを使用するためにCampaignインターフェイスに表示される&#x200B;**label**。 （例：「ファイルを暗号化」）。
* インスタンスにインストールする&#x200B;**コマンド**。

リクエストが処理されると、**[!UICONTROL Load file]**&#x200B;および&#x200B;**[!UICONTROL Extract file]**&#x200B;アクティビティの&#x200B;**[!UICONTROL Pre-processing stage]**&#x200B;フィールドで暗号化/復号化コマンドを使用できるようになります。 これらを使用して、インポートまたはエクスポートするファイルを復号化または暗号化できます。

![](assets/preprocessing-encryption.png)

**関連トピック：**

* [ファイルを読み込み](../../automating/using/load-file.md)
* [ファイルを抽出](../../automating/using/extract-file.md)

## ユースケース：コントロールパネルで生成されたキーを使用して暗号化されたデータのインポート {#use-case-gpg-decrypt}

このユースケースでは、外部システムで暗号化されたデータを Campaign コントロールパネルで生成されたキーを使用してインポートするためのワークフローを作成します。

![](assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

このユースケースを実行する手順は次のとおりです。

1. Campaign コントロールパネルを使用して、キーペア（公開鍵と秘密鍵）を生成します。詳細な手順については、[Campaign コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=ja#decrypting-data)を参照してください。

   * 公開鍵は外部システムと共有され、外部システムはこのキーを使用して Campaign に送信するデータを暗号化します。
   * 秘密鍵は、受信する暗号化されたデータを復号化するために Campaign で使用されます。

   ![](assets/gpg_generate.png)

1. 外部システムでは、Campaign コントロールパネルからダウンロードした公開鍵を使用して、Campaign Standardにインポートするデータを暗号化します。

1. Campaign Standardで、暗号化されたデータを読み込むワークフローを構築し、Campaign コントロールパネル経由でインストールされた秘密鍵を使用して復号化します。 これをおこなうには、次のようにワークフローを作成します。

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** アクティビティ：ファイルを外部ソースからCampaignに転送します。この例では、SFTPサーバーからファイルを転送します。
   * **[!UICONTROL Load file]** アクティビティ：ファイルからデータベースにデータを読み込み、データベースで生成された秘密鍵を使用して復号化Campaign コントロールパネル。

1. **[!UICONTROL Transfer file]**&#x200B;アクティビティを開き、必要に応じて設定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/load-file.md)を参照してください。

   「 **[!UICONTROL Protocol]** 」タブで、SFTPサーバーと、転送する暗号化された.gpgファイルに関する詳細を指定します。

   ![](assets/gpg_transfer.png)

1. **[!UICONTROL Load file]**&#x200B;アクティビティを開き、必要に応じて設定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/load-file.md)を参照してください。

   受信データを復号化するために、アクティビティに前処理ステージを追加します。これをおこなうには、リストから&#x200B;**[!UICONTROL Decryption GPG]**&#x200B;オプションを選択します。

   >[!NOTE]
   >
   >データの復号化に使用する秘密鍵を指定する必要はありません。 秘密鍵はCampaign コントロールパネルに保存され、ファイルの復号化に使用する鍵を自動的に検出します。

   ![](assets/gpg_load.png)

1. 「**[!UICONTROL OK]**」をクリックして、アクティビティの設定を確定します。

1. これで、ワークフローを開始できます。

## ユースケース：コントロールパネルにインストールされたキーを使用したデータの暗号化および書き出し {#use-case-gpg-encrypt}

このユースケースでは、Campaign コントロールパネルにインストールされたキーを使用してデータを暗号化およびエクスポートするためのワークフローを作成します。

![](assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

このユースケースを実行する手順は次のとおりです。

1. GPG ユーティリティを使用して GPG キーペア（公開鍵／秘密鍵）を生成し、公開キーを Campaign コントロールパネルにインストールします。詳細な手順については、[Campaign コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data)を参照してください。

   ![](assets/gpg_install.png)

1. 「 」Campaign Standardで、データをエクスポートするワークフローを作成し、ワークフロー経由でインストールされた秘密鍵を使用してCampaign コントロールパネルを暗号化します。 これをおこなうには、次のようにワークフローを作成します。

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** アクティビティ：この例では、クエリを実行して、エクスポートするデータベースのデータをターゲットにします。
   * **[!UICONTROL Extract file]** アクティビティ：データを暗号化してファイルに抽出します。
   * **[!UICONTROL Transfer file]** アクティビティ：暗号化されたデータを含むファイルをSFTPサーバーに転送します。

1. **[!UICONTROL Query]**&#x200B;アクティビティを設定し、データベースから目的のデータをターゲットにします。 詳しくは、[この節](../../automating/using/query.md)を参照してください。

1. **[!UICONTROL Extract file]**&#x200B;アクティビティを開き、必要に応じて設定します（出力ファイル、列、形式など）。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/extract-file.md)を参照してください。

   抽出するデータを暗号化するために、アクティビティに前処理ステージを追加します。 これをおこなうには、データの暗号化に使用する暗号化GPGキーを選択します。

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >括弧内の値は、GPG暗号化ツールを使用してキーペアを生成する際に定義した&#x200B;**comment**&#x200B;です。 正しい一致キーを選択していることを確認してください。選択していない場合、受信者はファイルを復号化できません。

1. **[!UICONTROL Transfer file]**&#x200B;アクティビティを開き、ファイルの送信先のSFTPサーバーを指定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/transfer-file.md)を参照してください。

   ![](assets/gpg-transfer-encrypt.png)

1. これで、ワークフローを開始できます。ワークフローを実行すると、クエリで選択された対象データが、暗号化された .gpg ファイルにエクスポートされ、SFTP サーバーに転送されます。

## チュートリアルビデオ {#video}

このビデオでは、GPG キーを使用してデータを復号化する方法を紹介します。

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

このビデオでは、GPGキーを使用してデータを暗号化する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)からご覧いただけます。
