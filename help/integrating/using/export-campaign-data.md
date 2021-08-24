---
solution: Campaign Standard
product: campaign
title: Campaign から Adobe Experience Platform へのデータのエクスポート
description: Adobe Experience PlatformからCampaign Standardにデータを書き出す方法を説明します。
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
source-git-commit: ca8473f50b132b2d5ca58c6403d144fbf62741b0
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 68%

---

# Campaign から Adobe Experience Platform へのデータのエクスポート {#sources}

Campaign StandardデータをAdobeのリアルタイム顧客データプラットフォーム(RTCDP)に書き出すには、まずCampaign Standardでワークフローを構築して、Amazonストレージサービス(S3)またはAzure BLOBストレージの場所で共有するデータを書き出す必要があります。

ワークフローを構成し、ストレージの場所にデータが送信されたら、S3 または Azure Blob のストレージの場所を Adobe Experience Platform の&#x200B;**ソース**&#x200B;として接続する必要があります。

>[!NOTE]
>
>Campaign で生成されたデータのみ（送信数、開封数、クリック数など）をAdobe Experience Platform にエクスポートすることをお勧めします。サードパーティのソース（CRM など）から取り込まれたデータは、Adobe Experience Platform に直接インポートする必要があります。

## Campaign Standardでの書き出しワークフローの作成

Campaign StandardからS3またはAzure BLOBストレージの場所にデータをエクスポートするには、エクスポートするデータをターゲティングするワークフローを作成し、ストレージの場所に送信する必要があります。

これをおこなうには、以下を追加して設定します。

* ターゲットデータをCSVファイルに抽出する&#x200B;**[!UICONTROL Extract file]**&#x200B;アクティビティ。 このアクティビティの設定方法について詳しくは、[こちらの節](../../automating/using/extract-file.md)を参照してください。

   ![](assets/rtcdp-extract-file.png)

* CSVファイルをストレージの場所に転送する&#x200B;**[!UICONTROL Transfer file]**&#x200B;アクティビティ。 分割アクティビティの設定方法について詳しくは、[こちらの節](../../automating/using/transfer-file.md)を参照してください。

   ![](assets/rtcdp-transfer-file.png)

例えば、以下のワークフローでは、ログを定期的に CSV ファイルに抽出し、そのファイルをストレージの場所に転送します。

![](assets/aep-export.png)

データ管理ワークフローの例については、[ワークフローの使用例](../../automating/using/about-workflow-use-cases.md#management)の節を参照してください。

関連トピック ： 

* [データ管理アクティビティ](../../automating/using/about-data-management-activities.md)
* [データのインポートおよびエクスポートについて](../../automating/using/about-data-import-and-export.md)


## ストレージの場所をソースとして接続する

Amazon Storage Service(S3)またはAzure Blobストレージの場所をExperience Platformの&#x200B;**ソース**&#x200B;として接続する主な手順を以下に示します。 これらの各手順について詳しくは、[ソースコネクタのドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)を参照してください。

1. Adobe Experience Platformの&#x200B;**[!UICONTROL Sources]**&#x200B;メニューで、ストレージの場所への接続を作成します。

   * [Amazon S3 ソース接続の作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=ja)
   * [Azure Blob コネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html?lang=ja)

   >[!NOTE]
   >
   >ストレージの場所は、Amazon S3、パスワードを使用した SFTP、SSH キーを使用した SFTP、または Azure Blob 接続に設定できます。 Adobe Campaign にデータを送信する際には、Amazon S3 または Azure Blob を使用する方法を推奨します。

   ![](assets/rtcdp-connector.png)

1. クラウドストレージのバッチ接続のデータフローを設定します。 データフローとは、ストレージの場所からデータを取得し、Adobe Experience Platform データセットに取り込むようスケジュール設定されたタスクです。 この手順では、データ選択や、CSV フィールドの XDM スキーマへのマッピングなど、ストレージの場所からデータを取得するよう設定できます。

   詳しくは、[このページ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html?lang=ja)を参照してください。

   ![](assets/rtcdp-map-xdm.png)

1. ソースの設定が完了すると、Adobe Experience Platform は指定したストレージの場所からファイルをインポートします。

   この操作は、必要に応じてスケジュールできます。 エクスポートの実行回数は、インスタンスに既に存在する負荷に応じて、1 日最大 6 回までとすることをお勧めします。
