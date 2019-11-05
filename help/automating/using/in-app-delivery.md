---
title: アプリ内配信
description: アプリ内配信アクティビティを使用すると、ワークフロー内でのアプリ内メッセージの送信を設定できます。
page-status-flag: 非活性化の
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: チャネル活動
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# アプリ内配信{#in-app-delivery}

## 説明 {#description}

![](assets/wkf_in_app_1.png)

アプリ **内配信アクティビティでは** 、ワークフロー内でのアプリ内メッセージの送信を設定できます。 アプリ内メッセージを使用すると、ユーザーがアプリ内でアクティブな場合にメッセージを表示できます。 アプリ内配信について詳しくは、この節を参照してく [ださい](../../channels/using/about-in-app-messaging.md)。

## 使用状況 {#context-of-use}

The **[!UICONTROL In-App delivery]** activity is generally used to automate sending an In-App message to a target audience calculated in the same workflow.

受信者は、クエリー、交差などのターゲットアクティビティを介して、同じワークフロー内のアクティビティの上流に定義されます。

メッセージ準備は、ワークフロー実行パラメータに従ってトリガされる。 メッセージダッシュボードから、手動でメッセージを送信する確認を要求するかどうかを選択できます（デフォルトでは必須）。 ワークフローは、手動で開始するかまたはワークフロー内にスケジューラーアクティビティを置いて自動的に実行させます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Query]** にドラッグ&amp;ドロップします。 手順4で選択したテンプ **[!UICONTROL Query]** レートに従って、タブ内のアクティビティ **[!UICONTROL Properties]** ターゲットディメンションを更新する必要があることに注意してください。

   * ターゲットディメンションは、テンプレートに対して **[!UICONTROL mobileApp (mobileAppV5)]** に設定する必要が **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** あります。
   * ターゲットディメンションは、テンプレートに対して **[!UICONTROL profile (profile)]** に設定する必要が **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** あります。
   * ターゲットディメンションは、テンプレートに対して **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** に設定する必要が **[!UICONTROL Target users based on their Mobile profile (inApp)]** あります。

1. アクティビティをワークフロー **[!UICONTROL In-App delivery]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションのボタンを使用して、アクティビティの一般的なプロパティと詳細なオプション（配信自体ではなく） ![](assets/dlv_activity_params-24px.png) にアクセスできます。

   ![](assets/wkf_in_app_3.png)

1. アプリ内メッセージの種類を選択します。 これは、アクティビティでターゲット設定されたデータに依存 **[!UICONTROL Query]** します。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:このメッセージタイプを使用すると、モバイルアプリを登録したAdobe Campaignプロファイルをターゲットにし、Campaignで使用可能なプロファイル属性を使用してアプリ内メッセージをパーソナライズできます。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:このメッセージタイプを使用すると、Campaignに既存のプロファイルがない場合でも、モバイルアプリのすべてのユーザーにメッセージを送信できます。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:このメッセージタイプを使用すると、Campaignにモバイルプロファイルがあるモバイルアプリのすべてのユーザーをターゲットにし、モバイルデバイスから取得したプロファイル属性を使用してアプリ内メッセージをパーソナライズできます。
   ![](assets/wkf_in_app_4.png)

1. アプリ内メッセージのプロパティを入力し、フィールドでモバイルアプリを選択 **[!UICONTROL Associate a Mobile App to a delivery]** します。
1. タブで、メ **[!UICONTROL Triggers]** ッセージをトリガーするイベントをドラッグ&amp;ドロップします。 次の3つのカテゴリのイベントを使用できます。
1. アプリ内コンテンツを定義します。 アプリ内のカスタマイズに関す [る節を参照してください](../../channels/using/customizing-an-in-app-message.md)。
1. デフォルトでは、アクティビティ **[!UICONTROL In-App delivery]** にはアウトバウンド遷移は含まれません。 アクティビティにアウトバウンド遷移を追加する場合は、アクティビティのアドバンスアクティビティオプション **[!UICONTROL In-App delivery]** （アクティビティのクイックアクションのボタン）のタブに移動し、次のいず **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) れかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**:これにより、インバウンドトランジションと完全に同じ母集団を含むアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、メッセージの送信先の母集団を含むアウトバウンド移行を生成できます。 配信準備中に除外されたターゲットのメンバーは、この移行から除外されます。
   ![](assets/wkf_in_app_5.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、アプリ内ダッシュボードに直接移動します。 編集できるのは、そのコンテンツのみです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローを開始した後も、ワークフローから作成されたメッセージの送信を確認する必要があります。 ただし、メッセージのダッシュボードからは、メッセージがワークフローから作成された場合にのみ、このオプションを無効にで **[!UICONTROL Request confirmation before sending messages]** きます。 このオプションのチェックを外すと、準備が完了した後、通知なしでメッセージが送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリのマーケティングアクティビティリストでアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 プッシュ通知の概要ウィンドウ内のリンクを使用すると、リンクされた要素（ワークフロー、キャンペーンなど）に直接アクセスできます。

マーケティングアクティビティリストからアクセスできる親配信では、（アクティビティの設定時に指定された集計期間に従って）処理された送信の総数を **[!UICONTROL In-App delivery]** 表示できます。 これを行うには、を選択して親配信のブロックの詳細ビュー **[!UICONTROL Deployment]** を開きます ![](assets/wkf_dlv_detail_button.png)。
