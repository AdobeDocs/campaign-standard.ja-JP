---
solution: Campaign Standard
product: campaign
title: SMS メッセージのパーソナライズ
description: SMSメッセージをパーソナライズする際の表記変換オプションの特異性を確認します。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# SMS メッセージのパーソナライズ{#personalizing-sms-messages}

SMSメッセージのパーソナライゼーションの原則は、[電子メール](../../designing/using/personalization.md#inserting-a-personalization-field)の原則と同じです。ただし、表記変換オプションによってはエンコーディングが変わり、送信するSMSメッセージの数が増える場合があるので、注意が必要です。詳しくは、[表記変換と SMS の長さ](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)を参照してください。

ここに、パーソナライゼーションフィールドが含まれている SMS メッセージのサンプルを示します。表記変換が選択されているかどうかに応じて、生成される送信の数が変わります。

**&lt;LastName>&lt;FirstName>様、新製品が発売されました。是非ストアでご覧ください。**

* 受信者の名前が「John Smith」であれば、特殊文字が含まれていないので、Adobe Campaign は SMS メッセージごとに最大 160 文字まで可能な GSM エンコードを選択します。したがって、メッセージは単体で送信されます。
* 受信者の名前が「Raphaël Forêt」であると、GSM では「ë」と「ê」をエンコードできません。この場合、Adobe Campaign では、表記変換が有効になっているかどうかに応じて、次のいずれかの動作を選択します。

   * 表記変換が許可されている場合は、「ë」と「ê」が「e」に置き換えられます。その結果、GSM エンコーディングを使用できるので、SMS で最大 160 文字まで使用できます。メッセージは若干変更されますが、単一の SMS メッセージとして送信されます。
   * 表記変換が許可されていない場合、Adobe Campaign ではバイナリ形式（Unicode）でのメッセージ送信を選択します。したがって、すべての文字がそのまま送信されます。Unicode の SMS メッセージは 70 文字までに制限されているので、Adobe Campaign ではメッセージを 2 つに分割して送信する必要があります。

>[!NOTE]
>
>最適なエンコーディングはアルゴリズムによって自動的に選択されます。このアルゴリズムは、メッセージごとにケースバイケースで独立に実行されます。こうして、Unicode エンコーディングが必要なパーソナライズされたメッセージのみ Unicode で送信され、その他のすべてのメッセージは GSM エンコーディングを使用します。

## SMS 送信者 {#sms-sender}

SMS 送信者の名前をパーソナライズすることができます。詳しくは、[SMS プロパティの設定](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)の節を参照してください。
