---
title: 送信の確認
seo-title: 送信の確認
description: 送信の確認
seo-description: メッセージの準備を終える方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 1eab32- ffd2-45d0- a8b4- f97ee59a1bd
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 送信および追跡メッセージ
discoiquuid: 8bb160b1-7de9-4c1f- bb89- b2e5fubafed41
context-tags: 配信，デプロイメント，戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e9dd7c374903d0c57ac4881ed125c3215bd7fe11

---


# Confirming the send{#confirming-the-send}

メッセージの準備が完了し、承認手順が実行されたら、送信できます。For more on messages preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

**[!UICONTROL Start deliveries]** その役割を持つユーザーのみが送信を確認できます。For more on this, refer to the [List of roles](../../administration/using/list-of-roles.md) section.

このロールを持たないユーザーには、次のメッセージが表示されます。

![](assets/confirm_delivery_2.png)

To send your delivery, click the **[!UICONTROL Confirm send]** button found in the message's action bar.

![](assets/confirm_delivery.png)

**[!UICONTROL OK]** ボタンをクリックして送信を確定するように求められます。

![](assets/confirm_delivery1.png)

メッセージが送信されています。

>[!NOTE]
>
>メッセージがスケジュールされている場合は、送信時に送信されます。For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

集計期間のない定期配信を使用している場合は、配信の送信前に確認を要求できます。To do this, open the **[!UICONTROL Schedule]** block of the delivery dashboard, then activate the dedicated option.

![](assets/confirmation_recurring_deliveries.png)

**[!UICONTROL Deployment]** ブロックは送信の進行状況を示します。

Once the message is sent to the contacts, the **[!UICONTROL Deployment]** zone shows your KPIs (Key Performance Indicator) data , including:

* 配信するメッセージの数
* 送信されるメッセージの数
* 配信されるメッセージのパーセント
* バウンスとエラーの割合
* 開くメッセージの割合
* メッセージ内のクリック数のパーセント（電子メール用）

   >[!NOTE]
   >
   >The **[!UICONTROL Open rate]** and **[!UICONTROL Click-through rate]** are updated every hour.

![](assets/sending_delivery.png)

If the KPIs take too long to update or don't take into account the results from the sending logs, click the **[!UICONTROL Compute stats]** button in the **[!UICONTROL Deployment]** window.

![](assets/sending_delivery7.png)

メッセージは、オーディエンスの一部を構成するクライアントプロファイルの履歴で表示できます。See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

メッセージが送信されると、受信者の行動を追跡し、その受信者の行動を測定するために監視できます。これについて詳しくは、以下のセクションを参照してください。

* [メッセージの追跡](../../sending/using/tracking-messages.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)

