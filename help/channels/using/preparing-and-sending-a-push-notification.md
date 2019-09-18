---
title: プッシュ通知の準備と送信
seo-title: プッシュ通知の準備と送信
description: プッシュ通知の準備と送信
seo-description: 次の手順に従って、Adobe Campaignで1回送信プッシュ通知を作成します。
page-status-flag: 未活性化の
uuid: 01997725-ca0a-420c-9e81-5ea801652f87
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: ec930cd4-6365-4e54-babe-9dc2eed041fc
context-tags: 配信，mobileAppContent，戻る
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# プッシュ通知の準備と送信{#preparing-and-sending-a-push-notification}

## 通知の準備 {#preparing-the-notification}

Adobe Campaignを使用してプッシュ通知を作成する手順は、次のとおりです。

1. ウィンドウで、 **[!UICONTROL Marketing activities]** 新しいマ [ーケティング活動を作成します](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   単一のプッシュ通知は、キャンペーンまたはAdobe Campaignのホ [ーム](../../start/using/marketing-activities.md#creating-a-marketing-activity) ·ページからも作成で [きます](../../start/using/interface-description.md#home-page)。

   また、ワークフローでプッシュ通知配信アクティビティを使用することもできます。 このアクティビティは、「 [Push通知配信](../../automating/using/push-notification-delivery.md) 」セクションに表示されます。

1. Select **[!UICONTROL Push notification]**.
1. テンプレートを選択します。

   ![](assets/push_notif_type.png)

   デフォルトでは、次の2つのテンプレートのいずれかを選択できます。

   * **[!UICONTROL Send push to Campaign profiles]**:このテンプレートを使用して、モバイルアプリケーションを購読し、プッシュ通知を受信するように選択したAdobe Campaign CRMプロファイルを対象にします。 個人用設定フィ [ールドは](../../designing/using/personalization.md#inserting-a-personalization-field) 、受信者の名など、プッシュ通知に挿入できます。
   * **[!UICONTROL Send push to app subscribers]**:このテンプレートを使用して、アプリケーションから通知を受け取るのを選択した既知の匿名モバイルアプリケーションユーザーにプッシュ通知を送信します。 これらのメッセージは、モバイルアプリケーションから収集したデータを使用してパーソナライズできます。
   また、多言語テンプレートを選択することもできます。 詳細については、「多言語プッシュ通 [知を作成する」を参照してください](../../channels/using/creating-a-multilingual-push-notification.md)。

   テンプレートの詳細については、「テンプレートの管理」セク [ションを参照して](../../start/using/about-templates.md) ください。

1. プッシュ通知のプロパティを入力し、フィールドでモバイルアプリを選択 **[!UICONTROL Associate a Mobile App to a delivery]** します。

   ドロップダウンには、SDK V4とExperience Platform SDKアプリケーションの両方が表示されます。

   ![](assets/push_notif_properties.png)

   プッシュ通知をキャンペーンにリンクできます。 これを行うには、作成済のキャンペーンから選択します。

1. 次の画面では、対象ユーザーを指定できます。たとえば、特定のモバイルアプリケーションを購読しているVIPのすべての顧客を指定できます。 詳細については、「対象ユーザーの作成」を参 [照してくださ](../../audiences/using/creating-audiences.md)い。

   前の手順で選択したモバイルアプリケーションに基づいて、対象ユーザーが自動的にフィルタ処理されます。

   ![](assets/push_notif_audience.png)

1. Push通知をカスタマイズできるようになりました。 まず、メッセージのスタイルを選択します。ま **[!UICONTROL Alert/Message/Badge]** た **[!UICONTROL Silent push]**&#x200B;は プッシュ通知の種類については、「プッシュ通知につ [いて](../../channels/using/about-push-notifications.md) 」を参照してください。

   プッシュ通知の内容を編集し、詳細オプションを定義します。 「プッシュ通 [知のカスタマイズ」を参照してくださ](../../channels/using/customizing-a-push-notification.md)い。

   ![](assets/push_notif_content.png)

   ここで設定したプッシュ通知の内容とオプションは、ペイロードの形式でモバイルアプリに渡されます。 ペイロードの詳細な構造については、「 [Understanding ACS push notifications payload structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) 」を参照してください。

1. Click **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. 通知を送信する前に、テストプロファイルを使用して通知をテストし、配信を送信する前に受信者が表示する内容を正確に確認できます。 配信要 **[!UICONTROL Audiences]** 約から選択し、タブをクリック **[!UICONTROL Test profiles]** します。

   テストの送信の詳細については、「テストプロファイル」を参 [照してくださ](../../sending/using/managing-test-profiles-and-sending-proofs.md)い。

1. テストプロファイルを選択し、をクリックし **[!UICONTROL Preview]** て通知を表示します。コンテンツは、テストプロファイルデータを使用してカスタマイズされます。
1. 異なるデバイスでプッシュ通知のレイアウトを確認します。レンダリングをプレビューするには、iPhone、Android phone、iPad、またはAndroidタブレットを選択します。

   ![](assets/push_notif_preview.png)

1. は、テ **[!UICONTROL Estimated Payload Size]** ストプロファイルデータに基づく見積です。 実際のペイロードサイズは、異なる場合があります。 メッセージの制限は4KBです。

   >[!CAUTION]
   >
   >ペイロードサイズが4KBの制限を超える場合、メッセージは配信されません。 個人用設定データは、メッセージのサイズに影響します。

## 通知の送信 {#sending-the-notification}

プッシュ通知は、対象ユーザーの条件を定義することにより、Adobe Campaignで選択した対象ユーザーに送信できます。 次の例では、選択した対象ユーザーは4つのターゲットのモバイルアプリサブスクライバーで構成されています。

1. をクリック **[!UICONTROL Prepare]** して、ターゲットを計算し、通知を生成します。

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Note that the **[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]** one due to exclusions which can be viewed by clicking ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. このタブ **[!UICONTROL Exclusion logs]** では、送信されたターゲットから除外されたすべてのメッセージの一覧と、この除外の原因を確認できます。

   ここでは、プロファイルが重複していたため、アドレスがブラックリストに含まれていたため、モバイルアプリのサブスクライバーの1つが除外されたことを確認できます。

   ![](assets/push_send_5.png)

1. タブをクリック **[!UICONTROL Exclusion causes]** して、除外されたメッセージのボリュームを表示します。

   ![](assets/push_send_7.png)

1. これで、押し込み通知の送信を **[!UICONTROL Confirm]** 開始するには、をクリックします。
1. メッセージダッシュボードとログを使用して、配信のステータスを確認します。 詳細については、「メッセージと配信 [ログを送信する](../../sending/using/confirming-the-send.md) 」を参 [照してください](../../sending/using/monitoring-a-delivery.md#delivery-logs)。

   この例では、メッセージダッシュボードに、Adobe Campaignが2つのプッシュ通知を送信しようとしたことが表示されます。1つはデバイスに正常に配信され、もう1つは障害が発生しました。 配信にエラーが発生した理由を確認するには、ウィンドウ ![](assets/lp_link_properties.png) の下部にあるボタンをクリック **[!UICONTROL Deployment]** します。

   ![](assets/push_send_4.png)

1. ウィンドウで **[!UICONTROL Deployment]** タブをクリックし **[!UICONTROL Sending logs]** て、送信されたプッシュ通知とそのステータスのリストにアクセスします。 この配信では、1つのプッシュ通知が正常に送信され、もう1つのプッシュ通知は不正なデバイストークンのために失敗しました。 この加入者は、今後の配信からブラックリストに表示されます。

   >[!NOTE]
   >
   >理由は、Adobe Campaignの下流で発生した障害です。 apnやfcmなどのプロバイダが失敗した場合も、その理由は同様に反映される。 プロバイダの障害の詳細については、 [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) and [](https://firebase.google.com/docs/cloud-messaging/http-server-ref) Androidのマニュアルを参照してください。

   ![](assets/push_send_6.png)

動的なレポートを使用して、プッシュ通知の配信の影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)

