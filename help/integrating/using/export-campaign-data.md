---
title: Campaign から Adobe Experience Platform へのデータのエクスポート
description: Campaign StandardからAdobe Experience Platformにデータを書き出す方法について説明します。
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
TQID: https://experienceleague.adobe.com/wevJB72xRacTndQ1-VOyKHOtRak0UKJT2V-pzUd6d-Q
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: b70f632b-2cfd-43d0-9266-284281100d70id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 537
ht-degree: 63%

---

# Campaign から Adobe Experience Platform へのデータのエクスポート {#sources}

Campaign Standard データをAdobe Real-time Customer Data Platform （RTCDP）に書き出すには、まずCampaign Standardでワークフローを作成して、Amazon Storage Service （S3）またはAzure Blob ストレージの場所に書き出す必要があります。

ワークフローを構成し、ストレージの場所にデータが送信されたら、S3 または Azure Blob のストレージの場所を Adobe Experience Platform の&#x200B;**ソース**&#x200B;として接続する必要があります。

>[!NOTE]
>
>Campaignで生成されたデータのみを書き出すことをお勧めします（送信、開封、クリックなど）。 Adobe Experience Platformに接続されます。 サードパーティのソース（CRM など）から取り込まれたデータは、Adobe Experience Platform に直接読み込む必要があります。

## Campaign Standardでの書き出しワークフローの作成

Campaign StandardからS3またはAzure Blob ストレージの場所にデータを書き出すには、書き出すデータをターゲットとするワークフローを作成して、ストレージの場所に送信する必要があります。

これをおこなうには、以下を追加して設定します。

* ターゲット データをCSV ファイルに抽出するための&#x200B;**[!UICONTROL Extract file]** アクティビティ。 このアクティビティの設定方法について詳しくは、[こちらの節](../../automating/using/extract-file.md)を参照してください。

  ![](assets/rtcdp-extract-file.png)

* CSV ファイルをストレージの場所に転送するための&#x200B;**[!UICONTROL Transfer file]** アクティビティ。 分割アクティビティの設定方法について詳しくは、[こちらの節](../../automating/using/transfer-file.md)を参照してください。

  ![](assets/rtcdp-transfer-file.png)

例えば、以下のワークフローでは、ログを定期的に CSV ファイルに抽出し、そのファイルをストレージの場所に転送します。

![](assets/aep-export.png)

データ管理ワークフローの例については、[ ワークフローのユースケース ](../../automating/using/about-workflow-use-cases.md#management)の節を参照してください。

関連トピック ：

* [データ管理アクティビティ](../../automating/using/about-data-management-activities.md)
* [データのインポートおよびエクスポートについて](../../automating/using/about-data-import-and-export.md)


## ストレージの場所をソースとして接続する

Amazon Storage Service （S3）またはAzure Blob ストレージの場所を&#x200B;**Source**&#x200B;としてAdobe Experience Platformに接続するための主な手順を以下に示します。 これらの各手順について詳しくは、[ソースコネクタのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)を参照してください。

1. Adobe Experience Platform **[!UICONTROL Sources]** メニューで、ストレージの場所への接続を作成します。

   * [Amazon S3 ソース接続の作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=ja)
   * [Azure Blob コネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html?lang=ja)

   >[!NOTE]
   >
   >ストレージの場所は、Amazon S3、パスワードを使用した SFTP、SSH キーを使用した SFTP、または Azure Blob 接続に設定できます。 Adobe Campaign にデータを送信する際には、Amazon S3 または Azure Blob を使用する方法を推奨します。

   ![](assets/rtcdp-connector.png)

1. クラウドストレージのバッチ接続のデータフローを設定します。 データフローとは、ストレージの場所からデータを取得し、Adobe Experience Platform データセットに取り込むようスケジュール設定されたタスクです。 この手順では、データ選択や、CSV フィールドの XDM スキーマへのマッピングを含め、ストレージの場所からのデータ取り込みを設定できます。

   詳しくは、[このページ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html?lang=ja)を参照してください。

   ![](assets/rtcdp-map-xdm.png)

1. ソースの設定が完了すると、Adobe Experience Platform は指定したストレージの場所からファイルをインポートします。

   この操作は、必要に応じてスケジュールできます。 エクスポートの実行回数は、インスタンスに既に存在する負荷に応じて、1 日最大 6 回までとすることをお勧めします。
