---
title: アプリ内配信
description: アプリ内配信アクティビティを使用すると、ワークフロー内でのアプリ内メッセージの送信を設定できます。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 43%

---

# アプリ内配信{#in-app-delivery}

## 説明 {#description}

![](assets/wkf_in_app_1.png)

「**アプリ内配信**」アクティビティを使用すると、ワークフロー内でのアプリ内メッセージの送信を設定できます。 アプリ内メッセージを使用すると、ユーザーがアプリ内でアクティブな場合にメッセージを表示できます。 アプリ内配信について詳しくは、この[節](../../channels/using/about-in-app-messaging.md)を参照してください。

## 使用状況 {#context-of-use}

**[!UICONTROL In-App delivery]**&#x200B;アクティビティは、通常、同じワークフロー内で計算されるターゲットオーディエンスへのアプリ内メッセージの送信を自動化するために使用されます。

受信者は、同じワークフロー内のアクティビティの上流で、クエリや積集合などのターゲティングアクティビティを通じて定義されます。

メッセージの準備は、ワークフロー実行パラメーターに従ってトリガーされます。メッセージを送信するために手動確認を要求するかどうかをメッセージダッシュボードで選択できます（デフォルトでは必須）。ワークフローは、手動で開始するか、ワークフロー内に「スケジューラー」アクティビティを配置して自動的に実行することができます。

## 設定 {#configuration}

1. ワークフローに「 **[!UICONTROL Query]** 」アクティビティをドラッグ&amp;ドロップします。 手順4で選択したテンプレートに従って、「**[!UICONTROL Properties]**」タブの&#x200B;**[!UICONTROL Query]**&#x200B;アクティビティのターゲティングディメンションを更新する必要があります。

   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**&#x200B;テンプレートのターゲティングディメンションは&#x200B;**[!UICONTROL mobileApp (mobileAppV5)]**&#x200B;に設定する必要があります。
   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**&#x200B;テンプレートのターゲティングディメンションは&#x200B;**[!UICONTROL profile (profile)]**&#x200B;に設定する必要があります。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**&#x200B;テンプレートのターゲティングディメンションは&#x200B;**[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]**&#x200B;に設定する必要があります。

1. ワークフローに「**[!UICONTROL In-App delivery]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、（配信自体のオプションではなく）アクティビティの一般的なプロパティや詳細設定オプションにアクセスできます。

   ![](assets/wkf_in_app_3.png)

1. アプリ内メッセージタイプを選択します。 これは、**[!UICONTROL Query]**&#x200B;アクティビティでターゲット設定されたデータに依存します。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:このメッセージタイプでは、モバイルアプリケーションを購読したAdobe Campaignプロファイルをターゲットにし、Campaignで使用可能なプロファイル属性を使用してアプリ内メッセージをパーソナライズできます。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:このメッセージタイプでは、Campaignにプロファイルが存在しない場合でも、モバイルアプリケーションのすべてのユーザーにメッセージを送信できます。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:このメッセージタイプでは、Campaignにモバイルプロファイルがあるモバイルアプリのすべてのユーザーをターゲットにし、モバイルデバイスから取得した任意のプロファイル属性を使用してアプリ内メッセージをパーソナライズできます。

   ![](assets/wkf_in_app_4.png)

1. アプリ内メッセージのプロパティを入力し、「 **[!UICONTROL Associate a Mobile App to a delivery]** 」フィールドでモバイルアプリを選択します。
1. 「**[!UICONTROL Triggers]**」タブで、メッセージのトリガーとして使用するイベントをドラッグ＆ドロップします。次の3つのカテゴリのイベントを使用できます。
1. アプリ内コンテンツを定義します。 [アプリ内のカスタマイズ](../../channels/using/customizing-an-in-app-message.md)に関する節を参照してください。
1. デフォルトでは、「**[!UICONTROL In-App delivery]**」アクティビティにアウトバウンドトランジションは含まれていません。アウトバウンドトランジションを「**[!UICONTROL In-App delivery]**」アクティビティに追加する場合は、アクティビティの詳細設定オプション（アクティビティのクイックアクションにある ![](assets/dlv_activity_params-24px.png) ボタンで開く）の「**[!UICONTROL General]**」タブに移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**：インバウンドトランジションとまったく同じ母集団を含んだアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、メッセージの送信先となった母集団を含んだアウトバウンドトランジションを生成できます。配信の準備中に除外されたターゲットのメンバーは、このトランジションから除外されます。

   ![](assets/wkf_in_app_5.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、アプリ内ダッシュボードに直接移動します。 そのコンテンツのみ編集可能です。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみトリガーされます。ワークフローで作成したメッセージでも、ワークフローを開始した後で送信の確認をおこなう必要があります。ただし、メッセージダッシュボードから操作している場合と、メッセージをワークフローから作成した場合に限り、「**[!UICONTROL Request confirmation before sending messages]**」オプションを無効にできます。このオプションをオフにした場合は、準備が完了したら、追加の通知なしでそのままメッセージが送信されます。

## 備考 {#remarks}

ワークフロー内で作成された配信には、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを確認できます。プッシュ通知の概要パネルのリンクを使用すると、リンクされた要素（ワークフロー、キャンペーンなど）に直接アクセスできます。

マーケティングアクティビティリストからアクセスできる親配信では、（**[!UICONTROL In-App delivery]**&#x200B;アクティビティが設定されたときに指定された集計期間に従って）処理された送信の合計数を表示できます。 この合計数を表示するには、![](assets/wkf_dlv_detail_button.png) をクリックして、親配信の「**[!UICONTROL Deployment]**」ブロックの詳細表示を開きます。
