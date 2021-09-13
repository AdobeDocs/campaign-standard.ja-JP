---
title: 受信 SMS の管理
description: STOP SMSを管理し、受信SMSをAdobe Campaignに格納する方法について説明します。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 7%

---

# 受信 SMS の管理{#managing-incoming-sms}

## 停止SMSの管理 {#managing-stop-sms}

プロファイルが Campaign 経由で送信された SMS メッセージに返信する場合、自動的に返信されるメッセージや、実行するアクションを設定できます。

この設定は、[SMSルーティング外部アカウント](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)の&#x200B;**[!UICONTROL Automatic reply sent to the MO]**&#x200B;セクションで定義します。 MOは「モバイル発信」を意味し、SMSを送信したモバイルに対する自動応答を設定できます。

それには、次の手順に従います。

1. 詳細設定メニューのAdobe Campaignロゴから、**[!UICONTROL Administration > Application settings > External accounts]**&#x200B;を選択し、**[!UICONTROL SMS routing via SMPP]**&#x200B;外部アカウントを選択します。
1. 「**[!UICONTROL Automatic reply sent to the MO]**」カテゴリで「**[!UICONTROL Create element]**」をクリックし、自動返信の設定を開始します。

   ![](assets/sms_mo_1.png)

1. この自動返信をトリガーするキーワードを選択します。 キーワードは大文字と小文字が区別されません。例えば、ここで受信者が「STOP」というキーワードを送信すると、自動返信を受け取ります。

   キーワードに関係なく同じ返信を送信する場合は、この列を空のままにします。

   ![](assets/sms_mo_2.png)

1. 「 **[!UICONTROL Short code]** 」フィールドで、配信の送信に通常使用される番号を指定し、送信者名を指定します。 また、**[!UICONTROL Short code]**&#x200B;列を空のままにして、ショートコードに関係なく同じ返信を送信することもできます。

   ![](assets/sms_mo_4.png)

1. 受信者に送信する回答を「**[!UICONTROL Reply]**」フィールドに入力します。

   返信せずにアクションを実行する場合は、**[!UICONTROL Reply]**&#x200B;列を空白のままにします。 例えば、「STOP」以外のメッセージを送信したユーザーの電話番号を強制隔離から削除できます。

   ![](assets/sms_mo_3.png)

1. **[!UICONTROL Additional action]**&#x200B;フィールドで、自動返信にアクションをリンクします。

   * **[!UICONTROL Send to quarantine]**&#x200B;アクションは、プロファイルの電話番号を自動的に強制隔離します。
   * **[!UICONTROL Remove from quarantine]**&#x200B;アクションにより、プロファイルの電話番号が強制隔離から削除されます。
   * 「**[!UICONTROL None]**」アクションでは、アクションを実行せずに受信者にのみメッセージを送信できます。

   例えば、以下の設定では、受信者が「STOP」というキーワードを送信すると、自動的に購読解除の確認が送信され、その電話番号が強制隔離のステータス「a0/>」になります。 **[!UICONTROL On denylist]**&#x200B;このステータスは電話番号のみを表し、ユーザーが引き続き電子メールメッセージを受信できるようにプロファイルを表します。

   ![](assets/sms_mo.png)

1. 「**[!UICONTROL Save]**」をクリックします。

1. SMS配信&#x200B;**[!UICONTROL Properties]**&#x200B;の&#x200B;**[!UICONTROL Advanced parameters]**&#x200B;から、オプトアウトした受信者を自動的に除外する特定の&#x200B;**[!UICONTROL Short code]**&#x200B;を設定できます。 詳しくは、[この節](../../administration/using/configuring-sms-channel.md#configuring-sms-properties)を参照してください。

これで、受信者は、メッセージを自動的に購読解除し、この自動返信を使用して強制隔離に送信できるようになります。 強制隔離された受信者は、 **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Quarantines]**&#x200B;メニューから利用できる&#x200B;**[!UICONTROL Addresses]**&#x200B;テーブルにリストされます。 強制隔離について詳しくは、この[節](../../sending/using/understanding-quarantine-management.md)を参照してください。

これらの受信SMSは、必要に応じて保存できます。 詳しくは、[](#storing-incoming-sms)を参照してください。

## 受信SMSの保存 {#storing-incoming-sms}

**[!UICONTROL SMS routing via SMPP]**&#x200B;外部アカウントで、例えば購読者がSMSメッセージに「STOP」と返信して受信者リストから削除する場合など、受信メッセージを保存するように選択できます。

![](assets/sms_config_mo_1.png)

**[!UICONTROL SMPP channel settings]**&#x200B;カテゴリの&#x200B;**[!UICONTROL Store incoming MO in the database]**&#x200B;をチェックすると、すべてのSMSがinSMSテーブルに保存され、ワークフローの「クエリ」アクティビティで取得できます。

それには、次の手順に従います。

1. **[!UICONTROL SMPP channel settings]**&#x200B;フィールドで、「**[!UICONTROL Store incoming MO in the database]**」をオンにします。

   ![](assets/sms_config_mo_2.png)

1. 「**[!UICONTROL Marketing activities]**」タブで「**[!UICONTROL Create]**」をクリックし、「**[!UICONTROL Workflow]**」を選択します。

   ![](assets/sms_config_mo_3.png)

1. ワークフローのタイプを選択します。
1. ワークフローのプロパティを編集し、「**[!UICONTROL Create]**」をクリックします。 ワークフローの作成について詳しくは、この[節](../../automating/using/building-a-workflow.md)を参照してください。
1. **[!UICONTROL Query]**&#x200B;アクティビティをドラッグ&amp;ドロップし、アクティビティをダブルクリックします。
1. クエリの「**[!UICONTROL Properties]**」タブで、「**[!UICONTROL Resource]**」フィールドで「**[!UICONTROL Incoming SMS (inSMS)]**」を選択します。

   ![](assets/sms_config_mo_4.png)

1. 次に、「**[!UICONTROL Target]**」タブで、**[!UICONTROL Incoming SMS attributes]**&#x200B;ルールをドラッグ&amp;ドロップします。

   ![](assets/sms_config_mo_5.png)

1. ここでは、前日からのすべての受信メッセージをターゲットにします。 「**[!UICONTROL Field]**」カテゴリで「**[!UICONTROL Creation date (created)]**」を選択します。
1. **[!UICONTROL Filter type]**&#x200B;で&#x200B;**[!UICONTROL Relative]**&#x200B;を選択し、**[!UICONTROL Level of precision]**&#x200B;で&#x200B;**[!UICONTROL Day]**&#x200B;を選択します。

   ![](assets/sms_config_mo_6.png)

1. その後、今日、前日、過去数日のデータを取得するよう選択できます。 クエリを設定したら、「**[!UICONTROL Confirm]**」をクリックします。

このクエリは、選択された時間範囲に応じて、受信したすべてのSTOPメッセージを取得します。

「 」アクティビティを使用すると、例えば、母集団を作成し、配信をより適切にパーソナライズできます。
