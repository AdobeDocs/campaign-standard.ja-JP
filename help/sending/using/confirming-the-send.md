---
title: 送信の確認
description: メッセージの準備を完了する方法について説明します。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 0a0fe969-cdfd-4b0c-a746-081038424d86
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 41%

---

# 送信の確認{#confirming-the-send}

メッセージの準備と承認手順が完了したら、メッセージを送信できます。メッセージの準備について詳しくは、[送信の準備](../../sending/using/preparing-the-send.md)を参照してください。

次の条件を満たすユーザーのみ： **[!UICONTROL Start deliveries]** ロールが送信を確認できます。 詳しくは、[役割のリスト](../../administration/using/list-of-roles.md)の節を参照してください。

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## メッセージの送信 {#sending-message}

準備が完了したら、次の手順に従ってメッセージを送信します。

1. 次をクリック： **[!UICONTROL Confirm send]** ボタンが表示されます。

   ![](assets/confirm_delivery.png)

1. 「 **[!UICONTROL OK]** 」ボタンをクリックします。

   ![](assets/confirm_delivery1.png)

1. メッセージが送信されるまでお待ちください。 **[!UICONTROL Deployment]** ブロックには、送信の進行状況が表示されます。

>[!NOTE]
>
>メッセージがスケジュールされている場合、送信時間に達すると送信されます。 メッセージのスケジュールについて詳しくは、[この節](../../sending/using/about-scheduling-messages.md)を参照してください。

集計期間のない繰り返し配信を使用している場合は、配信が送信される前に確認をリクエストできます。メッセージを設定する際に、 **[!UICONTROL Schedule]** 配信ダッシュボードのブロックを選択し、該当するオプションを有効化します。

![](assets/confirmation_recurring_deliveries.png)

## メッセージ指標について {#message-indicators}

メッセージが連絡先に送信されると、 **[!UICONTROL Deployment]** ゾーンには、次のような KPI（主要業績評価指標）データが表示されます。

* 配信するメッセージの数
* 送信されたメッセージの数
* 配信されたメッセージの割合
* バウンスとエラーの割合
* メッセージの開封率
* メッセージ内クリック率（メールの場合）

  >[!NOTE]
  >
  >**[!UICONTROL Open rate]** と **[!UICONTROL Click-through rate]** は、1 時間ごとに更新されます。

![](assets/sending_delivery.png)

KPI の更新に時間がかかりすぎる場合、または送信ログの結果が反映されていない場合は、 **[!UICONTROL Compute stats]** ボタン **[!UICONTROL Deployment]** ウィンドウ

![](assets/sending_delivery7.png)

メッセージは、ターゲットプロファイルの 1 つの履歴で表示できます。 [統合された顧客プロファイル](../../audiences/using/integrated-customer-profile.md)を参照してください。

メッセージが送信されたら、そのメッセージの受信者の行動を追跡し、メッセージを監視して影響を測定できます。 詳しくは、以下の節を参照してください。

* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)

### 配信成功レポート {#delivered-status-report}

>[!NOTE]
>
>この節の内容は、E メールチャネルにのみ適用されます。

Adobe Analytics の **[!UICONTROL Summary]** 各電子メールのビュー、 **[!UICONTROL Delivered]** 割合は、100%から始まり、次に配信全体で徐々に減少します [有効期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)（ソフトバウンスとハードバウンスがレポートされるため）<!--from the Enhanced MTA to Campaign-->.

実際、すべてのメッセージは、 **[!UICONTROL Sent]** （内） [ログの送信](../../sending/using/monitoring-a-delivery.md#sending-logs) キャンペーンから Enhanced MTA（メッセージ転送エージェント）に正常にリレーされたら、すぐに実行します。 メッセージの[バウンス](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)が Enhanced MTA からキャンペーンに返されるまで、メッセージのステータスは変わりません。

ハードバウンスメッセージが Enhanced MTA から返されると、そのステータスは **[!UICONTROL Sent]** から **[!UICONTROL Failed]** そして **[!UICONTROL Delivered]** 割合は、それに応じて減少します。

ソフトバウンスメッセージが Enhanced MTA から返された場合、それらは引き続き **[!UICONTROL Sent]** そして **[!UICONTROL Delivered]** 割合はまだ更新されていません。 ソフトバウンスメッセージは、配信の有効期間中ずっと[再試行](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)されます。

* 有効期間が終了する前に再試行が成功した場合、メッセージのステータスは「 **[!UICONTROL Sent]** そして **[!UICONTROL Delivered]** 割合は変更されません。

* それ以外の場合、ステータスは「 **[!UICONTROL Failed]** そして **[!UICONTROL Delivered]** 割合は、それに応じて減少します。

したがって、最終的な **[!UICONTROL Delivered]** 割合、および最終的な数 **[!UICONTROL Sent]** および **[!UICONTROL Failed]** メッセージ。

### メールフィードバックサービス（ベータ版） {#email-feedback-service}

メールフィードバックサービス（EFS）機能を使用すると、フィードバックが Enhanced MTA（メッセージ転送エージェント）から直接取り込まれるので、各メールのステータスが正確にレポートされます。

>[!IMPORTANT]
>
>メールフィードバックサービスは、現在ベータ版機能としてご利用いただけます。

配信が開始された後も、 **[!UICONTROL Delivered]** メッセージが Campaign から Enhanced MTA に正常にリレーされた場合の割合。

![](assets/efs-sending.png)

配信ログには、 **[!UICONTROL Pending]** 各ターゲットアドレスのステータス。

![](assets/efs-pending.png)

ターゲットプロファイルに対するメッセージ配信が Enhanced MTA からリアルタイムでレポートされると、配信ログに **[!UICONTROL Sent]** メッセージを正常に受信した各アドレスのステータス。 The **[!UICONTROL Delivered]** 配信が成功するたびに、割合が増えます。

ハードバウンスメッセージが Enhanced MTA から返されると、ログのステータスは **[!UICONTROL Pending]** から **[!UICONTROL Failed]** そして **[!UICONTROL Bounces + errors]** 割合は、それに応じて増加します。

ソフトバウンスメッセージが Enhanced MTA から返されると、ログのステータスも **[!UICONTROL Pending]** から **[!UICONTROL Failed]** そして **[!UICONTROL Bounces + errors]** 割合は、それに応じて増加します。 The **[!UICONTROL Delivered]** 割合は変更されません。 その後、ソフトバウンスメッセージが配信[有効期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)中ずっと再試行されます。

* 有効期間が終了する前に再試行が成功した場合、メッセージのステータスは「 **[!UICONTROL Sent]** そして **[!UICONTROL Delivered]** 割合は、それに応じて増加します。

* それ以外の場合、ステータスは「 **[!UICONTROL Failed]**. The **[!UICONTROL Delivered]** および **[!UICONTROL Bounces + errors]** パーセンテージは変更されません。

>[!NOTE]
>
>ハードバウンスとソフトバウンスについて詳しくは、[この節](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)を参照してください。
>
>一時的な配信エラー後の再試行について詳しくは、[この節](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)を参照してください。

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### EFS によって導入された変更 {#changes-introduced-by-efs}

次の表に、KPI の変更と、EFS 機能によって導入された送信ログのステータスを示します。

**メールフィードバックサービスを使用する**

| 送信プロセスの手順 | KPI 概要 | 送信ログのステータス |
|--- |--- |--- |
| Campaign から Enhanced MTA にメッセージが正常に転送される | <ul><li>**[!UICONTROL Delivered]** 0%から始まる割合</li><li>**[!UICONTROL Bounces + errors]** 0%から始まる割合</li></ul> | 保留中 |
| Enhanced MTA からハードバウンスメッセージが返される | <ul><li>変更なし **[!UICONTROL Delivered]** 割合</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が増加します</li></ul> | 失敗 |
| ソフトバウンスメッセージが Enhanced MTA から返される | <ul><li>変更なし **[!UICONTROL Delivered]** 割合</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が増加します</li></ul> | 失敗 |
| ソフトバウンスメッセージの再試行が成功する | <ul><li>**[!UICONTROL Delivered]** それに応じて割合が増加します</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が減少する</li></ul> | 送信済み |
| ソフトバウンスメッセージの再試行に失敗する | <ul><li> 変更なし **[!UICONTROL Delivered]** 割合 </li><li> 変更なし **[!UICONTROL Bounces + errors]** 割合 </li></ul> | 失敗 |

**メールフィードバックサービスを使用しない**

| 送信プロセスの手順 | KPI 概要 | 送信ログのステータス |
|--- |--- |--- |
| Campaign から Enhanced MTA にメッセージが正常に転送される | <ul><li>**[!UICONTROL Delivered]** 100%から始まる割合</li><li>**[!UICONTROL Bounces + errors]** 0%から始まる割合</li></ul> | 送信済み |
| Enhanced MTA からハードバウンスメッセージが返される | <ul><li>**[!UICONTROL Delivered]** それに応じて割合が減少する</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が増加します</li></ul> | 失敗 |
| ソフトバウンスメッセージが Enhanced MTA から返される | <ul><li>変更なし **[!UICONTROL Delivered]** 割合</li><li>変更なし **[!UICONTROL Bounces + errors]** 割合</li></ul> | 送信済み |
| ソフトバウンスメッセージの再試行が成功する | <ul><li>変更なし **[!UICONTROL Delivered]** 割合</li><li>変更なし **[!UICONTROL Bounces + errors]** 割合</li></ul> | 送信済み |
| ソフトバウンスメッセージの再試行に失敗する | <ul><li>**[!UICONTROL Delivered]** それに応じて割合が減少する</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が増加します</li></ul> | 失敗 |
