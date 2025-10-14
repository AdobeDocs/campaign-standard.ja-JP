---
title: 暗号化されたデータの管理
description: 暗号化データの管理方法を説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows, Encryption
role: Data Architect
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: 69c47c8f3cbb405acbef634aa1ebaef8e767f159
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 28%

---

# 暗号化されたデータの管理 {#managing-encrypted-data}

## 前処理ステージについて {#about-preprocessing-stages}

Campaign サーバーのインポート対象となるデータの暗号化が必要になる場合があります（PII データが含まれている場合など）。

送信データの暗号化または受信データの復号化を可能にするには、[Campaign コントロールパネル](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=ja) を使用して GPG キーを管理する必要があります。

>[!NOTE]
>
>コントロールパネルは、AWS でホストされるすべてのお客様が利用できます（自分のマーケティングインスタンスをオンプレミスでホストするお客様を除く）。

Campaign コントロールパネルを使用する資格がない場合は、Adobeカスタマーケアに連絡して、必要な暗号化/復号化コマンドをインスタンスに提供してもらう必要があります。 それには、次を示すリクエストを送信します。

* コマンドを使用するために Campaign インターフェイスに表示される **ラベル**。 例えば、「ファイルを暗号化」などです。
* インスタンスにインストールする **コマンド**。

リクエストが処理されると、暗号化/復号化コマンドは、**[!UICONTROL Load file]** および **[!UICONTROL Extract file]** アクティビティの **[!UICONTROL Pre-processing stage]** フィールドで使用できるようになります。 インポートまたはエクスポートするファイルの暗号化または復号化に使用できます。

![](assets/preprocessing-encryption.png)

**関連トピック：**

* [ファイルを読み込み](../../automating/using/load-file.md)
* [ファイルを抽出](../../automating/using/extract-file.md)

## ユースケース：Campaign コントロールパネルで生成されたキーを使用して暗号化されたデータのインポート {#use-case-gpg-decrypt}

このユースケースでは、外部Campaign コントロールパネルで暗号化されたデータをシステムで生成されたキーを使用してインポートするためのワークフローを作成します。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

このユースケースを実行する手順は次のとおりです。

1. コントロールパネルを使用して、キーペア（公開鍵と秘密鍵）を生成します。詳細な手順については、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=ja#decrypting-data)を参照してください。

   * 公開鍵は外部システムと共有され、外部システムはこのキーを使用して Campaign に送信するデータを暗号化します。
   * 秘密鍵は、Campaign で受信した暗号化データの復号化に使用されます。

   ![](assets/gpg_generate.png)

1. 外部システムでは、Campaign コントロールパネルからダウンロードした公開鍵を使用して、Campaign Standardに読み込むデータを暗号化します。

1. Campaign Standardとして、暗号化されたデータをインポートするワークフローを作成し、Campaign コントロールパネル経由でインストールされた秘密鍵を使用して復号化します。 これを行うには、次のようにワークフローを作成します。

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** アクティビティ：外部ソースから Campaign にファイルを転送します。 この例では、SFTP サーバーからファイルを転送します。
   * **[!UICONTROL Load file]** クティビティ：ファイルからデータベースにデータを読み込み、Campaign コントロールパネルで生成された秘密鍵を使用して復号化します。

1. **[!UICONTROL Transfer file]** アクティビティを開き、必要に応じて設定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/load-file.md)を参照してください。

   「**[!UICONTROL Protocol]**」タブで、転送する sftp サーバーと暗号化された.gpg ファイルに関する詳細を指定します。

   ![](assets/gpg_transfer.png)

1. **[!UICONTROL Load file]** アクティビティを開き、必要に応じて設定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/load-file.md)を参照してください。

   受信データを復号化するために、アクティビティに前処理ステージを追加します。それには、リストから「**[!UICONTROL Decryption GPG]**」オプションを選択します。

   >[!NOTE]
   >
   >データの復号化に使用する秘密鍵を指定する必要はありません。 秘密鍵はCampaign コントロールパネルに保存され、ファイルの復号化に使用する鍵が自動的に検出されます。

   ![](assets/gpg_load.png)

1. 「**[!UICONTROL OK]**」をクリックして、アクティビティの設定を確認します。

1. これで、ワークフローを実行できます。

## ユースケース：Campaign コントロールパネルにインストールされたキーを使用したデータの暗号化およびエクスポート {#use-case-gpg-encrypt}

このユースケースでは、Campaign コントロールパネルにインストールされたキーを使用してデータを暗号化およびエクスポートするためのワークフローを作成します。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

このユースケースを実行する手順は次のとおりです。

1. GPG ユーティリティを使用して GPG キーペア（公開鍵／秘密鍵）を生成し、公開キーを コントロールパネルにインストールします。詳細な手順については、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=ja#encrypting-data)を参照してください。

   ![](assets/gpg_install.png)

1. Campaign Standardとして、データをエクスポートするワークフローを作成し、Campaign コントロールパネル経由でインストールされた秘密鍵を使用してデータを暗号化します。 これを行うには、次のようにワークフローを作成します。

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** アクティビティ：この例では、クエリを実行して、書き出すデータベースからのデータをターゲットにします。
   * **[!UICONTROL Extract file]** アクティビティ：データを暗号化し、ファイルに抽出します。
   * **[!UICONTROL Transfer file]** アクティビティ：暗号化されたデータを含むファイルを SFTP サーバーに転送します。

1. **[!UICONTROL Query]** アクティビティを設定して、データベースから目的のデータをターゲットにします。 詳しくは、[この節](../../automating/using/query.md)を参照してください。

1. **[!UICONTROL Extract file]** アクティビティを開き、必要に応じて設定します（出力ファイル、列、形式など）。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/extract-file.md)を参照してください。

   抽出するデータを暗号化するために、アクティビティに前処理ステージを追加します。 これを行うには、データの暗号化に使用する暗号化 GPG キーを選択します。

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >括弧内の値は、GPG 暗号化ツールを使用してキーペアを生成する際に定義した **コメント** です。 一致する正しいキーを選択していることを確認してください。選択されていないと、受信者はファイルを復号化できません。

1. **[!UICONTROL Transfer file]** アクティビティを開き、ファイルの送信先の SFTP サーバーを指定します。 アクティビティの設定方法に関するグローバルな概念については、[こちら](../../automating/using/transfer-file.md)を参照してください。

   ![](assets/gpg-transfer-encrypt.png)

1. これで、ワークフローを開始できます。ワークフローを実行すると、クエリで選択された対象データが、暗号化された .gpg ファイルにエクスポートされ、SFTP サーバーに転送されます。

## チュートリアルビデオ {#video}

このビデオでは、GPG キーを使用してデータを復号化する方法を紹介します。

>[!VIDEO](https://video.tv.adobe.com/v/41350?quality=12&captions=jpn)

このビデオでは、GPG キーを使用してデータを暗号化する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/41336?quality=12&captions=jpn)

その他のCampaign Standardチュートリアルビデオについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。
