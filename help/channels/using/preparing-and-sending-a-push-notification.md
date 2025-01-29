---
title: プッシュ通知の作成と送信
description: Adobe Campaignで 1 回限りのプッシュ通知を作成するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 3%

---

# プッシュ通知の準備と送信{#preparing-and-sending-a-push-notification}

## 通知の準備 {#preparing-the-notification}

Adobe Campaignでプッシュ通知を作成する手順は次のとおりです。

1. **[!UICONTROL Marketing activities]** ウィンドウで [ 新しいマーケティングアクティビティを作成 ](../../start/using/marketing-activities.md#creating-a-marketing-activity) します。

   また、[ キャンペーン ](../../start/using/marketing-activities.md#creating-a-marketing-activity) またはAdobe Campaign[ ホームページ ](../../start/using/interface-description.md#home-page) から 1 つのプッシュ通知を作成することもできます。

   また、ワークフローでプッシュ通知配信アクティビティを使用することもできます。 このアクティビティは、「プッシュ通知配信 [ セクションに表示さ ](../../automating/using/push-notification-delivery.md) ます。

1. 「**[!UICONTROL Push notification]**」を選択します。
1. テンプレートを選択します。

   ![](assets/push_notif_type.png)

   デフォルトでは、次の 2 つのテンプレートのいずれかを選択できます。

   * **[!UICONTROL Send push to Campaign profiles]**：このテンプレートを使用して、モバイルアプリケーションを購読し、プッシュ通知の受信をオプトインしたAdobe Campaign CRM プロファイルをターゲットに設定します。 受信者の名など、プッシュ通知に [ パーソナライゼーション ](../../designing/using/personalization.md#inserting-a-personalization-field) フィールドを挿入できます。
   * **[!UICONTROL Send push to app subscribers]**：このテンプレートを使用すると、アプリケーションからの通知の受信をオプトインしたすべての既知のモバイルアプリケーションユーザーおよび匿名モバイルアプリケーションユーザーにプッシュ通知を送信できます。 モバイルアプリケーションから収集したデータを使用して、これらのメッセージをパーソナライズできます。

   また、多言語テンプレートを選択することもできます。 詳しくは、[ 多言語プッシュ通知の作成 ](../../channels/using/creating-a-multilingual-push-notification.md) を参照してください。

   テンプレートについて詳しくは、[ テンプレートの管理 ](../../start/using/marketing-activity-templates.md) の節を参照してください。

1. プッシュ通知のプロパティを入力し、「**[!UICONTROL Associate a Mobile App to a delivery]**」フィールドでモバイルアプリを選択します。

   ドロップダウンに、SDK V4 とExperience Platform SDKの両方のアプリケーションが表示されることに注意してください。

   ![](assets/push_notif_properties.png)

   プッシュ通知をキャンペーンにリンクできます。 それには、作成済みのキャンペーンから選択します。

1. 次の画面では、オーディエンス（例：特定のモバイルアプリケーションを購読したすべてのVIP ユーザー）を指定できます。 詳しくは、[ オーディエンスの作成 ](../../audiences/using/creating-audiences.md) を参照してください。

   オーディエンスは、前の手順で選択したモバイルアプリケーションに基づいて自動的にフィルタリングされます。

   ![](assets/push_notif_audience.png)

1. プッシュ通知をカスタマイズできるようになりました。 最初に、メッセージスタイルとして **[!UICONTROL Alert/Message/Badge]** または **[!UICONTROL Silent push]** を選択します。 プッシュ通知のタイプについては、[ プッシュ通知について ](../../channels/using/about-push-notifications.md) の節で説明します。

   プッシュ通知の内容を編集し、詳細オプションを定義します。 [ プッシュ通知のカスタマイズ ](../../channels/using/customizing-a-push-notification.md) を参照してください。

   ![](assets/push_notif_content.png)

   ここで設定したプッシュ通知の内容とオプションは、ペイロードの形式でモバイルアプリに渡されます。 ペイロードの詳細な構造については、[Campaign Standardプッシュ通知ペイロード構造について ](../../administration/using/push-payload.md) のテクニカルノートに記載されています。

1. 「**[!UICONTROL Create]**」をクリックします。

   ![](assets/push_notif_content_2.png)

1. 通知を送信する前に、テストプロファイルでテストしてから、配信を送信する前に受信者に表示される内容を正確に確認できます。 配信概要から **[!UICONTROL Audiences]** を選択し、「**[!UICONTROL Test profiles]**」タブをクリックします。

   テストの送信について詳しくは、[ テストプロファイル ](../../sending/using/sending-proofs.md) を参照してください。

1. テストプロファイルを選択し、「**[!UICONTROL Preview]**」をクリックして、テストプロファイルデータでコンテンツがパーソナライズされたという通知が表示されます。
1. 様々なデバイスでのプッシュ通知レイアウトの確認：iPhone、Android phone、iPad、Android タブレットのいずれかを選択して、レンダリングをプレビューします。

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]** は、テストプロファイルデータに基づく予測です。 実際のペイロードサイズは異なる場合があります。 メッセージの上限は 4 KB です。

   >[!CAUTION]
   >
   >ペイロードサイズが 4 KB の制限を超えた場合、メッセージは配信されません。

パーソナライゼーションデータはメッセージのサイズに影響します。

## 通知の送信 {#sending-the-notification}

プッシュ通知は、オーディエンス条件を定義することで、Adobe Campaignで選択したオーディエンスに送信できます。 以下の例では、選択したオーディエンスは、4 人のターゲットモバイルアプリ購読者で構成されています。

1. 「**[!UICONTROL Prepare]**」をクリックし、ターゲットを計算して通知を生成します。

   ![](assets/push_send_1.png)

1. 準備が正常に完了すると、**[!UICONTROL Deployment]** ウィンドウに KPI 「**[!UICONTROL Target]**」および「**[!UICONTROL To deliver]**」が表示されます。 **[!UICONTROL To deliver]** 除外の数が **[!UICONTROL Targeted]** の数より少ないのは、除外ウィンドウの下部にあるボタンをクリックすると表示でき ![](assets/lp_link_properties.png) ため **[!UICONTROL Deployment]** す。

   ![](assets/push_send_2.png)

1. 「**[!UICONTROL Exclusion logs]**」タブには、送信されたターゲットから除外されたすべてのメッセージのリストと、この除外の理由が表示されます。

   ここでは、アドレスがブロックリスト上にあったので、モバイルアプリ購読者の 1 人が除外され、プロファイルが重複していたので、他の購読者が除外されたことがわかります。

   ![](assets/push_send_5.png)

1. 「**[!UICONTROL Exclusion causes]**」タブをクリックして、除外されたメッセージの量を表示します。

   ![](assets/push_send_7.png)

1. 「**[!UICONTROL Confirm]**」をクリックして、プッシュ通知の送信を開始できるようになりました。
1. 配信のステータスは、メッセージダッシュボードとログで確認できます。詳しくは、[ メッセージの送信 ](../../sending/using/confirming-the-send.md) および [ 配信ログ ](../../sending/using/monitoring-a-delivery.md#delivery-logs) を参照してください。

   この例では、Adobe Campaignが 2 つのプッシュ通知を送信しようとしたことをメッセージダッシュボードに表示します。1 つはデバイスに正常に配信され、もう 1 つは失敗しました。 配信にエラーが発生した理由を確認するには、**[!UICONTROL Deployment]** 信ウィンドウの下部にある「![](assets/lp_link_properties.png)」ボタンをクリックします。

   ![](assets/push_send_4.png)

1. **[!UICONTROL Deployment]** ウィンドウで、「**[!UICONTROL Sending logs]**」タブをクリックして、送信済みプッシュ通知とそのステータスのリストにアクセスします。 この配信では、1 つのプッシュ通知が正常に送信されましたが、もう 1 つは無効なデバイストークンが原因で失敗しました。 その後、この購読者は今後の配信からブロックリストに追加されます。

   >[!NOTE]
   >
   >Adobe Campaignのダウンストリームでエラーが発生する可能性があります。 apn や fcm などのプロバイダーで障害が発生した場合も、その理由は同様に反映されます。 プロバイダーのエラーについて詳しくは、[Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) および [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref?hl=ja) ドキュメントを参照してください。

   ![](assets/push_send_6.png)

動的レポートを使用して、プッシュ通知配信の影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)
