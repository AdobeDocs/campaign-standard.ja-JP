---
title: SMS チャネルの設定
description: 「SMSの構成手順を確認します。 ルーティング、エンコーディング、形式および詳細なプロパティ。 "
page-status-flag: never-activated
uuid: 5f13dbd5-9522-4199-8d9a-44c397cb2458
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 356d4d4f-3d5a-468c-bff8-96767cd8fff6
context-tags: extAccountMobile,overview;extAccount,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 10339aa3a5d16bb995a763b6d846e234c5f1325a
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 42%

---


# SMS チャネルの設定{#configuring-sms-channel}

SMSメッセージを送信するには、管理者が[ > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > ] **[!UICONTROL SMS]****[!UICONTROL SMS accounts]** メニューの下で1つまたは複数の外部アカウントを構成する必要があります。

外部アカウントの作成と変更の手順については、「 [外部アカウント](../../administration/using/external-accounts.md) 」の節を参照してください。 SMSメッセージを送信する外部アカウントに固有のパラメータは、次のとおりです。

## SMSルーティングの定義 {#defining-an-sms-routing}

この外部アカウント **[!UICONTROL SMS routing via SMPP]** はデフォルトで提供されていますが、他のアカウントを追加すると便利です。

SMPP プロトコルを使用する場合、新しい外部アカウントを作成することもできます。SMS のプロトコルと設定について詳しくは、この[技術メモ](https://helpx.adobe.com/jp/campaign/kb/sms-connector-protocol-and-settings.html)を参照してください。

1. から新しい外部アカウントを作成し **[!UICONTROL Administration > Application settings > External accounts]**&#x200B;ます。
1. アカウントタイプを、 **[!UICONTROL Routing]**&#x200B;チャネルを、配信を、と **[!UICONTROL Mobile (SMS)]** を定義し、モードをと定義 **[!UICONTROL Bulk delivery]**&#x200B;します。

   ![](assets/sms_routing.png)

1. 接続設定を定義します。

   SMSメッセージの送信に固有の接続設定を入力するには、SMSサービスプロバイダーに問い合わせて、各外部アカウントフィールドの入力方法を伝えてください。

   ![](assets/sms_connection.png)

   この **[!UICONTROL Enable TLS over SMPP]** オプションを使用すると、SMPPトラフィックを暗号化できます。

   **[!UICONTROL Enable verbose SMPP traces in the log file]** すべてのSMPPトラフィックをログファイルにダンプできます。 コネクタのトラブルシューティングやプロバイダー側が確認できるトラフィックとの比較をおこなうには、このオプションを有効にする必要があります。

1. Contact Adobe who will give you the value to enter into the **[!UICONTROL SMS-C implementation name]** field, depending on the provider chosen.
1. SMPPチャネル設定を定義します。 詳しくは、「 [SMSのエンコードと形式](#sms-encoding-and-formats) 」の項を参照してください。

   すべての受信SMSをinSMSテーブルに格納する **[!UICONTROL Store incoming MO in the database]** 場合は、を有効にします。 受信SMSの取得方法の詳細については、この [セクションを参照してください](../../channels/using/managing-incoming-sms.md#storing-incoming-sms)。

   この **[!UICONTROL Enable Real-time KPI updates during SR processing]** オプションを使用すると、配信を送信した後に、リアルタイムでKPI **[!UICONTROL Delivered]** または **[!UICONTROL Bounces + Errors]** KPIを更新できます。 これらのKPIは、 **[!UICONTROL Deployment]** ウィンドウに表示され、プロバイダから受け取ったSR（ステータスレポート）から直接再計算されます。

   ![](assets/sms_connection_1.png)

1. パラメーターを定義し **[!UICONTROL Throughput and timeouts]** ます。

   送信メッセージ(「MT」、「Mobile Terminated」)の最大スループットを1秒あたりのMTで指定できます。 該当するフィールドに「0」と入力した場合、スループットは無制限となります。

   期間を示すどのフィールドでも、値は秒単位で入力する必要があります。

1. 特定のエンコーディングマッピングを定義する必要がある場合に備えて、SMS-C固有のパラメータを定義します。 For more information, refer to the [SMSC specifics](#smsc-specifics) section.

   SMPPプロトコルを適用せずに、SMSプロバイダ(SMS-C)のサーバーに **[!UICONTROL Send full phone number (send characters other than digits)]****[!UICONTROL +]** プレフィックスを転送する場合は、このオプションを有効にします。

   However, given that certain providers require the use of the **[!UICONTROL +]** prefix, it is advised that you check with your provider and they will suggest that you enable this option if necessary.

1. 必要に応じて、返信の内容に基づいてアクションをトリガする自動返信を定義します。 詳しくは、[この節](../../channels/using/managing-incoming-sms.md#managing-stop-sms)を参照してください。
1. SMSルーティング外部アカウントの構成を保存します。

新しいルーティングを使用して、SMSメッセージをAdobe Campaignと共に送信できるようになりました。

## SMSのエンコードと形式 {#sms-encoding-and-formats}

### SMSエンコード、長さ、および変換 {#sms-encoding--length-and-transliteration}

デフォルトでは、SMS の文字数は GSM（Global System for Mobile Communications）標準に準じています。

GSM エンコードを使用する SMS メッセージは 160 文字以内に制限されています。複数の部分に分けて送信されるメッセージの場合は、SMS 1 件につき 153 文字以内です。

>[!NOTE]
>
>2 文字としてカウントされる文字もあります（中括弧、角括弧、ユーロ記号など）。使用可能なGSM文字のリストは、「文字 [表 — GSM標準](#table-of-characters---gsm-standard) 」セクションに表示されます。

必要に応じて、文字の表記変換をチェックボックスで指定できます。

![](assets/sms_transliteration.png)

表記変換では、SMS の特定の文字が GSM 標準に準じていない場合に、別の文字に置き換えられます。

* 表記変換が&#x200B;**許可されている**&#x200B;場合、標準に準じていない文字はメッセージの送信時に GSM 文字に置き換えられます。例えば、「ë」は「e」に置き換えられます。そのため、メッセージは若干改変されますが、文字制限は同じです。
* 表記変換が&#x200B;**許可されていない**&#x200B;場合、標準に準じていない文字があるメッセージはバイナリフォーマット（Unicode）で送信されます。そのため、すべての文字がそのまま送信されます。ただし、Unicode を使用する SMS メッセージは 70 文字以内に制限されています。複数の部分に分けて送信されるメッセージの場合は、SMS 1 件につき 67 文字以内です。文字数が上限を超えると、メッセージは複数に分かれて送信されますが、追加料金が発生する場合があります。

>[!IMPORTANT]
>
>パーソナライゼーションフィールドを SMS メッセージのコンテンツに入れると、GSM エンコードに対応していない文字が含まれる場合があります。コンテンツの例は、「SMSメッセージの [個人化](../../channels/using/personalizing-sms-messages.md) 」セクションにあります。

デフォルトでは、文字の表記変換は無効です。SMS メッセージのすべての文字をそのまま送信する場合（例えば、固有名詞が改変されないようにする場合）、このオプションは無効にしておくことをお勧めします。

ただし、SMS メッセージに Unicode メッセージ用の文字が多数含まれる場合、このオプションを有効にしてメッセージ送信のコストを抑えることもできます。

### Table of characters - GSM Standard {#table-of-characters---gsm-standard}

この節では、GSM 標準に準じている文字を紹介します。メッセージ本文に、ここで紹介されていない文字が含まれている場合、メッセージ全体がバイナリフォーマット（Unicode）に変換され、文字数が 70 文字以内に制限されます。詳しくは、「 [SMS encoding, length, and transiteration](#sms-encoding--length-and-transliteration) 」の項を参照してください。

**基本的な文字**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> P<br /> </td> 
   <td> ¿<br /> </td> 
   <td> P<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> A<br /> </td> 
   <td> Q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> B<br /> </td> 
   <td> R<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> C<br /> </td> 
   <td> S<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> F<br /> </td> 
   <td> V<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> G<br /> </td> 
   <td> W<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> H<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> Ç<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> I<br /> </td> 
   <td> Y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> J<br /> </td> 
   <td> Z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> K<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> Æ<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> Ñ<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP：スペース

ESC：エスケープ

LF：ラインフィード

CR：キャリッジリターン

**高度な文字（2 回カウント）**

^ { } [ ~ ] | €

### SMSCの詳細 {#smsc-specifics}

>[!NOTE]
>
>これらのオプションを使用すると、コネクタが非標準のSMSC（つまり、SMPP 3.4仕様に厳密に従っていない）または特定のエンコーディング要件に対応でき、上級ユーザーのみが設定する必要があります。

Adobe Campaign では、SMS メッセージの送信時に 1 つまたは複数のテキストエンコードを使用できます。エンコードごとに独自の文字セットがあり、SMS メッセージに入力できる文字数もそれぞれ異なります。

この **[!UICONTROL DATA_CODING]** フィールドは、Adobe Campaignがエンコーディングが使用されているSMS-Cと通信できるようにします。

>[!NOTE]
>
>**data_coding** の値と実際に使用されているエンコードの間のマッピングは標準化されています。Nevertheless, certain SMS-C have their own specific mapping: in this case, your **Adobe Campaign** administrator needs to declare this mapping. 詳しくは、プロバイダーにお問い合わせください。

The **[!UICONTROL Define a specific mapping of encodings]** functionality allows you to declare **data_codings** and to force the encoding if necessary: to do this, specify a single encoding in the table.

**設定**

* この機能がチェックされていない場合、コネクタは次の汎用的な動作を行います。 **[!UICONTROL Define a specific mapping of encodings]**

   * **data_coding = 0** を設定して、GSM エンコードの使用を試行します。
   * GSM エンコードが失敗した場合は、**data_coding = 8** を設定して、**UCS2** エンコードの使用を試行します。

   ![](assets/sms_data_coding.png)

* この機能をチェックすると、使用するエンコーディングとリンクされた **[!UICONTROL Define a specific mapping of encodings]****[!UICONTROL data_coding]** フィールドの値を定義できます。 Adobe Campaignは、リスト内の最初のエンコーディングを使用しようとしますが、次の場合は、最初のエンコーディングが不可能であると判断されます。

   宣言の順序は重要です。**コスト**&#x200B;が少ない順にリストを設定し、SMS メッセージになるべく多くの文字を使用できるようにすることをお勧めします。

   使用するエンコードのみを宣言してください。SMS-Cが提供するエンコーディングの一部が使用目的に合わない場合は、リストで宣言しないでください。

   ![](assets/sms_data_coding1.png)

### MO に送信された自動返信 {#automatic-reply-sent-to-the-mo}

プロファイルがキャンペーン経由で送信されたSMSメッセージに返信する場合、自動的に返信されるメッセージや、実行するアクションを設定できます。

詳しくは、[この節](../../channels/using/managing-incoming-sms.md)を参照してください。

## SMSプロパティを構成する {#configuring-sms-properties}

このセクションでは、SMS配信またはSMSテンプレートのプロパティ画面でSMSに固有のパラメータのリストについて説明します。

SMSメッセージを送信するための特定のパラメータは、およびのセク **[!UICONTROL Send]****[!UICONTROL Advanced parameters]** ションで再グループ化されます。

![](assets/sms_options.png)

次の節を **[!UICONTROL Advanced parameters]** 参照してください。

* この **[!UICONTROL From]** オプションを使用すると、SMSメッセージの送信者の名前を文字列を使用して個人設定できます。 これは、受信者の携帯電話でSMSメッセージの送信者名として表示される名前です。

   このフィールドが空の場合は、外部アカウントで指定されたソース番号が使用されます。 ソース番号が指定されない場合は、使用される短いコードになります。 SMS配信に固有の外部アカウントは、「SMSルーティングの [定義](#defining-an-sms-routing) 」セクションに表示されます。

   ![](assets/sms_smpp_2.png)

   >[!IMPORTANT]
   >
   >送信者の住所の変更に関して、お住まいの国の法律を確認してください。 また、SMSサービスプロバイダーに、この機能にオファーしているかどうかを確認する必要もあります。

SMSテンプレートの **[!UICONTROL Send]** セクションで、次の操作を行います。

* この **[!UICONTROL Maximum number of SMS per message]** オプションを使用すると、メッセージの送信に使用するSMSメッセージの数を定義できます。 この数を超えると、メッセージは送信されません。

   >[!IMPORTANT]
   >
   >SMSメッセージの内容にパーソナライゼーションフィールドや条件付きテキストを挿入した場合は、メッセージの長さと、送信するSMSメッセージの数が受信者によって異なる場合があります。 For more on this, refer to the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

   ![](assets/sms_smpp_3.png)

* この **[!UICONTROL Transmission mode]** フィールドでは、SMSメッセージの配信方法を指定できます。

   * **[!UICONTROL Saved on SIM card]**: メッセージは受信者の電話SIMカードに保存されます。
   * **[!UICONTROL Saved on mobile]**: そのメッセージは電話の内部メモリに保存される。
   * **[!UICONTROL Flash]**: このメッセージは、受信者の携帯電話に通知として表示され、保存されずに表示されなくなります。
