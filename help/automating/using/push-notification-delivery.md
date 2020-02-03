---
title: プッシュ通知配信
description: プッシュ通知配信アクティビティを使用すると、ワークフロー内で1回の送信プッシュ通知または定期的なプッシュ通知を送信するように設定できます。
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# プッシュ通知配信{#push-notification-delivery}

## 説明 {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

アクティビテ **[!UICONTROL Push notification]**ィを使用すると、ワークフローでプッシュ通知を送信するように設定できます。 1回の送信通知で1**&#x200B;回だけ送信する&#x200B;**か**、繰り返し送信することがで&#x200B;**きます。

単一送信通知は、1回送信される、標準的なモバイルアプリのプッシュ通知配信です。

定期的な通知を使用すると、同じモバイルアプリのプッシュ通知配信を、定義した期間に異なるターゲットに複数回送信できます。 ニーズに合ったレポートを取得するために、期間ごとに配信を集計できます。

## 使用状況 {#context-of-use}

The **[!UICONTROL Push notification]**activity is generally used to automate sending a notification to a target calculated in the same workflow.

スケジューラーにリンクされている場合、定期的なプッシュ通知を定義できます。

受信者は、クエリー、交差などのターゲットアクティビティを介して、同じワークフロー内のアクティビティの上流に定義されます。

メッセージ準備は、ワークフロー実行パラメータに従ってトリガされる。 メッセージダッシュボードから、手動でメッセージを送信する確認を要求するかどうかを選択できます（デフォルトでは必須）。 ワークフローは、手動で開始するかまたはワークフロー内にスケジューラーアクティビティを置いて自動的に実行させます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Push notification]**にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションのボタンを使用して、アクティビティの一般的なプロパティと詳細なオプション（配信自体ではなく） ![](assets/dlv_activity_params-24px.png) にアクセスできます。 このボタンは、アクティビティに固有 **[!UICONTROL Push notification]**です。 プッシュ通知のプロパティは、プッシュダッシュボードのアクションバーからアクセスできます。

1. プッシュ通知送信モードを選択します。

   * **[!UICONTROL Single notification]**:プッシュ通知は1回だけ送信されます。 アクティビティにアウトバウンド遷移を追加するかどうかを指定できます。 異なる移行タイプについては、この手順の手順7で説明します。
   * **[!UICONTROL Recurring notification]**:プッシュ通知は、アクティビティで定義された頻度に従って、複数回送信され**[!UICONTROL Scheduler]** ます。 送信の集計期間を選択します。 これにより、定義した期間に発生したすべての送信を、1回の単一のプッシュ通知で再グループ化できます。この通知は、繰り返し実行とも呼ばれ **** 、アプリのマーケティングアクティビティリストからアクセスできます。

      例えば、誕生日の通知を毎日繰り返し送信する場合、1か月あたりの送信を集計するように選択できます。 これにより、通知が毎日送信されるにもかかわらず、毎月配信されるレポートを受け取ることができます。

1. 通知タイプを選択します。 これらのタイプは、//メニューで定義されたプッシュ通知テ **[!UICONTROL Resources]**ンプレ**[!UICONTROL Templates]** ートにあ **[!UICONTROL Delivery templates]**ります。
1. プッシュ通知の一般的なプロパティを入力します。 また、既存のキャンペーンに添付することもできます。 ワークフローの配信アクティビティのラベルがプッシュ通知ラベルで更新されます。
1. プッシュ通知のコンテンツを定義します。 プッシュ [通知の作成を参照してください。](../../channels/using/preparing-and-sending-a-push-notification.md)
1. デフォルトでは、アクティビティ **[!UICONTROL Push notification]**にはアウトバウンド遷移は含まれません。 アクティビティにアウトバウンド遷移を追加する場合は、アクティビティのアドバンスアクティビティオプション**[!UICONTROL Push Notification]** （アクティビティのクイックアクションのボタン）のタブに移動し、次のいず **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png)れかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**:これにより、インバウンドトランジションと完全に同じ母集団を含むアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、通知の送信先の母集団を含むアウトバウンド移行を生成できます。 配信準備中に除外されたターゲットのメンバーは、この移行から除外されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、プッシュ通知ダッシュボードに直接移動します。 編集できるのは、そのコンテンツのみです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローを開始した後も、ワークフローから作成されたメッセージの送信を確認する必要があります。 ただし、メッセージのダッシュボードからは、メッセージがワークフローから作成された場合にのみ、このオプションを無効にで **[!UICONTROL Request confirmation before sending messages]**きます。 このオプションのチェックを外すと、準備が完了した後、通知なしでメッセージが送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリのマーケティングアクティビティリストでアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 プッシュ通知の概要ウィンドウ内のリンクを使用すると、リンクされた要素（ワークフロー、キャンペーンなど）に直接アクセスできます。

マーケティングアクティビティリストからアクセスできる親配信では、（アクティビティの設定時に指定された集計期間に従って）処理された送信の総数を **[!UICONTROL Push notification]**表示できます。 これを行うには、を選択して親配信のブロックの詳細ビュー**[!UICONTROL Deployment]** を開きます ![](assets/wkf_dlv_detail_button.png)。

## ワークフローを使用した定期的なプッシュ通知の送信 {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

この例では、パーソナライズされたプッシュ通知が月の初日の午後8時に、タイムゾーンに応じてモバイルアプリケーションの購読者に送信されます。 手順は次のとおりです。

1. アクティビテ **[!UICONTROL Scheduler]**ィを使用すると、配信開始前のワークフロー日数を開始し、任意のタイムゾーンの午後8時に各加入者に通知を送信できます。

   * フィールド **[!UICONTROL Execution frequency]**で「月別」を選択します。
   * フィールドで[午後8時]を選択 **[!UICONTROL Time]**します。
   * 毎月の配信日を選択します。
   * ワークフローの開始日を選択します。配信を開始する1日以上前の日付を選択します。 そうしないと、選択した時間が既にタイムゾーンに含まれている場合は、1日後にメッセージを受け取る受信者もいます。
   * タブで、 **[!UICONTROL Execution options]**ワークフローを開始するタイムゾーンをフィールドで選択し**[!UICONTROL Time zone]** ます。 例えば、ワークフローは太平洋標準時の午後8時（月の初日の1週間前）に開始され、該当するすべてのタイムゾーンに対して配信を作成できる時間が与えられます。
   >[!NOTE]
   >
   >デフォルトでは、選択したタイムゾーンは、ワークフローのプロパティで定義されたタイムゾーンになります(「ワーク [フローの構築](../../automating/using/building-a-workflow.md)」を参照)。

   ![](assets/wkf_push_example_5.png)

1. **Query** アクティビティでは、20 ～ 30歳のVIP顧客（モバイルアプリケーションを購読し、送信した電子メールを開かなかった顧客）をターゲットに設定できます。

   * オーディエンス（VIPのお客様）を選択し、年齢に基づいてフィルターを適用します。
   * 購読をアプリ要素にド **ラッグ&amp;ドロップし** 、ワークスペースに入れます。 「存 **在する** 」を選択し、使用するモバイルアプリケーションを選択します。
   * 顧客に送信した電子メールを選択します。
   * 配信ログ（ログ）要素 **をワークスペースにドラッグ&amp;ドロップし****** 、「存在する」を選択して、電子メールを受け取ったすべての顧客をターゲットにします。
   * 追跡ログ（追跡）要素 **をワークスペースにドラッグ&amp;ドロップし、「存在しない****** 」を選択して、電子メールを開かなかったすべての顧客をターゲットにします。

      ![](assets/wkf_push_example_2.png)

1. プッシュ **通知アクティビティでは** 、メッセージの内容を入力し、使用するパーソナライゼーションフィールドを選択できます。

   * オプションを選 **[!UICONTROL Recurring notification]**択します。
   * プッシュ通知のコンテンツを定義します。 プッシュ通知の内容について詳しくは、この節を参照してく [ださい](../../channels/using/preparing-and-sending-a-push-notification.md)。
   * ブロック内で、 **[!UICONTROL Schedule]**を選択しま**[!UICONTROL Messages to be sent automatically on the time zone specified below]**&#x200B;す。 ここでは、ワークフローで **[!UICONTROL Time zone of the contact date]**「太平洋」を選択しま**[!UICONTROL Scheduler]**&#x200B;す。
   * フィールド **[!UICONTROL Optimize the sending time per recipient]**で、を選択しま**[!UICONTROL Send at the recipient's time zone]**&#x200B;す。

      ![](assets/wkf_push_example_4.png)

1. ボタンをクリッ **[!UICONTROL Start]**クして、定期的なワークフローを開始します。

   ![](assets/wkf_push_example_3.png)

ワークフローが実行されています。 選択した開始日の太平洋標準時の午後8時に開始し、月の初日の午後8時に定期的なプッシュが顧客のタイムゾーンに応じて送信されます。 **[!UICONTROL Scheduler]**
