---
title: プッシュ通知の準備と送信
description: Adobe Campaignで単一送信プッシュ通知を作成するには、次の手順に従います。
page-status-flag: 非活性化の
uuid: 01997725-ca0a-420c-9e81-5ea801652f87
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: ec930cd4-6365-4e54-babe-9dc2eed041fc
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# プッシュ通知の準備と送信{#preparing-and-sending-a-push-notification}

## 通知の準備 {#preparing-the-notification}

Adobe Campaignでプッシュ通知を作成する手順は次のとおりです。

1. ウィンドウから、 **[!UICONTROL Marketing activities]** 新しいマ [ーケティングアクティビティを作成します](../../start/using/marketing-activities.md#creating-a-marketing-activity)。

   単一のプッシュ通知は、キャンペーンまたはAdobe Campaignホームペ [ージ](../../start/using/marketing-activities.md#creating-a-marketing-activity) からも作成で [きます](../../start/using/interface-description.md#home-page)。

   また、プッシュ通知配信アクティビティをワークフローで使用することもできます。 このアクティビティは、「プッシュ通知 [配信](../../automating/using/push-notification-delivery.md) 」セクションに表示されます。

1. Select **[!UICONTROL Push notification]**.
1. テンプレートを選択します.

   ![](assets/push_notif_type.png)

   デフォルトでは、次の2つのテンプレートのうち1つを選択できます。

   * **[!UICONTROL Send push to Campaign profiles]**:このテンプレートを使用して、モバイルアプリケーションを購読し、プッシュ通知の受信を希望するオプトインを持つAdobe Campaign CRMプロファイルをターゲットに設定します。 受信者の名な [ど](../../designing/using/personalization.md#inserting-a-personalization-field) 、個人設定フィールドをプッシュ通知に挿入できます。
   * **[!UICONTROL Send push to app subscribers]**:このテンプレートを使用して、アプリからの通知の受信をオプトインしている既知の匿名モバイルアプリユーザーにプッシュ通知を送信します。 モバイルアプリケーションから収集したデータを使用して、これらのメッセージをパーソナライズできます。
   また、多言語テンプレートを選択することもできます。 詳しくは、多言語プッシュ通 [知の作成を参照してください](../../channels/using/creating-a-multilingual-push-notification.md)。

   テンプレートの詳細については、「テンプレートの管理」の節 [を参照してくださ](../../start/using/about-templates.md) い。

1. プッシュ通知プロパティを入力し、フィールドでモバイルアプリを選択 **[!UICONTROL Associate a Mobile App to a delivery]** します。

   ドロップダウンには、SDK V4とExperience Platform SDKの両方のアプリケーションが表示されます。

   ![](assets/push_notif_properties.png)

   プッシュ通知をキャンペーンにリンクできます。 これを行うには、既に作成済みのキャンペーンから選択します。

1. 次の画面では、オーディエンスを指定できます。例えば、特定のモバイルアプリケーションを購読しているすべてのVIP顧客を指定できます。 詳しくは、「オーディエンスの作成」を参 [照してくださ](../../audiences/using/creating-audiences.md)い。

   オーディエンスは、前の手順で選択したモバイルアプリに基づいて自動的にフィルタリングされます。

   ![](assets/push_notif_audience.png)

1. プッシュ通知をカスタマイズできるようになりました。 まず、メッセージのスタイルを選択します。ま **[!UICONTROL Alert/Message/Badge]** た **[!UICONTROL Silent push]**&#x200B;は プッシュ通知のタイプについては、プッシュ通知につ [いての節で説明します](../../channels/using/about-push-notifications.md) 。

   プッシュ通知の内容を編集し、アドバンスオプションを定義します。 See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   ここで設定したプッシュ通知コンテンツとオプションは、ペイロードの形式でモバイルアプリに渡されます。 ペイロードの詳細な構造は、「ACSプッシュ通知ペイロ [ード構造について](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) 」で説明します。

1. Click **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. 通知を送信する前に、テストプロファイルを使用して通知をテストし、配信を送信する前に受信者に表示される内容を正確に確認できます。 配信サマ **[!UICONTROL Audiences]** リから選択し、タブをクリック **[!UICONTROL Test profiles]** します。

   テストの送信について詳しくは、テストプロファイルを参 [照してください](../../sending/using/managing-test-profiles-and-sending-proofs.md)。

1. テストプロファイルを選択し、をクリック **[!UICONTROL Preview]** して通知を表示します。コンテンツは、テストプロファイルデータを使用してパーソナライズされます。
1. 別のデバイスでのプッシュ通知レイアウトの確認：レンダリングをプレビューするには、「iPhone」、「Android phone」、「iPad」または「Androidタブレット」を選択します。

   ![](assets/push_notif_preview.png)

1. は、テ **[!UICONTROL Estimated Payload Size]** ストプロファイルデータに基づく推定です。 実際のペイロードサイズは異なる場合があります。 メッセージの制限は4 KBです。

   >[!CAUTION]
   >
   >ペイロードサイズが4 KBの制限を超える場合、メッセージは配信されません。 パーソナライゼーションデータは、メッセージのサイズに影響を与えます。

## 通知の送信 {#sending-the-notification}

プッシュ通知は、オーディエンス条件を定義することで、Adobe Campaignの選択したオーディエンスに送信できます。 以下の例では、選択したオーディエンスは、4人のターゲットを定めたモバイルアプリの購読者で構成されています。

1. をクリック **[!UICONTROL Prepare]** して、ターゲットを計算し、通知を生成します。

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Note that the **[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]** one due to exclusions which can be viewed by clicking ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. タブで、送 **[!UICONTROL Exclusion logs]** 信されたターゲットから除外されたすべてのメッセージのリストと、この除外の原因を確認できます。

   ここでは、アドレスがブラックリストに記載されていたためにモバイルアプリの購読者の1人が除外され、プロファイルが重複していたために他の購読者が除外されたことがわかります。

   ![](assets/push_send_5.png)

1. タブをクリッ **[!UICONTROL Exclusion causes]** クして、除外されたメッセージの量を表示します。

   ![](assets/push_send_7.png)

1. をクリックして、プッシュ通 **[!UICONTROL Confirm]** 知の送信を開始できるようになりました。
1. メッセージダッシュボードとログで配信のステータスを確認します。 詳しくは、「メッセージおよび配信 [ログの送信](../../sending/using/confirming-the-send.md)[」を参](../../sending/using/monitoring-a-delivery.md#delivery-logs)照してください。

   この例では、メッセージダッシュボードに、Adobe Campaignが2つのプッシュ通知を送信しようとしたことが表示されます。1つはデバイスに正常に配信され、もう1つは失敗しました。 配信にエラーが発生した理由を確認するには、ウィンドウ ![](assets/lp_link_properties.png) 下部のボタンをクリック **[!UICONTROL Deployment]** します。

   ![](assets/push_send_4.png)

1. ウィンドウで **[!UICONTROL Deployment]** タブをクリックし **[!UICONTROL Sending logs]** て、送信されたプッシュ通知のリストとそのステータスにアクセスします。 この配信では、1つのプッシュ通知が正常に送信されたのに対し、もう1つのプッシュ通知は、デバイストークンが正しくないために失敗しました。 その後、この加入者は、今後の配信からブラックリストに記載されます。

   >[!NOTE]
   >
   >理由は、Adobe Campaignの下流でエラーが発生した場合にもあります。 apnsやfcmなどのプロバイダーが失敗した場合も、その理由は反映されます。 プロバイダーの障害について詳しくは、 [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) / [Androidのドキュメントを参照してください](https://firebase.google.com/docs/cloud-messaging/http-server-ref) 。

   ![](assets/push_send_6.png)

動的レポートを使用して、プッシュ通知配信の影響を測定できるようになりました。

**関連トピック：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)

