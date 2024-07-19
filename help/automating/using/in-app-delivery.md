---
title: アプリ内配信
description: アプリ内配信アクティビティでは、ワークフロー内でアプリ内メッセージの送信を設定できます。
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 39%

---

# アプリ内配信{#in-app-delivery}

## 説明 {#description}

![](assets/wkf_in_app_1.png)

**アプリ内配信** アクティビティでは、ワークフロー内でアプリ内メッセージの送信を設定できます。 アプリ内メッセージを使用すると、アプリケーション内でユーザーがアクティブな場合にメッセージを表示できます。 アプリ内配信について詳しくは、この [ 節 ](../../channels/using/about-in-app-messaging.md) を参照してください。

## 使用コンテキスト {#context-of-use}

通常、**[!UICONTROL In-App delivery]** アクティビティは、同じワークフローで計算されたターゲットオーディエンスに対するアプリ内メッセージの送信を自動化するために使用します。

受信者は、クエリ、交差などのターゲティングアクティビティを通じて、同じワークフロー内のアクティビティの上流に定義されます。

メッセージの準備は、ワークフロー実行パラメーターに従ってトリガーされます。メッセージを送信するために手動確認を要求するかどうかをメッセージダッシュボードで選択できます（デフォルトでは必須）。ワークフローは、手動で開始するか、ワークフロー内に「スケジューラー」アクティビティを配置して自動的に実行することができます。

## 設定 {#configuration}

1. **[!UICONTROL Query]** アクティビティをワークフローにドラッグ&amp;ドロップします。 手順 4 で選択したテンプレートに従って、「**[!UICONTROL Properties]**」タブの **[!UICONTROL Query]** アクティビティのターゲティングディメンションを更新する必要があります。

   * ターゲティングディメンションは、**[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** テンプレートの **[!UICONTROL mobileApp (mobileAppV5)]** に設定する必要があります。
   * ターゲティングディメンションは、**[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** テンプレートの **[!UICONTROL profile (profile)]** に設定する必要があります。
   * ターゲティングディメンションは、**[!UICONTROL Target users based on their Mobile profile (inApp)]** テンプレートの **[!UICONTROL subscriptions to an application (`nms:appSubscriptionRcp:appSubscriptionRcpDetail`）]** 設定する必要があります。

1. ワークフローに「**[!UICONTROL In-App delivery]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの「![](assets/dlv_activity_params-24px.png)」ボタンを使用して、アクティビティの（配信自体ではなく）一般的なプロパティと詳細オプションにアクセスできます。

   ![](assets/wkf_in_app_3.png)

1. アプリ内メッセージのタイプを選択します。 これは、**[!UICONTROL Query]** アクティビティでターゲットにしたデータによって異なります。

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**：このメッセージタイプを使用すると、モバイルアプリケーションを購読しているAdobe Campaign プロファイルをターゲットに設定し、Campaign で使用可能なプロファイル属性を使用してアプリ内メッセージをパーソナライズできます。
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**：このメッセージタイプを使用すると、Campaign に既存のプロファイルがない場合でも、モバイルアプリケーションのすべてのユーザーにメッセージを送信できます。
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**：このメッセージタイプを使用すると、既知または不明にかかわらず、Campaign でモバイルプロファイルを持つモバイルアプリのすべてのユーザーをターゲットにしたり、モバイルデバイスから取得したプロファイル属性を使用してアプリ内メッセージをパーソナライズしたりできます。

   ![](assets/wkf_in_app_4.png)

1. アプリ内メッセージのプロパティを入力し、「**[!UICONTROL Associate a Mobile App to a delivery]**」フィールドでモバイルアプリを選択します。
1. 「**[!UICONTROL Triggers]**」タブで、メッセージのトリガーとして使用するイベントをドラッグ＆ドロップします。次の 3 つのカテゴリのイベントを使用できます。
1. アプリ内コンテンツを定義します。 [ アプリ内カスタマイズ ](../../channels/using/customizing-an-in-app-message.md) に関する節を参照してください。
1. デフォルトでは、「**[!UICONTROL In-App delivery]**」アクティビティにアウトバウンドトランジションは含まれていません。アウトバウンドトランジションを「**[!UICONTROL In-App delivery]**」アクティビティに追加する場合は、アクティビティの詳細設定オプション（アクティビティのクイックアクションにある ![](assets/dlv_activity_params-24px.png) ボタンで開く）の「**[!UICONTROL General]**」タブに移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**：インバウンドトランジションとまったく同じ母集団を含んだアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**: メッセージの送信先の母集団を含むアウトバウンドトランジションを生成できます。 配信準備で除外されたターゲットのメンバーは、このトランジションから除外されます。

   ![](assets/wkf_in_app_5.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、アプリ内ダッシュボードに直接移動します。 そのコンテンツのみ編集可能です。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみトリガーされます。ワークフローで作成したメッセージでも、ワークフローを開始した後で送信の確認をおこなう必要があります。ただし、メッセージダッシュボードから操作している場合と、メッセージをワークフローから作成した場合に限り、「**[!UICONTROL Request confirmation before sending messages]**」オプションを無効にできます。このオプションをオフにした場合は、準備が完了したら、追加の通知なしでそのままメッセージが送信されます。

## 備考 {#remarks}

ワークフロー内で作成された配信には、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを確認できます。プッシュ通知の概要ペインのリンクを使用すると、リンクされた要素（ワークフロー、キャンペーンなど）に直接アクセスできます。

マーケティングアクティビティリストからアクセスできる親配信では、処理された送信の合計数を表示できます（**[!UICONTROL In-App delivery]** 信アクティビティが設定されたときに指定された集計期間による）。 この合計数を表示するには、![](assets/wkf_dlv_detail_button.png) をクリックして、親配信の「**[!UICONTROL Deployment]**」ブロックの詳細表示を開きます。
