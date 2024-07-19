---
title: 受信 SMS の管理
description: STOP SMS を管理し、受信 SMS をAdobe Campaignに保存する方法について説明します。
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: 30d0c2552bea3a7cbd8500be4e8c0c74e5a40a99
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# 受信 SMS の管理{#managing-incoming-sms}

## 停止 SMS の管理 {#managing-stop-sms}

Campaign 経由で送信された SMS メッセージにプロファイルが返信した場合、自動的に送り返されるメッセージと実行するアクションを設定できます。

この設定は、[SMS ルーティング外部アカウント ](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) の「**[!UICONTROL Automatic reply sent to the MO]**」セクションで定義されます。 MO は「Mobile Originated」を意味し、SMS を送信したモバイルへの自動返信を設定できることを意味します。

それには、次の手順に従います。

1. Adobe Campaign ロゴを使用して詳細メニューから、**[!UICONTROL SMS routing via SMPP]** の外部アカウント **[!UICONTROL Administration > Application settings > External accounts]** 選択します。
1. **[!UICONTROL Automatic reply sent to the MO]** カテゴリの **[!UICONTROL Create element]** をクリックして、自動応答の設定を開始します。

   ![](assets/sms_mo_1.png)

1. この自動応答をトリガーにするキーワードを選んでください。 キーワードでは大文字と小文字が区別されません。 例えば、受信者が「STOP」というキーワードを送信すると、自動返信を受け取ります。

   キーワードに関係なく同じ返信を送信する場合は、この列を空のままにします。

   >[!IMPORTANT]
   >
   >英数字のみを使用できます。

   ![](assets/sms_mo_2.png)

1. 「**[!UICONTROL Short code]**」フィールドに、通常は配信の送信に使用される送信者名の代わりとなる数字を指定します。 **[!UICONTROL Short code]** 列を空のままにして、ショートコードに関係なく同じ返信を送信することもできます。

   ![](assets/sms_mo_4.png)

1. 受信者に送信する回答をフィールド **[!UICONTROL Reply]** に入力します。

   返信を送信せずにアクションを実行するには、**[!UICONTROL Reply]** 列を空のままにします。 例えば、「STOP」以外のメッセージで返信したユーザーの電話番号を強制隔離から削除できます。

   ![](assets/sms_mo_3.png)

1. 「**[!UICONTROL Additional action]**」フィールドに、自動返信にアクションをリンクします。

   * **[!UICONTROL Send to quarantine]** アクションは、プロファイルの電話番号を自動的に強制隔離します。
   * **[!UICONTROL Remove from quarantine]** アクションは、強制隔離からプロファイルの電話番号を削除します。
   * **[!UICONTROL None]** アクションを使用すると、アクションを実行せずに、受信者にのみメッセージを送信できます。

   例えば、以下の設定では、受信者が「STOP」というキーワードを送信すると、購読解除の確認が自動的に受信され、電話番号は「**[!UICONTROL On denylist]**」ステータスで強制隔離に送信されます。 このステータスは電話番号のみに適用されます。プロファイルは、ユーザーが引き続きメールメッセージを受信できるようにするものです。

   ![](assets/sms_mo.png)

1. 「**[!UICONTROL Save]**」をクリックします。

1. SMS 配信 **[!UICONTROL Properties]** ールの **[!UICONTROL Advanced parameters]** から、オプトアウトした受信者を自動的に除外する特定の **[!UICONTROL Short code]** を設定できます。 詳しくは、[ この節 ](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) を参照してください。

これで、受信者がメッセージの購読を自動的に解除し、この自動返信で強制隔離に送信できるようになりました。 強制隔離された受信者のリストは、**[!UICONTROL Addresses]** のテーブルに表示されます。このテーブルは、**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Quarantines]** のメニューから使用できます。 強制隔離について詳しくは、この [ 節 ](../../sending/using/understanding-quarantine-management.md) を参照してください。

これらの受信 SMS は、必要に応じて保存できます。 詳しくは、この [ 節 ](#storing-incoming-sms) を参照してください。

## 受信 SMS の保存 {#storing-incoming-sms}

**[!UICONTROL SMS routing via SMPP]** 外部アカウントでは、受信メッセージの保存を選択できます。例えば、購読者が受信者リストから削除するために SMS メッセージに「STOP」と返信した場合などです。

![](assets/sms_config_mo_1.png)

**[!UICONTROL SMPP channel settings]** カテゴリに **[!UICONTROL Store incoming MO in the database]** をチェックインすると、すべての SMS が inSMS テーブルに保存され、ワークフローのクエリアクティビティを使用して取得できます。

それには、次の手順に従います。

1. 「**[!UICONTROL SMPP channel settings]**」フィールドで、「**[!UICONTROL Store incoming MO in the database]**」をチェックします。

   ![](assets/sms_config_mo_2.png)

1. 「**[!UICONTROL Marketing activities]**」タブで「」をクリック **[!UICONTROL Create]**、「**[!UICONTROL Workflow]**」を選択します。

   ![](assets/sms_config_mo_3.png)

1. ワークフロータイプを選択します。
1. ワークフローのプロパティを編集し、「**[!UICONTROL Create]**」をクリックします。 ワークフローの作成について詳しくは、この [ 節 ](../../automating/using/building-a-workflow.md) を参照してください。
1. **[!UICONTROL Query]** アクティビティをドラッグ&amp;ドロップし、そのアクティビティをダブルクリックします。
1. クエリの「**[!UICONTROL Properties]**」タブで、「**[!UICONTROL Resource]**」フィールドの「**[!UICONTROL Incoming SMS (inSMS)]**」を選択します。

   ![](assets/sms_config_mo_4.png)

1. 次に、「**[!UICONTROL Target]**」タブで、**[!UICONTROL Incoming SMS attributes]** ルールをドラッグ&amp;ドロップします。

   ![](assets/sms_config_mo_5.png)

1. ここでは、前日からの受信メッセージをすべてターゲットにします。 **[!UICONTROL Field]** カテゴリで、「**[!UICONTROL Creation date (created)]**」を選択します。
1. 「**[!UICONTROL Filter type]**」で「**[!UICONTROL Relative]**」を選択し、「**[!UICONTROL Level of precision]**」で「**[!UICONTROL Day]**」を選択します。

   ![](assets/sms_config_mo_6.png)

1. その後、今日、前日または過去数日間からデータを取得するよう選択できます。 クエリを設定したら、「**[!UICONTROL Confirm]**」をクリックします。

このクエリは、選択した時間範囲に応じて、受信したすべての STOP メッセージを取得します。

アクティビティを使用すると、例えば母集団を作成し、配信をより適切にパーソナライズできます。
