---
title: POI データを使用した Campaign メッセージのパーソナライズ
description: POI データ統合を使用して、購読者の場所に基づいてパーソナライズされたメッセージを作成する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 10%

---

# POI データを使用した Campaign メッセージのパーソナライズ{#personalizing-campaign-messages-with-point-of-interest-data}

Adobe Campaignでは、モバイルアプリケーションの購読者から収集した POI データを使用して、パーソナライズされたマーケティングメッセージ（メールなど）を送信できます。

標準配信を使用して反応できるのは、目標点データのみです。 [&#x200B; トランザクションメッセージ &#x200B;](../../channels/using/getting-started-with-transactional-msg.md) は場所データを使用できません。

反応できる最も早い時間は約 10 分です。

この場合、過去 2 週間以内にボストンのストアに訪問したすべての購読者にメールを送信することにします。

1. メールマーケティングアクティビティを作成します。
1. 配信のオーディエンスを定義する場合は、**[!UICONTROL Subscriptions to an application]** 要素をワークスペースにドラッグ&amp;ドロップします。

   ![](assets/poi_subscriptions_app.png)

   オーディエンスの管理について詳しくは、[&#x200B; オーディエンスの定義 &#x200B;](../../audiences/using/creating-audiences.md) の節を参照してください。

1. **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** ウィンドウで、**[!UICONTROL POI Location Subscription]** 要素をワークスペースにドラッグ&amp;ドロップします。

   ![](assets/poi_add_rule_profile_subscription.png)

1. **[!UICONTROL Add a rule - POI Location Subscription]** ウィンドウで、使用する目標点のラベルを入力します。

   ![](assets/poi_location_subscription.png)

1. 「**[!UICONTROL Filter type]**」フィールドで「**[!UICONTROL Relative]**」を選択します。
1. 「**[!UICONTROL Preceding days]**」オプションをオンにし、対応するフィールドに **[!UICONTROL 15]** と入力します。
1. ユーザーが目標点にアクセスした必要がある回数を定義します。
1. 「**[!UICONTROL Confirm]**」をクリックして、オーディエンスを保存します。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. メールにコンテンツを追加します。

   ![](assets/poi_email_content.png)

1. アクティビティの作成を確認して、メールのダッシュボードを表示します。
1. メッセージを送信します。

10% の割引オファーが記載されたメールは、次の購読者に送信されます。

* あなたのボストンの店を過去 2 週間以内に少なくとも 1 回訪問しました。
* 訪問中に少なくとも 1 回はモバイルアプリケーションをフォアグラウンドで使用していました。

**関連トピック：**

* [メールの作成](../../channels/using/creating-an-email.md)
* [コンテンツの定義](../../designing/using/personalization.md#example-email-personalization)
* [メッセージの送信](../../sending/using/confirming-the-send.md)
