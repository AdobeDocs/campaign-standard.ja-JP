---
title: POI データを使用した Campaign メッセージのパーソナライズ
description: Point of Interest データの統合により、購読者の場所にもとづいてパーソナライズされたメッセージを作成する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
TQID: https://experienceleague.adobe.com/IaSdwDcX-TJSOGn9-9vbRi9zQmRkmyCXXlanq-FvGnQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 262
ht-degree: 10%

---

# POI データを使用した Campaign メッセージのパーソナライズ{#personalizing-campaign-messages-with-point-of-interest-data}

Adobe Campaignでは、モバイルアプリケーションの購読者から収集したPoints of Interest データを使用して、電子メールなどのパーソナライズされたマーケティングメッセージを送信できます。

標準的な配信では、Point of Interest データでのみ対応できます。 [&#x200B; トランザクションメッセージ &#x200B;](../../channels/using/getting-started-with-transactional-msg.md)は場所データを使用できません。

最も早く反応できるのは約10分です。

この場合、過去2週間以内にボストンの店舗を訪問したすべての購読者にメールを送信することにします。

1. メールマーケティングアクティビティの作成。
1. 配信のオーディエンスを定義する際に、**[!UICONTROL Subscriptions to an application]**&#x200B;要素をワークスペースにドラッグ&amp;ドロップします。

   ![](assets/poi_subscriptions_app.png)

   オーディエンスの管理について詳しくは、[&#x200B; オーディエンスの定義](../../audiences/using/creating-audiences.md) セクションを参照してください。

1. **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** ウィンドウで、**[!UICONTROL POI Location Subscription]**&#x200B;要素をワークスペースにドラッグ&amp;ドロップします。

   ![](assets/poi_add_rule_profile_subscription.png)

1. **[!UICONTROL Add a rule - POI Location Subscription]** ウィンドウで、使用するPoint of Interestのラベルを入力します。

   ![](assets/poi_location_subscription.png)

1. 「**[!UICONTROL Filter type]**」フィールドで「**[!UICONTROL Relative]**」を選択します。
1. 「**[!UICONTROL Preceding days]**」オプションをオンにし、対応するフィールドに「**[!UICONTROL 15]**」と入力します。
1. ユーザーがPoint of Interestにアクセスした回数を定義します。
1. 「**[!UICONTROL Confirm]**」をクリックして、オーディエンスを保存します。

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. メールにコンテンツを追加する：

   ![](assets/poi_email_content.png)

1. メールのダッシュボードを表示するアクティビティの作成を確認します。
1. メッセージを送信。

10%割引オファーの電子メールは、次のような顧客に送信されます。

* 過去2週間に少なくとも1回はボストンの店舗を訪れた。
* 訪問中に少なくとも1回はモバイルアプリケーションを前面に配置していました。

**関連トピック：**

* [メールの作成](../../channels/using/creating-an-email.md)
* [コンテンツの定義](../../designing/using/personalization.md#example-email-personalization)
* [メッセージの送信](../../sending/using/confirming-the-send.md)
