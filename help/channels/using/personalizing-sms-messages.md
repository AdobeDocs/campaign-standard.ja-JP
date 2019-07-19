---
title: SMSメッセージのパーソナライズ
seo-title: SMSメッセージのパーソナライズ
description: SMSメッセージのパーソナライズ
seo-description: SMSメッセージをパーソナライズする際のトランスレートオプションの特異性を検出します。
page-status-flag: 常にアクティブ化されていない
uuid: 123fe70c- c279-40a3-88b6-6bfb2453ec83
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: sms- messages
discoiquuid: 7c64785c- e3c2-4ca- a547-002990aae3f9
delivercontext-tags: DeliveryCreation，ウィザード;delivery， ssContent， back;delivery， ssContent， back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Personalizing SMS messages{#personalizing-sms-messages}

The principles for personalizing SMS messages are the same as those for [emails](../../designing/using/inserting-a-personalization-field.md). これらのオプションは、エンコードに影響を与える可能性があるため、送信するSMSメッセージの数に応じて、トランスレートオプションを認識する必要があります。For more on this, refer to the [Transliteration and SMS length](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

ここでは、パーソナライゼーションフィールドを含むサンプルSMSメッセージを使用して、変換が選択されているかどうかに応じて、同じ数の送信を生成しません。

**&lt; firstName&gt;&lt; LastName&gt;の新製品をご利用いただけるようになりました。Come and check them out in store!**

* "John Smith"という名前の受信者に対して特殊文字が含まれていない場合、Adobe CampaignはGSMエンコーディングを選択します。これは、SMSメッセージあたり最大160文字を承認するGSMエンコーディングを選択します。したがって、メッセージは単一の部分で送信されます。
* "Raphavel Forent"という名前の受信者の場合、GSMでは"a"と"e"はエンコードできません。トランスレートが有効かどうかによって、Adobe Campaignでは次の2つの動作を選択できます。

   * 変換された"a"と"o"が"e"である場合、GSMエンコーディングを使用できるので、SMSでは最大160文字まで使用できます。このメッセージは単一のSMSメッセージとして送信されますが、わずかに変更されます。
   * 変換が許可されていない場合、Adobe Campaignはメッセージをバイナリ形式（Unicode）で送信するように選択します。そのため、すべての文字が送信されます。UnicodeのSMSメッセージは70文字に制限されているので、Adobe Campaignではメッセージを2つの部分に送信する必要があります。

>[!NOTE]
>
>最適なエンコーディングを自動的に選択するアルゴリズムは、メッセージごとに個別に実行され、大文字と小文字が区別されます。これにより、Unicodeエンコードを必要とするパーソナライズされたメッセージのみがUnicodeで送信されます。他のすべてのユーザーはGSMエンコーディングを使用します。

