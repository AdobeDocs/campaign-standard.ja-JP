---
title: ソースと宛先の基本を学ぶ
description: Adobe Experience Platform のソースと宛先について説明します。
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
TQID: 'https://experienceleague.adobe.com/r1rASYXuo-xeKH80eZVYG-jUhxy93GuTa8CIDyouSNY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 64%
---
# ソースと宛先の概要 {#rtcdp}

## ソースと宛先について

Adobe Experience Platformでは、Campaign StandardとAdobe Real-time Customer Data Platform （RTCDP）間でデータを共有できます。 これにより、Campaign ワークフローで Adobe Experience Platform のオーディエンスをターゲットにして、オーディエンスに関するデータ（送信数、開封数、クリック数など）をアドビのリアルタイム顧客データプラットフォームに返すことができます。

* **宛先**&#x200B;を使用して、Adobe Experience PlatformからCampaign Standardにオーディエンスを取り込みます。 これにより、マーケティングキャンペーンで既知のデータや不明なデータを活用することができます。
* **ソース**&#x200B;を使用して、Campaign Standard データ（送信、開封、クリックなど）をAdobe Experience Platformに書き出します。 これにより、異なるソースから収集したデータを 1 か所に集め、得られたインサイトを利用してより多くのことを実行できます。


>[!IMPORTANT]
>
>この統合を使用する際は、Adobe Campaign の契約条件が定める SFTP ストレージ、データベースストレージ、アクティブプロファイルの制限に注意してください。

アドビのリアルタイム顧客データプラットフォーム、宛先、ソースについて詳しくは、次のページを参照してください。

* [アドビのリアルタイム顧客データプラットフォーム](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=ja)
* [宛先に関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=ja)
* [ソースに関するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=ja)

## Campaign StandardとAdobe Experience Platformの連携

Adobe Experience PlatformとCampaign Standard間でデータを共有するには、まずAdobe Campaignを&#x200B;**宛先**&#x200B;として接続し、AWS S3またはAzure BLOB ストレージの場所を&#x200B;**Source**&#x200B;としてAdobe Experience Platformに接続する必要があります。

コネクタを設定したら、ワークフローを使用してデータのインポートまたはCampaign Standardへのエクスポートを設定できます。

![](assets/rtcdp-schema.png)

これらのインポートおよびエクスポートプロセスの設定方法について詳しくは、次の節を参照してください。

* [Campaign への Adobe Experience Platform オーディエンスの取り込み](../../integrating/using/ingest-aep-data.md)
* [Campaign から Adobe Experience Platform へのデータのエクスポート](../../integrating/using/export-campaign-data.md)
