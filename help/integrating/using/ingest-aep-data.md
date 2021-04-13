---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platformオーディエンスをキャンペーンに取り込む
description: Adobe Experience PlatformオーディエンスをCampaign Standardに取り込む方法を学びます。
audience: integrating
content-type: reference
feature: ソースと宛先
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 894d691f1df3a613bacc74e149e5fdf7f4531d92
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---


# Adobe Experience Platformオーディエンスをキャンペーンに取り込む{#destinations}

Adobe Experience Platformオーディエンスをキャンペーンに取り込み、ワークフローで使用するには、まずAdobe CampaignをAdobe Experience Platform **宛先**&#x200B;として接続し、エクスポートするセグメントと共に設定する必要があります。

宛先が設定されると、データはストレージの場所にエクスポートされ、取り込むために、Campaign Standardに専用のワークフローを構築する必要があります。

## Adobe Campaignを宛先として接続

Adobe Experience Platformで、Adobe Campaignとの接続を設定するには、書き出したセグメントのストレージの場所を選択します。 また、この手順では、エクスポートするセグメントを選択し、追加のXDMフィールドを指定して含めることもできます。

詳しくは、[宛先ドキュメント](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html)を参照してください。

宛先の設定が完了すると、Adobe Experience Platformは指定したストレージーの場所にタブ区切りの.txtまたは.csvファイルを作成します。 この操作は、24時間に1回スケジュールされて実行されます。

セグメントをキャンペーンに取り込むCampaign Standardワークフローを設定できるようになりました。

## Campaign Standardでのインポートワークフローの作成

Campaign Standardを宛先として設定したら、Adobe Experience Platformが書き出したファイルを読み込むための専用のワークフローを構築する必要があります。

これを行うには、**[!UICONTROL Transfer file]**&#x200B;アクティビティを追加して設定する必要があります。 このアクティビティの設定方法について詳しくは、[この](../../automating/using/transfer-file.md)セクションを参照してください。

![](assets/rtcdp-transfer-file.png)

その後、必要に応じてワークフローを構築できます(セグメントデータを使用してデータベースを更新し、チャネル間の配信をセグメントに送信するなど)。

例えば、以下のワークフローでは、ストレージーの場所から毎日ファイルをダウンロードし、その後、セグメントデータを使用してキャンペーンデータベースを更新します。

![](assets/rtcdp-workflow.png)

データ管理ワークフローの例については、[ワークフローの使用例](../../automating/using/about-workflow-use-cases.md#management)を参照してください。

関連トピック ： 

* [データ管理アクティビティ](../../automating/using/about-data-management-activities.md)
* [データインポートおよびエクスポートについて](../../automating/using/about-data-import-and-export.md)
