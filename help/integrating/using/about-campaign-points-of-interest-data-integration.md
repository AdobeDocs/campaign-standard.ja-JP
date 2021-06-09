---
solution: Campaign Standard
product: campaign
title: Campaign と POI データの統合について
description: モバイルアプリケーションの購読者から目標地点データを収集することで、Adobe Campaignでの統合を通じて、場所ベースのマーケティングメッセージを購読者に送信します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: オーディエンス
role: Data Architect
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 6%

---

# Campaign と POI データの統合について{#about-campaign-points-of-interest-data-integration}

お客様のオンラインプレゼンスを追跡するだけでなく、お客様の物理的な場所を活用することもできます。 Adobe Analytics for Mobileとの統合により、Adobe Campaignを使用して、モバイルアプリケーションの購読者に場所ベースのマーケティングメッセージを送信できます。

目標地点は、緯度、経度およびラベルに関連付けられた半径で構成されます。 これらは、[AdobeMobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html)インターフェイスで定義されます。

購読者がモバイルアプリケーションを開くと、その場所が目標地点と一致する場合、Adobe CampaignはMobile SDKを使用してExperience Cloudをキャプチャします。 この情報を使用して、ユーザーの場所（Eメール、プッシュ通知、SMSメッセージなど）に基づいてパーソナライズされたメッセージを送信できます。

例えば、アプリを使用し、過去2週間以内にボストンの店舗の1つを訪問した顧客に10%の割引オファーを送信できます。

使用例については、POIデータを使用したCampaignメッセージのパーソナライズ[の節で説明しています。](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md)
