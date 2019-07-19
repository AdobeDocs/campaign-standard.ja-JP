---
title: ダイレクトメール配信
seo-title: ダイレクトメール配信
description: ダイレクトメール配信
seo-description: ダイレクトメール配信アクティビティを使用すると、単一のダイレクトメールまたは定期的なダイレクトメールをワークフローで送信できます。
page-status-flag: 常にアクティブ化されていない
uuid: bfa7b176- a17c-4079- a073-64b8ce4788ed
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: チャネルアクティビティ
discoiquuid: b9ddb2a0-54ff-4ada- be6f-8109fa06d461
context-tags: DirectMail，ワークフロー，メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Direct mail delivery{#direct-mail-delivery}

## 説明 {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

**[!UICONTROL Direct mail delivery]** このアクティビティでは、ダイレクトメールキャンペーンに使用するプロファイルデータを含むファイルを設定および準備できます。This can be a direct mail that is used just once, or it can be a **recurring** direct mail.

標準のダイレクトメールは1回送信されます。

定期的なメールを使用すると、定義済みの期間にわたって、同一のダイレクトメールを複数回のターゲットに送信できます。期間ごとの配信を集計して、ニーズに対応するレポートを取得できます。

## Context of use {#context-of-use}

**[!UICONTROL Direct mail delivery]** このアクティビティは、プロファイルデータを含むファイルの準備を自動化するために一般的に使用されます。このファイルは、郵送を担当するパートナー/プロバイダーに送信できます。

スケジューラーにリンクすると、定期的なダイレクトメールを定義できます。

ダイレクトメールの受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフロー内のアクティビティのアップストリームを定義します。住所が指定されていないプロファイルは、ダイレクトメールが準備されると自動的に除外されます。

メッセージの実行パラメーターに従ってメッセージの準備がトリガーされます。メッセージダッシュボードから、メッセージを送信するかどうかを手動で確認できます（デフォルトで必須）。ワークフローを手動で開始することも、ワークフローにスケジューラーアクティビティを配置して実行を自動化することもできます。

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Direct mail delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. このボタンは、チャネルアクティビティに固有のボタンです。ダイレクトメールのプロパティには、ダイレクトメールダッシュボードのアクションバーからアクセスできます。

1. ダイレクトメール送信モードを選択します。

   * **[!UICONTROL Direct mail]**:ダイレクトメールが1回送信されます。アクティビティにアウトバウンドトランジションを追加するかどうかを指定できます。この手順の手順7では、様々な移行タイプについて説明しています。
   * **[!UICONTROL Recurring direct mail]**: **[!UICONTROL Scheduler]** アクティビティで定義された頻度に従って、ダイレクトメールが数回送信されます。送信の集計期間を選択します。This allows you to regroup all the sends that occur during the defined period in one single direct mail that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      例えば、定期的に誕生日のメールが処理された場合、毎月送信するように選択できます。これにより、メールは毎日処理されるので、配信に関するレポートを毎月受信できます。

      >[!NOTE]
      >
      >定期的なダイレクトメールの場合、ワークフローの実行ごとに新しいファイルが生成されます。選択した集計期間は、この動作に影響しません。

1. ダイレクトメールタイプを選択します。The direct mail types come from templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. ダイレクトメールの一般的なプロパティを入力します。既存のキャンペーンにも添付できます。ワークフローの配信アクティビティのラベルが、ダイレクトメールラベルで更新されます。
1. ダイレクトメールのコンテンツを定義します。[コンテンツの編集](../../designing/using/about-personalization.md)に関するセクションを参照してください。
1. By default, the **[!UICONTROL Direct mail delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Direct mail delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**:これにより、インバウンドトランジションとまったく同じ訪問者を含むアウトバウンドトランジションを生成できます。この移行には、ダイレクトメールアクティビティによって生成されたファイルと、ダイレクトメールアクティビティによって受信された生の母集団が含まれます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、ダイレクトメールを送信する母集団を含むアウトバウンドトランジションを生成できます。ダイレクトメール準備中に除外されるターゲットのメンバー（強制隔離、無効なアドレスなど）は、この移行から除外されます。この移行には、ダイレクトメールによって生成されたファイルも含まれます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、直接ダイレクトメールダッシュボードに移動します。編集できるのはコンテンツのみです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみが開始されます。ワークフローを開始した後でもワークフローから作成されたメッセージを送信する必要があります。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. このオプションのチェックを解除すると、準備が完了すると、それ以上通知なしでメッセージが送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。ダイレクトメールサマリペインのリンクを使用すると、リンクされた要素（定期的なダイレクトメールの場合にはワークフロー、キャンペーン、親配信）に直接アクセスできます。

![](assets/wkf_display_parent_elements_direct_mail.png)

定期配信の実行は、デフォルトでマスクされます。To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of mails that have been processed (according to the aggregation period specified when the **[!UICONTROL Direct mail delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## Example {#example}

**[!UICONTROL Direct mail delivery]**[「ダイレクトメール](../../channels/using/example-of-direct-mail-in-a-workflow.md) 」の章では、この例を使用できます。
