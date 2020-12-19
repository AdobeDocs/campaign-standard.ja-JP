---
solution: Campaign Standard
product: campaign
title: プッシュ通知の作成と送信
description: Adobe Campaignで単一送信プッシュ通知を作成するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 4%

---


# プッシュ通知の準備と送信{#preparing-and-sending-a-push-notification}

## 通知を準備中{#preparing-the-notification}

Adobe Campaignを使用してプッシュ通知を作成する手順は、次のとおりです。

1. **[!UICONTROL Marketing activities]**&#x200B;ウィンドウで、[新しいマーケティングアクティビティ](../../start/using/marketing-activities.md#creating-a-marketing-activity)を作成します。

   1つのプッシュ通知は、[キャンペーン](../../start/using/marketing-activities.md#creating-a-marketing-activity)またはAdobe Campaign[ホームページ](../../start/using/interface-description.md#home-page)からも作成できます。

   また、プッシュ通知配信アクティビティをワークフローで使用することもできます。 このアクティビティは、[プッシュ通知配信](../../automating/using/push-notification-delivery.md)セクションに表示されます。

1. 「**[!UICONTROL Push notification]**」を選択します。
1. テンプレートを選択します.

   ![](assets/push_notif_type.png)

   デフォルトでは、次の2つのテンプレートのいずれかを選択できます。

   * **[!UICONTROL Send push to Campaign profiles]**:このテンプレートを使用して、モバイルアプリケーションを購読し、プッシュ通知の受信を希望するAdobe CampaignCRMプロファイルをターゲットします。プッシュ通知には、受信者の名など、[パーソナライゼーション](../../designing/using/personalization.md#inserting-a-personalization-field)フィールドを挿入できます。
   * **[!UICONTROL Send push to app subscribers]**:このテンプレートを使用して、アプリケーションからの通知の受信をオプトインしている、既知で匿名のモバイルアプリケーションユーザー全員にプッシュ通知を送信します。モバイルアプリケーションから収集したデータを使用して、これらのメッセージをパーソナライズできます。

   また、多言語テンプレートを選択することもできます。 詳しくは、「[多言語プッシュ通知の作成](../../channels/using/creating-a-multilingual-push-notification.md)」を参照してください。

   テンプレートの詳細については、「[テンプレートの管理](../../start/using/marketing-activity-templates.md)」の節を参照してください。

1. プッシュ通知プロパティを入力し、**[!UICONTROL Associate a Mobile App to a delivery]**&#x200B;フィールドでモバイルアプリを選択します。

   ドロップダウンには、SDK V4とExperience PlatformSDKの両方のアプリケーションが表示されます。

   ![](assets/push_notif_properties.png)

   プッシュ通知をキャンペーンにリンクできます。 これを行うには、既に作成されているキャンペーンから選択します。

1. 次の画面では、オーディエンスを指定できます。例えば、特定のモバイルアプリケーションを購読しているVIPのすべての顧客を指定できます。 詳しくは、[オーディエンスの作成](../../audiences/using/creating-audiences.md)を参照してください。

   オーディエンスは、前の手順で選択したモバイルアプリに基づいて自動的にフィルタリングされます。

   ![](assets/push_notif_audience.png)

1. プッシュ通知をカスタマイズできるようになりました。 最初に、メッセージのスタイルを選択します。**[!UICONTROL Alert/Message/Badge]**&#x200B;または&#x200B;**[!UICONTROL Silent push]**。 プッシュ通知のタイプについては、[プッシュ通知について](../../channels/using/about-push-notifications.md)の節で説明します。

   プッシュ通知の内容を編集し、高度なオプションを定義します。 「[プッシュ通知のカスタマイズ](../../channels/using/customizing-a-push-notification.md)」を参照してください。

   ![](assets/push_notif_content.png)

   ここで設定するプッシュ通知コンテンツとオプションは、ペイロードの形式でモバイルアプリに渡されます。 ペイロードの詳細な構造は、[ACSプッシュ通知ペイロード構造について](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/push-notifications/push-payload.translate.html)テクノテートで説明しています。

1. 「**[!UICONTROL Create]**」をクリックします。

   ![](assets/push_notif_content_2.png)

1. 通知を送信する前に、テストプロファイルを使用してテストを実行し、配信を送信する前に受信者に表示される内容を正確に確認できます。 配信の概要から&#x200B;**[!UICONTROL Audiences]**&#x200B;を選択し、「**[!UICONTROL Test profiles]**」タブをクリックします。

   テストの送信について詳しくは、[テストプロファイル](../../sending/using/sending-proofs.md)を参照してください。

1. テストプロファイルを選択し、**[!UICONTROL Preview]**&#x200B;をクリックして通知を表示します。コンテンツは、テストプロファイルデータを使用してパーソナライズされます。
1. 別のデバイスでのプッシュ通知レイアウトの確認：「iPhone」、「Android phone」、「iPad」または「Androidタブレットでプレビューレンダリング」を選択します。

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]**&#x200B;は、テストプロファイルデータに基づく予測です。 実際のペイロードサイズは異なる場合があります。 メッセージの制限は4 KBです。

   >[!CAUTION]
   >
   >ペイロードのサイズが4 KBの制限を超える場合、メッセージは配信されません。

パーソナライゼーションデータは、メッセージのサイズに影響します。

## 通知を送信{#sending-the-notification}

オーディエンス条件を定義すると、Adobe Campaign内の選択したオーディエンスにプッシュ通知を送信できます。 以下の例では、選択したオーディエンスは4人のターゲットモバイルアプリの購読者で構成されています。

1. **[!UICONTROL Prepare]**&#x200B;をクリックしてターゲットを計算し、通知を生成します。

   ![](assets/push_send_1.png)

1. 準備が正常に完了すると、**[!UICONTROL Deployment]**&#x200B;ウィンドウに次のKPIが表示されます。**[!UICONTROL Target]**&#x200B;と&#x200B;**[!UICONTROL To deliver]**。 **[!UICONTROL Deployment]**&#x200B;ウィンドウの下部にある![](assets/lp_link_properties.png)ボタンをクリックすると表示できる除外があるので、**[!UICONTROL To deliver]**&#x200B;の数が&#x200B;**[!UICONTROL Targeted]**&#x200B;より少ないことに注意してください。

   ![](assets/push_send_2.png)

1. **[!UICONTROL Exclusion logs]**&#x200B;タブには、送信されたターゲットから除外されたすべてのメッセージのリストと、この除外の原因が表示されます。

   ここでは、アドレスがプロファイルにあったためにモバイルアプリのサブスクライバーの1人が除外されブロックリスト、他のサブスクライバーが重複にあったために除外されたことがわかります。

   ![](assets/push_send_5.png)

1. 「**[!UICONTROL Exclusion causes]**」タブをクリックして、除外されたメッセージの量を表示します。

   ![](assets/push_send_7.png)

1. **[!UICONTROL Confirm]**&#x200B;をクリックして、プッシュ通知を送信する開始を設定できるようになりました。
1. 配信のステータスは、メッセージダッシュボードとログで確認できます。詳しくは、[メッセージの送信](../../sending/using/confirming-the-send.md)と[配信ログ](../../sending/using/monitoring-a-delivery.md#delivery-logs)を参照してください。

   この例では、メッセージダッシュボードに、Adobe Campaignが2つのプッシュ通知を送信しようとしたことが表示されます。1つはデバイスに正常に配信され、もう1つは失敗しました。 配信にエラーがある理由を知るには、**[!UICONTROL Deployment]**&#x200B;ウィンドウの下部にある![](assets/lp_link_properties.png)ボタンをクリックします。

   ![](assets/push_send_4.png)

1. **[!UICONTROL Deployment]**&#x200B;ウィンドウで「**[!UICONTROL Sending logs]**」タブをクリックし、送信されたプッシュ通知のリストとそのステータスにアクセスします。 この配信では、1つのプッシュ通知が正常に送信されたのに対し、もう1つのプッシュ通知は、デバイストークンの不良が原因で失敗しました。 その後、このサブスクライバは、さらに別の配信からブロックリストに追加されます。

   >[!NOTE]
   >
   >Adobe Campaignの下流で障害が発生した場合、その理由が考えられます。 apnsやfcmなどのプロバイダーがエラーを発生させた場合も、その理由には反映されます。 プロバイダーでのエラーについて詳しくは、[Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html)および[Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref)のドキュメントを参照してください。

   ![](assets/push_send_6.png)

動的レポートを使用して、プッシュ通知配信の影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)
