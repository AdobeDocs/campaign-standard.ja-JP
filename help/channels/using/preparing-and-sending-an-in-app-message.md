---
title: アプリ内メッセージの準備と送信
description: アプリ内メッセージを作成して、特定のコンテンツを持つアプリの購読者をターゲットします。
page-status-flag: never-activated
uuid: a79b0466-8641-46cc-a70f-e4e839587bb2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: 18bf5297-a688-4302-abe4-e2fbcafdb515
context-tags: delivery,triggers,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 5%

---


# アプリ内メッセージの準備と送信{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>アプリ内パーソナライゼーションは、通常、CRM IDやモバイルアプリログインIDのリンケージフィールドに依存します。 Adobe Campaignに関連して使用する場合は、このリンケージフィールドを保護する責任を負います。 リンケージフィールドを安全に保たないと、パーソナライズされたメッセージが脆弱になる可能性があります。 お客様が安全なリンケージフィールドの構成、管理、および保護の慣行に従わない場合、不正なアクセスまたはプロファイルデータの使用に起因する損害に対して、アドビは責任を負いません。

Adobe Campaignでは、次の3種類のアプリ内メッセージを使用できます。

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: このメッセージタイプを使用すると、モバイルアプリケーションを購読しているターゲットAdobe Campaignプロファイル(CRMプロファイル)を使用できます。 このメッセージタイプは、Adobe Campaignで使用可能なすべてのプロファイル属性を使用してパーソナライズできますが、個人情報と機密情報を含むメッセージが権限のあるユーザーのみに使用されるように、モバイルSDKとキャンペーンのアプリ内メッセージサービスとの間で安全なハンドシェイクが必要です。

   このメッセージタイプをユーザーのデバイスにダウンロードするには、モバイルSDKは、モバイルプロファイルをAdobe CampaignのCRMプロファイルに接続するために使用するリンケージフィールドを送信する必要があります。 アプリ内をサポートするために必要なSDK APIについて詳しくは、この [ページを参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference)。

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: このメッセージタイプを使用すると、Adobe Campaignに既存のプロファイルがない場合でも、モバイルアプリのすべてのユーザー（現在または将来）にメッセージを送信できます。 したがって、Adobe Campaignにユーザプロファイルが存在しない場合でも、メッセージをカスタマイズする場合は、パーソナライゼーションは不可能です。
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**: このメッセージタイプを使用すると、モバイルプロファイルをAdobe Campaignに持つモバイルアプリの既知ユーザーまたは匿名ユーザー全員をターゲットできます。 このメッセージタイプは、個人属性と機密属性のみを使用してパーソナライズでき、モバイルSDKとAdobe Campaignのアプリ内メッセージサービス間の安全なハンドシェイクは必要ありません。

   個人データと機密データの処理方法の詳細については、「モバイルプロファイルフィールドの個人データと機密データの [処理](#handling-mobile-profile-fields-with-personal-and-sensitive-data)」を参照してください。

![](assets/diagram_inapp.png)

## 個人データおよび機密データを使用したモバイルプロファイルフィールドの処理 {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

モバイルデバイスからAdobe Campaignに送信するデータを収集するには、このリソースを拡張する必要があります。 これを行うには、この [ページで詳細な手順を参照してください](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) 。

アプリ内メッセージのパーソナライズ機能をより安全に有効にするには、このリソースのモバイルプロファイルフィールドを適宜設定する必要があります。In your **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, when creating your new mobile profiles fields, check **[!UICONTROL Personal and Sensitive]** to make them unavailable during In-App messages personalization.

>[!NOTE]
>
>この表に、カスタムリソース拡張機能を持つ既存の実装がある場合、アプリ内メッセージのパーソナライズ用にフィールドを活用する前に、フィールドに適切なラベルを付けることをお勧めします。

![](assets/in_app_personal_data_2.png)

Once your **[!UICONTROL Subscriptions to an application]** custom resource is configured and published, you can start preparing your In-App delivery using the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template. Only non-personal and non-sensitive fields will be available from **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource for personalization.

If you require personalization with **Personal and Sensitive** fields, we recommend using the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template which has additional security mechanism to ensure that your users&#39; PII data remains secure.

## アプリ内メッセージの準備 {#preparing-your-in-app-message}

Adobe Campaignを含むスタンドアロンのアプリ内メッセージを作成する手順は、次のとおりです。

1. Adobe Campaignホームページで、カードをクリックし **[!UICONTROL In-App messaging]** ます。

   ボタンをクリックして、「 **マーケティングアクティビティ** 」タブからアプリ内を作成することもでき **[!UICONTROL Create]** ます。

   アプリ内メッセージは、キャンペーン、Adobe Campaignホームページ、またはワークフローからも作成できます。

1. 「 **アプリ内メッセージ**」を選択します。

   ![](assets/inapp_creating.png)

1. オーディエンスのターゲット設定に関するニーズに応じて、適切なテンプレートを選択します。

   ![](assets/inapp_creating_2.png)

   デフォルトでは、次の3つのあらかじめ用意されているテンプレートのいずれかを選択できます。

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. アプリ内メッセージのプロパティを入力し、フィールドでモバイルアプリを選択し **[!UICONTROL Associate a Mobile App to a delivery]** ます。 モバイルアプリをAdobe Campaign Standardと共に設定しなかった場合、モバイルアプリはリストに表示されないことに注意してください。 For more information on mobile application configuration, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/inapp_creating_3.png)

1. アプリ内メッセージのターゲット対象オーディエンスを選択します。 オーディエンスは、この配信に関連付けられているモバイルアプリケーションに応じて、事前にフィルタリングされます。

   この手順は、モバイルアプリケーションのすべてのユーザーをターゲットするので、と一緒に行う必要はありま **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** せん。

   ![](assets/inapp_creating_8.png)

1. タブで、メッセージをトリガーするイベントをドラッグ&amp;ドロップし **[!UICONTROL Triggers]** ます。 トリガーを選択すると、アプリ内メッセージが表示される原因となるユーザーが行うアクションを選択できます。

   次の4つのカテゴリのイベントを使用できます。

   * **[!UICONTROL Mobile Application events]**: モバイルアプリケーションに実装されるカスタムイベント。

      For more on events creations, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

   * **[!UICONTROL Life Cycle events]**: Adobe Mobile SDKでサポートされ、すぐに使用できるライフサイクルイベントです。

      ライフサイクルイベントの詳細については、この [ページを参照してください](https://docs.adobe.com/content/help/en/mobile-services/android/metrics.html)。

   * **[!UICONTROL Analytics Events]**: モバイルアプリで実装されるカテゴリに応じて、以下の3つの実装がサポートされます。 アドビAnalytics、コンテキストデータまたは表示状態。

      これらのイベントは、アドビAnalyticsのライセンスをお持ちの場合にのみ利用できます。

   * **[!UICONTROL Places]**: 次の3つのカテゴリは、リアルタイムの場所データを利用して、文脈上関連のあるモバイルエクスペリエンスを配信します。 コンテキストデータを配置、カスタムメタデータを配置、または配置イベントタイプを配置します。

      Adobe Placesの詳細については、Placesのドキュメントを参照して [ください](https://placesdocs.com/)。
   ![](assets/inapp_creating_4.png)

1. コンテキストデータイベントを手動で追加する必要があるのに対し、Adobe Experience Platformの起動でAnalyticsの拡張機能に設定されたレポートスイートに基づいて、アドビのAnalytics州と表示州のイベントが自動的に設定されます。 **[!UICONTROL Analytics Events]**

   これらのイベントは、アドビAnalyticsのライセンスをお持ちの場合にのみ利用できます。

   ![](assets/inapp_creating_7.png)

1. トリガーを使用する場合、「配置」コンテキストデータ、「配置」カスタムメタデータまたは「配置」イベントタイプは、Adobe Placesで作成されたすべてのライブラリと目標地点に基づいて自動的に設定されます。 **[!UICONTROL Places]**

   このトリガは、Experience Platform Launchの場所拡張で選択したライブラリの目標地点に対してのみ、デバイスに適用されることに注意してください。 Places拡張機能とそのインストール方法の詳細については、この [ドキュメントを参照してください](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html)。

1. タブで、トリガーの頻度、開始日、終了日、曜日、アプリ内メッセージをアクティブにする時間を選択し **[!UICONTROL Frequency & duration]** ます。

   ![](assets/inapp_creating_5.png)

1. メッセージの内容を編集し、アドバンスオプションを定義します。 See [Customizing an In-App message](https://helpx.adobe.com/campaign/standard/channels/using/customizing-a-push-notification.html).

   ![](assets/inapp_creating_6.png)

1. クリック **[!UICONTROL Create]** .

これで、アプリ内メッセージをターゲットオーディエンスに送信する準備が整いました。

**関連トピック：**

* [アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)
* [アプリ内レポート](../../reporting/using/in-app-report.md)
* [ワークフロー内でのアプリ内メッセージの送信](../../automating/using/in-app-delivery.md)

## アプリ内メッセージの送信 {#sending-your-in-app-message}

配信の準備が完了し、承認手順が完了したら、メッセージを送信できます。

1. をクリック **[!UICONTROL Prepare]** してターゲットを計算し、メッセージを生成します。

   ![](assets/inapp_sending_4.png)

1. 準備が完了したら、**Deployment** ウィンドウに **Target** および **To deliver** の KPI が表示されます。

   配信内の潜在的な除外やエラーの ![](assets/lp_link_properties.png) ボタンをクリックして、デプロイメントウィンドウを確認できます。

   ![](assets/inapp_sending_5.png)

1. アプリ内メッセージ **[!UICONTROL Confirm]** の送信開始をクリックします。

   ![](assets/inapp_sending_6.png)

1. メッセージダッシュボードとログで配信のステータスを確認します。 詳しくは、[この節](../../sending/using/monitoring-a-delivery.md)を参照してください。

   **[!UICONTROL Delivered]** および **[!UICONTROL Sent]** KPIの数は、キャンペーンからメッセージ配信サービスに正常に送信されたものに基づきます。 これらのKPIは、メッセージ配信サービスからメッセージを正常に受信またはダウンロードしたモバイルデバイスの数を示すものではありません。

   ![](assets/inapp_sending_7.png)

1. 配信レポートを使用して、アプリ内メッセージの影響を測定します。 For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

**関連トピック：**

* [アプリ内レポート](../../reporting/using/in-app-report.md)
* [ワークフロー内でのアプリ内メッセージの送信](../../automating/using/in-app-delivery.md)

