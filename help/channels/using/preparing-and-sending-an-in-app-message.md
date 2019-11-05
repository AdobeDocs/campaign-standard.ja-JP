---
title: アプリ内メッセージの準備と送信
description: アプリ内メッセージを作成して、特定のコンテンツを持つアプリの購読者をターゲットにします。
page-status-flag: 非活性化の
uuid: a79b0466-8641-46cc-a70f-e4e839587bb2
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: アプリ内メッセージ
discoiquuid: 18bf5297-a688-4302-abe4-e2fbcafdb515
context-tags: 配信，トリガー，戻る；配信の作成，ウィザード
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# アプリ内メッセージの準備と送信{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>アプリ内パーソナライゼーションは、通常、CRM IDやモバイルアプリログインIDであるリンケージフィールドに依存しています。 お客様は、Adobe Campaignとの関連で使用する場合、このリンケージフィールドを保護する責任を負います。 リンケージフィールドのセキュリティ保護を怠った場合は、パーソナライズされたメッセージが脆弱になる可能性があります。 お客様が安全なリンケージフィールドの構成、管理、および保護の慣行に従わない場合、アドビは、不正なアクセスまたはプロファイルデータの使用に起因する損害に対して責任を負いません。

Adobe Campaignでは、次の3種類のアプリ内メッセージを利用できます。

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:このメッセージタイプを使用すると、モバイルアプリケーションを登録したAdobe Campaignプロファイル（CRMプロファイル）をターゲットに設定できます。 このメッセージタイプは、Adobe Campaignで使用可能なすべてのプロファイル属性を使用してパーソナライズできますが、権限のあるユーザーのみが個人情報を含むメッセージを使用するように、Mobile SDKとCampaignのアプリ内メッセージサービス間の安全なハンドシェイクが必要です。

   このメッセージタイプをユーザーのデバイスにダウンロードするには、モバイルSDKは、モバイルプロファイルをAdobe CampaignのCRMプロファイルに接続するために使用するリンケージフィールドを送信する必要があります。 アプリ内をサポートするために必要なSDK APIについて詳しくは、このページを参照してく [ださい](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference)。

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:このメッセージタイプを使用すると、Adobe Campaignに既存のプロファイルがない場合でも、モバイルアプリケーションのすべてのユーザー（現在または将来）にメッセージを送信できます。 したがって、ユーザープロファイルがAdobe Campaignに存在しない場合でも、メッセージをカスタマイズする場合は、パーソナライゼーションを実行できません。
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**:このメッセージタイプを使用すると、Adobe Campaignでモバイルプロファイルを持つモバイルアプリの既知または匿名のすべてのユーザーをターゲットに設定できます。 このメッセージタイプは、個人属性と非機密属性のみを使用してパーソナライズでき、Mobile SDKとAdobe Campaignのアプリ内メッセージサービス間の安全なハンドシェイクは必要ありません。

   個人データと機密データの処理方法について詳しくは、「モバイルプロファイルフィールドの個人デ [ータと機密データの処理」を参照してください](#handling-mobile-profile-fields-with-personal-and-sensitive-data)。

![](assets/diagram_inapp.png)

## 個人データおよび機密データを使用したモバイルプロファイルフィールドの処理 {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

モバイルデバイスからAdobe Campaignに送信するデータを収集するには、このリソースを拡張する必要があります。 そのためには、詳細な手順につ [いては](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) 、このページを参照してください。

アプリ内メッセージのパーソナライズ機能をより安全に有効にするには、このリソースのモバイルプロファイルフィールドを適宜設定する必要があります。In your **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, when creating your new mobile profiles fields, check **[!UICONTROL Personal and Sensitive]** to make them unavailable during In-App messages personalization.

>[!NOTE]
>
>この表に、カスタムリソース拡張機能を持つ既存の実装がある場合は、アプリ内メッセージのパーソナライゼーションに利用する前に、フィールドに適切なラベルを付けることをお勧めします。

![](assets/in_app_personal_data_2.png)

Once your **[!UICONTROL Subscriptions to an application]** custom resource is configured and published, you can start preparing your In-App delivery using the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template. Only non-personal and non-sensitive fields will be available from **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource for personalization.

If you require personalization with **Personal and Sensitive** fields, we recommend using the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template which has additional security mechanism to ensure that your users' PII data remains secure.

## アプリ内メッセージの準備 {#preparing-your-in-app-message}

Adobe Campaignでスタンドアロンのアプリ内メッセージを作成する手順は次のとおりです。

1. Adobe Campaignのホームページで、カードをクリック **[!UICONTROL In-App messaging]** します。

   「マーケティングアクティビティ」タブで、ボタンをクリックし **て** 、アプリ内を作成することもで **[!UICONTROL Create]** きます。

   アプリ内メッセージは、キャンペーン、Adobe Campaignホームページ、またはワークフローからも作成できます。

1. 「アプリ **内メッセージ」を選択します**。

   ![](assets/inapp_creating.png)

1. オーディエンスのターゲット設定のニーズに基づいて、適切なテンプレートを選択します。

   ![](assets/inapp_creating_2.png)

   デフォルトでは、次の3つのあらかじめ用意されているテンプレートのいずれかを選択できます。

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. アプリ内メッセージのプロパティを入力し、フィールドでモバイルアプリを選択 **[!UICONTROL Associate a Mobile App to a delivery]** します。

   ![](assets/inapp_creating_3.png)

1. アプリ内メッセージのターゲットにするオーディエンスを選択します。 オーディエンスは、この配信に関連付けられているモバイルアプリに応じて事前にフィルタリングされます。

   この手順は、モバイルアプリケーションのすべてのユーザーを対象 **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** とするので、と共には必要ありません。

   ![](assets/inapp_creating_8.png)

1. タブで、メ **[!UICONTROL Triggers]** ッセージをトリガーするイベントをドラッグ&amp;ドロップします。 トリガーを選択すると、アプリ内メッセージを表示するユーザーによって行われるアクションを選択できます。

   次の4つのカテゴリのイベントを使用できます。

   * **[!UICONTROL Mobile Application events]**:モバイルアプリケーションに実装されるカスタムイベント。

      イベントの作成について詳しくは、このページを参照して [ください](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)。

   * **[!UICONTROL Life Cycle events]**:Adobe Mobile SDKでサポートされる、そのまま使用できるライフサイクルイベントです。

      ライフサイクルイベントの詳細については、このページを参照して [くださ](https://marketing.adobe.com/resources/help/en_US/mobile/android/metrics.html)い。

   * **[!UICONTROL Analytics Events]**:モバイルアプリに実装されているものに応じて、次の3つのカテゴリがサポートされます。Adobe Analytics、コンテキストデータまたはビュー状態。

      これらのイベントは、Adobe Analyticsライセンスをお持ちの場合にのみ使用できます。

   * **[!UICONTROL Places]**:次の3つのカテゴリは、リアルタイムの場所データを利用して、文脈に関連するモバイルエクスペリエンスを配信します。コンテキストデータを配置し、カスタムメタデータまたは場所イベントタイプを配置します。

      Adobe Placesについて詳しくは、Placesのドキュメントを参照し [てください](https://placesdocs.com/)。
   ![](assets/inapp_creating_4.png)

1. コンテキストデータイベ **[!UICONTROL Analytics Events]**&#x200B;ントを手動で追加する必要があるのに対して、Adobe Analyticsおよびビュー状態イベントを使用する場合は、Adobe Experience Platform LaunchのAnalytics拡張で設定されたレポートスイートに基づいて自動的に設定されます。

   これらのイベントは、Adobe Analyticsライセンスをお持ちの場合にのみ使用できます。

   ![](assets/inapp_creating_7.png)

1. トリガーを使用する場合、「配置」コ **[!UICONTROL Places]** ンテキストデータ、「配置」カスタムメタデータまたは「配置」イベントタイプは、Adobe Placesで作成されたすべてのライブラリと目標地点に基づいて自動的に設定されます。

   このトリガーは、エクスペリエンスプラットフォームの起動の場所拡張で選択したライブラリからの目標地点に対してのみ、デバイスに適用されます。 Places拡張機能とそのインストール方法の詳細については、このドキュメントを参照してく [ださい](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/places-extension-1/places-extension)。

1. タブで **[!UICONTROL Frequency & duration]** 、トリガーの頻度、開始日と終了日、アプリ内メッセージがアクティブになる曜日と時間を選択します。

   ![](assets/inapp_creating_5.png)

1. メッセージの内容を編集し、アドバンスオプションを定義します。 See [Customizing an In-App message](https://helpx.adobe.com/campaign/standard/channels/using/customizing-a-push-notification.html).

   ![](assets/inapp_creating_6.png)

1. Click **[!UICONTROL Create]**.

これで、ターゲットのオーディエンスにアプリ内メッセージを送信する準備が整いました。

**関連トピック：**

* [アプリ内メッセージのカスタマイズ](../../channels/using/customizing-an-in-app-message.md)
* [アプリ内レポート](../../reporting/using/in-app-report.md)
* [ワークフロー内でのアプリ内メッセージの送信](../../automating/using/in-app-delivery.md)

## アプリ内メッセージの送信 {#sending-your-in-app-message}

配信の準備が完了し、承認手順が完了したら、メッセージを送信できます。

1. をクリック **[!UICONTROL Prepare]** して、ターゲットを計算し、メッセージを生成します。

   ![](assets/inapp_sending_4.png)

1. 準備が完了したら、**Deployment** ウィンドウが表示され、**Target** および **To deliver** の KPI を示します。

   配信ウィンドウを確認するには、配信で発生する可能性のある除外 ![](assets/lp_link_properties.png) やエラーのボタンをクリックします。

   ![](assets/inapp_sending_5.png)

1. をクリック **[!UICONTROL Confirm]** して、アプリ内メッセージの送信を開始します。

   ![](assets/inapp_sending_6.png)

1. メッセージダッシュボードとログで配信のステータスを確認します。 詳しくは、[この節](../../sending/using/monitoring-a-delivery.md)を参照してください。

   **[!UICONTROL Delivered]** および **[!UICONTROL Sent]** KPIの数は、キャンペーンからメッセージ配信サービスに正常に送信されたものに基づきます。 これらのKPIは、メッセージ配信サービスからメッセージを正常に受信またはダウンロードしたモバイルデバイスの数を示すものではありません。

   ![](assets/inapp_sending_7.png)

1. 配信レポートを使用して、アプリ内メッセージの影響を測定します。 For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

**関連トピック：**

* [アプリ内レポート](../../reporting/using/in-app-report.md)
* [ワークフロー内でのアプリ内メッセージの送信](../../automating/using/in-app-delivery.md)

