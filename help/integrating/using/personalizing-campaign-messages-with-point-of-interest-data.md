---
title: 目標地点データを使用したキャンペーンメッセージのパーソナライズ
description: 目標地点データの統合により、購読者の場所に基づいてパーソナライズされたメッセージを作成する方法を説明します。
page-status-flag: 非活性化の
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンと分析をモバイル用に活用
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 目標地点データを使用したキャンペーンメッセージのパーソナライズ{#personalizing-campaign-messages-with-point-of-interest-data}

Adobe Campaignでは、モバイルアプリの購読者から収集した目標地点データを使用して、電子メールなどのパーソナライズされたマーケティングメッセージを送信できます。

目標地点データに対しては、標準的な配信に対してのみ反応できます。 [トランザクションメッセージ](../../channels/using/about-transactional-messaging.md) で場所データを使用することはできません。

反応が早いのは約10分です

この場合、過去2週間以内にボストンストアを訪問したすべての購読者に電子メールを送信することにします。

1. 電子メールマーケティングアクティビティを作成します。
1. 配信のオーディエンスを定義する場合は、要素をワークスペースにドラ **[!UICONTROL Subscriptions to an application]** ッグ&amp;ドロップします。

   ![](assets/poi_subscriptions_app.png)

   オーディエンスの管理について詳しくは、「オーディエ [ンスの定義](../../audiences/using/creating-audiences.md) 」セクションを参照してください。

1. ウィンドウで、 **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** 要素をワークスペースにドラッグ **[!UICONTROL POI Location Subscription]** &amp;ドロップします。

   ![](assets/poi_add_rule_profile_subscription.png)

1. ウィンドウ **[!UICONTROL Add a rule - POI Location Subscription]** に、使用する目標地点のラベルを入力します。

   ![](assets/poi_location_subscription.png)

1. フィールド **[!UICONTROL Filter type]** で、を選択しま **[!UICONTROL Relative]**&#x200B;す。
1. オプションを **[!UICONTROL Preceding days]** 選択し、対応する **[!UICONTROL 15]** フィールドに入力します。
1. ユーザーが目標地点を訪問した回数を定義します。
1. をクリック **[!UICONTROL Confirm]** して、オーディエンスを保存します。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. 電子メールにコンテンツを追加します。

   ![](assets/poi_email_content.png)

1. 電子メールのダッシュボードを表示するアクティビティの作成を確認します。
1. メッセージを送信します。

10%割引オファーを含む電子メールは、次の条件を満たす購読者に送信されます。

* 2週間以内に少なくとも1回はボストンの店を訪問した。
* 訪問中にモバイルアプリが最低1回フォアグラウンドになっていた。

**関連トピック：**

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [コンテンツの定義](../../designing/using/personalization.md#example-email-personalization)
* [メッセージの送信](../../sending/using/confirming-the-send.md)

