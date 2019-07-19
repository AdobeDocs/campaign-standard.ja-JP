---
title: 目標地点データのあるキャンペーンメッセージのパーソナライズ
seo-title: 目標地点データのあるキャンペーンメッセージのパーソナライズ
description: 目標地点データのあるキャンペーンメッセージのパーソナライズ
seo-description: 目標地点データ統合を使用して、購読者の場所に基づいてパーソナライズされたメッセージを作成する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: d74c3e55- f130-441b- bc2a-06ddcd5d9784
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- analytics- for- mobile
discoiquuid: a1736ba3-5121-4d01- bf04- ebb7e701e2e0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Personalizing Campaign messages with Point of Interest data{#personalizing-campaign-messages-with-point-of-interest-data}

Adobe Campaignでは、モバイルアプリの購読者から収集された目標地点データを使用して、電子メールなどのパーソナライズされたマーケティングメッセージを送信できます。

標準配信では目標地点データのみに反応できます。[トランザクションメッセージ](../../channels/using/about-transactional-messaging.md) では場所データを使用できません。

反応できる最も早い時間は10分です。

この場合、過去2週間以内にボストンストアを訪問したすべての購読者に電子メールを送信します。

1. 電子メールマーケティングアクティビティを作成します。
1. When defining the delivery's audience, drag and drop the **[!UICONTROL Subscriptions to an application]** element into the workspace.

   ![](assets/poi_subscriptions_app.png)

   Managing audiences is detailed in the [Defining audiences](../../audiences/using/creating-audiences.md) section.

1. **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** ウィンドウで、要素を **[!UICONTROL POI Location Subscription]** ワークスペースにドラッグ&amp;ドロップします。

   ![](assets/poi_add_rule_profile_subscription.png)

1. **[!UICONTROL Add a rule - POI Location Subscription]** ウィンドウで、使用する目標地点のラベルを入力します。

   ![](assets/poi_location_subscription.png)

1. **[!UICONTROL Filter type]** フィールドで、を選択 **[!UICONTROL Relative]**&#x200B;します。
1. **[!UICONTROL Preceding days]** オプションをチェックして、対応するフィールド **[!UICONTROL 15]** に入力します。
1. ユーザーが目標地点を訪問した回数を定義します。
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 電子メールにコンテンツを追加します。

   ![](assets/poi_email_content.png)

1. アクティビティの作成を確認して、電子メールのダッシュボードを表示します。
1. メッセージを送信します。

10%割引オファーを含む電子メールは、購読者に送信されます。

* 過去2週間以内に、ボストンストアに少なくとも1回訪問してください。
* 訪問中に少なくとも1回はモバイルアプリケーションをフォアグラウンドで使用していました。

**関連トピック:**

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [コンテンツの定義](../../designing/using/example--email-personalization.md)
* [メッセージの送信](../../sending/using/confirming-the-send.md)

