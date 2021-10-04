---
title: メッセージのプレビュー
description: コンテンツエディターまたは E メールデザイナーでメッセージをプレビューする方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Seed Address
role: User
level: Intermediate
exl-id: ac8c1265-f530-4438-ab2d-3ca17615ca85
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 16%

---

# 配信のプレビュー {#previewing-messages}

## E メールのプレビュー {#previewing-emails}

Campaign Standardを使用すると、送信前にメッセージをプレビューして、メッセージのパーソナライゼーションと受信者へのメッセージの表示方法を確認できます。

メッセージのプレビューは、メッセージのターゲットに追加する **テストプロファイル** を使用して実行されます。

**email** メッセージの場合、Campaign Standardを使用すると、テストプロファイルではなく、ターゲットプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージの正確な内容を取得できます。 詳しくは、[ターゲットプロファイルを使用した電子メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)を参照してください。

テストプロファイルを使用してメッセージをプレビューするには、次の手順に従います。

1. [E メールデザイナー ](../../designing/using/designing-content-in-adobe-campaign.md) で、**[!UICONTROL Preview]** ボタンをクリックします。

   ![](assets/sending_preview.png)

   E メールのデスクトップビューとレスポンシブモバイルビューが並べて表示されます。

1. 各プレビュー中にスパム対策チェックが自動的に実行されます。**[!UICONTROL Anti-spam analysis]** ボタンをクリックして、警告の詳細を確認します。

   ![](assets/sending_anti-spam_analysis.png)

1. 「 **[!UICONTROL Change profile]** 」ボタンを選択して、パーソナライゼーション要素をテストするテストプロファイルを選択します。

   ![](assets/sending_test-profile.png)

1. **[!UICONTROL Preview]** モードを終了するには、画面の左上にある **[!UICONTROL Edit]** ボタンをクリックします。

   ![](assets/sending_preview_edit.png)

**関連トピック**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [ターゲットプロファイルを使用した E メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)

## SMS メッセージのプレビュー {#previewing-sms}

**SMS** メッセージの場合、Campaign Standardを使用すると、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージの正確な内容を取得できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用して SMS メッセージをプレビューするには、次の手順に従います。

1. SMS メッセージの **[!UICONTROL Properties]** に入力し、オーディエンスを選択したら、配信をパーソナライズできます。 詳しくは、[](../../channels/using/personalizing-sms-messages.md) を参照してください。

   ![](assets/sms_preview.png)

1. コンテンツをパーソナライズしたら、**[!UICONTROL Create]** をクリックして **[!UICONTROL Summary]** ウィンドウにアクセスします。

1. **[!UICONTROL Summary]** ウィンドウで「**[!UICONTROL Content]**」をクリックして、配信のプレビューを開始します。

   ![](assets/sms_preview_2.png)

1. ツールバーの **[!UICONTROL Preview]** をクリックします。

   ![](assets/sms_preview_3.png)

1. **[!UICONTROL Change profile]** をクリックしてテストプロファイルを選択し、**[!UICONTROL Confirm]** をクリックします。

   ![](assets/sms_preview_4.png)

選択したテストプロファイルに応じて、メッセージの正確な表示を確認できます。

**関連トピック**

* [SMS メッセージについて](../../channels/using/about-sms-messages.md)
* [SMS メッセージの作成](../../channels/using/creating-an-sms-message.md)
* [SMS メッセージのパーソナライズ](../../channels/using/personalizing-sms-messages.md)

## プッシュ通知のプレビュー {#previewing-push}

**プッシュ通知** の場合、Campaign Standardを使用すると、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージの正確な内容を取得できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用してプッシュ通知をプレビューするには、次の手順に従います。

1. プッシュ通知の **[!UICONTROL Properties]** に入力し、オーディエンスを選択すると、配信をパーソナライズできます。 詳しくは、[ プッシュ通知のカスタマイズ ](../../channels/using/customizing-a-push-notification.md) を参照してください。

1. コンテンツをパーソナライズした後、プレビューウィンドウでデバイスと OS に応じて、プッシュ通知のレンダリングを直接確認できます。

   ![](assets/push_preview.png)

1. テストプロファイルを使用してプッシュ通知をプレビューするには、**[!UICONTROL Preview with test profile]** をクリックします。

   ![](assets/push_preview_2.png)

1. テストプロファイルを選択し、**[!UICONTROL Confirm]** を選択します。

選択したテストプロファイルに応じて、メッセージの正確な表示を確認できます。

![](assets/push_preview_3.png)

**関連トピック**

* [プッシュ通知について](../../channels/using/about-push-notifications.md)
* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [プッシュ通知のカスタマイズ](../../channels/using/customizing-a-push-notification.md)

## アプリ内メッセージのプレビュー {#previewing-in-app}

**アプリ内** の場合、Campaign Standardを使用すると、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージの正確な内容を取得できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用してアプリ内メッセージをプレビューするには、次の手順に従います。

1. アプリ内メッセージの **[!UICONTROL Properties]** に入力し、オーディエンスを選択して **[!UICONTROL Triggers]** を設定したら、配信をパーソナライズできます。 詳しくは、[ アプリ内メッセージのカスタマイズ ](../../channels/using/customizing-an-in-app-message.md) を参照してください。

1. コンテンツをパーソナライズした後、プレビューウィンドウでデバイスと OS に応じて、アプリ内メッセージのレンダリングを直接確認できます。

   ![](assets/in_app_preview.png)

1. テストプロファイルを使用してアプリ内メッセージをプレビューするには、**[!UICONTROL Preview]** をクリックします。

   ![](assets/in_app_preview_2.png)

1. テストプロファイルを選択し、**[!UICONTROL Confirm]** を選択します。

選択したテストプロファイルに応じて、メッセージの正確な表示を確認できます。

![](assets/in_app_preview_3.png)

**関連トピック**

* [アプリ内メッセージについて](../../channels/using/about-in-app-messaging.md)
* [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)
