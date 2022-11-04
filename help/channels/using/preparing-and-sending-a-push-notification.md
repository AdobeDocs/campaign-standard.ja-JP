---
title: プッシュ通知の作成と送信
description: 以下の手順に従って、Adobe Campaignで単一送信のプッシュ通知を作成します。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
source-git-commit: 708bdc1d5dc1c30d609ba0fa1c17debe403afd72
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 4%

---

# プッシュ通知の準備と送信{#preparing-and-sending-a-push-notification}

## 通知の準備 {#preparing-the-notification}

Adobe Campaignでプッシュ通知を作成する手順は、次のとおりです。

1. 次の **[!UICONTROL Marketing activities]** 窓 [新しいマーケティングアクティビティの作成](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   また、 [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) Adobe Campaignから [ホームページ](../../start/using/interface-description.md#home-page).

   また、ワークフロー内でプッシュ通知配信アクティビティを使用することもできます。 このアクティビティは、 [プッシュ通知配信](../../automating/using/push-notification-delivery.md) 」セクションに入力します。

1. 「**[!UICONTROL Push notification]**」を選択します。
1. テンプレートを選択します。

   ![](assets/push_notif_type.png)

   デフォルトでは、次の 2 つのテンプレートのいずれかを選択できます。

   * **[!UICONTROL Send push to Campaign profiles]**:このテンプレートを使用して、モバイルアプリケーションを購読し、プッシュ通知の受信をオプトインしたAdobe Campaign CRM プロファイルをターゲットに設定します。 次を挿入できます。 [パーソナライズ](../../designing/using/personalization.md#inserting-a-personalization-field) フィールドをプッシュ通知に組み込みます（受信者の名など）。
   * **[!UICONTROL Send push to app subscribers]**:このテンプレートを使用して、アプリケーションからの通知の受信をオプトインした既知の匿名モバイルアプリケーションユーザーにプッシュ通知を送信します。 モバイルアプリケーションから収集したデータを使用して、これらのメッセージをパーソナライズできます。

   また、多言語のテンプレートを選択することもできます。 詳しくは、 [多言語プッシュ通知の作成](../../channels/using/creating-a-multilingual-push-notification.md).

   テンプレートについて詳しくは、 [テンプレートの管理](../../start/using/marketing-activity-templates.md) 」セクションに入力します。

1. プッシュ通知のプロパティを入力し、 **[!UICONTROL Associate a Mobile App to a delivery]** フィールドに入力します。

   このドロップダウンには、SDK V4 とExperience PlatformSDK の両方のアプリケーションが表示されます。

   ![](assets/push_notif_properties.png)

   プッシュ通知をキャンペーンにリンクできます。 これをおこなうには、既に作成されているキャンペーンから選択します。

1. 次の画面で、オーディエンス ( 例えば、特定のモバイルアプリケーションを購読しているVIPのすべての顧客 ) を指定できます。 詳しくは、 [オーディエンスの作成](../../audiences/using/creating-audiences.md).

   オーディエンスは、前の手順で選択したモバイルアプリに基づいて、自動的にフィルタリングされます。

   ![](assets/push_notif_audience.png)

1. これで、プッシュ通知をカスタマイズできるようになりました。 まず、メッセージのスタイルを選択します。 **[!UICONTROL Alert/Message/Badge]** または **[!UICONTROL Silent push]**. プッシュ通知のタイプについては、 [プッシュ通知について](../../channels/using/about-push-notifications.md) 」セクションに入力します。

   プッシュ通知の内容を編集し、詳細設定オプションを定義します。 詳しくは、 [プッシュ通知のカスタマイズ](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   ここで設定したプッシュ通知のコンテンツとオプションは、ペイロードの形式でモバイルアプリに渡されます。 ペイロードの詳細な構造については、 [Campaign Standardプッシュ通知のペイロード構造について](../../administration/using/push-payload.md) テクニカルノート

1. 「**[!UICONTROL Create]**」をクリックします。

   ![](assets/push_notif_content_2.png)

1. 通知を送信する前に、テストプロファイルでテストし、配信を送信する前に、受信者に送られる内容を正確に確認できます。 選択 **[!UICONTROL Audiences]** 配信の概要から、 **[!UICONTROL Test profiles]** タブをクリックします。

   テストの送信について詳しくは、 [テストプロファイル](../../sending/using/sending-proofs.md).

1. テストプロファイルを選択し、 **[!UICONTROL Preview]** 通知を表示するには：コンテンツは、テストプロファイルデータを使用してパーソナライズされます。
1. 様々なデバイスでのプッシュ通知レイアウトを確認します。レンダリングをプレビューするには、「 iPhone 」、「 Android phone 」、「 iPad 」または「 Android tablet 」を選択します。

   ![](assets/push_notif_preview.png)

1. この **[!UICONTROL Estimated Payload Size]** は、テストプロファイルデータに基づく推定です。 実際のペイロードサイズは変わる場合があります。 メッセージの上限は 4 KB です。

   >[!CAUTION]
   >
   >ペイロードのサイズが 4KB の制限を超える場合、メッセージは配信されません。

パーソナライゼーションデータはメッセージのサイズに影響を与えます。

## 通知の送信 {#sending-the-notification}

オーディエンス条件を定義することで、Adobe Campaignの選択したオーディエンスにプッシュ通知を送信できます。 以下の例では、選択したオーディエンスは、ターゲットとなる 4 人のモバイルアプリ購読者で構成されています。

1. クリック **[!UICONTROL Prepare]** を使用して、ターゲットを計算し、通知を生成します。

   ![](assets/push_send_1.png)

1. 準備が完了したら、 **[!UICONTROL Deployment]** window には次の KPI が表示されます。 **[!UICONTROL Target]** および **[!UICONTROL To deliver]**. なお、 **[!UICONTROL To deliver]** カウントが **[!UICONTROL Targeted]** 1 つは、クリックすると表示できる除外 ![](assets/lp_link_properties.png) ボタン **[!UICONTROL Deployment]** ウィンドウ

   ![](assets/push_send_2.png)

1. 内 **[!UICONTROL Exclusion logs]** 「 」タブには、送信されたターゲットから除外されたすべてのメッセージのリストと、この除外の理由が表示されます。

   ここでは、アドレスが上にあったので、モバイルアプリの購読者の 1 人が除外されましたブロックリスト。プロファイルが重複しているので、他の購読者も除外されています。

   ![](assets/push_send_5.png)

1. 次をクリック： **[!UICONTROL Exclusion causes]** タブをクリックして、除外されたメッセージのボリュームを表示します。

   ![](assets/push_send_7.png)

1. これで、 **[!UICONTROL Confirm]** ：プッシュ通知の送信を開始します。
1. 配信のステータスは、メッセージダッシュボードとログで確認できます。詳しくは、 [メッセージの送信](../../sending/using/confirming-the-send.md) および [配信ログ](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   この例では、メッセージダッシュボードに、Adobe Campaignが 2 つのプッシュ通知の送信を試みたことが表示されます。1 つはデバイスに正常に配信され、もう 1 つは失敗しました。 配信にエラーが発生した理由を知るには、 ![](assets/lp_link_properties.png) ボタン **[!UICONTROL Deployment]** ウィンドウ

   ![](assets/push_send_4.png)

1. 次の **[!UICONTROL Deployment]** ウィンドウで、 **[!UICONTROL Sending logs]** タブをクリックして、送信されたプッシュ通知のリストとそのステータスにアクセスします。 この配信では、1 つのプッシュ通知が正常に送信されたのに対して、もう 1 つは、デバイストークンが不正なために失敗しました。 その後、この購読者が以降の配信からブロックリストに追加されます。

   >[!NOTE]
   >
   >理由は、Adobe Campaignの下流にあるエラーになる可能性があります。 apns や fcm などのプロバイダーからエラーが発生した場合、その理由も同様に反映されます。 プロバイダーのエラーの詳細については、 [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) および [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) ドキュメント。

   ![](assets/push_send_6.png)

動的レポートを使用して、プッシュ通知配信の影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)
