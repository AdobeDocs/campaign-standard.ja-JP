---
solution: Campaign Standard
product: campaign
title: 受信 SMS の管理
description: STOP SMSを管理し、着信SMSをAdobe Campaignに格納する方法を説明します。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 8%

---


# 受信 SMS の管理{#managing-incoming-sms}

## STOP SMS {#managing-stop-sms}の管理

プロファイルが Campaign 経由で送信された SMS メッセージに返信する場合、自動的に返信されるメッセージや、実行するアクションを設定できます。

この構成は、[SMSルーティング外部アカウント](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)の&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;セクションで定義されています。 MOは「Mobile Originated」を表し、SMSを送信したモバイルに対して自動応答を設定できます。

それには、次の手順に従います。

1. 詳細設定メニューのAdobe Campaignロゴから、「**[!UICONTROL Administration > Application settings > External accounts]**」、「**[!UICONTROL SMS routing via SMPP]**」の順に選択します。
1. **[!UICONTROL Automatic reply sent to the MO]**&#x200B;カテゴリの下の&#x200B;**[!UICONTROL Create element]**&#x200B;をクリックして、自動返信の設定を開始します。

   ![](assets/sms_mo_1.png)

1. この自動返信をトリガーするキーワードを選択します。 キーワードは大文字と小文字が区別されません。例えば、受信者がキーワード「STOP」を送信した場合、ユーザーは自動応答を受け取ります。

   キーワードが何であろうと同じ返信を送信する場合は、この列を空欄にします。

   ![](assets/sms_mo_2.png)

1. **[!UICONTROL Short code]**&#x200B;フィールドに、配信の送信に通常使用され、送信者名として使用される番号を指定します。 また、**[!UICONTROL Short code]**&#x200B;列を空のままにして、短いコードが何であっても同じ返信を送ることもできます。

   ![](assets/sms_mo_4.png)

1. 受信者に送信する回答を&#x200B;**[!UICONTROL Reply]**&#x200B;フィールドに入力します。

   返信を送信せずにアクションを実行するには、**[!UICONTROL Reply]**&#x200B;列を空のままにします。 例えば、「STOP」以外のメッセージで返信する強制隔離の電話番号をユーザーから削除できます。

   ![](assets/sms_mo_3.png)

1. **[!UICONTROL Additional action]**&#x200B;フィールドに、自動返信に対するアクションをリンクします。

   * **[!UICONTROL Send to quarantine]**&#x200B;操作は、プロファイルの電話番号を自動的に強制隔離します。
   * **[!UICONTROL Remove from quarantine]**&#x200B;操作により、プロファイルの電話番号が強制隔離から削除されます。
   * **[!UICONTROL None]**&#x200B;操作を行うと、受信者にメッセージを送信するだけで、操作を行うことはできません。

   例えば、以下の設定では、受信者がキーワード「STOP」を送信すると、購読解除の確認メッセージが自動的に送信され、電話番号が&#x200B;**[!UICONTROL On denylist]**&#x200B;ステータスの強制隔離に送信されます。 このステータスは電話番号のみを表し、プロファイルは電子メールの受信を続けるようにします。

   ![](assets/sms_mo.png)

受信者は、メッセージを自動的に登録解除し、この自動応答を含む強制隔離に送信できるようになりました。 検疫された受信者は、**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**&#x200B;メニューから利用できる&#x200B;**[!UICONTROL Addresses]**&#x200B;テーブルに一覧表示されます。 強制隔離の詳細については、[](../../sending/using/understanding-quarantine-management.md)を参照してください。

これらの受信SMSは、必要に応じて保存できます。 詳しくは、[](#storing-incoming-sms)を参照してください。

## 受信SMS {#storing-incoming-sms}を保存中

**[!UICONTROL SMS routing via SMPP]**&#x200B;外部アカウントでは、例えば、受信者リストから削除するために加入者がSMSメッセージに「STOP」と返信した場合に、受信メッセージを保存するように選択できます。

![](assets/sms_config_mo_1.png)

**[!UICONTROL SMPP channel settings]**&#x200B;カテゴリの&#x200B;**[!UICONTROL Store incoming MO in the database]**&#x200B;をチェックすると、すべてのSMSがinSMSテーブルに格納され、ワークフロー内のクエリアクティビティを介して取得できます。

それには、次の手順に従います。

1. **[!UICONTROL SMPP channel settings]**&#x200B;フィールドで、**[!UICONTROL Store incoming MO in the database]**&#x200B;をチェックします。

   ![](assets/sms_config_mo_2.png)

1. 「**[!UICONTROL Marketing activities]**」タブで「**[!UICONTROL Create]**」をクリックし、「**[!UICONTROL Workflow]**」を選択します。

   ![](assets/sms_config_mo_3.png)

1. ワークフローのタイプを選択します。
1. ワークフローのプロパティを編集し、**[!UICONTROL Create]**&#x200B;をクリックします。 ワークフローの作成について詳しくは、[](../../automating/using/building-a-workflow.md)を参照してください。
1. **[!UICONTROL Query]**&#x200B;アクティビティをドラッグ&amp;ドロップし、アクティビティを重複クリックします。
1. クエリの&#x200B;**[!UICONTROL Properties]**&#x200B;タブで、**[!UICONTROL Resource]**&#x200B;フィールドの&#x200B;**[!UICONTROL Incoming SMS (inSMS)]**&#x200B;を選択します。

   ![](assets/sms_config_mo_4.png)

1. 次に、「**[!UICONTROL Target]**」タブで&#x200B;**[!UICONTROL Incoming SMS attributes]**&#x200B;ルールをドラッグ&amp;ドロップします。

   ![](assets/sms_config_mo_5.png)

1. ここでは、前日からのすべての受信メッセージをターゲットします。 **[!UICONTROL Field]**&#x200B;カテゴリで&#x200B;**[!UICONTROL Creation date (created)]**&#x200B;を選択します。
1. **[!UICONTROL Filter type]**&#x200B;で&#x200B;**[!UICONTROL Relative]**&#x200B;を選択し、**[!UICONTROL Level of precision]**&#x200B;で&#x200B;**[!UICONTROL Day]**&#x200B;を選択します。

   ![](assets/sms_config_mo_6.png)

1. その後、今日、前日、または最近の数日からデータを取得するように選択できます。 クエリを設定したら、**[!UICONTROL Confirm]**&#x200B;をクリックします。

このクエリは、選択した時間範囲に応じて、受信したすべてのSTOPメッセージを取得します。

このアクティビティを使用すると、例えば訪問者を作成し、配信をよりパーソナライズすることができます。
