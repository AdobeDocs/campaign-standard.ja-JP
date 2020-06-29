---
title: 電子メール配信
description: 電子メール配信アクティビティを使用すると、ワークフローで単一の送信電子メールまたは定期的な電子メールを送信する設定ができます。
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 2%

---


# 電子メール配信{#email-delivery}

## 説明 {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

この **[!UICONTROL Email delivery]** アクティビティでは、ワークフローでの電子メールの送信を設定できます。 これは、 **単一の送信** (Send **)電子メールで1回だけ送信するか、** 定期的な電子メールにすることができます。

単一の送信電子メールは、1回だけ送信される標準的な電子メールです。

定期的な電子メールを使用すると、定義した期間に同じ電子メールを複数の異なるターゲットに複数回送信できます。 期間ごとの配信を集計して、ニーズに合ったレポートを取得できます。

## 使用状況 {#context-of-use}

The **[!UICONTROL Email delivery]** activity is generally used to automate sending an email to a target calculated in the same workflow.

スケジューラーにリンクすると、定期的な電子メールを定義できます。

電子メール受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフローのアクティビティの上流に定義されます。

メッセージ作成は、ワークフロー実行パラメータに従ってトリガされる。 メッセージダッシュボードから、手動で確認を行ってメッセージを送信するかどうかを選択できます（デフォルトでは必須）。 ワークフローは、手動で開始するかまたはワークフロー内にスケジューラーアクティビティを置いて自動的に実行させます。

**関連トピック：**

* [使用例： 週に1回の電子メール配信の作成](../../automating/using/workflow-weekly-offer.md)
* [使用例： 場所でセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [使用例： 補完的な配信の作成](../../automating/using/workflow-created-query-with-complement.md)
* [使用例： 非開封者に新しい配信を送信する再ターゲティングワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)
* [使用例： 誕生日配信](../../automating/using/birthday-delivery.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Email delivery]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、アクティビティの一般的なプロパティや詳細なオプション(配信自体ではなく)にアクセスできます。 このボタンは、 **[!UICONTROL Email delivery]** アクティビティに固有です。 電子メールのプロパティは、電子メールダッシュボードのアクションバーからアクセスできます。

1. 電子メール送信モードを選択します。

   * **[!UICONTROL Email]**: 電子メールは1回送信されます。 外部トランジションをアクティビティに追加するかどうかを指定できます。 様々なトランジションタイプについては、この手順の手順7で説明します。
   * **[!UICONTROL Recurring email]**: 電子メールは、 **[!UICONTROL Scheduler]** アクティビティで定義されている頻度に従って、複数回送信されます。 送信の集計期間を選択します。 これにより、1つの電子メールの中で定義した期間に発生したすべての送信を再グループ化できます。この電子メールは **定期的な実行** とも呼ばれ、アプリのマーケティングアクティビティリストからアクセスできます。

      例えば、誕生日の電子メールを毎日送信する場合は、1か月あたりの送信を集計できます。 これにより、電子メールは毎日送信されますが、配信のレポートを毎月受け取ることができます。
   >[!NOTE]
   >
   >反復配信は、 **集計期間に基づいて作成される**。 たとえば、集計期間が「日別」の場合、配信は1日に1回のみ再準備されます。 このワークフローを1日に複数回呼び出す場合は、を使用し [!UICONTROL No aggregation]ます。

1. 電子メールのタイプを選択します。 電子メールのタイプは、 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Delivery templates]** メニューで定義された電子メールテンプレートに基づいています。
1. 電子メールの一般的なプロパティを入力します。 既存のキャンペーンに添付することもできます。 ワークフローの配信アクティビティのラベルが電子メールラベルで更新されます。
1. 電子メールコンテンツを定義します。 コン [テンツ編集に関する項を参照](../../designing/using/designing-content-in-adobe-campaign.md)。
1. デフォルトでは、 **[!UICONTROL Email delivery]** アクティビティには送信トランジションは含まれません。 外部トランジションを **[!UICONTROL Email delivery]** アクティビティに追加する場合は、[詳細アクティビティ]タブ(アクティビティのクイックアクションの **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) ボタン)に移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**: これにより、受信トランジションと完全に同じ母集団を含む送信トランジションを生成できます。
   * **[!UICONTROL Add outbound transition with the population]**: これにより、電子メールの送信先の訪問者を含むアウトバウンドトランジションを生成できます。 配信の準備(強制隔離、無効な電子メールなど)中に除外されたターゲットのメンバー をこのトランジションから除外します。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、電子メールダッシュボードに直接送信されます。 編集できるのは、そのコンテンツだけです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローを開始した後も、ワークフローから作成されたメッセージの送信を確認する必要があります。 ただし、メッセージダッシュボードから、およびメッセージがワークフローから作成された場合のみ、この **[!UICONTROL Request confirmation before sending messages]** オプションを無効にできます。 このオプションをオフにすると、準備が完了した後、メッセージは予告なしに送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリのマーケティングアクティビティリストからアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 電子メールの概要ペインのリンクを使用すると、リンクされた配信(定期的な電子メールの場合は、ワークフロー、キャンペーン、親要素)に直接アクセスできます。

![](assets/wkf_display_recurrent_executions_2.png)

ただし、定期配信の実行は、デフォルトでマスクされます。 表示するには、マーケティングアクティビティの検索パネルで **[!UICONTROL Show recurring executions]** オプションを選択します。

![](assets/wkf_display_recurrent_executions.png)

マーケティングアクティビティリストから、または関連する繰り返し実行を介して直接アクセスできる親配信では、処理された送信の総数を表示できます( **[!UICONTROL Email delivery]** アクティビティの設定時に指定した集計期間に従います)。 これを行うには、を選択して親配信の **[!UICONTROL Deployment]** ブロックの詳細表示を開き ![](assets/wkf_dlv_detail_button.png)ます。

![](assets/wkf_display_recurrent_executions_3.png)
