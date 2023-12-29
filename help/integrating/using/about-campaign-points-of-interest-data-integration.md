---
title: Campaign と POI データの統合について
description: モバイルアプリケーションの購読者から Points of Interest データを収集することで、Adobe Campaignの統合を通じて、購読者に場所ベースのマーケティングメッセージを送信します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 6%

---

# Campaign と POI データの統合について{#about-campaign-points-of-interest-data-integration}

お客様のオンラインプレゼンスを追跡するだけでなく、お客様の物理的な場所を活用することもできます。 Adobe Analytics for Mobile との統合により、Adobe Campaignを使用して、モバイルアプリケーションの購読者に場所ベースのマーケティングメッセージを送信できます。

目標地点は、緯度、経度、およびラベルに関連付けられた半径で構成されます。 これらは、 [AdobeMobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html) インターフェイス。

購読者がモバイルアプリケーションを開くと、その場所が目標地点と一致する場合、Adobe CampaignはExperience CloudMobile SDK を使用してデータをキャプチャします。 この情報を使用して、ユーザーの場所（E メール、プッシュ通知、SMS メッセージなど）に基づいてパーソナライズされたメッセージを送信できます。

例えば、アプリを使用し、過去 2 週間以内にボストンの店舗の 1 つを訪問した顧客に 10%の割引オファーを送信できます。

使用例については、 [POI データを使用した Campaign メッセージのパーソナライズ](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md) 」セクションに入力します。
