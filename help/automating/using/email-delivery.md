---
title: E メール配信
description: 電子メール配信アクティビティでは、ワークフローで単一の送信電子メールまたは定期的な電子メールを送信するように設定できます。
page-status-flag: 非活性化の
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: チャネル活動
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: 配信，ワークフロー，メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# E メール配信{#email-delivery}

## 説明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

このア **[!UICONTROL Email delivery]** クティビティでは、ワークフローでの電子メールの送信を設定できます。 1回の送信電子メ **ールで** 1回だけ送信することも、繰り返し送信する電子メールでもかまい **ません** 。

単一送信電子メールは、1回送信される標準電子メールです。

定期的な電子メールを使用すると、定義した期間に同じ電子メールを異なるターゲットに複数回送信できます。 ニーズに合ったレポートを取得するために、期間ごとに配信を集計できます。

## 使用状況 {#context-of-use}

The **[!UICONTROL Email delivery]** activity is generally used to automate sending an email to a target calculated in the same workflow.

スケジューラーにリンクする場合は、定期的な電子メールを定義できます。

電子メールの受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフロー内のアクティビティの上流に定義されます。

メッセージ準備は、ワークフロー実行パラメータに従ってトリガされる。 メッセージダッシュボードから、手動でメッセージを送信する確認を要求するかどうかを選択できます（デフォルトでは必須）。 ワークフローは、手動で開始するかまたはワークフロー内にスケジューラーアクティビティを置いて自動的に実行させます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Email delivery]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションのボタンを使用して、アクティビティの一般的なプロパティと詳細なオプション（配信自体ではなく） ![](assets/dlv_activity_params-24px.png) にアクセスできます。 このボタンは、アクティビティに固有 **[!UICONTROL Email delivery]** です。 電子メールのプロパティは、電子メールダッシュボードのアクションバーからアクセスできます。

1. 電子メール送信モードを選択します。

   * **[!UICONTROL Email]**:電子メールは1回だけ送信されます。 アクティビティにアウトバウンド遷移を追加するかどうかを指定できます。 異なる移行タイプについては、この手順の手順7で説明します。
   * **[!UICONTROL Recurring email]**:電子メールは、アクティビティで定義された頻度に従って、複数回送信され **[!UICONTROL Scheduler]** ます。 送信の集計期間を選択します。 これにより、定義した期間に発生したすべての送信を、 **Recurring execution** （反復実行）とも呼ばれる1つの電子メールで再グループ化し、アプリのマーケティングアクティビティリストからアクセスできます。

      例えば、毎日送信される誕生日の電子メールを繰り返し送信する場合、1か月あたりの送信数を集計するように選択できます。 これにより、電子メールは毎日送信されますが、配信に関するレポートを毎月受け取ることができます。

1. 電子メールの種類を選択します。 電子メールのタイプは、//メニューで定義された電子メールテ **[!UICONTROL Resources]** ンプレート **[!UICONTROL Templates]** に基づ **[!UICONTROL Delivery templates]** きます。
1. 電子メールの一般的なプロパティを入力します。 また、既存のキャンペーンに添付することもできます。 ワークフローの配信アクティビティのラベルが電子メールラベルで更新されます。
1. 電子メールの内容を定義します。 コンテンツ編集に関する項 [を参照](../../designing/using/overview.md)。
1. デフォルトでは、アクティビティ **[!UICONTROL Email delivery]** にはアウトバウンド遷移は含まれません。 アクティビティにアウトバウンド遷移を追加する場合は、アクティビティのアドバンスアクティビティオプション **[!UICONTROL Email delivery]** （アクティビティのクイックアクションのボタン）のタブに移動し、次のいず **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) れかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**:これにより、インバウンドトランジションと完全に同じ母集団を含むアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、電子メールの送信先の訪問者を含むアウトバウンドトランジションを生成できます。 配信の準備中に除外されるターゲットのメンバー（検疫、無効な電子メールなど）は、この移行から除外されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、電子メールダッシュボードに直接移動します。 編集できるのは、そのコンテンツのみです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローを開始した後も、ワークフローから作成されたメッセージの送信を確認する必要があります。 ただし、メッセージのダッシュボードからは、メッセージがワークフローから作成された場合にのみ、このオプションを無効にで **[!UICONTROL Request confirmation before sending messages]** きます。 このオプションのチェックを外すと、準備が完了した後、通知なしでメッセージが送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリのマーケティングアクティビティリストでアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 電子メールの概要ペインのリンクを使用すると、リンクされた要素（定期的な電子メールの場合は、ワークフロー、キャンペーン、親配信）に直接アクセスできます。

![](assets/wkf_display_recurrent_executions_2.png)

繰り返し配信の実行は、デフォルトでマスクされます。 これらを表示するには、マーケティングア **[!UICONTROL Show recurring executions]** クティビティの検索パネルでオプションを選択します。

![](assets/wkf_display_recurrent_executions.png)

親配信では、マーケティングアクティビティリストから、または関連する反復実行を介して直接アクセスでき、処理された送信の総数（アクティビティの設定時に指定した集計期間に従う）を表示で **[!UICONTROL Email delivery]** きます。 これを行うには、を選択して親配信のブロックの詳細ビュー **[!UICONTROL Deployment]** を開きます ![](assets/wkf_dlv_detail_button.png)。

![](assets/wkf_display_recurrent_executions_3.png)

## 例 ：{#example}

![](assets/wkf_delivery_example_1.png)

次の例は誕生日ワークフローです。 誕生日がその日のプロファイルに毎日電子メールが送られます。 手順は次のとおりです。

* では、 **[!UICONTROL Scheduler]** 毎日午前8時にワークフローを開始できます。

   ![](assets/wkf_delivery_example_2.png)

* このア **[!UICONTROL Query]** クティビティでは、ワークフローが実行されるたびに、電子メールを提供し、その誕生日が現在の日にあるプロファイルを計算できます。 誕生日の計算は、クエリ編集ツールのパレットで使用できる定義済みのフィルターを使用して実行されます。

   ![](assets/wkf_delivery_example_3.png)

* これは **[!UICONTROL Email]** 繰り返し起こる 送信は月別に集計されます。 したがって、1か月で送信されたすべての電子メールは1つのビューに集計されます。 そのため、1年後に365件の配信が実行されますが、Adobe Campaignインターフェイスでは12回の表示(繰り返し実 **行**)に再グループ化されます。 履歴とレポートの詳細は毎月表示され、送信ごとには表示されません。

   ![](assets/wkf_delivery_example_4.png)

**関連トピック**

* [使用例：週に1回の電子メール配信の作成](../../automating/using/workflow-weekly-offer.md)
* [使用例：場所でセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [使用例：補完を含む配信の作成](../../automating/using/workflow-created-query-with-complement.md)
* [使用例：未開封者に新しい配信を送信する再ターゲットワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)