---
title: Campaign と POI データの統合について
description: モバイルアプリケーションの購読者からPoints of Interest データを収集し、Adobe Campaignとの統合により、位置情報にもとづくマーケティングメッセージを購読者に送ります。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
TQID: 'https://experienceleague.adobe.com/NMHm-sHLhsjMqprniSnxca27zpoxGEhRGKlt1IJXfVg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# Campaign と POI データの統合について{#about-campaign-points-of-interest-data-integration}

顧客のオンラインプレゼンスを追跡するだけでなく、物理的な場所を利用することもできます。 Adobe Analytics for Mobileと連携することで、Adobe Campaignを使用して、ロケーションベースのマーケティングメッセージをモバイルアプリケーションの購読者に送信できます。

目標点は、ラベルに関連付けられた緯度、経度、半径で構成されます。 これらは、[Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html) インターフェイスで定義されます。

顧客がモバイルアプリケーションを開くと、位置情報がPoint of Interestと一致する場合、Adobe CampaignはExperience Cloud Mobile SDKを介してデータを取得します。 この情報を使用して、ユーザーの場所（電子メール、プッシュ通知、SMS メッセージなど）に基づいてパーソナライズされたメッセージを送信できます。

例えば、過去2週間以内にボストンのある店舗を訪問し、アプリを使用している顧客に10%の割引オファーを送信することができます。

ユースケースについては、「[Point of Interest データを使用したキャンペーンメッセージのパーソナライズ ](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md)」セクションを参照してください。
