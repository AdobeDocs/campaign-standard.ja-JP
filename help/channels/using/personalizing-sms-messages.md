---
title: SMSメッセージの個人用設定
seo-title: SMSメッセージの個人用設定
description: SMSメッセージの個人用設定
seo-description: SMSメッセージをパーソナライズする際の翻訳オプションの特定性を確認します。
page-status-flag: 未活性化の
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: SMSメッセージ
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,wizard；配信，smsContent,back；配信，smsContent,back
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# SMSメッセージの個人用設定{#personalizing-sms-messages}

SMSメッセージのパーソナライズの原則は、電子メールの原則と同じ [です](../../designing/using/personalization.md#inserting-a-personalization-field)。 これらのオプションは、エンコードに影響を与え、したがって送信するSMSメッセージの数に影響を与える可能性があるので、翻訳オプションに注意する必要があります。 詳細は、「翻訳とSMSの長さ」の項 [を参照してください](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) 。

ここでは、翻訳が選択されているかどうかに応じて、同じ送信数が生成されない個人用設定フィールドを含むSMSメッセージの例を示します。

**おい&lt;名&gt; &lt;姓&gt;、新製品が発売されました。 店に来て見て来い！**

* 「John Smith」という名前の受信者の場合、特殊文字が含まれていないため、Adobe CampaignはSMSメッセージごとに最大160文字のGSMエンコードを選択します。 そのため、メッセージは1つの部分で送信されます。
* Raphael Foretという名前の受信者の場合、GSMでは'rek'と'ee'の文字をエンコードできません。 翻訳が有効になっているかどうかに応じて、Adobe Campaignでは次の2つの動作を選択できます。

   * 翻訳が許可されている場合、'e'は'e'に置き換えられ、GSMエンコードが使用でき、SMSでは最大160文字まで使用できます。 このメッセージは1つのSMSメッセージとして送信されますが、若干変更されます。
   * 翻訳が許可されていない場合、Adobe Campaignは、バイナリ形式(Unicode)でメッセージを送信するよう選択します。そのため、すべての文字がそのように送られます。 UnicodeのSMSメッセージは70文字に制限されているため、Adobe Campaignはメッセージを2つの部分で送信する必要があります。

>[!NOTE]
>
>最適な符号化を自動的に選択するアルゴリズムは、メッセージ毎に、ケースバイケースに独立に実行される。 この方法では、Unicodeエンコードを必要とするパーソナライズされたメッセージのみがUnicodeで送信されます。その他のすべてはGSMエンコードを使用します。

## SMS送信者 {#sms-sender}

SMS送信者の名前をカスタマイズできます。 詳細については、「 [SMS設定」の項を参照してください](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) 。
