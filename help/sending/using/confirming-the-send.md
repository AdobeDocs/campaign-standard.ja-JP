---
title: 送信の確認
description: メッセージの準備を完了する方法について説明します。
page-status-flag: never-activated
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---


# 送信の確認{#confirming-the-send}

メッセージの準備と承認手順が完了したら、メッセージを送信できます。メッセージの準備について詳しくは、[送信の準備](../../sending/using/preparing-the-send.md)を参照してください。

送信を確認できるのは、**[!UICONTROL Start deliveries]** 役割を持つユーザーのみです。詳しくは、[役割のリスト](../../administration/using/list-of-roles.md)の節を参照してください。

この役割を持たないユーザーには、次のメッセージが表示されます。

![](assets/confirm_delivery_2.png)

配信を送信するには、メッセージのアクションバーにある「**[!UICONTROL Confirm send]**」ボタンをクリックします。

![](assets/confirm_delivery.png)

「**[!UICONTROL OK]**」ボタンをクリックして送信を完了するように求められます。

![](assets/confirm_delivery1.png)

メッセージが送信中になります。

>[!NOTE]
>
>メッセージがスケジュールされている場合、送信時間に達すると送信されます。メッセージのスケジュールについて詳しくは、[この節](../../sending/using/about-scheduling-messages.md)を参照してください。

集計期間のない繰り返し配信を使用している場合は、配信が送信される前に確認をリクエストできます。これをおこなうには、配信ダッシュボードの **[!UICONTROL Schedule]** ブロックを開き、該当するオプションを有効化します。

![](assets/confirmation_recurring_deliveries.png)

**[!UICONTROL Deployment]** ブロックには、送信の進行状況が表示されます。

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

KPI の更新に時間がかかりすぎる場合、または送信ログの結果が考慮されていない場合は、**[!UICONTROL Deployment]** ウィンドウの「**[!UICONTROL Compute stats]**」ボタンをクリックします。

![](assets/sending_delivery7.png)

メッセージは、オーディエンスの一部を構成するクライアントプロファイルの 1 つの履歴で表示できます。[統合された顧客プロファイル](../../audiences/using/integrated-customer-profile.md)を参照してください。

メッセージが送信されると、そのメッセージの受信者の行動を追跡および監視して、メッセージの影響を測定できます。詳しくは、以下の節を参照してください。

* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)

