---
title: 送信の確認
description: メッセージの準備を完了する方法を説明します。
page-status-flag: 非活性化の
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: sending-and-tracking-messages
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: 配信，デプロイ，戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 送信の確認{#confirming-the-send}

メッセージの準備が完了し、承認手順が完了したら、メッセージを送信できます。 メッセージの準備の詳細については、「送信の準備 [」を参照してください](../../sending/using/preparing-the-send.md)。

役割を持つユーザーのみ **[!UICONTROL Start deliveries]** が送信を確認できます。 詳しくは、「ロールのリスト」の節 [を参照してください](../../administration/using/list-of-roles.md) 。

このロールを持たないユーザーには、次のメッセージが表示されます。

![](assets/confirm_delivery_2.png)

配信を送信するには、メッセージのアク **[!UICONTROL Confirm send]** ションバーにあるボタンをクリックします。

![](assets/confirm_delivery.png)

ボタンをクリックして、送信を完了するように求めら **[!UICONTROL OK]** れます。

![](assets/confirm_delivery1.png)

メッセージを送信中です。

>[!NOTE]
>
>メッセージがスケジュールされている場合、送信時間に達すると送信されます。 For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

集計期間なしの定期配信を使用している場合は、配信が送信される前に確認をリクエストできます。 これを行うには、配信ダッシュボード **[!UICONTROL Schedule]** のブロックを開き、専用オプションをアクティブにします。

![](assets/confirmation_recurring_deliveries.png)

ブロッ **[!UICONTROL Deployment]** クは送信の進行状況を示します。

メッセージが連絡先に送信されると、ゾーンには次の **[!UICONTROL Deployment]** ようなKPI（主要業績評価指標）データが表示されます。

* 配信するメッセージの数
* 送信されたメッセージの数
* 配信されたメッセージの割合
* バウンスとエラーの割合
* 開いているメッセージの割合
* メッセージのクリックの割合（電子メール用）

   >[!NOTE]
   >
   >とは、 **[!UICONTROL Open rate]** 毎 **[!UICONTROL Click-through rate]** 時間更新されます。

![](assets/sending_delivery.png)

KPIの更新に時間がかかりすぎる場合や、送信ログの結果を考慮に入れない場合は、ウィンドウのボタンを **[!UICONTROL Compute stats]** クリックし **[!UICONTROL Deployment]** ます。

![](assets/sending_delivery7.png)

メッセージは、オーディエンスの一部を構成するクライアントプロファイルの履歴に表示できます。 See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

メッセージが送信されたら、受信者の行動を追跡し、その影響を測定するためにメッセージを監視できます。 詳しくは、以下の節を参照してください。

* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)

