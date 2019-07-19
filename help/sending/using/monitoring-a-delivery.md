---
title: 配信の監視
seo-title: 配信の監視
description: 配信の監視
seo-description: 配信の監視方法を確認します。
page-status-flag: 常にアクティブ化されていない
uuid: 7772c607- deld-40fd-8322-4d49119979b4
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 送信中
content-type: 参照
topic-tags: 監視メッセージ
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: delivery， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Monitoring a delivery{#monitoring-a-delivery}

配信を監視し、その影響を測定するには、いくつかの方法があります。

* **メッセージログ**:これらのログには、メッセージダッシュボードから直接アクセスできます。送信の詳細、除外されたターゲット、および開封やクリックなどのトラッキング情報が表示されます。

   To view the message logs, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   Several tabs contain information (if it exists) regarding the **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** and **[!UICONTROL Tracked URLs]**. [配信ログ](../../sending/using/monitoring-a-delivery.md#delivery-logs)を参照してください。

   ![](assets/sending_delivery1.png)

   ログには、配信と配達確認に関するすべてのメッセージが含まれています。特定のアイコンを使用すると、エラーや警告を特定できます。For more on this, see [Approving messages](../../sending/using/previewing-messages.md).

   You can export the log by clicking the **[!UICONTROL Export list]** button.

   ![](assets/sending_delivery2.png)

* **配信アラート**:配信成功または失敗を追跡するために、Adobe Campaignは通知システムを提供して、重要なシステムアクティビティをユーザーに通知する通知を送信します。
* **レポート**:メッセージダッシュボードから、この特定のメッセージに関する複数のレポートにアクセスできます。You also have a **[!UICONTROL Reports]** menu that allows you to access a complete list of built-in or custom reports that you can use to outline specific metrics related to your message or campaign.
* 管理者は、独自のレポートまたはBIツールで処理できる別のファイルにログをエクスポートすることもできます。For more on this, see [Exporting logs](../../automating/using/exporting-logs.md).

**関連トピック:**

* [エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)
* [レポート](../../reporting/using/about-dynamic-reports.md)

## Delivery logs {#delivery-logs}

### Sending logs {#sending-logs}

**[!UICONTROL Sending logs]** このタブには、この配信のすべてのオカレンスの履歴が表示されます。送信されたメッセージとそのステータスは、ここに保存されます。これにより、各受信者の配信ステータスを表示できます。

**[!UICONTROL Sent]** ステータスを持つプロファイルごとに **[!UICONTROL Date]** 、メッセージが送信されたときに列が表示されます。

![](assets/sending_delivery3.png)

### Exclusion logs {#exclusion-logs}

**[!UICONTROL Exclusion logs]** タブには、送信されたターゲットから除外されたすべてのメッセージが一覧表示され、送信失敗の理由が指定されます。

![](assets/sending_delivery4.png)

### Exclusion causes {#exclusion-causes}

**[!UICONTROL Exclusion causes]** このタブには、ターゲット送信から除外されたメッセージのボリューム（メッセージ数）が表示されます。

![](assets/sending_delivery5.png)

