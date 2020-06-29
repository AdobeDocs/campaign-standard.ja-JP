---
title: ダイレクトメール配信
description: ダイレクトメール配信アクティビティを使用すると、ワークフロー内で1通のダイレクトメールまたは定期的なダイレクトメールを送信するように設定できます。
page-status-flag: never-activated
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 3%

---


# ダイレクトメール配信{#direct-mail-delivery}

## 説明 {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

この **[!UICONTROL Direct mail delivery]** アクティビティを使用すると、ダイレクトメールキャンペーンに使用するプロファイルデータを含むファイルを構成および準備できます。 1回だけ使用するダイレクトメール、または **定期的なダイレクト** メールを使用できます。

標準のダイレクトメールは1回送信されます。

定期的なメールを使用すると、定義した期間に同じダイレクトメールを異なるターゲットに複数回送信できます。 期間ごとの配信を集計して、ニーズに合ったレポートを取得できます。

## 使用状況 {#context-of-use}

この **[!UICONTROL Direct mail delivery]** アクティビティは、通常、プロファイルデータを含むファイルの作成を自動化するために使用されます。 その後、このファイルをメーリング担当のパートナー/プロバイダに送信できます。

スケジューラーにリンクされた場合は、定期的なダイレクトメールを定義できます。

ダイレクトメール受信者は、クエリ、交差などのターゲットアクティビティを介して、同じワークフローのアクティビティの上流に定義されます。 住所が指定されていないプロファイルは、ダイレクトメールの作成時に自動的に除外されます。

メッセージ作成は、ワークフロー実行パラメータに従ってトリガされる。 メッセージダッシュボードから、手動で確認を行ってメッセージを送信するかどうかを選択できます（デフォルトでは必須）。 ワークフローは、手動で開始するかまたはワークフロー内にスケジューラーアクティビティを置いて自動的に実行させます。

**関連トピック：**

* [使用例： 電子メールとダイレクトメールの配信の結合](../../automating/using/coupling-email-direct-mail.md)
* [ダイレクトメールについて](../../channels/using/about-direct-mail.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Direct mail delivery]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   >[!NOTE]
   >
   >アクティビティのクイックアクションの ![](assets/dlv_activity_params-24px.png) ボタンを使用して、アクティビティの一般的なプロパティや詳細なオプション(配信自体ではなく)にアクセスできます。 このボタンは、チャネルアクティビティに固有です。 ダイレクトメールのプロパティは、ダイレクトメールダッシュボードのアクションバーからアクセスできます。

1. ダイレクトメールの送信モードを選択します。

   * **[!UICONTROL Direct mail]**: ダイレクトメールは1回だけ送信されます。 外部トランジションをアクティビティに追加するかどうかを指定できます。 様々なトランジションタイプについては、この手順の手順7で説明します。
   * **[!UICONTROL Recurring direct mail]**: ダイレクトメールは、 **[!UICONTROL Scheduler]** アクティビティで定義されている頻度に従って複数回送信されます。 送信の集計期間を選択します。 これにより、1つの「 **定期的な実行** 」とも呼ばれ、アプリのマーケティングアクティビティリストからアクセスできる、定義した期間中に発生したすべての送信を再グループ化できます。

      例えば、誕生日のメールを毎日処理する場合は、1か月あたりの送信回数を集計できます。 これにより、毎日処理されるメールでも、配信のレポートを毎月受け取ることができます。

      >[!NOTE]
      >
      >定期的なダイレクトメールの場合、ワークフローの実行のたびに新しいファイルが生成されます。 選択した集計期間は、この動作に影響を与えません。

1. ダイレクトメールの種類を選択します。 ダイレクトメールのタイプは、[ **[!UICONTROL Resources]** >] **[!UICONTROL Templates]** > [ **[!UICONTROL Delivery templates]** ]メニューで定義されたテンプレートから取得されます。
1. ダイレクトメールの一般的なプロパティを入力します。 既存のキャンペーンに添付することもできます。 ワークフローの配信アクティビティのラベルが、ダイレクトメールのラベルで更新されます。
1. ダイレクトメールの内容を定義します。 コン [テンツ編集に関する項を参照](../../designing/using/personalization.md)。
1. デフォルトでは、 **[!UICONTROL Direct mail delivery]** アクティビティには送信トランジションは含まれません。 外部トランジションを **[!UICONTROL Direct mail delivery]** アクティビティに追加する場合は、[詳細アクティビティ]タブ(アクティビティのクイックアクションの **[!UICONTROL General]**![](assets/dlv_activity_params-24px.png) ボタン)に移動し、次のいずれかのオプションをオンにします。

   * **[!UICONTROL Add outbound transition without the population]**: これにより、受信トランジションと完全に同じ母集団を含む送信トランジションを生成できます。 このトランジションには、ダイレクトメールアクティビティによって生成されたファイルと、ダイレクトメールアクティビティが受信した生の母集団が含まれます。
   * **[!UICONTROL Add outbound transition with the population]**: これにより、ダイレクトメールの送信先の母集団を含む送信トランジションを生成できます。 ダイレクトメールの準備(強制隔離、無効なアドレスなど)中に除外されたターゲットのメンバ をこのトランジションから除外します。 トランジションには、ダイレクトメールで生成されたファイルも含まれます。

1. アクティビティの設定を確認し、ワークフローを保存します。

アクティビティを再度開くと、直接ダイレクトメールダッシュボードに移動します。 編集できるのは、そのコンテンツだけです。

デフォルトでは、配信ワークフローを開始すると、メッセージの準備のみがトリガーされます。 ワークフローを開始した後も、ワークフローから作成されたメッセージの送信を確認する必要があります。 ただし、メッセージダッシュボードから、およびメッセージがワークフローから作成された場合のみ、この **[!UICONTROL Request confirmation before sending messages]** オプションを無効にできます。 このオプションをオフにすると、準備が完了した後、メッセージは予告なしに送信されます。

## Remarks {#remarks}

ワークフロー内で作成された配信は、アプリのマーケティングアクティビティリストからアクセスできます。 ダッシュボードを使用して、ワークフローの実行ステータスを表示できます。 [ダイレクトメールの概要]ウィンドウのリンクを使用すると、リンクされた配信(定期的なダイレクトメールの場合は、ワークフロー、キャンペーン、親要素)に直接アクセスできます。

![](assets/wkf_display_parent_elements_direct_mail.png)

定期配信の実行は、デフォルトでマスクされます。 表示するには、マーケティングアクティビティの検索パネルで **[!UICONTROL Show recurring executions]** オプションを選択します。

![](assets/wkf_display_recurrent_executions_direct_mail.png)

マーケティングアクティビティリストから、または関連する繰り返し実行を介して直接アクセスできる親配信では、処理されたメールの合計数を表示できます( **[!UICONTROL Direct mail delivery]** アクティビティの設定時に指定した集計期間に従います)。 これを行うには、親配信の **[!UICONTROL Deployment]** ブロックの詳細表示を開き、 ![](assets/wkf_dlv_detail_button.png) ボタンを選択します。

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
