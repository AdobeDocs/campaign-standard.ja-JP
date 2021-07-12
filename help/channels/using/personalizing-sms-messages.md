---
solution: Campaign Standard
product: campaign
title: SMS メッセージのパーソナライズ
description: SMSメッセージをパーソナライズする際の表記変換オプションの特異性を確認します。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 6c01662e-1e19-4cec-aa21-6e84b9b7a677
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 100%

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

>[!IMPORTANT]
>
>送信者アドレスの変更について、お住まいの国の法律を確認してください。また、SMS サービスプロバイダーに問い合わせて、この機能を提供しているかどうかを確認する必要があります。

「**[!UICONTROL From]**」オプションを使用すると、文字列を使用して SMS メッセージの送信者名をパーソナライズできます。これは、受信者の携帯電話で SMS メッセージの送信者名として表示される名前です。

このフィールドが空の場合は、外部アカウントで指定されたソース番号が使用されます。ソース番号が指定されていない場合は、ショートコードが使用されます。SMS 配信に固有の外部アカウントは、[SMS ルーティングの定義](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)の節に記載されています。

![](assets/sms_creation_8.png)



