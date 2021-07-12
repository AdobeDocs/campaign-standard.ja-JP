---
solution: Campaign Standard
product: campaign
title: メッセージのプレビュー
description: コンテンツエディターまたはEメールデザイナーでメッセージをプレビューする方法を説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: シードアドレス
role: User
level: Intermediate
exl-id: ac8c1265-f530-4438-ab2d-3ca17615ca85
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 16%

---

# 配信のプレビュー {#previewing-messages}

## Eメールのプレビュー {#previewing-emails}

Campaign Standardでは、送信前にメッセージをプレビューして、メッセージのパーソナライゼーションと受信者への表示方法を確認できます。

メッセージのプレビューは、メッセージのターゲットに追加する&#x200B;**テストプロファイル**&#x200B;を使用して実行されます。

**eメール**&#x200B;メッセージの場合、Campaign Standardを使用すると、テストプロファイルではなく、ターゲットプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージの正確な内容を取得できます。 詳しくは、[ターゲットプロファイルを使用した電子メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)を参照してください。

テストプロファイルを使用してメッセージをプレビューするには、次の手順に従います。

1. [Eメールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)で、「**[!UICONTROL Preview]**」ボタンをクリックします。

   ![](assets/sending_preview.png)

   Eメールのデスクトップビューとレスポンシブモバイルビューが並べて表示されます。

1. 各プレビュー中にスパム対策チェックが自動的に実行されます。警告の詳細を確認するには、「**[!UICONTROL Anti-spam analysis]**」ボタンをクリックします。

   ![](assets/sending_anti-spam_analysis.png)

1. 「 **[!UICONTROL Change profile]** 」ボタンを選択して、パーソナライゼーション要素をテストするテストプロファイルを選択します。

   ![](assets/sending_test-profile.png)

1. **[!UICONTROL Preview]**&#x200B;モードを終了するには、画面の左上にある&#x200B;**[!UICONTROL Edit]**&#x200B;ボタンをクリックします。

   ![](assets/sending_preview_edit.png)

**関連トピック**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [ターゲットプロファイルを使用した E メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)

## SMSメッセージのプレビュー {#previewing-sms}

**SMS**&#x200B;メッセージの場合、Campaign Standardを使用すると、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージの正確な内容を取得できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用してSMSメッセージをプレビューするには、次の手順に従います。

1. SMSメッセージの&#x200B;**[!UICONTROL Properties]**&#x200B;に入力してオーディエンスを選択したら、配信をパーソナライズできます。 詳しくは、[](../../channels/using/personalizing-sms-messages.md)を参照してください。

   ![](assets/sms_preview.png)

1. コンテンツをパーソナライズしたら、**[!UICONTROL Create]**&#x200B;をクリックして&#x200B;**[!UICONTROL Summary]**&#x200B;ウィンドウにアクセスします。

1. **[!UICONTROL Summary]**&#x200B;ウィンドウで「**[!UICONTROL Content]**」をクリックし、配信のプレビューを開始します。

   ![](assets/sms_preview_2.png)

1. ツールバーの&#x200B;**[!UICONTROL Preview]**&#x200B;をクリックします。

   ![](assets/sms_preview_3.png)

1. **[!UICONTROL Change profile]**&#x200B;をクリックしてテストプロファイルを選択し、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/sms_preview_4.png)

選択したテストプロファイルに応じて、メッセージの正確な表示を確認できます。

**関連トピック**

* [SMS メッセージについて](../../channels/using/about-sms-messages.md)
* [SMS メッセージの作成](../../channels/using/creating-an-sms-message.md)
* [SMS メッセージのパーソナライズ](../../channels/using/personalizing-sms-messages.md)

## プッシュ通知のプレビュー {#previewing-push}

**プッシュ通知**&#x200B;の場合、Campaign Standardを使用すると、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージの正確な内容を取得できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用してプッシュ通知をプレビューするには、次の手順に従います。

1. プッシュ通知の&#x200B;**[!UICONTROL Properties]**&#x200B;に入力し、オーディエンスを選択すると、配信をパーソナライズできます。 詳しくは、[プッシュ通知のカスタマイズ](../../channels/using/customizing-a-push-notification.md)を参照してください。

1. コンテンツをパーソナライズした後、プレビューウィンドウでデバイスとOSに応じて、プッシュ通知のレンダリングを直接確認できます。

   ![](assets/push_preview.png)

1. テストプロファイルを使用してプッシュ通知をプレビューするには、「**[!UICONTROL Preview with test profile]**」をクリックします。

   ![](assets/push_preview_2.png)

1. テストプロファイルを選択し、**[!UICONTROL Confirm]**&#x200B;を選択します。

選択したテストプロファイルに応じて、メッセージの正確な表示を確認できます。

![](assets/push_preview_3.png)

**関連トピック**

* [プッシュ通知について](../../channels/using/about-push-notifications.md)
* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [プッシュ通知のカスタマイズ](../../channels/using/customizing-a-push-notification.md)

## アプリ内メッセージのプレビュー {#previewing-in-app}

**アプリ内**&#x200B;の場合、Campaign Standardを使用すると、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージの正確な内容を取得できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用してアプリ内メッセージをプレビューするには、次の手順に従います。

1. アプリ内メッセージの&#x200B;**[!UICONTROL Properties]**&#x200B;に入力し、オーディエンスを選択して&#x200B;**[!UICONTROL Triggers]**&#x200B;を設定したら、配信をパーソナライズできます。 詳しくは、[アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)を参照してください。

1. コンテンツをパーソナライズした後、プレビューウィンドウでデバイスとOSに応じて、アプリ内メッセージのレンダリングを直接確認できます。

   ![](assets/in_app_preview.png)

1. テストプロファイルを使用してアプリ内メッセージをプレビューするには、**[!UICONTROL Preview]**&#x200B;をクリックします。

   ![](assets/in_app_preview_2.png)

1. テストプロファイルを選択し、**[!UICONTROL Confirm]**&#x200B;を選択します。

選択したテストプロファイルに応じて、メッセージの正確な表示を確認できます。

![](assets/in_app_preview_3.png)

**関連トピック**

* [アプリ内メッセージについて](../../channels/using/about-in-app-messaging.md)
* [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)
