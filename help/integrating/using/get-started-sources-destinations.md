---
solution: Campaign Standard
product: campaign
title: ソースと宛先の基本を学ぶ
description: Adobe Experience Platform のソースと宛先について説明します。
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: ca8473f50b132b2d5ca58c6403d144fbf62741b0
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 64%

---

# ソースと宛先の概要 {#rtcdp}

## ソースと宛先について

Adobe Experience Platformを使用すると、Campaign StandardとAdobeのリアルタイム顧客データプラットフォーム(RTCDP)の間でデータを共有できます。 これにより、Campaign ワークフローで Adobe Experience Platform のオーディエンスをターゲットにして、オーディエンスに関するデータ（送信数、開封数、クリック数など）をアドビのリアルタイム顧客データプラットフォームに返すことができます。

* **宛先**&#x200B;を使用して、オーディエンスをAdobe Experience PlatformからCampaign Standardに取り込みます。 これにより、マーケティングキャンペーンで既知のデータや不明なデータを活用することができます。
* **Sources**&#x200B;を使用して、Campaign Standardデータ（例：送信、開封、クリック）をAdobe Experience Platformにエクスポートします。 これにより、異なるソースから収集したデータを 1 か所に集め、得られたインサイトを利用してより多くのことを実行できます。


>[!IMPORTANT]
>
>この統合を使用する際は、Adobe Campaign の契約条件が定める SFTP ストレージ、データベースストレージ、アクティブプロファイルの制限に注意してください。

アドビのリアルタイム顧客データプラットフォーム、宛先、ソースについて詳しくは、次のページを参照してください。

* [アドビのリアルタイム顧客データプラットフォーム](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja)
* [宛先に関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=ja)
* [ソースに関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)

## Campaign StandardとAdobe Experience Platformの接続

Adobe Experience PlatformとCampaign Standardの間でデータを共有するには、まずAdobe Campaignを&#x200B;**宛先**&#x200B;として接続し、AdobeエクスペリエンスプラットフォームでAWS S3またはAzure BLOBストレージの場所を&#x200B;**ソース**&#x200B;として接続する必要があります。

コネクタを設定したら、ワークフローを使用してデータのインポートまたはCampaign Standardへのエクスポートを設定できます。

![](assets/rtcdp-schema.png)

これらのインポートおよびエクスポートプロセスの設定方法について詳しくは、次の節を参照してください。

* [Campaign への Adobe Experience Platform オーディエンスの取り込み](../../integrating/using/ingest-aep-data.md)
* [Campaign から Adobe Experience Platform へのデータのエクスポート](../../integrating/using/export-campaign-data.md)
