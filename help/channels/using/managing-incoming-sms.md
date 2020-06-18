---
title: 受信 SMS の管理
description: STOP SMSを管理し、着信SMSをAdobe Campaignに格納する方法を説明します。
page-status-flag: never-activated
uuid: f063052b-96ef-41b6-bf1b-4006de73f0b9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: ee1970e6-1ced-46e0-94e6-8337768300ee
delivercontext-tags: delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 2%

---


# 受信 SMS の管理{#managing-incoming-sms}

## 停止SMSの管理 {#managing-stop-sms}

プロファイルがキャンペーン経由で送信されたSMSメッセージに返信する場合、自動的に返信されるメッセージや、実行するアクションを設定できます。

この構成は、 **[!UICONTROL Automatic reply sent to the MO]** SMSルーティング外部アカウントの [セクションで定義されます](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)。 MOは「Mobile Originated」を表し、SMSを送信したモバイルに対して自動応答を設定できます。

これをおこなうには：

1. 詳細メニューで、Adobe Campaignのロゴを使用して、 **[!UICONTROL Administration > Application settings > External accounts]****[!UICONTROL SMS routing via SMPP]** 外部アカウントを選択します。
1. [ **[!UICONTROL Automatic reply sent to the MO]** カテゴリ]で、自動返信を設定する開始 **[!UICONTROL Create element]** に移動します。

   ![](assets/sms_mo_1.png)

1. この自動返信をトリガーするキーワードを選択します。 キーワードは大文字と小文字が区別されません。例えば、受信者がキーワード「STOP」を送信した場合、ユーザーは自動応答を受け取ります。

   キーワードが何であろうと同じ返信を送信する場合は、この列を空欄にします。

   ![](assets/sms_mo_2.png)

1. 配信の送信に通常使用され、送信者名として使用される番号を **[!UICONTROL Short code]** フィールドに指定します。 また、短いコードが何であっても同じ返信を送信する場合は、 **[!UICONTROL Short code]** 列を空のままにすることもできます。

   ![](assets/sms_mo_4.png)

1. 受信者に送信する回答をフィールドに入力し **[!UICONTROL Reply]**&#x200B;ます。

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. 例えば、「STOP」以外のメッセージで返信する強制隔離の電話番号をユーザーから削除できます。

   ![](assets/sms_mo_3.png)

1. このフィールドで、自動返信にアクションをリンクし **[!UICONTROL Additional action]** ます。

   * この **[!UICONTROL Send to quarantine]** 操作により、プロファイルの電話番号が自動的に強制隔離されます。
   * 強制隔離からプロファイルの電話番号が削除され **[!UICONTROL Remove from quarantine]** ます。
   * この **[!UICONTROL None]** 操作により、受信者にメッセージを送信するだけで、操作を実行する必要はありません。
   例えば、以下の設定では、受信者がキーワード「STOP」を送信すると、購読解除の確認メッセージが自動的に送信され、電話番号が **[!UICONTROL On block list]** ステータスと共に強制隔離に送信されます。 このステータスは電話番号のみを示し、プロファイルはブロックリストに追加されないので、ユーザーは電子メールメッセージの受信を続行します。

   ![](assets/sms_mo.png)

受信者は、メッセージを自動的に登録解除し、この自動応答を含む強制隔離に送信できるようになりました。 隔離された受信者は、 **[!UICONTROL Addresses]** / **[!UICONTROL Administration]** / **[!UICONTROL Channels]****[!UICONTROL Quarantines]** メニューで利用できる表に一覧表示されます。 For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

これらの受信SMSは、必要に応じて保存できます。 For more information on this, refer to this [section](#storing-incoming-sms).

## 受信SMSの格納 {#storing-incoming-sms}

外部アカウントでは、受信者リストから削除するために加入者がSMSメッセージに「STOP」と返信した場合など、受信メッセージを保存するように選択できます。 **[!UICONTROL SMS routing via SMPP]**

![](assets/sms_config_mo_1.png)

カテゴリ **[!UICONTROL Store incoming MO in the database]****[!UICONTROL SMPP channel settings]** をチェックインすると、すべてのSMSがinSMSテーブルに保存され、ワークフロー内のクエリアクティビティを介して取得できます。

これをおこなうには：

1. フィールドでチェック **[!UICONTROL SMPP channel settings]** を入れ **[!UICONTROL Store incoming MO in the database]**&#x200B;ます。

   ![](assets/sms_config_mo_2.png)

1. タブでをクリックし、を選択 **[!UICONTROL Marketing activities]** し **[!UICONTROL Create]****[!UICONTROL Workflow]**&#x200B;ます。

   ![](assets/sms_config_mo_3.png)

1. ワークフローのタイプを選択します。
1. ワークフローのプロパティを編集し、をクリックし **[!UICONTROL Create]**&#x200B;ます。 For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. アクティビティをドラッグ&amp;ドロップし、重複を押しながら **[!UICONTROL Query]** アクティビティをクリックします。
1. クエリの **[!UICONTROL Properties]** タブで、フィールド **[!UICONTROL Incoming SMS (inSMS)]** のを選択し **[!UICONTROL Resource]** ます。

   ![](assets/sms_config_mo_4.png)

1. 次に、 **[!UICONTROL Target]** タブでルールをドラッグ&amp;ドロップし **[!UICONTROL Incoming SMS attributes]** ます。

   ![](assets/sms_config_mo_5.png)

1. ここでは、前日からのすべての受信メッセージをターゲットします。 カテゴリでを選択し **[!UICONTROL Field]** ま **[!UICONTROL Creation date (created)]**&#x200B;す。
1. でを選択 **[!UICONTROL Filter type]**&#x200B;し、 **[!UICONTROL Relative]** でを選択し **[!UICONTROL Level of precision]**&#x200B;ま **[!UICONTROL Day]**&#x200B;す。

   ![](assets/sms_config_mo_6.png)

1. その後、今日、前日、または最近の数日からデータを取得するように選択できます。 クエリ **[!UICONTROL Confirm]** が設定されたら、をクリックします。

このクエリは、選択した時間範囲に応じて、受信したすべてのSTOPメッセージを取得します。

このアクティビティを使用すると、例えば訪問者を作成し、配信をよりパーソナライズすることができます。
