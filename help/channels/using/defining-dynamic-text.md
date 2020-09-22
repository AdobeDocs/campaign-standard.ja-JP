---
title: ダイナミックテキストの定義
description: Adobe Campaignで定義された条件に従って、様々なテキストを動的にユーザーに表示する方法を説明します。
page-status-flag: never-activated
uuid: bbcd200c-4fb4-467b-ba39-09b8bee9bcaa
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: 6bb6cee3-5674-4113-8073-5a9572b3e830
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 564613ecc2879be87d1f85f9f15e675697690139
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---


# ダイナミックテキストの定義{#defining-dynamic-text}

動的テキストは、動的コンテンツと同じ方法で定義されます。 「動的コンテンツの [定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) 」の節を参照してください。

>[!NOTE]
>
>SMSおよびプッシュの場合は、ダイナミックテキストのみを定義できます。 動的なコンテンツとテキストの両方をランディングページに定義できます。 電子メールデザイナで動的テキストを定義する場合は、 [電子メール内の動的コンテンツの](../../designing/using/designing-content-in-adobe-campaign.md)定義を参照してください [](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)。

サロゲートペア（Unicode文字セットの基本多言語面に含まれない文字）は、2バイト（16ビット）で格納できず、2つのUTF-16文字にエンコードする必要があることに注意してください。 これらの文字には、CJKイデオグラフ、ほとんどの絵文字、一部の言語が含まれます。
<br>これらの文字は、動的テキストで非互換性の問題の原因となる場合があります。 メッセージを送信する前に、強力なテストを実行する必要があります。


次の例は、SMSメッセージで動的テキストを定義する方法を示しています。

1. メッセージまたはランディングページの本文のテキストを選択します。
1. 「**[!UICONTROL Enable dynamic text]**」をクリックします。

   ![](assets/dynamic_text_sms_1.png)

   この **[!UICONTROL Dynamic text]** オプションはパレットに表示されます。 動的コンテンツと同じ方法で設定します。

1. バリアントを選択します。

   ![](assets/dynamic_text_sms_2.png)

1. このバリアントの条件を定義します。

   ![](assets/dynamic_text_sms_4.png)

1つ以上のバリアントに対して条件を定義すると、ダイナミックテキストの周囲に紫の枠が表示されます。

![](assets/dynamic_text_sms_3.png)

