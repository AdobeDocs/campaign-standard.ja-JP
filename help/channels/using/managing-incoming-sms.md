---
title: 受信 SMS の管理
description: SMS を停止し、受信 SMS をAdobe Campaignに保存する方法を説明します。
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

プロファイルが Campaign 経由で送信された SMS メッセージに返信する場合、自動的に返信されるメッセージや、実行するアクションを設定できます。

この設定は、 **[!UICONTROL Automatic reply sent to the MO]** のセクション [SMS ルーティング外部アカウント](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO は「モバイル発信」を意味し、SMS を送信したモバイルに対する自動応答を設定できます。

それには、次の手順に従います。

1. 詳細設定メニューのAdobe Campaignロゴから、を選択します。 **[!UICONTROL Administration > Application settings > External accounts]** その後、 **[!UICONTROL SMS routing via SMPP]** 外部アカウント。
1. の下 **[!UICONTROL Automatic reply sent to the MO]** カテゴリ、クリック **[!UICONTROL Create element]** をクリックして自動返信の設定を開始します。

   ![](assets/sms_mo_1.png)

1. この自動返信をトリガーにするキーワードを選択します。 キーワードは大文字と小文字が区別されません。例えば、ここでは、受信者が「STOP」というキーワードを送信した場合、自動返信を受け取ります。

   キーワードに関係なく同じ返信を送信する場合は、この列を空のままにします。

   >[!IMPORTANT]
   >
   >英数字のみを使用できます。

   ![](assets/sms_mo_2.png)

1. Adobe Analytics の **[!UICONTROL Short code]** 「 」フィールドで、通常配信の送信に使用され、送信者名として使用される数値を指定します。 また、 **[!UICONTROL Short code]** 列が空の場合は、ショートコードに関係なく同じ返信を送信します。

   ![](assets/sms_mo_4.png)

1. 受信者に送信する回答を「 」フィールドに入力します **[!UICONTROL Reply]**.

   返信せずにアクションを実行する場合は、「 **[!UICONTROL Reply]** 列が空です。 例えば、「STOP」以外のメッセージを送信したユーザーの電話番号を強制隔離から削除できます。

   ![](assets/sms_mo_3.png)

1. Adobe Analytics の **[!UICONTROL Additional action]** フィールドで、自動返信にアクションをリンクします。

   * The **[!UICONTROL Send to quarantine]** アクションは、プロファイルの電話番号を自動的に強制隔離します。
   * The **[!UICONTROL Remove from quarantine]** 「 」アクションを実行すると、プロファイルの電話番号が強制隔離から削除されます。
   * The **[!UICONTROL None]** 「 」アクションを使用すると、アクションを実行せずに受信者にのみメッセージを送信できます。

   例えば、以下の設定では、受信者が「STOP」というキーワードを送信した場合、自動的に購読解除の確認が送信され、その電話番号が **[!UICONTROL On denylist]** ステータス。 このステータスは電話番号のみを表し、ユーザーが引き続き電子メールメッセージを受信できるようにプロファイルを表します。

   ![](assets/sms_mo.png)

1. 「**[!UICONTROL Save]**」をクリックします。

1. 次から： **[!UICONTROL Advanced parameters]** SMS 配信の **[!UICONTROL Properties]**&#x200B;を設定すると、 **[!UICONTROL Short code]** をクリックすると、オプトアウトした受信者が自動的に除外されます。 詳しくは、 [この節](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

これで、受信者は、メッセージを自動的に購読解除し、この自動返信を使用して強制隔離に送信できるようになりました。 強制隔離された受信者のリストは、 **[!UICONTROL Addresses]** ～を通じて入手できるテーブル **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** メニュー。 強制隔離について詳しくは、 [セクション](../../sending/using/understanding-quarantine-management.md).

これらの受信 SMS は、必要に応じて保存できます。 詳しくは、 [セクション](#storing-incoming-sms).

## 受信 SMS の保存 {#storing-incoming-sms}

Adobe Analytics の **[!UICONTROL SMS routing via SMPP]** 外部アカウントを使用する場合、例えば、購読者が SMS メッセージに「STOP」と返信して受信者リストから削除する場合など、受信メッセージを保存するように選択できます。

![](assets/sms_config_mo_1.png)

次をチェックして **[!UICONTROL Store incoming MO in the database]** （内） **[!UICONTROL SMPP channel settings]** カテゴリの場合、すべての SMS は inSMS テーブルに保存され、ワークフローの「クエリ」アクティビティで取得できます。

それには、次の手順に従います。

1. Adobe Analytics の **[!UICONTROL SMPP channel settings]** フィールド、チェック **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. Adobe Analytics の **[!UICONTROL Marketing activities]** タブ、クリック **[!UICONTROL Create]** 次に、 **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. ワークフローのタイプを選択します。
1. ワークフローのプロパティを編集し、「 **[!UICONTROL Create]**. ワークフローの作成について詳しくは、この [セクション](../../automating/using/building-a-workflow.md).
1. 次をドラッグ&amp;ドロップ： **[!UICONTROL Query]** 「 」アクティビティを選択し、「 」アクティビティをダブルクリックします。
1. Adobe Analytics の **[!UICONTROL Properties]** タブで、「 」を選択します。 **[!UICONTROL Incoming SMS (inSMS)]** （内） **[!UICONTROL Resource]** フィールドに入力します。

   ![](assets/sms_config_mo_4.png)

1. 次に、 **[!UICONTROL Target]** 「 」タブで、「 」をドラッグ&amp;ドロップします。 **[!UICONTROL Incoming SMS attributes]** ルールを使用します。

   ![](assets/sms_config_mo_5.png)

1. ここでは、前日からのすべての受信メッセージをターゲットにします。 Adobe Analytics の **[!UICONTROL Field]** カテゴリ、選択 **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**&#x200B;を選択します。 **[!UICONTROL Relative]** その後、 **[!UICONTROL Level of precision]**&#x200B;を選択します。 **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. その後、今日、前日、過去数日のデータを取得するよう選択できます。 クリック **[!UICONTROL Confirm]** クエリを設定する際に使用します。

このクエリは、選択された時間範囲に応じて、受信したすべての STOP メッセージを取得します。

「 」アクティビティを使用すると、例えば、母集団を作成し、配信をより適切にパーソナライズすることができます。
