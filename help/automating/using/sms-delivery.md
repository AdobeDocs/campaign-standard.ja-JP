---
title: SMS 配信
description: SMS配信アクティビティを使用すると、ワークフロー内で1回の送信SMSまたは定期的なSMSを送信するように設定できます。
page-status-flag: never-activated
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 16afc307df6902584624d6457954a472b11c5129
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 5%

---


# SMS 配信{#sms-delivery}

## 説明 {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

この **[!UICONTROL SMS delivery]** アクティビティでは、ワークフローでのSMSの送信を構成できます。 これは、 **単一の送信** SMSで1回だけ送信するか、 **** 定期的なSMSにすることができます。

単一の送信SMSメッセージは、1回だけ送信される標準のSMSです。

定期的なSMSメッセージを使用すると、定義した期間に同じSMSを異なるターゲットに複数回送信できます。 期間ごとの配信を集計して、ニーズに合ったレポートを取得できます。

## 使用状況 {#context-of-use}

The **[!UICONTROL SMS delivery]** activity is generally used to automate sending an SMS to a target calculated in the same workflow.

スケジューラーにリンクされている場合は、定期的なSMSメッセージを定義できます。

SMS 受信者は、同じワークフロー内アクティビティの上流でクエリやインタセクションなどのターゲティングアクティビティによって定義されます。

メッセージ作成は、ワークフロー実行パラメータに従ってトリガされる。 メッセージダッシュボードから、手動で確認を行ってメッセージを送信するかどうかを選択できます（デフォルトでは必須）。 ワークフローは、手動で開始するかまたはワークフロー内にスケジューラーアクティビティを置いて自動的に実行させます。

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL SMS delivery]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >ワークフローのアクションバーの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、アクティビティの一般的なプロパティや詳細なオプション(配信自体ではなく)にアクセスできます。 このボタンは、 **[!UICONTROL SMS delivery]** アクティビティに固有です。 SMSプロパティは、SMSダッシュボードのアクションバーからアクセスできます。

1. SMS送信モードを選択します。

   * **[!UICONTROL SMS]**: SMSは1回だけ送信されます。 外部トランジションをアクティビティに追加するかどうかを指定できます。 様々なトランジションタイプについては、この手順の手順7で説明します。
   * **[!UICONTROL Recurring SMS]**: SMSは、 **[!UICONTROL Scheduler]** アクティビティで定義されている頻度に従って、複数回送信されます。 送信の集計期間を選択します。 これにより、定義した期間に発生したすべての送信を1つの表示に再グループ化し、 **反復実行とも呼ばれ** 、アプリのマーケティングアクティビティリストからアクセスできます。

      例えば、誕生日に関する定期的なSMS（毎日送信される）の場合、1か月あたりの送信を集計できます。 これにより、毎日SMSが送信されるにもかかわらず、配信のレポートを毎月受信できます。

1. SMSの種類を選択します。 SMSタイプは、 [ **[!UICONTROL Resources]** > **[!UICONTROL Templates]** >] **[!UICONTROL Delivery templates]** メニューで定義されているSMSテンプレートから取得されます。
1. SMSの一般的なプロパティを入力します。 既存のキャンペーンに添付することもできます。 ワークフローの配信アクティビティのラベルがSMSラベルで更新されます。
1. SMSコンテンツを定義します。 SMSメッセージの [作成に関する節を参照してください](../../channels/using/creating-an-sms-message.md)。
1. デフォルトでは、 **[!UICONTROL SMS delivery]** アクティビティには送信トランジションは含まれません。 外部トランジションを **[!UICONTROL SMS delivery]** アクティビティに追加する場合は、[詳細アクティビティ]タブ(アクティビティのクイックアクションの **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) ボタン)に移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**: これにより、受信トランジションと完全に同じ母集団を含む送信トランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**: これにより、SMSの送信先の母集団を含む送信トランジションを生成できます。 配信の準備中に除外されたターゲットのメンバー(強制隔離、無効な数など) をこのトランジションから除外します。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、SMSダッシュボードに直接移動します。 編集できるのは、そのコンテンツだけです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローを開始した後も、ワークフローから作成されたメッセージの送信を確認する必要があります。 ただし、メッセージダッシュボードから、およびメッセージがワークフローから作成された場合のみ、この **[!UICONTROL Request confirmation before sending messages]** オプションを無効にできます。 このオプションをオフにすると、準備が完了した後、メッセージは予告なしに送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリのマーケティングアクティビティリストからアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 SMSサマリペインのリンクを使用すると、リンクされた配信(定期的なSMSの場合は、ワークフロー、キャンペーン、親要素)に直接アクセスできます。

ただし、定期配信の実行は、デフォルトでマスクされます。 表示するには、マーケティングアクティビティの検索パネルで **[!UICONTROL Show recurring executions]** オプションを選択します。

マーケティングアクティビティリストから、または関連する繰り返し実行を介して直接アクセスできる親配信では、処理された送信の総数を表示できます( **[!UICONTROL SMS delivery]** アクティビティの設定時に指定した集計期間に従います)。 これを行うには、を選択して親配信の **[!UICONTROL Deployment]** ブロックの詳細表示を開き ![](assets/wkf_dlv_detail_button.png)ます。
