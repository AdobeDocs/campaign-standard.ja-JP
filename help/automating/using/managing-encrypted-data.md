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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: adc5e92183b891a70cac4aa7a6ed96148d104a20
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 7%

---


# 暗号化されたデータの管理 {#managing-encrypted-data}

## 前処理ステージについて {#about-preprocessing-stages}

場合によっては、キャンペーンサーバーにPIIデータが含まれている場合など、暗号化サーバーを読み込むデータを暗号化する必要があります。

暗号化されたファイルを読み込んだり書き出したりするには、まずアドビカスタマーケアに連絡して、インスタンスに必要な暗号化/復号化コマンドが提供されるようにする必要があります。

これを行うには、次のことを示すリクエストを送信します。

* コマンドを使用するためにキャンペーンインタフェースに表示される **ラベル** 。 例えば、「ファイルを暗号化」などです。
* インスタンスにインストールする **コマンド** 。

要求が処理されると、暗号化/復号化コマンドは、 **[!UICONTROL Pre-processing stage]** フィールド内の、およびの **[!UICONTROL Load file]****[!UICONTROL Extract file]** アクティビティから使用できます。 読み込みまたは書き出しを行うファイルは、これらを使用して復号化または暗号化できます。

![](assets/preprocessing-encryption.png)

>[!NOTE]
>
>GPGキーは、AWSでホストするすべてのお客様が利用できるコントロールパネルを使用して、インスタンスに追加できます（自分のマーケティングインスタンスをオンプレミスでホストするお客様を除く）。
>
>For more on this, refer to [Control Panel documentation](https://docs.adobe.com/content/help/ja-JP/control-panel/using/control-panel-home.html).

**関連トピック：**

* [ファイル読み込み](../../automating/using/load-file.md)
* [ファイル抽出](../../automating/using/extract-file.md)

## 使用例： コントロールパネルで生成されたキーを使用して暗号化されたデータの読み込み {#use-case-gpg-decrypt}

この使用例では、外部システムで暗号化されたデータを読み込むために、コントロールパネルで生成されたキーを使用してワークフローを構築します。

この使用例を実行する手順は次のとおりです。

1. コントロールパネルを使用して、キーペア（公開/秘密）を生成します。 詳細な手順は、 [コントロールパネルのドキュメントで確認できます](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data)。

   * 公開鍵は外部システムと共有され、外部システムはこのキーを使用して Campaign に送信するデータを暗号化します。
   * 秘密鍵は、受信する暗号化されたデータを復号化するために Campaign で使用されます。
   ![](assets/gpg_generate.png)

1. 外部システムでは、コントロールパネルからダウンロードした公開鍵を使用して、Campaign Standardにインポートするデータを暗号化します。

   ![](assets/gpg_external.png)

1. Campaign Standardで、暗号化されたデータを読み込むためのワークフローを作成し、コントロールパネルからインストールされた秘密鍵を使用して復号化します。 これを行うには、次のようにワークフローを構築します。

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** アクティビティ: ファイルを外部ソースからキャンペーンに転送します。 この例では、SFTPサーバーからファイルを転送します。
   * **[!UICONTROL Load file]** アクティビティ: ファイルのデータをデータベースに読み込み、コントロールパネルで生成された秘密鍵を使用して復号化します。

1. アクティビティを開き、必要に応じて **[!UICONTROL Transfer file]** 設定します。 この節では、アクティビティの設定方法に関するグローバルな概念について説明 [します](../../automating/using/load-file.md)。

   「 **[!UICONTROL Protocol]** 」タブで、転送するsftpサーバーと暗号化された.gpgファイルに関する詳細を指定します。

   ![](assets/gpg_transfer.png)

1. アクティビティを開き、必要に応じて **[!UICONTROL Load file]** 設定します。 この節では、アクティビティの設定方法に関するグローバルな概念について説明 [します](../../automating/using/load-file.md)。

   受信追加データを復号化するための、アクティビティへの事前処理段階。 これを行うには、リストから **[!UICONTROL Decryption GPG]** オプションを選択します。

   >[!NOTE]
   >
   >データの復号化に使用する秘密鍵を指定する必要はありません。 秘密鍵はコントロールパネルに保存され、ファイルの復号化に使用する鍵を自動的に検出します。

   ![](assets/gpg_load.png)

1. 「**[!UICONTROL OK]**」をクリックして、アクティビティの設定を確定します。

1. これで、ワークフローを実行できます。

## 使用例： コントロールパネルにインストールされたキーを使用して、データを暗号化およびエクスポートする {#use-case-gpg-encrypt}

この場合、コントロールパネルにインストールされたキーを使用してデータを暗号化およびエクスポートするためのワークフローを構築します。

この使用例を実行する手順は次のとおりです。

1. GPGユーティリティを使用してGPGキーペア（公開/秘密）を生成し、公開キーをコントロールパネルにインストールします。 詳細な手順は、 [コントロールパネルのドキュメントで確認できます](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data)。

   ![](assets/gpg_install.png)

1. Campaign Standardで、データを書き出すワークフローを作成し、コントロールパネルからインストールされた秘密鍵を使用して書き出します。 これを行うには、次のようにワークフローを構築します。

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** アクティビティ: この例では、クエリを実行して、エクスポートするデータベースのデータをターゲットします。
   * **[!UICONTROL Extract file]** アクティビティ: データを暗号化し、ファイルに抽出します。
   * **[!UICONTROL Transfer file]** アクティビティ: 暗号化されたデータを含むファイルをSFTPサーバーに転送します。

1. データベースから必要なデータをターゲットするように **[!UICONTROL Query]** アクティビティを設定します。 詳しくは、[この節](../../automating/using/query.md)を参照してください。

1. アクティビティを開き、必要に応じて設定します（出力ファイル、列、形式など）。 **[!UICONTROL Extract file]** この節では、アクティビティの設定方法に関するグローバルな概念について説明 [します](../../automating/using/extract-file.md)。

   抽出す追加るデータを暗号化するための、アクティビティへの事前処理段階。 これを行うには、データの暗号化に使用する暗号化GPGキーを選択します。

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >括弧内の値は、GPG暗号化ツールを使用してキーペアを生成する際に定義した **** コメントです。 正しい一致キーを選択していることを確認してください。選択していない場合、受信者はファイルを復号化できません。

1. アクティビティを開き、ファイルの送信先のSFTPサーバーを指定します。 **[!UICONTROL Transfer file]** この節では、アクティビティの設定方法に関するグローバルな概念について説明 [します](../../automating/using/transfer-file.md)。

   ![](assets/gpg-transfer-encrypt.png)

1. これで、ワークフローを実行できます。 実行後、クエリによるデータターゲットは、暗号化された.gpgファイルにSFTPサーバにエクスポートされます。

   ![](assets/gpg-sftp-encrypt.png)
