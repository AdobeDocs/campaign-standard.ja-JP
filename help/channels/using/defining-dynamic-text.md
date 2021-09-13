---
title: ダイナミックテキストの定義
description: Adobe Campaignで定義された条件に従って、様々なテキストをユーザーに動的に表示する方法を説明します。
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# ダイナミックテキストの定義{#defining-dynamic-text}

動的テキストは、動的コンテンツと同じ方法で定義します。 [動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)の節を参照してください。

>[!NOTE]
>
>SMSおよびプッシュの場合、ダイナミックテキストのみ定義できます。 ランディングページに動的コンテンツとテキストの両方を定義できます。 [Eメールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)で動的テキストを定義する場合は、[Eメールでの動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)を参照してください。

サロゲートペア（Unicode文字セットの基本多言語プレーンに含まれない文字）は、2バイト（16ビット）で格納できず、2つのUTF-16文字にエンコードする必要があります。 これらの文字には、CJKの表意文字、ほとんどの絵文字、一部の言語が含まれます。
<br>これらの文字は、ダイナミックテキストで非互換性の問題を引き起こす可能性があります。メッセージを送信する前に、強力なテストを実行する必要があります。


次の例は、SMSメッセージに動的テキストを定義する方法を示しています。

1. メッセージまたはランディングページの本文のテキストを選択します。
1. 「**[!UICONTROL Enable dynamic text]**」をクリックします。

   ![](assets/dynamic_text_sms_1.png)

   パレットに&#x200B;**[!UICONTROL Dynamic text]**&#x200B;オプションが表示されます。 動的コンテンツと同じ方法で設定します。

1. バリアントを選択します。

   ![](assets/dynamic_text_sms_2.png)

1. このバリアントの条件を定義します。

   ![](assets/dynamic_text_sms_4.png)

少なくとも1つのバリアントに対して条件を定義すると、ダイナミックテキストの周囲に紫色の枠が表示されます。

![](assets/dynamic_text_sms_3.png)
