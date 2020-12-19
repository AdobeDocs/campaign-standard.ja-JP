---
solution: Campaign Standard
product: campaign
title: POI データを使用した Campaign メッセージのパーソナライズ
description: 目標地点データの統合を使用して、購読者の場所に基づいてパーソナライズされたメッセージを作成する方法について説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# POI データを使用した Campaign メッセージのパーソナライズ{#personalizing-campaign-messages-with-point-of-interest-data}

Adobe Campaignでは、モバイルアプリの購読者から収集した目標地点データを使用して、電子メールなどのパーソナライズされたマーケティングメッセージを送信できます。

目標地点データは、標準配信とのみ反応できます。 [トランザクション](../../channels/using/getting-started-with-transactional-msg.md) メッセージでは、場所のデータを使用できません。

反応が早いのは約10分です。

この場合、過去2週間以内にボストンストアを訪問したすべての購読者に電子メールを送信することにします。

1. 電子メールマーケティングアクティビティを作成します。
1. 配信のオーディエンスを定義する際に、**[!UICONTROL Subscriptions to an application]**&#x200B;要素をワークスペースにドラッグ&amp;ドロップします。

   ![](assets/poi_subscriptions_app.png)

   オーディエンスの管理の詳細については、「[オーディエンスの定義](../../audiences/using/creating-audiences.md)」の節を参照してください。

1. **[!UICONTROL Add a rule - Profile/Subscriptions to an application]**&#x200B;ウィンドウで、**[!UICONTROL POI Location Subscription]**&#x200B;要素をワークスペースにドラッグ&amp;ドロップします。

   ![](assets/poi_add_rule_profile_subscription.png)

1. **[!UICONTROL Add a rule - POI Location Subscription]**&#x200B;ウィンドウで、使用する目標地点のラベルを入力します。

   ![](assets/poi_location_subscription.png)

1. 「**[!UICONTROL Filter type]**」フィールドで「**[!UICONTROL Relative]**」を選択します。
1. **[!UICONTROL Preceding days]**&#x200B;オプションをチェックし、対応するフィールドに&#x200B;**[!UICONTROL 15]**&#x200B;と入力します。
1. ユーザーが目標地点を訪問した回数を定義します。
1. **[!UICONTROL Confirm]**&#x200B;をクリックしてオーディエンスを保存します。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 電子メールの追加内容。

   ![](assets/poi_email_content.png)

1. 電子メールのダッシュボードを表示するアクティビティの作成を確認します。
1. メッセージを送信します。

10%割引オファーの電子メールは、次の条件を満たすサブスクライバーに送信されます。

* 過去2週間以内に少なくとも1回はボストンの店を訪問した。
* 訪問中、モバイルアプリがフォアグラウンドになっていた。

**関連トピック：**

* [E メールの作成](../../channels/using/creating-an-email.md)
* [コンテンツの定義](../../designing/using/personalization.md#example-email-personalization)
* [メッセージの送信](../../sending/using/confirming-the-send.md)

