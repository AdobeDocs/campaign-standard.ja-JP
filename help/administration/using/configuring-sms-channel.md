---
title: SMSチャネルの設定
seo-title: SMSチャネルの設定
description: SMSチャネルの設定
seo-description: 「SMSの構成手順を確認します。ルーティング、エンコード、形式および詳細なプロパティ。 "
page-status-flag: 非活性化の
uuid: 5f13dbd5-9522-4199-8d9a-44c397cb2458
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: 設定チャネル
discoiquuid: 356d4d4f-3d5a-468c-bff8-96767cd8ff6
context-tags: extAccountMobile,overview;extAccount,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0c455e965d21996ffbadeddf336c6709ce8ee8f3

---


# SMSチャネルの設定{#configuring-sms-channel}

SMSメッセージを送信するには、管理者が[ &gt; ] &gt; [ ]メニューの下で1つまたは複数の外部アカウントを設 **[!UICONTROL Administration]** 定する **[!UICONTROL Channels]** 必要 **[!UICONTROL SMS]** があ **[!UICONTROL SMS accounts]** ります。

外部アカウントの作成および変更手順については、「外部アカウント」の節を [参照してくださ](../../administration/using/external-accounts.md) い。 以下に、SMSメッセージを送信する外部アカウントに固有のパラメータを示します。

## SMSルーティングの定義 {#defining-an-sms-routing}

外部アカウントはデ **[!UICONTROL SMS routing via SMPP]** フォルトで提供されますが、他のアカウントを追加すると便利です。

SMPP プロトコルを使用する場合、新しい外部アカウントを作成することもできます。SMS のプロトコルと設定について詳しくは、この[技術メモ](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html)を参照してください。

1. から新しい外部アカウントを作成しま **[!UICONTROL Administration > Application settings > External accounts]**&#x200B;す。
1. アカウントタイプを、チャ **[!UICONTROL Routing]**&#x200B;ネルを、配信モードを **[!UICONTROL Mobile (SMS)]** として定義しま **[!UICONTROL Bulk delivery]**&#x200B;す。

   これらのルーティングパラメータを定義すると、SMSコネクタ( **[!UICONTROL Generic SMPP]** )が自動的に選択されます。 このコネクタを使用すると、Adobe CampaignはSMPPプロトコルを介してShort Message Service Center(SMS-C)に接続し、SMSメッセージをターゲットプロファイルに直接送信できます。

   ![](assets/sms_routing.png)

1. 接続設定を定義します。

   SMSメッセージの送信に固有の接続設定を入力するには、SMSサービスプロバイダに問い合わせて、異なる外部アカウントフィールドの入力方法を伝えてください。

   ![](assets/sms_connection.png)

   このオプ **[!UICONTROL Enable TLS over SMPP]** ションを使用すると、SMPPトラフィックを暗号化できます。

   **[!UICONTROL Enable verbose SMPP traces in the log file]** すべてのSMPPトラフィックをログファイルにダンプできます。 コネクタのトラブルシューティングやプロバイダー側が確認できるトラフィックとの比較をおこなうには、このオプションを有効にする必要があります。

1. Contact Adobe who will give you the value to enter into the **[!UICONTROL SMS-C implementation name]** field, depending on the provider chosen.
1. SMPPチャネル設定を定義します。 詳しくは、「 [SMSエンコーディングと形式」の節を参照してください](#sms-encoding-and-formats) 。

   受信したす **[!UICONTROL Store incoming MO in the database]** べてのSMSをinSMSテーブルに保存する場合は、を有効にします。 受信SMSの取得方法の詳細については、この節を参照してく [ださい](../../channels/using/managing-incoming-sms.md#storing-incoming-sms)。

   このオ **[!UICONTROL Enable Real-time KPI updates during SR processing]** プションを使用す **[!UICONTROL Delivered]** ると、配 **[!UICONTROL Bounces + Errors]** 信後にKPIまたはKPIをリアルタイムで更新できます。 これらのKPIは、ウィンドウ内にあ **[!UICONTROL Deployment]** り、プロバイダから受け取ったSR（ステータスレポート）から直接再計算されます。

   ![](assets/sms_connection_1.png)

1. パラメーターを定 **[!UICONTROL Throughput and timeouts]** 義します。

   送信メッセージ(「MT」、「Mobile Terminated」)の最大スループットを1秒あたりのMTで指定できます。 該当するフィールドに「0」と入力した場合、スループットは無制限となります。

   期間を示すどのフィールドでも、値は秒単位で入力する必要があります。

1. 特定のエンコーディングマッピングを定義する必要がある場合に備えて、SMS-C固有のパラメータを定義します。 For more information, refer to the [SMSC specifics](#smsc-specifics) section.

   SMPPプロト **[!UICONTROL Send full phone number (send characters other than digits)]** コルを使用せず、SMSプロバイダ(SMS-C)のサーバにプレフィッ **[!UICONTROL +]** クスを転送する場合は、このオプションを有効にします。

   However, given that certain providers require the use of the **[!UICONTROL +]** prefix, it is advised that you check with your provider and they will suggest that you enable this option if necessary.

1. 必要に応じて、自動返信を定義し、返信の内容に基づいてアクションをトリガします。 詳しくは、[この節](../../channels/using/managing-incoming-sms.md#managing-stop-sms)を参照してください。
1. SMSルーティング外部アカウントの構成を保存します。

新しいルーティングを使用して、Adobe CampaignでSMSメッセージを送信できるようになりました。

## SMSのエンコーディングと形式 {#sms-encoding-and-formats}

### SMSエンコード、長さ、および文字変換 {#sms-encoding--length-and-transliteration}

デフォルトでは、SMS の文字数は GSM（Global System for Mobile Communications）標準に準じています。

GSM エンコードを使用する SMS メッセージは 160 文字以内に制限されています。複数の部分に分けて送信されるメッセージの場合は、SMS 1 件につき 153 文字以内です。

>[!NOTE]
>
>2 文字としてカウントされる文字もあります（中括弧、角括弧、ユーロ記号など）。使用可能なGSM文字のリストは、「 [Table of characters - GSM Standard](#table-of-characters---gsm-standard) 」セクションに表示されます。

必要に応じて、文字の表記変換をチェックボックスで指定できます。

![](assets/sms_transliteration.png)

表記変換では、SMS の特定の文字が GSM 標準に準じていない場合に、別の文字に置き換えられます。

* 表記変換が&#x200B;**許可されている**&#x200B;場合、標準に準じていない文字はメッセージの送信時に GSM 文字に置き換えられます。例えば、「ë」は「e」に置き換えられます。そのため、メッセージは若干改変されますが、文字制限は同じです。
* 表記変換が&#x200B;**許可されていない**&#x200B;場合、標準に準じていない文字があるメッセージはバイナリフォーマット（Unicode）で送信されます。そのため、すべての文字がそのまま送信されます。ただし、Unicode を使用する SMS メッセージは 70 文字以内に制限されています。複数の部分に分けて送信されるメッセージの場合は、SMS 1 件につき 67 文字以内です。文字数が上限を超えると、メッセージは複数に分かれて送信されますが、追加料金が発生する場合があります。

>[!CAUTION]
>
>パーソナライゼーションフィールドを SMS メッセージのコンテンツに入れると、GSM エンコードに対応していない文字が含まれる場合があります。コンテンツの例は、「SMSメッセージの個人 [化」の節にあります](../../channels/using/personalizing-sms-messages.md) 。

デフォルトでは、文字の表記変換は無効です。SMS メッセージのすべての文字をそのまま送信する場合（例えば、固有名詞が改変されないようにする場合）、このオプションは無効にしておくことをお勧めします。

ただし、SMS メッセージに Unicode メッセージ用の文字が多数含まれる場合、このオプションを有効にしてメッセージ送信のコストを抑えることもできます。

### Table of characters - GSM Standard {#table-of-characters---gsm-standard}

この節では、GSM 標準に準じている文字を紹介します。メッセージ本文に、ここで紹介されていない文字が含まれている場合、メッセージ全体がバイナリフォーマット（Unicode）に変換され、文字数が 70 文字以内に制限されます。詳しくは、 [SMSのエンコード、長さ、読み取り方法の節を参照してください](#sms-encoding--length-and-transliteration) 。

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

SP:スペース

ESC:Escape

LF:ラインフィード

CR:キャリッジリターン

**高度な文字（2 回カウント）**

^ { } [ ~ ] | €

### SMSCの詳細 {#smsc-specifics}

>[!NOTE]
>
>これらのオプションを使用すると、コネクタが非標準のSMSC（つまり、SMPP 3.4仕様に厳密に従っていない）や特定のエンコーディング要件に対応でき、上級ユーザーのみが設定する必要があります。

Adobe Campaign では、SMS メッセージの送信時に 1 つまたは複数のテキストエンコードを使用できます。エンコードごとに独自の文字セットがあり、SMS メッセージに入力できる文字数もそれぞれ異なります。

このフ **[!UICONTROL DATA_CODING]** ィールドを使用すると、Adobe Campaignはエンコーディングが使用されるSMS-Cと通信できます。

>[!NOTE]
>
>**data_coding** の値と実際に使用されているエンコードの間のマッピングは標準化されています。Nevertheless, certain SMS-C have their own specific mapping: in this case, your **Adobe Campaign** administrator needs to declare this mapping. 詳しくは、プロバイダーにお問い合わせください。

The **[!UICONTROL Define a specific mapping of encodings]** functionality allows you to declare **data_codings** and to force the encoding if necessary: to do this, specify a single encoding in the table.

**設定**

* この機能がチェ **[!UICONTROL Define a specific mapping of encodings]** ックされていない場合、コネクタは汎用的な動作を行います。

   * **data_coding = 0** を設定して、GSM エンコードの使用を試行します。
   * GSM エンコードが失敗した場合は、**data_coding = 8** を設定して、**UCS2** エンコードの使用を試行します。
   ![](assets/sms_data_coding.png)

* この機能を **[!UICONTROL Define a specific mapping of encodings]** チェックすると、使用するエンコーディングとリンクされたフィールドの値を定義で **[!UICONTROL data_coding]** きます。 Adobe Campaignは、リスト内の最初のエンコーディングを使用しようとしますが、最初のエンコーディングが不可能である場合は次のようになります。

   宣言の順序は重要です。**コスト**&#x200B;が少ない順にリストを設定し、SMS メッセージになるべく多くの文字を使用できるようにすることをお勧めします。

   使用するエンコードのみを宣言してください。SMS-Cが提供するエンコーディングの一部が使用目的に合わない場合は、リストで宣言しないでください。

   ![](assets/sms_data_coding1.png)

### MO に送信された自動返信 {#automatic-reply-sent-to-the-mo}

プロファイルがキャンペーン経由で送信されたSMSメッセージに返信する場合は、自動的に返信されるメッセージや、実行するアクションを設定できます。

詳しくは、[この節](../../channels/using/managing-incoming-sms.md)を参照してください。

## SMSプロパティの設定 {#configuring-sms-properties}

このセクションでは、SMS配信またはSMSテンプレートのプロパティ画面でSMSに固有のパラメータのリストについて説明します。

SMSメッセージを送信するための特定のパラメータは、およびのセクシ **[!UICONTROL Send]** ョンに再グループ化 **[!UICONTROL Advanced parameters]** されます。

![](assets/sms_options.png)

* このオ **[!UICONTROL From]** プションを使用すると、文字列を使用してSMSメッセージの送信者の名前をパーソナライズできます。 受信者の携帯電話でSMSメッセージの送信者名として表示される名前です。

   このフィールドが空の場合は、外部アカウントで提供されるソース番号が使用されます。 ソース番号が指定されていない場合は、短いコードが使用されます。 SMS配信に固有の外部アカウントは、[外部SMSアカウント]セク [ションに表示されます](#defining-an-sms-routing) 。

   ![](assets/sms_smpp.png)

   >[!CAUTION]
   >
   >送信者の住所の変更に関しては、お住まいの国の法律をご確認ください。 また、SMSサービスプロバイダにこの機能が提供されているかどうかを確認する必要があります。

* このオ **[!UICONTROL Maximum number of SMS per message]** プションを使用すると、メッセージの送信に使用するSMSメッセージの数を定義できます。 この数を超えると、メッセージは送信されません。

   >[!CAUTION]
   >
   >SMSメッセージの内容にパーソナライゼーションフィールドまたは条件テキストを挿入した場合、メッセージの長さと、送信するSMSメッセージの数が受信者によって異なる可能性があります。 For more on this, refer to the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

* このフ **[!UICONTROL Transmission mode]** ィールドを使用すると、SMSメッセージの配信方法を指定できます。

   * **[!UICONTROL Saved on SIM card]**:受信者の電話SIMカードにメッセージが保存されます。
   * **[!UICONTROL Saved on mobile]**:メッセージは電話の内部メモリに保存されます。
   * **[!UICONTROL Flash]**:このメッセージは、受信者の携帯電話に通知として表示され、保存されずに表示されなくなります。

