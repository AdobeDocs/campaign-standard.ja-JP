---
solution: Campaign Standard
product: campaign
title: アプリ内配信
description: アプリ内配信アクティビティを使用すると、ワークフロー内でのアプリ内メッセージの送信を設定できます。
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 43%

---


# アプリ内配信{#in-app-delivery}

## 説明 {#description}

![](assets/wkf_in_app_1.png)

アプリ **内配信** アクティビティを使用すると、ワークフロー内でのアプリ内メッセージの送信を設定できます。 アプリ内メッセージを使用すると、ユーザーがアプリ内でアクティブな場合にメッセージを表示できます。 アプリ内配信について詳しくは、この [節を参照してください](../../channels/using/about-in-app-messaging.md)。

## 使用状況 {#context-of-use}

The **[!UICONTROL In-App delivery]** activity is generally used to automate sending an In-App message to a target audience calculated in the same workflow.

受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフローのアクティビティの上流に定義されます。

メッセージの準備は、ワークフロー実行パラメーターに従ってトリガーされます。メッセージを送信するために手動確認を要求するかどうかをメッセージダッシュボードで選択できます（デフォルトでは必須）。ワークフローは、手動で開始するか、ワークフロー内に「スケジューラー」アクティビティを配置して自動的に実行することができます。

## 設定 {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. 手順4で選択したテンプレートに従って、 **[!UICONTROL Query]** タブの **[!UICONTROL Properties]** アクティビティターゲティングディメンションを更新する必要があります。

   * ターゲティングディメンションは、テンプレート **[!UICONTROL mobileApp (mobileAppV5)]** 用にに設定する必要があり **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** ます。
   * ターゲティングディメンションは、テンプレート **[!UICONTROL profile (profile)]** 用にに設定する必要があり **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** ます。
   * ターゲティングディメンションは、テンプレート **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** 用にに設定する必要があり **[!UICONTROL Target users based on their Mobile profile (inApp)]** ます。

1. ワークフローに「**[!UICONTROL In-App delivery]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、（配信自体のオプションではなく）アクティビティの一般的なプロパティや詳細設定オプションにアクセスできます。

   ![](assets/wkf_in_app_3.png)

1. アプリ内メッセージの種類を選択します。 これは、 **[!UICONTROL Query]** アクティビティでターゲット設定されているデータに依存します。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:このメッセージタイプを使用すると、モバイルアプリを購読しているターゲットAdobe Campaignプロファイルをキャンペーンし、アプリ内メッセージをプロファイルで使用可能な属性とパーソナライズできます。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:このメッセージタイプを使用すると、キャンペーン内に既存のプロファイルがない場合でも、モバイルアプリのすべてのユーザーにメッセージを送信できます。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:このメッセージタイプを使用すると、モバイルプロファイルが既知か不明かにかかわらず、キャンペーンにモバイルアプリのすべてのユーザーをターゲットし、モバイルデバイスから取得したプロファイル属性を使用してアプリ内メッセージをパーソナライズできます。

   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. 「**[!UICONTROL Triggers]**」タブで、メッセージのトリガーとして使用するイベントをドラッグ＆ドロップします。次の3つのカテゴリのイベントを使用できます。
1. アプリ内コンテンツを定義します。 アプリ [内のカスタマイズに関する節を参照してください](../../channels/using/customizing-an-in-app-message.md)。
1. デフォルトでは、「**[!UICONTROL In-App delivery]**」アクティビティにアウトバウンドトランジションは含まれていません。アウトバウンドトランジションを「**[!UICONTROL In-App delivery]**」アクティビティに追加する場合は、アクティビティの詳細設定オプション（アクティビティのクイックアクションにある ![](assets/dlv_activity_params-24px.png) ボタンで開く）の「**[!UICONTROL General]**」タブに移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**：インバウンドトランジションとまったく同じ母集団を含んだアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、メッセージの送信先の母集団を含むアウトバウンドトランジションを生成できます。 配信準備中に除外されたターゲットの部材は、このトランジションから除外される。

   ![](assets/wkf_in_app_5.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、アプリ内ダッシュボードーに直接移動します。 そのコンテンツのみ編集可能です。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみトリガーされます。ワークフローで作成したメッセージでも、ワークフローを開始した後で送信の確認をおこなう必要があります。ただし、メッセージダッシュボードから操作している場合と、メッセージをワークフローから作成した場合に限り、「**[!UICONTROL Request confirmation before sending messages]**」オプションを無効にできます。このオプションをオフにした場合は、準備が完了したら、追加の通知なしでそのままメッセージが送信されます。

## 備考 {#remarks}

ワークフロー内で作成された配信には、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを確認できます。プッシュ通知の概要ペインのリンクを使用すると、リンクされた要素(ワークフロー、キャンペーンなど)に直接アクセスできます。

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). この合計数を表示するには、![](assets/wkf_dlv_detail_button.png) をクリックして、親配信の「**[!UICONTROL Deployment]**」ブロックの詳細表示を開きます。
