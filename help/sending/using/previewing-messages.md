---
solution: Campaign Standard
product: campaign
title: メッセージのプレビュー
description: コンテンツエディターまたは電子メールデザイナーでメッセージをプレビューする方法について説明します。
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Seed Address
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 16%

---


# 配信メッセージのプレビュー {#previewing-messages}

## 電子メールのプレビュー{#previewing-emails}

Campaign Standardを使用すると、メッセージを送信する前にプレビューでき、受信者の個人設定とメッセージの表示方法を確認できます。

メッセージのプレビューは、メッセージのターゲットに追加する&#x200B;**テストプロファイル**&#x200B;を使用して実行されます。

**email**&#x200B;メッセージの場合、Campaign Standardを使用すると、テストプロファイルではなく、対象プロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージを正確に表示できます。 詳しくは、[ターゲットプロファイルを使用した電子メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)を参照してください。

テストプロファイルを使用してプレビューを行うには、次の手順に従います。

1. [電子メールデザイナー](../../designing/using/designing-content-in-adobe-campaign.md)で、**[!UICONTROL Preview]**&#x200B;ボタンをクリックします。

   ![](assets/sending_preview.png)

   デスクトップ表示と電子メールのレスポンシブモバイル表示が並べて表示されます。

1. 各プレビュー中にスパム対策チェックが自動的に実行されます。**[!UICONTROL Anti-spam analysis]**&#x200B;ボタンをクリックして、警告に関する詳細を確認します。

   ![](assets/sending_anti-spam_analysis.png)

1. **[!UICONTROL Change profile]**&#x200B;ボタンを選択して、パーソナライゼーション要素をテストするテストプロファイルを選択します。

   ![](assets/sending_test-profile.png)

1. **[!UICONTROL Preview]**&#x200B;モードを終了するには、画面の左上にある&#x200B;**[!UICONTROL Edit]**&#x200B;ボタンをクリックします。

   ![](assets/sending_preview_edit.png)

**関連トピック**

* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [ターゲットプロファイルを使用した E メールメッセージのテスト](../../sending/using/testing-messages-using-target.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)

## SMSメッセージのプレビュー{#previewing-sms}

**SMS**&#x200B;メッセージの場合、Campaign Standardでは、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージを正確に表示できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用してSMSメッセージをプレビューするには、次の手順に従います。

1. SMSメッセージの&#x200B;**[!UICONTROL Properties]**&#x200B;を入力し、オーディエンスを選択すると、配信を個人用に設定できます。 詳しくは、[](../../channels/using/personalizing-sms-messages.md)を参照してください。

   ![](assets/sms_preview.png)

1. コンテンツを個人設定した後、**[!UICONTROL Create]**&#x200B;をクリックして&#x200B;**[!UICONTROL Summary]**&#x200B;ウィンドウにアクセスします。

1. **[!UICONTROL Summary]**&#x200B;ウィンドウで&#x200B;**[!UICONTROL Content]**&#x200B;をクリックし、配信のプレビューを開始します。

   ![](assets/sms_preview_2.png)

1. ツールバーの&#x200B;**[!UICONTROL Preview]**&#x200B;をクリックします。

   ![](assets/sms_preview_3.png)

1. **[!UICONTROL Change profile]**&#x200B;をクリックしてテストプロファイルを選択し、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/sms_preview_4.png)

選択したテストプロファイルに応じて、メッセージが正確に表示されます。

**関連トピック**

* [SMS メッセージについて](../../channels/using/about-sms-messages.md)
* [SMS メッセージの作成](../../channels/using/creating-an-sms-message.md)
* [SMS メッセージのパーソナライズ](../../channels/using/personalizing-sms-messages.md)

## プッシュ通知のプレビュー{#previewing-push}

**プッシュ通知**&#x200B;の場合、Campaign Standardでは、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のプロファイルが受け取るメッセージを正確に表示できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用してプッシュ通知をプレビューするには、次の手順に従います。

1. プッシュ通知の&#x200B;**[!UICONTROL Properties]**&#x200B;に入力し、オーディエンスを選択すると、配信をパーソナライズできます。 詳しくは、[プッシュ通知のカスタマイズ](../../channels/using/customizing-a-push-notification.md)を参照してください。

1. コンテンツを個人設定した後、プレビューーウィンドウのデバイスやOSに応じて、プッシュ通知のレンダリングを直接確認できます。

   ![](assets/push_preview.png)

1. テストプロファイルを使用してプッシュ通知をプレビューするには、**[!UICONTROL Preview with test profile]**&#x200B;をクリックします。

   ![](assets/push_preview_2.png)

1. テストプロファイルを選択し、**[!UICONTROL Confirm]**&#x200B;を選択します。

選択したテストプロファイルに応じて、メッセージが正確に表示されます。

![](assets/push_preview_3.png)

**関連トピック**

* [プッシュ通知について](../../channels/using/about-push-notifications.md)
* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [プッシュ通知のカスタマイズ](../../channels/using/customizing-a-push-notification.md)

## アプリ内メッセージのプレビュー{#previewing-in-app}

**アプリ内**&#x200B;の場合、Campaign Standardは、テストプロファイルを使用してプレビューを行うことができます。 これにより、特定のプロファイルが受け取るメッセージを正確に表示できます。 詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照してください。

テストプロファイルを使用してアプリ内メッセージをプレビューするには、次の手順に従います。

1. アプリ内メッセージの&#x200B;**[!UICONTROL Properties]**&#x200B;に入力し、オーディエンスを選択して&#x200B;**[!UICONTROL Triggers]**&#x200B;を設定すると、配信をパーソナライズできます。 詳しくは、[アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)を参照してください。

1. コンテンツを個人化した後、プレビューーウィンドウでデバイスやOSに応じて、アプリ内メッセージのレンダリングを直接確認できます。

   ![](assets/in_app_preview.png)

1. テストプロファイルを使用してアプリ内メッセージをプレビューするには、**[!UICONTROL Preview]**&#x200B;をクリックします。

   ![](assets/in_app_preview_2.png)

1. テストプロファイルを選択し、**[!UICONTROL Confirm]**&#x200B;を選択します。

選択したテストプロファイルに応じて、メッセージが正確に表示されます。

![](assets/in_app_preview_3.png)

**関連トピック**

* [アプリ内メッセージについて](../../channels/using/about-in-app-messaging.md)
* [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)