---
title: Point of Interestデータを使用したキャンペーンメッセージのパーソナライズ
seo-title: Point of Interestデータを使用したキャンペーンメッセージのパーソナライズ
description: Point of Interestデータを使用したキャンペーンメッセージのパーソナライズ
seo-description: POI(Point of Interest)データ統合を使用して、購読者の場所に基づいて個人用メッセージを作成する方法を説明します。
page-status-flag: 未活性化の
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 積分
content-type: 参照
topic-tags: モバイル向けのキャンペーンと分析の協力
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 781904d58f520987e978ad5d1cdc9e34871ca876

---


# Point of Interestデータを使用したキャンペーンメッセージのパーソナライズ{#personalizing-campaign-messages-with-point-of-interest-data}

Adobe Campaignでは、モバイルアプリケーションの購読者から収集したPoints of Interestデータを使用して、電子メールなどの個別のマーケティングメッセージを送信できます。

「関心事項」データに対してのみ、標準搬送と反応できます。 [トランザクションメッセージは](../../channels/using/about-transactional-messaging.md) 、場所のデータを使用できません。

最も早い反応は約10分です。

この場合、過去2週間以内にボストンストアを訪れたすべての購読者に電子メールを送信することにします。

1. 電子メールマーケティング活動を作成します。
1. 配信先を定義する場合は、要素をワークスペースにドラッ **[!UICONTROL Subscriptions to an application]** グ·アンド·ドロップします。

   ![](assets/poi_subscriptions_app.png)

   対象ユーザーの管理の詳細については、「対象ユーザー [の定義](../../audiences/using/creating-audiences.md) 」セクションを参照してください。

1. ウィンドウ **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** で、要素をワークスペースにド **[!UICONTROL POI Location Subscription]** ラッグ&amp;ドロップします。

   ![](assets/poi_add_rule_profile_subscription.png)

1. ウィンドウ **[!UICONTROL Add a rule - POI Location Subscription]** で、使用する注視点(POI)のラベルを入力します。

   ![](assets/poi_location_subscription.png)

1. フィールド **[!UICONTROL Filter type]** で、を選択しま **[!UICONTROL Relative]**&#x200B;す。
1. オプションをチェ **[!UICONTROL Preceding days]** ックし、対応するフ **[!UICONTROL 15]** ィールドにを入力します。
1. ユーザーが対象地点にアクセスした回数を定義します。
1. クリックし **[!UICONTROL Confirm]** て、対象ユーザーを保存します。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. メールにコンテンツを追加します。

   ![](assets/poi_email_content.png)

1. 電子メールのダッシュボードを表示するアクティビティの作成を確認します。
1. メッセージを送信します。

10%割引の提供を受け取った電子メールは、次の登録者に送信されます。

* 過去2週間に少なくとも1回はボストンの店を訪れた。
* 訪問中に少なくとも1回は、モバイルアプリケーションをフォアグラウンドに置いておいた。

**関連トピック：**

* [電子メールの作成](../../channels/using/creating-an-email.md)
* [コンテンツの定義](../../designing/using/personalization.md#example-email-personalization)
* [メッセージの送信](../../sending/using/confirming-the-send.md)

