---
title: Campaign と POI データの統合について
description: モバイルアプリケーションの購読者から POI データを収集し、Adobe Campaignの統合を通じて購読者に場所ベースのマーケティングメッセージを送信します。
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

顧客のオンラインプレゼンスを追跡するだけでなく、顧客の物理的な場所を利用することもできます。 Adobe Analytics for Mobile との統合により、Adobe Campaignを使用して、モバイルアプリケーションの購読者に場所ベースのマーケティングメッセージを送信できます。

目標点は、ラベルに関連付けられた緯度、経度、および半径で構成されます。 これらは、[Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html?lang=ja) インターフェイスで定義されます。

購読者がモバイルアプリケーションを開くと、その場所が目標地点に一致する場合、Adobe CampaignはExperience CloudモバイルSDKを介してデータをキャプチャします。 この情報を使用して、ユーザーの場所（メール、プッシュ通知、SMS メッセージなど）に基づいてパーソナライズされたメッセージを送信できます。

例えば、アプリケーションを使用して過去 2 週間以内にボストンのいずれかの店舗を訪問した顧客に 10% の割引オファーを送信できます。

使用例については、[POI データを使用した Campaign メッセージのパーソナライズ ](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md) の節を参照してください。
