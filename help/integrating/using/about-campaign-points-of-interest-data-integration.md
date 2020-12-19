---
solution: Campaign Standard
product: campaign
title: Campaign と POI データの統合について
description: モバイルアプリの購読者から目標地点データを収集することで、Adobe Campaignの統合を通じて場所ベースのマーケティングメッセージを購読者に送信します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---


# Campaign と POI データの統合について{#about-campaign-points-of-interest-data-integration}

お客様のオンラインプレゼンスをトラッキングするだけでなく、物理的な場所を活用することもできます。 モバイル用Adobe Analyticsとの統合により、Adobe Campaignを使用して、場所ベースのマーケティングメッセージをモバイルアプリのサブスクリプションを購入したユーザーに送信できます。

目標地点は、ラベルに関連付けられた緯度、経度、半径で構成されます。 これらは、[AdobeMobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html)インターフェイスで定義されます。

購読者がモバイルアプリケーションを開くと、その場所が目標地点と一致する場合、Adobe CampaignはExperience CloudモバイルSDKを使用してデータをキャプチャします。 この情報を使用して、ユーザーの場所（電子メール、プッシュ通知、SMSメッセージなど）に基づいてパーソナライズされたメッセージを送信できます。

例えば、アプリを使用し、過去2週間以内にボストンのある店舗を訪問した顧客に10%割引オファーを送信できます。

[目標地点データ](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md)を使用したキャンペーンメッセージのパーソナライズの節に使用例が示されています。
