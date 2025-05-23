---
title: Adobe Campaign Standard での配信の監視
description: Adobe Campaign Standard で配信を監視する方法について説明します。
audience: sending
content-type: reference
topic-tags: monitoring-messages
context-tags: delivery,main
feature: Performance Monitoring
role: User
level: Beginner
exl-id: ddc92077-df73-411d-a161-3263581e6945
source-git-commit: ed60bde4785da9a8cc5a6cc0efcdb24e2c1f65e3
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 79%

---

# 配信の監視{#monitoring-a-delivery}

配信を監視してその影響を測定する方法はいくつかあります。 機能管理者は、メッセージログと配信ログにアクセスできます。

>[!IMPORTANT]
>
>**[!UICONTROL Administration]** の役割と **すべて [&#128279;](../../administration/using/users-management.md#functional-administrators) ユニットへのアクセス権を持つ機能  管理者** のみが、送信ログ、メッセージログ、トラッキングログ、除外またはサブスクリプションログにアクセスできます。 管理者以外のユーザーは、これらのログをターゲットにすることができますが、これはリンクされたテーブル（プロファイル、配信）から開始します。

* **メッセージログ**：これらのログは、メッセージダッシュボードから直接アクセスできます。送信の詳細、除外されたターゲットとその理由、および開封数やクリック数などの追跡情報が表示されます。

  メッセージログを表示するには、**[!UICONTROL Deployment]** ブロックの右下にあるアイコンをクリックします。

  いくつかのタブには、**[!UICONTROL Sending logs]**、**[!UICONTROL Exclusion logs]**、**[!UICONTROL Exclusion causes]**、**[!UICONTROL Tracking logs]**、**[!UICONTROL Tracked URLs]** に関する情報（存在する場合）が含まれます。[配信ログ](#delivery-logs)を参照してください。

  ![](assets/sending_delivery1.png)

  ログには、配信と配達確認に関するすべてのメッセージが含まれます。特別なアイコンによって、エラーまたは警告を識別できます。詳しくは、[メッセージの承認](../../sending/using/previewing-messages.md)を参照してください。

  「**[!UICONTROL Export list]**」ボタンをクリックすると、ログをエクスポートすることができます。

  ![](assets/sending_delivery2.png)

* **ジョブのログ**：配信によってトリガーされたバッチジョブのリストには、「**[!UICONTROL Summary]**」ドロップダウンリストから「**[!UICONTROL Job history]**」を選択して、メッセージダッシュボードからアクセスできます。

  リストから任意のジョブを選択して、選択した **[!UICONTROL Batch job]** の詳細を表示します。

  ![](assets/sending_delivery8.png)

* **配信アラート**：配信の成功または失敗を追跡するために、Adobe Campaign は重要なシステムアクティビティをユーザーに通知するメールアラートシステムを備えています。
* **レポート**：メッセージダッシュボードから、この特定のメッセージに関する複数のレポートにアクセスできます。また、組み込みレポートやカスタムレポートの完全なリストにアクセスできる **[!UICONTROL Reports]** メニューもあり、メッセージやキャンペーンに関連する特定の指標の概要を示すのに使用できます。
* 管理者は、独自のレポートまたは BI ツールで処理できる個別のファイルにログをエクスポートすることもできます。詳しくは、[ログのエクスポート](../../automating/using/exporting-logs.md)を参照してください。

**関連トピック：**

* [エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)
* [レポート](../../reporting/using/about-dynamic-reports.md)

## 配信ログ {#delivery-logs}

### 送信ログ {#sending-logs}

「**[!UICONTROL Sending logs]**」タブには、この配信のすべての発生履歴が表示されます。送信されたメッセージのリストとそのステータスがここに保存されます。各受信者の配信ステータスを表示できます。

**[!UICONTROL Date]** 列には、「**[!UICONTROL Sent]**」ステータスを持つ各プロファイルに対してメッセージが送信された日時が表示されます。

![](assets/sending_delivery3.png)

特定の送信ログの詳細にアクセスするには、対応する行の右側にある鉛筆アイコンをクリックします。

![](assets/sending_access-sending-log.png)

送信ログの詳細は、すべて読み取り専用です。ミラーページのプレビューを表示することもできます。

![](assets/sending_sending-log.png)

>[!NOTE]
>
>ミラーページレンダリングを Campaign ユーザーインターフェイスに表示するには、ミラーページサーバーの URL がセキュリティで保護されている必要があります。この場合、[ブランドを設定](../../administration/using/branding.md#configuring-and-using-brands)する際に http:// ではなく https:// を使用してこの URL を設定します。

### 除外ログ {#exclusion-logs}

「**[!UICONTROL Exclusion logs]**」タブには、送信されたターゲットから除外されたすべてのメッセージがリスト表示され、送信が失敗した理由を特定します。

![](assets/sending_delivery4.png)

### 除外の原因 {#exclusion-causes}

「**[!UICONTROL Exclusion causes]**」タブには、ターゲット送信から除外されたメッセージの量（メッセージ数）が表示されます。

![](assets/sending_delivery5.png)
