---
title: アプリ内配信
seo-title: アプリ内配信
description: アプリ内配信
seo-description: アプリ内配信アクティビティを使用すると、ワークフロー内でアプリ内メッセージを送信できます。
page-status-flag: 常にアクティブ化されていない
uuid: 528d9472- e447-47af- a6b2-3181aa5fb5ad
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: チャネルアクティビティ
discoiquuid: 19796aca-6e9e-4d3a-8917- ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# In-App delivery{#in-app-delivery}

## 説明 {#description}

![](assets/wkf_in_app_1.png)

**アプリ内配信** アクティビティを使用すると、ワークフロー内でアプリ内メッセージを送信できます。アプリ内メッセージを使用すると、ユーザーがアプリ内でアクティブになったときにメッセージを表示できます。For more information concerning the In-App delivery, refer to this [section](../../channels/using/about-in-app-messaging.md).

## Context of use {#context-of-use}

**[!UICONTROL In-App delivery]** このアクティビティは、一般に、同じワークフローでターゲットオーディエンスにアプリ内メッセージを送信するための自動化に使用されます。

クエリ、交差などのターゲットアクティビティを介して、同じワークフロー内のアクティビティのアップストリームが定義されます。

メッセージの実行パラメーターに従ってメッセージの準備がトリガーされます。メッセージダッシュボードから、メッセージを送信するかどうかを手動で確認できます（デフォルトで必須）。ワークフローを手動で開始することも、ワークフローにスケジューラーアクティビティを配置して実行を自動化することもできます。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. Please note that the **[!UICONTROL Query]** activity targeting dimension in the **[!UICONTROL Properties]** tab needs to be updated according to the template chosen in Step 4:

   * Targeting dimension should be set to **[!UICONTROL mobileApp (mobileAppV5)]** for the **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** template.
   * Targeting dimension should be set to **[!UICONTROL profile (profile)]** for the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template.
   * Targeting dimension should be set to **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** for the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template.

1. Drag and drop a **[!UICONTROL In-App delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions.

   ![](assets/wkf_in_app_3.png)

1. アプリ内メッセージタイプを選択します。This will depend on the data targeted in your **[!UICONTROL Query]** activity.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:このメッセージタイプを使用すると、モバイルアプリケーションをサブスクライブしているAdobe Campaignプロファイルをターゲットにしたり、キャンペーンで利用可能なプロファイル属性を使用してアプリ内メッセージをパーソナライズしたりできます。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:このメッセージタイプを使用すると、キャンペーンに既存のプロファイルがない場合でも、モバイルアプリケーションのすべてのユーザーにメッセージを送信できます。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:このメッセージタイプを使用すると、既知または不明かどうかにかかわらず、モバイルデバイスから取得されたプロファイル属性を使用してアプリ内メッセージをカスタマイズするモバイルアプリのすべてのユーザーをターゲット設定できます。
   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. **[!UICONTROL Triggers]** タブで、メッセージをトリガーするイベントをドラッグ&amp;ドロップします。次の3つのイベントを使用できます。
1. アプリ内コンテンツを定義します。Refer to the section concerning [In-App customization](../../channels/using/customizing-an-in-app-message.md).
1. By default, the **[!UICONTROL In-App delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL In-App delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**:これにより、インバウンドトランジションとまったく同じ訪問者を含むアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、メッセージが送信された母集団を含むアウトバウンドトランジションを生成できます。配信準備中に除外されたターゲットのメンバーは、この移行から除外されます。
   ![](assets/wkf_in_app_5.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、アプリ内ダッシュボードに直接移動します。編集できるのはコンテンツのみです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみが開始されます。ワークフローを開始した後でもワークフローから作成されたメッセージを送信する必要があります。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. このオプションのチェックを解除すると、準備が完了すると、それ以上通知なしでメッセージが送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。プッシュ通知サマリペインのリンクを使用すると、リンクされた要素（ワークフロー、キャンペーンなど）に直接アクセスできます。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).
