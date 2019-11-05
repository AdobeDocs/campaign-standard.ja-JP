---
title: SMS 配信
description: SMS配信アクティビティを使用すると、ワークフローで単一の送信SMSまたは定期的なSMSを送信するように設定できます。
page-status-flag: 非活性化の
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: チャネル活動
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# SMS 配信{#sms-delivery}

## 説明 {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

アクティビティ **[!UICONTROL SMS delivery]** を使用すると、ワークフローでSMSを送信するように設定できます。 1回の送信SMSで1回 **送信するか** 、定期的なSMSで **す** 。

単一の送信SMSメッセージは、1回だけ送信される標準SMSです。

定期的なSMSメッセージを使用すると、同じSMSを、定義した期間に異なるターゲットに複数回送信できます。 ニーズに合ったレポートを取得するために、期間ごとに配信を集計できます。

## 使用状況 {#context-of-use}

The **[!UICONTROL SMS delivery]** activity is generally used to automate sending an SMS to a target calculated in the same workflow.

スケジューラーにリンクする場合は、定期的なSMSメッセージを定義できます。

SMS 受信者は、同じワークフロー内アクティビティの上流でクエリやインタセクションなどのターゲティングアクティビティによって定義されます。

メッセージ準備は、ワークフロー実行パラメータに従ってトリガされる。 メッセージダッシュボードから、手動でメッセージを送信する確認を要求するかどうかを選択できます（デフォルトでは必須）。 ワークフローは、手動で開始するかまたはワークフロー内にスケジューラーアクティビティを置いて自動的に実行させます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL SMS delivery]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。

   >[!NOTE]
   >
   >ワークフローのアクションバーのボタンを使用して、（配信自体ではなく）アクティビティの一般プロパティと詳細オ ![](assets/dlv_activity_params-24px.png) プションにアクセスできます。 このボタンは、アクティビティに固有 **[!UICONTROL SMS delivery]** です。 SMSプロパティは、SMSダッシュボードのアクションバーからアクセスできます。

1. SMS送信モードを選択します。

   * **[!UICONTROL SMS]**:smsは1回だけ送信されます。 アクティビティにアウトバウンド遷移を追加するかどうかを指定できます。 異なる移行タイプについては、この手順の手順7で説明します。
   * **[!UICONTROL Recurring SMS]**:smsは、アクティビティで定義された頻度に従って、複数回送信され **[!UICONTROL Scheduler]** ます。 送信の集計期間を選択します。 これにより、定義した期間に発生したすべての送信を1つのビューに再グループ化し、 **Recurring execution** （反復実行）とも呼ばれ、アプリのマーケティングアクティビティリストからアクセスできます。

      例えば、誕生日のSMSを毎日送信する場合、1か月あたりの送信数を集計するように選択できます。 これにより、SMSは毎日送信されますが、配信に関するレポートを毎月受け取ることができます。

1. SMSタイプを選択します。 SMSタイプは、 &gt; &gt;メニューで定義されたSMSテンプ **[!UICONTROL Resources]** レート **[!UICONTROL Templates]** に基づ **[!UICONTROL Delivery templates]** きます。
1. SMSの一般的なプロパティを入力します。 また、既存のキャンペーンに添付することもできます。 ワークフローの配信アクティビティのラベルがSMSラベルで更新されます。
1. SMSコンテンツを定義します。 SMSメッセージの作成に関す [る節を参照してください](../../channels/using/creating-an-sms-message.md)。
1. デフォルトでは、アクティビティ **[!UICONTROL SMS delivery]** にはアウトバウンド遷移は含まれません。 アクティビティにアウトバウンド遷移を追加する場合は、アクティビティのアドバンスアクティビティオプション **[!UICONTROL SMS delivery]** （アクティビティのクイックアクションのボタン）のタブに移動し、次のいず **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) れかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**:これにより、インバウンドトランジションと完全に同じ母集団を含むアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、SMSの送信先の母集団を含むアウトバウンド移行を生成できます。 配信準備中に除外されるターゲットのメンバー（検疫、無効な番号など）は、この移行から除外されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、SMSダッシュボードに直接移動します。 編集できるのは、そのコンテンツのみです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローを開始した後も、ワークフローから作成されたメッセージの送信を確認する必要があります。 ただし、メッセージのダッシュボードからは、メッセージがワークフローから作成された場合にのみ、このオプションを無効にで **[!UICONTROL Request confirmation before sending messages]** きます。 このオプションのチェックを外すと、準備が完了した後、通知なしでメッセージが送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリのマーケティングアクティビティリストでアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 SMS概要ペインのリンクを使用すると、リンクされた要素（定期的なSMSの場合のワークフロー、キャンペーン、親配信）に直接アクセスできます。

繰り返し配信の実行は、デフォルトでマスクされます。 これらを表示するには、マーケティングア **[!UICONTROL Show recurring executions]** クティビティの検索パネルでオプションを選択します。

親配信では、マーケティングアクティビティリストから、または関連する反復実行を介して直接アクセスでき、処理された送信の総数（アクティビティの設定時に指定した集計期間に従う）を表示で **[!UICONTROL SMS delivery]** きます。 これを行うには、を選択して親配信のブロックの詳細ビュー **[!UICONTROL Deployment]** を開きます ![](assets/wkf_dlv_detail_button.png)。

## 例 ：{#example}

![](assets/wkf_sms_example_1.png)

次の例は誕生日ワークフローです。 毎日、誕生日のプロファイルにSMSが送られます。 手順は次のとおりです。

* では、 **[!UICONTROL Scheduler]** 毎日午前8時にワークフローを開始できます。

   ![](assets/wkf_delivery_example_2.png)

* このア **[!UICONTROL Query]** クティビティでは、携帯電話番号を入力し、その誕生日が現在の日にあるプロファイルを、ワークフローが実行されるたびに計算できます。 誕生日の計算は、クエリ編集ツールのパレットで使用できる定義済みのフィルターを使用して実行されます。

   ![](assets/wkf_delivery_example_3.png)

* これは **[!UICONTROL SMS]** 繰り返し起こる 送信は月別に集計されます。 したがって、1か月で送信されるすべてのSMSメッセージは、1つのビューに集約されます。 そのため、1年後に365件の配信が実行されますが、Adobe Campaignインターフェイスでは12回の表示(繰り返し実 **行**)に再グループ化されます。 履歴とレポートの詳細は毎月表示され、送信ごとには表示されません。

   ![](assets/wkf_sms_example_4.png)

ワークフロー内のSMS配信の別の例については、使用例を参照し [てください。未開封者に新しい配信を送信する再ターゲット化ワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)。
