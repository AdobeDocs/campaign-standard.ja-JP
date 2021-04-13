---
solution: Campaign Standard
product: campaign
title: キャンペーンからAdobe Experience Platformへのデータのエクスポート
description: Campaign StandardからAdobe Experience Platformにデータをエクスポートする方法を説明します。
audience: integrating
content-type: reference
feature: ソースと宛先
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: bf442b12506ef71cc76aa7fffb0e4c8bb2ce70da
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# キャンペーンからAdobe Experience Platformへのデータのエクスポート{#sources}

Campaign StandardデータをAdobeリアルタイムCustomer Data Platform (RTCDP)にエクスポートするには、まず、Campaign Standardでワークフローを構築して、共有するデータをS3またはAzure BLOBストレージの場所にエクスポートする必要があります。

ワークフローが構成され、ストレージの場所にデータが送信されたら、S3またはAzure BLOBストレージの場所をAdobeエクスペリエンスプラットフォームの&#x200B;**Source**&#x200B;として接続する必要があります。

>[!NOTE]

キャンペーン生成データのみ（送信、開く、クリック数など）をエクスポートすることをお勧めします。 Adobe Experience Platformに サードパーティのソース（CRMなど）から取り込まれたデータは、Adobe Experience Platformに直接読み込む必要があります。

## Campaign Standardでの書き出しワークフローの作成

Campaign StandardからS3またはAzure Blobストレージの場所にデータをエクスポートするには、エクスポートするデータをターゲットするワークフローを構築し、ストレージの場所に送信する必要があります。

これを行うには、以下を追加して設定します。

* ターゲットデータをCSVファイルに抽出する&#x200B;**[!UICONTROL Extract file]**&#x200B;アクティビティ。 このアクティビティの設定方法について詳しくは、[この](../../automating/using/extract-file.md)セクションを参照してください。

   ![](assets/rtcdp-extract-file.png)

* CSVファイルをストレージの場所に転送する&#x200B;**[!UICONTROL Transfer file]**&#x200B;アクティビティ。 このアクティビティの設定方法について詳しくは、[この](../../automating/using/transfer-file.md)セクションを参照してください。

   ![](assets/rtcdp-transfer-file.png)

例えば、以下のワークフローでは、ログを定期的にCSVファイルに抽出し、そのファイルをストレージーの場所に転送します。

![](assets/aep-export.png)

データ管理ワークフローの例については、[ワークフローの使用例](../../automating/using/about-workflow-use-cases.md#management)を参照してください。

関連トピック ： 

* [データ管理アクティビティ](../../automating/using/about-data-management-activities.md)
* [データインポートおよびエクスポートについて](../../automating/using/about-data-import-and-export.md)


## ストレージの場所をソースとして接続する

S3またはAzure BLOBストレージの場所をAdobeエクスペリエンスプラットフォームの&#x200B;**ソース**&#x200B;として接続する主な手順を以下に示します。 これらの各手順に関する詳細は、[ソースコネクタドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html)を参照してください。

1. Adobe Experience Platform **[!UICONTROL Sources]**&#x200B;メニューで、ストレージの場所への接続を作成します。

   * [AmazonS3ソース接続の作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Azure BLOBコネクタ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >ストレージの場所は、AmazonS3、パスワード付きSFTP、SSHキー付きSFTP、またはAzure Blob接続です。 Adobe Campaignにデータを送信する推奨される方法は、AmazonS3またはAzure Blobを使用する方法です：

   ![](assets/rtcdp-connector.png)

1. クラウドストレージのバッチ接続のデータフローを設定します。 データフローとは、ストレージの場所からAdobe Experience Platformデータセットにデータを取得し、取り込むスケジュール設定されたタスクです。 この手順では、データ選択、CSVフィールドのXDMスキーマへのマッピングなど、ストレージの場所からのデータインジェストを設定できます。

   詳細な情報は、[このページ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html)にあります。

   ![](assets/rtcdp-map-xdm.png)

1. ソースの設定が完了すると、Adobe Experience Platformは指定したストレージーの場所からファイルをインポートします。

   この操作は、必要に応じてスケジュールできます。 インスタンスに既に存在する負荷に応じて、1日に最大6回エクスポートを実行することをお勧めします。
