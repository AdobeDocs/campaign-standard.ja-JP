---
title: メッセージのプレビュー
description: コンテンツエディターまたは電子メールプレビューでメッセージを編集する方法について説明します。
page-status-flag: never-activated
uuid: 8dffca95-59fe-4e9b-93cb-73b33ffde020
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 8428f8ac-8ef5-46cd-9d93-10ec0ecd3ded
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 92bbf57f1a6eff67d2551dc83dd8cb5f6b38bd99

---


# プレビュー配信 {#previewing-messages}

## 電子メールのプレビュー {#previewing-emails}

Campaign Standardを使用すると、送信前にプレビューメッセージを送信し、メッセージのパーソナライゼーションと受信者の表示方法を確認できます。

メッセージプレビューは、メッ **セージのプロファイル** に追加したテストターゲットを使用して実行します。

電子メー **ルメッセージの場合** 、Campaign Standardを使用すると、テストプロファイルではなくターゲットプロファイルを使用してメッセージをプレビューできます。 これにより、特定のメッセージが受信するメッセージを正確にプロファイルできます。 詳しくは、ターゲットを設定したメッセージを使 [用した電子メールプロファイルのテストを参照してくださ](../../sending/using/testing-messages-using-target.md)い。

テストプレビューを使用してメッセージをプロファイルするには、次の手順に従います。

1. 電子メールデ [ザイナーで](../../designing/using/designing-content-in-adobe-campaign.md)、ボタンをクリッ **[!UICONTROL Preview]** クします。

   ![](assets/sending_preview.png)

   デスクトップ表示と電子メールのレスポンシブモバイル表示が並べて表示されます。

1. 各プレビュー中に自動的にスパム対策チェックを行う。 警告の詳細を **[!UICONTROL Anti-spam analysis]** 確認するには、ボタンをクリックします。

   ![](assets/sending_anti-spam_analysis.png)

1. このボタンを **[!UICONTROL Change profile]** 選択して、パーソナライゼーション要素をテストするプロファイルのテストを選択します。

   ![](assets/sending_test-profile.png)

1. モードを終了 **[!UICONTROL Preview]** するには、画面の左 **[!UICONTROL Edit]** 上にあるボタンをクリックします。

   ![](assets/sending_preview_edit.png)

**関連トピック**

* [テストプロファイル](../../audiences/using/managing-test-profiles.md)
* [ターゲットを設定したメッセージを使用した電子メールプロファイル](../../sending/using/testing-messages-using-target.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)

## SMSメッセージのプレビュー {#previewing-sms}

**SMSメッセージの場合** 、Campaign Standardではテストメッセージを使用してプロファイルできます。 これにより、特定のメッセージが受信するメッセージを正確にプロファイルできます。 詳しくは、テストプロファイルの管理を参 [照してください](../../audiences/using/managing-test-profiles.md)。

テストプレビューを使用してSMSメッセージをプロファイルするには、次の手順に従います。

1. SMSメッセージの内容を入力し、 **[!UICONTROL Properties]** オーディエンスを選択すると、メッセージをパーソナライズできます。 For more information, refer to [section](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_preview.png)

1. コンテンツをパーソナライズしたら、をクリックし **[!UICONTROL Create]** てウィンドウにアクセス **[!UICONTROL Summary]** します。

1. ウィンドウで、をク **[!UICONTROL Summary]** リックして、配信を **[!UICONTROL Content]** 開始プレビューします。

   ![](assets/sms_preview_2.png)

1. ツールバー **[!UICONTROL Preview]** のをクリックします。

   ![](assets/sms_preview_3.png)

1. 次に、テ **[!UICONTROL Change profile]** ストプロファイルをクリックしま **[!UICONTROL Confirm]**&#x200B;す。

   ![](assets/sms_preview_4.png)

選択したテストプロファイルに応じて、メッセージの正確な表現が表示されます。

**関連トピック**

* [SMS メッセージについて](../../channels/using/about-sms-messages.md)
* [SMS メッセージの作成](../../channels/using/creating-an-sms-message.md)
* [SMS メッセージのパーソナライズ](../../channels/using/personalizing-sms-messages.md)

## プッシュ通知のプレビュー {#previewing-push}

プッシュ **通知の場合**、Campaign Standardを使用すると、テストプロファイルを使用してメッセージをプレビューできます。 これにより、特定のメッセージが受信するメッセージを正確にプロファイルできます。 詳しくは、テストプロファイルの管理を参 [照してください](../../audiences/using/managing-test-profiles.md)。

テストプレビューを使用してプッシュ通知をプロファイルするには、次の手順に従います。

1. プッシュ通知のに入力し、 **[!UICONTROL Properties]** オーディエンスを選択すると、配信をパーソナライズできます。 詳しくは、プッシュ通知のカスタ [マイズを参照してください](../../channels/using/customizing-a-push-notification.md)。

1. コンテンツをパーソナライズした後、デバイスやOSに応じて、プッシュ通知のレンダリングをプレビューウィンドウで直接確認できます。

   ![](assets/push_preview.png)

1. テストプレビューを使用してプッシュ通知をプロファイルするには、をクリックしま **[!UICONTROL Preview with test profile]**&#x200B;す。

   ![](assets/push_preview_2.png)

1. テストプロファイルを選択しま **[!UICONTROL Confirm]**&#x200B;す。

選択したテストプロファイルに応じて、メッセージの正確な表現が表示されます。

![](assets/push_preview_3.png)

**関連トピック**

* [プッシュ通知について](../../channels/using/about-push-notifications.md)
* [プッシュ通知の準備と送信](../../channels/using/preparing-and-sending-a-push-notification.md)
* [プッシュ通知のカスタマイズ](../../channels/using/customizing-a-push-notification.md)

## アプリ内メッセージのプレビュー {#previewing-in-app}

アプリ **内の場合**、Campaign Standardを使用してプレビューメッセージをプロファイルできます。 これにより、特定のメッセージが受信するメッセージを正確にプロファイルできます。 詳しくは、テストプロファイルの管理を参 [照してください](../../audiences/using/managing-test-profiles.md)。

テストプレビューを使用してアプリ内メッセージをプロファイルするには、次の手順に従います。

1. アプリ内メッセージの **[!UICONTROL Properties]** 内容を入力し、オーディエンスを選択して設定したら、 **[!UICONTROL Triggers]**&#x200B;配信をパーソナライズできます。 詳しくは、「アプリ内メッセージのカ [スタマイズ」を参照してください](../../channels/using/customizing-an-in-app-message.md)。

1. コンテンツをパーソナライズした後、デバイスやOSに応じて、アプリ内メッセージのレンダリングをプレビューウィンドウで直接確認できます。

   ![](assets/in_app_preview.png)

1. テストプレビューを使用してアプリ内メッセージをプロファイルするには、をクリックしま **[!UICONTROL Preview]**&#x200B;す。

   ![](assets/in_app_preview_2.png)

1. テストプロファイルを選択しま **[!UICONTROL Confirm]**&#x200B;す。

選択したテストプロファイルに応じて、メッセージの正確な表現が表示されます。

![](assets/in_app_preview_3.png)

**関連トピック**

* [アプリ内メッセージについて](../../channels/using/about-in-app-messaging.md)
* [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)