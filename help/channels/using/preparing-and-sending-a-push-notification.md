---
title: プッシュ通知の準備と送信
seo-title: プッシュ通知の準備と送信
description: プッシュ通知の準備と送信
seo-description: Adobe Campaignで単一送信プッシュ通知を作成するには、次の手順に従います。
page-status-flag: 常にアクティブ化されていない
uuid: 01997725- ca0a-420c-9e81-5ea801652f87
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: ec930cd4-6365-4e54- babe-9dc2eed041fc
context-tags: delivery， mobileAppContent， back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Preparing and sending a push notification{#preparing-and-sending-a-push-notification}

## Preparing the notification {#preparing-the-notification}

Adobe Campaignを使用してプッシュ通知を作成する手順を次に示します。

1. **[!UICONTROL Marketing activities]** ウィンドウから、新しいマーケティングアクティビティ [を作成](../../start/using/marketing-activities.md#creating-a-marketing-activity)します。

   Note that a single push notification can also be created from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page).

   ワークフローでプッシュ通知配信アクティビティを使用することもできます。This activity is presented in the [Push notification delivery](../../automating/using/push-notification-delivery.md) section.

1. Select **[!UICONTROL Push notification]**.
1. テンプレートを選択します。

   ![](assets/push_notif_type.png)

   デフォルトでは、次の2つのテンプレートのいずれかを選択できます。

   * **[!UICONTROL Send push to Campaign profiles]**:このテンプレートを使用して、モバイルアプリケーションを購読しているAdobe Campaign CRMプロファイルをターゲットにし、プッシュ通知の受信をオプトインします。[パーソナライゼーションフィールド](../../designing/using/inserting-a-personalization-field.md) は、受信者の名などのプッシュ通知に挿入できます。
   * **[!UICONTROL Send push to app subscribers]**:このテンプレートを使用して、アプリケーションから通知を受信することをオプトインしている既知のすべてのモバイルアプリケーションユーザーにプッシュ通知を送信します。モバイルアプリケーションから収集したデータを使用して、これらのメッセージをパーソナライズできます。
   多言語テンプレートを選択することもできます。For more information, refer to [Creating a multilingual push notification](../../channels/using/creating-a-multilingual-push-notification.md).

   For more on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   ドロップダウンには、SDK V4とExperience Platform SDKアプリケーションの両方が表示されることに注意してください。

   ![](assets/push_notif_properties.png)

   プッシュ通知はキャンペーンにリンクできます。これを行うには、作成済みのキャンペーンから選択します。

1. 次の画面では、特定のモバイルアプリケーションを購読しているすべてのVIP顧客など、オーディエンスを指定できます。For more on this, see [Creating audiences](../../audiences/using/creating-audiences.md).

   オーディエンスは、前の手順で選択したモバイルアプリケーションに基づいて自動的にフィルタリングされます。

   ![](assets/push_notif_audience.png)

1. プッシュ通知をカスタマイズできるようになりました。First, choose the message style: **[!UICONTROL Alert/Message/Badge]** or **[!UICONTROL Silent push]**. The push notification types are described in the [About push notifications](../../channels/using/about-push-notifications.md) section.

   プッシュ通知のコンテンツを編集し、高度なオプションを定義します。See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   ここで設定したプッシュ通知コンテンツおよびオプションは、ペイロードの形式でモバイルアプリに渡されます。The detailed structure of the payload is described in the [Understanding ACS push notifications payload structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) technote.

1. **[!UICONTROL Create]**&#x200B;をクリックします。

   ![](assets/push_notif_content_2.png)

1. 通知を送信する前に、テストプロファイルでテストし、受信者が配信を送信する前に表示する内容を正確に確認できます。Select **[!UICONTROL Audiences]** from your delivery summary and click the **[!UICONTROL Test profiles]** tab.

   For more on sending tests, refer to [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md).

1. Select your test profiles and click **[!UICONTROL Preview]** to display the notification: content is personalized with the test profile data.
1. 様々なデバイスのプッシュ通知レイアウトを確認します。iPhone、Androidスマートフォン、iPadまたはAndroidタブレットを選択してレンダリングをプレビューします。

   ![](assets/push_notif_preview.png)

1. The **[!UICONTROL Estimated Payload Size]** is an estimate based on test profile data. 実際のペイロードサイズは異なる場合があります。メッセージの制限は4KBです。

   >[!CAUTION]
   >
   >ペイロードサイズが上限4KBを超えると、メッセージは配信されません。パーソナライゼーションデータはメッセージのサイズに影響します。

## Sending the notification {#sending-the-notification}

プッシュ通知は、オーディエンス条件を定義することで、Adobe Campaignで選択したオーディエンスに送信できます。以下の例では、選択したオーディエンスが4つのターゲットモバイルアプリの購読者で構成されています。

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. **[!UICONTROL To deliver]** この数は、ウィンドウの下部に **[!UICONTROL Targeted]** あるボタンをクリック ![](assets/lp_link_properties.png) して表示できる除外により、1より低いことに注意 **[!UICONTROL Deployment]** してください。

   ![](assets/push_send_2.png)

1. **[!UICONTROL Exclusion logs]** このタブでは、送信されたターゲットから除外されたすべてのメッセージのリストと、この除外の背後にある理由を確認できます。

   ここでは、プロファイルが重複しているので、モバイルアプリケーションの登録者の1人がブラックリストに記載されていて、他の購読者が他の購読者のものであることがわかりました。

   ![](assets/push_send_5.png)

1. Click the **[!UICONTROL Exclusion causes]** tab to display the volume of excluded messages.

   ![](assets/push_send_7.png)

1. You can now click **[!UICONTROL Confirm]** to start sending push notifications.
1. メッセージのダッシュボードとログから配信状況を確認します。For more on this, see [Sending messages](../../sending/using/confirming-the-send.md) and [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   この例では、メッセージダッシュボードに、Adobe Campaignがプッシュ通知を送信しようとしたことが表示されます。が正常にデバイスに配信され、もう1つが失敗しました。To know why the delivery has errors, click the ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_4.png)

1. **[!UICONTROL Deployment]** ウィンドウから、タブを **[!UICONTROL Sending logs]** クリックして、送信されたプッシュ通知とそのステータスのリストにアクセスします。この配信では、デバイストークンが不良なために、1つのプッシュ通知が正常に送信されました。その後、この購読者はさらに配信からブラックリストに登録されます。

   >[!NOTE]
   >
   >Adobe Campaignには、何らかの障害をダウンストリームすることができます。apnsやfcmなどのプロバイダーからのエラーが発生した場合、その理由も反映されます。For more information on provider failures, you can refer to the [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) and [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) documentation.

   ![](assets/push_send_6.png)

動的レポートでのプッシュ通知配信の影響を測定できるようになりました。

**関連トピック:**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)

