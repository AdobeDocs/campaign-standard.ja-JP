---
solution: Campaign Standard
product: campaign
title: 送信の確認
description: メッセージの準備を完了する方法について説明します。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 8c636ec7a35e9c34210bbb04b1b13aaa6a431345
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 22%

---


# 送信の確認{#confirming-the-send}

メッセージの準備と承認手順が完了したら、メッセージを送信できます。メッセージの準備について詳しくは、[送信の準備](../../sending/using/preparing-the-send.md)を参照してください。

送信を確認できるのは、**[!UICONTROL Start deliveries]** 役割を持つユーザーのみです。詳しくは、[役割のリスト](../../administration/using/list-of-roles.md)の節を参照してください。

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## メッセージの送信 {#sending-message}

準備が完了したら、次の手順に従ってメッセージを送信します。

1. メッセージのアクションバーにある&#x200B;**[!UICONTROL Confirm send]**&#x200B;ボタンをクリックします。

   ![](assets/confirm_delivery.png)

1. **[!UICONTROL OK]**&#x200B;ボタンをクリックして送信を終了します。

   ![](assets/confirm_delivery1.png)

1. メッセージが送信されるまで待ちます。 **[!UICONTROL Deployment]** ブロックには、送信の進行状況が表示されます。

>[!NOTE]
>
>メッセージがスケジュールされている場合、送信時間に達すると送信されます。メッセージのスケジュールについて詳しくは、[この節](../../sending/using/about-scheduling-messages.md)を参照してください。

集計期間のない繰り返し配信を使用している場合は、配信が送信される前に確認をリクエストできます。これを行うには、メッセージを設定する際に、配信ダッシュボードの&#x200B;**[!UICONTROL Schedule]**&#x200B;ブロックを開き、専用のオプションを有効にします。

![](assets/confirmation_recurring_deliveries.png)

## メッセージインジケータについて{#message-indicators}

メッセージが連絡先に送信されると、**[!UICONTROL Deployment]** ゾーンには次のような KPI（主要業績評価指標）データが表示されます。

* 配信するメッセージの数
* 送信されたメッセージの数
* 配信されたメッセージの割合
* バウンスとエラーの割合
* メッセージの開封率
* メッセージ内クリック率（E メールの場合）

   >[!NOTE]
   >
   >**[!UICONTROL Open rate]** と **[!UICONTROL Click-through rate]** は、1 時間ごとに更新されます。

![](assets/sending_delivery.png)

KPIの更新に時間がかかりすぎる場合、または送信ログの結果を考慮に入れない場合は、**[!UICONTROL Deployment]**&#x200B;ウィンドウの&#x200B;**[!UICONTROL Compute stats]**&#x200B;ボタンをクリックします。

![](assets/sending_delivery7.png)

メッセージは、対象となるプロファイルの1つの履歴で表示できます。 [統合された顧客プロファイル](../../audiences/using/integrated-customer-profile.md)を参照してください。

メッセージが送信されたら、メッセージの動作を追跡し、受信者の影響を監視できます。 詳しくは、以下の節を参照してください。

* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)

### 配信成功レポート{#delivered-status-report}

>[!NOTE]
>
>この節は電子メールチャネルにのみ適用されます。

各電子メールの&#x200B;**[!UICONTROL Summary]**&#x200B;表示では、**[!UICONTROL Delivered]**&#x200B;開始の割合が100%に達し、次に配信[有効期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)を通して徐々に下がります。これは、ソフトバウンスとハードバウンスが<!--from the Enhanced MTA to Campaign-->に返されるからです。

実際、すべてのメッセージは、キャンペーンから拡張MTA(Message Transfer Agent)に正常に中継されると、[送信ログ](../../sending/using/monitoring-a-delivery.md#sending-logs)に&#x200B;**[!UICONTROL Sent]**&#x200B;として表示されます。 メッセージの[バウンス](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)が拡張MTAからキャンペーンに返されるまで、これらのメッセージはそのステータスのままです。

強化されたMTAからハードバウンスメッセージが報告されると、そのステータスが&#x200B;**[!UICONTROL Sent]**&#x200B;から&#x200B;**[!UICONTROL Failed]**&#x200B;に変わり、それに応じて&#x200B;**[!UICONTROL Delivered]**&#x200B;の割合が減少します。

ソフトバウンスメッセージが拡張MTAから返されると、**[!UICONTROL Sent]**&#x200B;と表示され、**[!UICONTROL Delivered]**&#x200B;の割合はまだ更新されません。 ソフトバウンスメッセージは、配信の有効期間全体で[再試行](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)されます。

* 有効期間の終了前に再試行が成功した場合、メッセージのステータスは&#x200B;**[!UICONTROL Sent]**&#x200B;のままで、**[!UICONTROL Delivered]**&#x200B;の割合は変更されません。

* それ以外の場合は、ステータスが&#x200B;**[!UICONTROL Failed]**&#x200B;に変わり、それに応じて&#x200B;**[!UICONTROL Delivered]**&#x200B;の割合が減少します。

その結果、有効期間の終わりまで待って、最終的な&#x200B;**[!UICONTROL Delivered]**&#x200B;の割合と、実際に&#x200B;**[!UICONTROL Sent]**&#x200B;と&#x200B;**[!UICONTROL Failed]**&#x200B;のメッセージの最終回数を確認する必要があります。

### 電子メールフィードバックサービス（ベータ版） {#email-feedback-service}

Email Feedback Service(EFS)機能を使用すると、フィードバックが拡張MTA(Message Transfer Agent)から直接取り込まれるので、各電子メールのステータスが正確にレポートされます。

>[!IMPORTANT]
>
>電子メールフィードバックサービスは、現在ベータ版機能としてご利用いただけます。

配信が起動したら、キャンペーンから拡張MTAにメッセージが正常に中継された場合に、**[!UICONTROL Delivered]**&#x200B;の割合に変更はありません。

![](assets/efs-sending.png)

配信ログには、対象アドレスごとに&#x200B;**[!UICONTROL Pending]**&#x200B;ステータスが表示されます。

![](assets/efs-pending.png)

メッセージが対象プロファイルに実際に配信され、この情報が拡張MTAからリアルタイムでレポートされると、配信ログは、メッセージを受信した各アドレスの&#x200B;**[!UICONTROL Sent]**&#x200B;ステータスを示します。 **[!UICONTROL Delivered]**&#x200B;の割合は、配信が成功するたびに増加します。

強化されたMTAからハードバウンスメッセージが報告されると、そのログステータスが&#x200B;**[!UICONTROL Pending]**&#x200B;から&#x200B;**[!UICONTROL Failed]**&#x200B;に変わり、それに応じて&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;の割合が増えます。

ソフトバウンスメッセージが拡張MTAから返されると、ログのステータスも&#x200B;**[!UICONTROL Pending]**&#x200B;から&#x200B;**[!UICONTROL Failed]**&#x200B;に変わり、それに応じて&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;の割合が増えます。 **[!UICONTROL Delivered]**&#x200B;の割合は変更されません。 その後、ソフトバウンスメッセージが配信[有効期間](../../administration/using/configuring-email-channel.md#validity-period-parameters)を通して再試行されます。

* 有効期間の終了前に再試行が成功した場合、メッセージのステータスは&#x200B;**[!UICONTROL Sent]**&#x200B;に変わり、それに応じて&#x200B;**[!UICONTROL Delivered]**&#x200B;の割合が増えます。

* それ以外の場合は、ステータスは&#x200B;**[!UICONTROL Failed]**&#x200B;のままです。 **[!UICONTROL Delivered]**&#x200B;と&#x200B;**[!UICONTROL Bounces + errors]**&#x200B;の割合は変更されません。

>[!NOTE]
>
>ハードバウンスとソフトバウンスの詳細については、[このセクション](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)を参照してください。
>
>配信の一時的なエラー後の再試行について詳しくは、[このセクション](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)を参照してください。

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### EFSによって導入された変更{#changes-introduced-by-efs}

次の表に、KPIの変更と、EFS機能によって導入された送信ログのステータスを示します。

| <br>送信プロセスのステップ | KPIサマリ<br>EFSなし | ログの状態<br>EFSなしの送信 | KPIサマリ<br>EFSあり | ログの状態<br>EFSを送信中 |
|--- |--- |--- | --- | --- |
| キャンペーンから拡張MTAへのメッセージの転送が正常に行われました | <ul><li>**[!UICONTROL Delivered]** 100%の開始数</li><li>**[!UICONTROL Bounces + errors]** 0%での開始の割合</li></ul> | 送信済み | <ul><li>**[!UICONTROL Delivered]** 0%での開始の割合</li><li>**[!UICONTROL Bounces + errors]** 0%での開始の割合</li></ul> | 保留中 |
| 強化されたMTAからハードバウンスメッセージが返される | <ul><li>**[!UICONTROL Delivered]** それに応じて割合が減少する</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が増加する</li></ul> | 失敗 | <ul><li>**[!UICONTROL Delivered]**&#x200B;パーセンテージに変更はありません</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が増加する</li></ul> | 失敗 |
| ソフトバウンスメッセージが拡張MTAから返される | <ul><li>**[!UICONTROL Delivered]**&#x200B;パーセンテージに変更はありません</li><li>**[!UICONTROL Bounces + errors]**&#x200B;パーセンテージに変更はありません</li></ul> | 送信済み | <ul><li>**[!UICONTROL Delivered]**&#x200B;パーセンテージに変更はありません</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が増加する</li></ul> | 失敗 |
| ソフトバウンスメッセージの再試行が成功しました | <ul><li>**[!UICONTROL Delivered]**&#x200B;パーセンテージに変更はありません</li><li>**[!UICONTROL Bounces + errors]**&#x200B;パーセンテージに変更はありません</li></ul> | 送信済み | <ul><li>**[!UICONTROL Delivered]** それに応じて割合が増加する</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が減少する</li></ul> | 送信済み |
| ソフトバウンスメッセージの再試行に失敗 | <ul><li>**[!UICONTROL Delivered]** それに応じて割合が減少する</li><li>**[!UICONTROL Bounces + errors]** それに応じて割合が増加する</li></ul> | 失敗 | <ul><li> **[!UICONTROL Delivered]**&#x200B;パーセンテージに変更はありません </li><li> **[!UICONTROL Bounces + errors]**&#x200B;パーセンテージに変更はありません </li></ul> | 失敗 |
