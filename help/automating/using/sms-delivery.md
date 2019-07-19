---
title: SMS配信
seo-title: SMS配信
description: SMS配信
seo-description: SMS配信アクティビティを使用すると、ワークフローで単一の送信SMSまたは定期的なSMSを送信できます。
page-status-flag: 常にアクティブ化されていない
uuid: 736078c6- ac91-4440-825b-4a6ae31894ef
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: チャネルアクティビティ
discoiquuid: 978592b8-989a-446a-8a84-12b7ffc130
context-tags: sms， main;delivery， ssContent， back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# SMS delivery{#sms-delivery}

## 説明 {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

**[!UICONTROL SMS delivery]** アクティビティでは、ワークフローでのSMSの送信を設定できます。This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.

シングル送信SMSメッセージは標準SMSで、1回送信されます。

定期的なSMSメッセージを使用すると、定義済みの期間にわたって同一のSMSを複数回異なるターゲットに送信できます。期間ごとの配信を集計して、ニーズに対応するレポートを取得できます。

## Context of use {#context-of-use}

**[!UICONTROL SMS delivery]** このアクティビティは、一般に、同じワークフローで計算されたターゲットにSMSを送信するために使用されます。

スケジューラーにリンクすると、定期的なSMSメッセージを定義できます。

SMS受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフロー内のアクティビティのアップストリームを定義します。

メッセージの実行パラメーターに従ってメッセージの準備がトリガーされます。メッセージダッシュボードから、メッセージを送信するかどうかを手動で確認できます（デフォルトで必須）。ワークフローを手動で開始することも、ワークフローにスケジューラーアクティビティを配置して実行を自動化することもできます。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL SMS delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button in the workflow's action bar. This button is specific to the **[!UICONTROL SMS delivery]** activity. SMSプロパティには、SMSダッシュボードのアクションバーからアクセスできます。

1. SMS送信モードを選択します。

   * **[!UICONTROL SMS]**:SMSが1回送信されます。アクティビティにアウトバウンドトランジションを追加するかどうかを指定できます。この手順の手順7では、様々な移行タイプについて説明しています。
   * **[!UICONTROL Recurring SMS]**:SMSは **[!UICONTROL Scheduler]** 、アクティビティに定義されている頻度に従って複数回送信されます。送信の集計期間を選択します。This allows you to regroup all the sends that occur during the defined period into one single view that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      例えば、定期的に誕生日のSMSを送信する場合、毎月送信するように選択できます。これにより、SMSは毎日送信されるので、配信に関するレポートを毎月受信できます。

1. SMSタイプを選択します。The SMS types come from SMS templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. SMSの一般的なプロパティを入力します。既存のキャンペーンにも添付できます。ワークフローの配信アクティビティのラベルがSMSラベルで更新されます。
1. SMSコンテンツを定義します。Refer to the section concerning [Creating an SMS message](../../channels/using/creating-an-sms-message.md).
1. By default, the **[!UICONTROL SMS delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL SMS delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**:これにより、インバウンドトランジションとまったく同じ訪問者を含むアウトバウンドトランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**:これにより、SMSが送信された母集団を含むアウトバウンドトランジションを生成できます。配信準備中に除外されるターゲットのメンバー（強制隔離、無効な番号など）は、この移行から除外されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、そのアクティビティはSMSダッシュボードに直接表示されます。編集できるのはコンテンツのみです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみが開始されます。ワークフローを開始した後でもワークフローから作成されたメッセージを送信する必要があります。But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. このオプションのチェックを解除すると、準備が完了すると、それ以上通知なしでメッセージが送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリケーションのマーケティングアクティビティリストからアクセスできます。ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。SMSサマリペインのリンクを使用すると、リンクされた要素（定期的なSMSの場合にはワークフロー、キャンペーン、親配信）に直接アクセスできます。

定期配信の実行は、デフォルトでマスクされます。To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL SMS delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Example {#example}

![](assets/wkf_sms_example_1.png)

この例は誕生日のワークフローです。毎日、誕生日がその日のプロファイルに送信されます。これを行うには、次の手順に従います。

* **[!UICONTROL Scheduler]** これにより、毎日午前8時にワークフローを開始できます。

   ![](assets/wkf_delivery_example_2.png)

* **[!UICONTROL Query]** このアクティビティを使用すると、ワークフローが実行されるたびに、携帯電話番号と、当日に誕生日が指定されたプロファイルを計算できます。誕生日の計算は、クエリ編集ツールのパレットで使用可能な定義済みフィルターを使用して実行されます。

   ![](assets/wkf_delivery_example_3.png)

* The **[!UICONTROL SMS]** is recurring. 送信は月ごとに集計されます。そのため、1か月に送信されるすべてのSMSメッセージが1つのビューに集約されます。In one year, 365 deliveries are therefore executed but they are regrouped into 12 views (also called **recurring executions**) in the Adobe Campaign interface. 履歴とレポートの詳細は毎月表示され、送信ごとには表示されません。

   ![](assets/wkf_sms_example_4.png)

