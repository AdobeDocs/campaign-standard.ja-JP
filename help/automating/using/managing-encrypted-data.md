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
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 8%

---


# 暗号化されたデータの管理 {#managing-encrypted-data}

場合によっては、キャンペーンサーバーにPIIデータが含まれている場合など、暗号化サーバーを読み込むデータを暗号化する必要があります。

暗号化されたファイルを読み込んだり書き出したりするには、まずアドビカスタマーケアに連絡して、インスタンスに必要な暗号化/復号化コマンドが提供されるようにする必要があります。

これを行うには、次のことを示すリクエストを送信します。

* コマンドを使用するためにキャンペーンインタフェースに表示される **ラベル** 。 例えば、「ファイルを暗号化」などです。
* インスタンスにインストールする **コマンド** 。
たとえば、PGPを使ってファイルを復号するには、次のコマンドを使います。

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

要求が処理されると、暗号化/復号化コマンドは、 **[!UICONTROL Pre-processing stage]** フィールド内の、およびの **[!UICONTROL Load file]****[!UICONTROL Extract file]** アクティビティから使用できます。 読み込みまたは書き出しを行うファイルは、これらを使用して復号化または暗号化できます。

![](assets/preprocessing-encryption.png)

**関連トピック：**

* [ファイル読み込み](../../automating/using/load-file.md)
* [ファイル抽出](../../automating/using/extract-file.md)
