---
title: プッシュ通知の作成と送信
description: Adobe Campaignで1回送信プッシュ通知を作成するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
TQID: https://experienceleague.adobe.com/gTGkg0NPjtcDsY5RcaVwHklBVZ-dpLAe5qM9fcS9Bj4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 858
ht-degree: 4%

---

# プッシュ通知の準備と送信{#preparing-and-sending-a-push-notification}

## 通知の準備 {#preparing-the-notification}

Adobe Campaignでプッシュ通知を作成する手順は次のとおりです。

1. **[!UICONTROL Marketing activities]** ウィンドウから、[新しいマーケティング アクティビティを作成](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   1回のプッシュ通知は、[campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity)またはAdobe Campaign [ ホームページ ](../../start/using/interface-description.md#home-page)から作成することもできます。

   ワークフローでプッシュ通知配信アクティビティを使用することもできます。 このアクティビティは、[ プッシュ通知配信](../../automating/using/push-notification-delivery.md) セクションに表示されます。

1. 「**[!UICONTROL Push notification]**」を選択します。
1. テンプレートを選択します。

   ![](assets/push_notif_type.png)

   デフォルトでは、次の2つのテンプレートのいずれかを選択できます。

   * **[!UICONTROL Send push to Campaign profiles]**：このテンプレートを使用して、モバイルアプリケーションを購読し、プッシュ通知の受信をオプトインしているAdobe Campaign CRM プロファイルをターゲットにします。 受信者の名前など、[ パーソナライゼーション ](../../designing/using/personalization.md#inserting-a-personalization-field)のフィールドをプッシュ通知に挿入できます。
   * **[!UICONTROL Send push to app subscribers]**：このテンプレートを使用して、アプリケーションからの通知の受信をオプトインしたすべての既知および匿名のモバイルアプリケーションユーザーにプッシュ通知を送信します。 モバイルアプリケーションから収集したデータを使用して、これらのメッセージをパーソナライズできます。

   多言語テンプレートを選択することもできます。 詳しくは、[多言語プッシュ通知の作成](../../channels/using/creating-a-multilingual-push-notification.md)を参照してください。

   テンプレートについて詳しくは、「[ テンプレートの管理](../../start/using/marketing-activity-templates.md)」の節を参照してください。

1. プッシュ通知のプロパティを入力し、**[!UICONTROL Associate a Mobile App to a delivery]** フィールドでモバイルアプリを選択します。

   ドロップダウンには、SDK V4とExperience Platform SDKの両方のアプリケーションが表示されます。

   ![](assets/push_notif_properties.png)

   プッシュ通知をキャンペーンにリンクできます。 これを行うには、作成済みのキャンペーンから選択します。

1. 次の画面では、オーディエンスを指定できます。例えば、特定のモバイルアプリケーションを購読しているすべてのVIPのお客様を指定できます。 詳しくは、「[ オーディエンスの作成](../../audiences/using/creating-audiences.md)」を参照してください。

   前の手順で選択したモバイルアプリケーションに基づいて、オーディエンスが自動的にフィルタリングされます。

   ![](assets/push_notif_audience.png)

1. プッシュ通知をカスタマイズできるようになりました。 まず、メッセージスタイルを選択します：**[!UICONTROL Alert/Message/Badge]**&#x200B;または&#x200B;**[!UICONTROL Silent push]**。 プッシュ通知の種類については、[ プッシュ通知について](../../channels/using/about-push-notifications.md) セクションで説明します。

   プッシュ通知のコンテンツを編集し、詳細オプションを定義します。 [ プッシュ通知のカスタマイズ ](../../channels/using/customizing-a-push-notification.md)を参照してください。

   ![](assets/push_notif_content.png)

   ここで設定したプッシュ通知のコンテンツとオプションは、ペイロードの形式でモバイルアプリに渡されます。 ペイロードの詳細な構造については、[Campaign Standard プッシュ通知ペイロード構造の概要](../../administration/using/push-payload.md)のテクニカルノートを参照してください。

1. 「**[!UICONTROL Create]**」をクリックします。

   ![](assets/push_notif_content_2.png)

1. 通知を送信する前に、テストプロファイルでテストし、配信を送信する前に受信者に表示される内容を正確に確認できます。 配信の概要から「**[!UICONTROL Audiences]**」を選択し、「**[!UICONTROL Test profiles]**」タブをクリックします。

   テストの送信について詳しくは、[ テストプロファイル ](../../sending/using/sending-proofs.md)を参照してください。

1. テストプロファイルを選択し、**[!UICONTROL Preview]**&#x200B;をクリックして通知を表示します。コンテンツはテストプロファイルデータでパーソナライズされます。
1. 様々なデバイスでプッシュ通知のレイアウトを確認する：iPhone、Android phone、iPadまたはAndroid タブレットを選択してレンダリングをプレビューします。

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]**&#x200B;は、テストプロファイルデータに基づく推定値です。 実際のペイロードのサイズは異なる場合があります。 メッセージの上限は4 KBです。

   >[!CAUTION]
   >
   >ペイロードサイズが4 KBの制限を超えると、メッセージは配信されません。

パーソナライゼーションデータは、メッセージのサイズに影響します。

## 通知の送信 {#sending-the-notification}

プッシュ通知は、オーディエンス条件を定義することで、Adobe Campaignで選択したオーディエンスに送信できます。 次の例では、選択したオーディエンスは4人のターゲットモバイルアプリ加入者で構成されています。

1. 「**[!UICONTROL Prepare]**」をクリックしてターゲットを計算し、通知を生成します。

   ![](assets/push_send_1.png)

1. 準備が正常に完了すると、**[!UICONTROL Deployment]** ウィンドウに次のKPIが表示されます：**[!UICONTROL Target]**&#x200B;と&#x200B;**[!UICONTROL To deliver]**。 **[!UICONTROL Deployment]** ウィンドウの下部にある「![](assets/lp_link_properties.png)」ボタンをクリックして表示できる除外事項のため、**[!UICONTROL To deliver]**&#x200B;数が&#x200B;**[!UICONTROL Targeted]**&#x200B;数よりも少ないことに注意してください。

   ![](assets/push_send_2.png)

1. 「**[!UICONTROL Exclusion logs]**」タブには、送信されたターゲットから除外されたすべてのメッセージのリストと、この除外の背後にある理由が表示されます。

   ここでは、プロファイルが重複していたため、メールアドレスがoCブロックリストにあったため、モバイルアプリのサブスクライバーの1人が除外されたことがわかります。

   ![](assets/push_send_5.png)

1. 「**[!UICONTROL Exclusion causes]**」タブをクリックして、除外されたメッセージの量を表示します。

   ![](assets/push_send_7.png)

1. **[!UICONTROL Confirm]**&#x200B;をクリックして、プッシュ通知の送信を開始できるようになりました。
1. 配信のステータスは、メッセージダッシュボードとログで確認できます。 詳しくは、[ メッセージの送信](../../sending/using/confirming-the-send.md)および[配信ログ ](../../sending/using/monitoring-a-delivery.md#delivery-logs)を参照してください。

   この例では、メッセージダッシュボードに、Adobe Campaignが2つのプッシュ通知を送信しようとしたことを表示します。1つはデバイスに正常に配信され、もう1つは失敗しました。 配信にエラーがある理由を確認するには、**[!UICONTROL Deployment]** ウィンドウの下部にある![](assets/lp_link_properties.png) ボタンをクリックします。

   ![](assets/push_send_4.png)

1. **[!UICONTROL Deployment]** ウィンドウで「**[!UICONTROL Sending logs]**」タブをクリックして、送信されたプッシュ通知のリストとそのステータスにアクセスします。 この配信では、1つのプッシュ通知が正常に送信されましたが、もう1つは不正なデバイストークンが原因で失敗しました。 その後、この購読者は、追加の配信からメールブロックリストに追加されます。

   >[!NOTE]
   >
   >Adobe Campaignのダウンストリームでエラーが発生する場合があります。 apnsやfcmなどのプロバイダーから障害が発生した場合、その理由も反映されます。 プロバイダーのエラーについて詳しくは、[Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html)および[Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref?hl=ja)のドキュメントを参照してください。

   ![](assets/push_send_6.png)

動的レポートを使用して、プッシュ通知配信の影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)
