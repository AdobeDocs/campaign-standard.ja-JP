---
title: SMS メッセージのパーソナライズ
description: SMSメッセージをパーソナライズする際の翻訳オプションの詳細を確認します。
page-status-flag: 非活性化の
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# SMS メッセージのパーソナライズ{#personalizing-sms-messages}

SMSメッセージの個人設定の原則は、電子メールの原則と同じ [です](../../designing/using/personalization.md#inserting-a-personalization-field)。 ただし、変換オプションはエンコーディングに影響を与え、送信するSMSメッセージの数に影響を与える可能性があるので、注意が必要です。 詳細については、「 [Transliteration and SMS length](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 」を参照してください。

ここでは、パーソナライゼーションフィールドを含むサンプルSMSメッセージを示します。このフィールドは、翻訳が選択されているかどうかに応じて、同じ数の送信を生成しません。

**&lt; FirstName &gt; &lt; lastName &gt;様、新製品をご利用いただけます。 店に来て見ろ！**

* 「John Smith」という名前の受信者の場合、特殊文字が含まれていないので、Adobe CampaignはSMSメッセージごとに最大160文字のGSMエンコードを選択します。 そのため、メッセージは単一の部分で送信されます。
* 「Raphaél Foret」という名前の受信者の場合、「」と「!」の文字はGSMでエンコードできません。 翻訳が有効になっているかどうかに応じて、Adobe Campaignでは次の2つの動作から選択できます。

   * 翻訳が許可された「レク」で、「e」が「e」に置き換えられる場合は、GSMエンコーディングを使用でき、SMSでは最大160文字を使用できます。 このメッセージは1つのSMSメッセージとして送信されますが、若干変更されます。
   * 翻訳が許可されていない場合、Adobe Campaignはメッセージをバイナリ形式(Unicode)で送信するよう選択します。したがって、すべての文字がそのように送信されます。 UnicodeのSMSメッセージは70文字に制限されているので、Adobe Campaignはメッセージを2つの部分で送信する必要があります。

>[!NOTE]
>
>最適なエンコーディングを自動的に選択するアルゴリズムは、メッセージごとに、ケースバイケースで独立して実行される。 この方法では、Unicodeエンコーディングを必要とするパーソナライズされたメッセージのみがUnicodeで送信されます。その他のすべてはGSMエンコーディングを使用します。

## SMS送信者 {#sms-sender}

SMS送信者の名前は個人用に設定できます。 For more on this, refer to the [SMS configuration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) section.
