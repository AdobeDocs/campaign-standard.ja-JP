---
solution: Campaign Standard
product: campaign
title: ダイナミックテキストの定義
description: Adobe Campaignで定義された条件に従って、様々なテキストを動的にユーザーに表示する方法を説明します。
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: 開業医
level: 初心者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---


# ダイナミックテキストの定義{#defining-dynamic-text}

動的テキストは、動的コンテンツと同じ方法で定義されます。 「[動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)」の節を参照してください。

>[!NOTE]
>
>SMSおよびプッシュの場合は、ダイナミックテキストのみを定義できます。 動的なコンテンツとテキストの両方をランディングページに定義できます。 [電子メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)で動的テキストを定義する場合は、[電子メール](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)での動的コンテンツの定義を参照してください。

サロゲートペア（Unicode文字セットの基本多言語面に含まれない文字）は、2バイト（16ビット）で格納できず、2つのUTF-16文字にエンコードする必要があることに注意してください。 これらの文字には、CJKイデオグラフ、ほとんどの絵文字、一部の言語が含まれます。
<br>これらの文字は、動的テキストで非互換性の問題の原因となる場合があります。メッセージを送信する前に、強力なテストを実行する必要があります。


次の例は、SMSメッセージで動的テキストを定義する方法を示しています。

1. メッセージまたはランディングページの本文のテキストを選択します。
1. 「**[!UICONTROL Enable dynamic text]**」をクリックします。

   ![](assets/dynamic_text_sms_1.png)

   パレットに&#x200B;**[!UICONTROL Dynamic text]**&#x200B;オプションが表示されます。 動的コンテンツと同じ方法で設定します。

1. バリアントを選択します。

   ![](assets/dynamic_text_sms_2.png)

1. このバリアントの条件を定義します。

   ![](assets/dynamic_text_sms_4.png)

1つ以上のバリアントに対して条件を定義すると、ダイナミックテキストの周囲に紫の枠が表示されます。

![](assets/dynamic_text_sms_3.png)
