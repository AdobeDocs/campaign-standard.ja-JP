---
title: ダイナミックテキストの定義
description: Adobe Campaignで定義された条件に従って、異なるテキストをユーザーに動的に表示する方法を説明します。
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
TQID: https://experienceleague.adobe.com/fgQySs0BUlvKT3CKMSaW-0fVe3W65qV1fDEZb1kDZ3w
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 3%

---

# ダイナミックテキストの定義{#defining-dynamic-text}

動的テキストは、動的コンテンツと同じように定義されます。 「[動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)」セクションを参照してください。

>[!NOTE]
>
>SMSとプッシュ通知の場合は、動的テキストのみを定義できます。 ランディングページでは、動的コンテンツとテキストの両方を定義できます。 [電子メール Designer](../../designing/using/designing-content-in-adobe-campaign.md)で動的テキストを定義する場合は、[電子メールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)を参照してください。

サロゲートペアは、Unicode文字セットの基本多言語面に含まれていない文字であり、2 バイト（16 ビット）で保存することはできず、2 UTF-16文字にエンコードする必要があります。 これらのキャラクターには、いくつかのCJKのイデオグラフィック、ほとんどの絵文字、いくつかの言語が含まれています。
<br>これらの文字は、動的テキストの互換性に関する問題を引き起こす可能性があります。 メッセージを送信する前に、強力なテストを実行する必要があります。


次の例は、SMS メッセージで動的テキストを定義する方法を示しています。

1. メッセージまたはランディングページの本文のテキストを選択します。
1. 「**[!UICONTROL Enable dynamic text]**」をクリックします。

   ![](assets/dynamic_text_sms_1.png)

   **[!UICONTROL Dynamic text]** オプションがパレットに表示されます。 動的コンテンツと同じように設定されます。

1. バリエーションを選択。

   ![](assets/dynamic_text_sms_2.png)

1. このバリエーションの条件を定義します。

   ![](assets/dynamic_text_sms_4.png)

少なくとも1つのバリアントに対して条件を定義すると、ダイナミックテキストの周囲に紫色のフレームが表示されます。

![](assets/dynamic_text_sms_3.png)
