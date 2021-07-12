---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでの配信品質の監視
description: Adobe Campaign Standardが提供するツールを使用して、プラットフォームの配信品質を監視します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 配信品質
role: User
level: Intermediate
exl-id: 683341fb-fef5-4aa1-8606-9526d9ae6290
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 48%

---

# 配信品質の監視{#monitor-deliverability}

以下に、**[!UICONTROL Delivery throughput]**&#x200B;レポートの詳細と、Adobe Campaignが提供する様々な監視ツールの詳細を示します。 配信品質の監視に関する追加のガイドラインを示します。
* プラットフォーム全体で配信スループットを定期的にチェックして、元のセットアップと整合性が取れているかどうかを検証します。
* 配信テンプレートで再試行が適切に設定されていることを確認します（再試行期間が 30 分、再試行回数が 21 回以上）。
* バウンスメールボックスがアクセス可能で、アカウントの有効期限が近づいていないかを定期的に検証します。
* 各配信スループットをチェックして、配信コンテンツの有効期限と整合性が取れていることを確認します（例：「フラッシュセール」は数日ではなく、数分で配信される必要があります）。
* エラーの数と新しい強制隔離が他の配信と整合性が取れていることをチェックします。
* 配信ログの詳細を慎重に調べて、ハイライト表示されたエラーの種類をチェックしまブロックリストす（、DNSの問題、スパム対策ルールなど）。

## 配信スループット {#delivery-throughput}

このレポートには、特定の期間のプラットフォーム全体の配信スループットに関する情報が含まれ、メッセージの配信速度を測定します。

詳しくは、[配信スループット](../../reporting/using/delivery-throughput.md)を参照してください。

![](assets/delivery_reports_1.png)

タイムスケールを変更して、表示する値を設定できます。

**[!UICONTROL Delivery summary]**&#x200B;や&#x200B;**[!UICONTROL Non-deliverables and bounces]**&#x200B;など、他のレポートも使用できます。 詳しくは、[動的レポート](../../reporting/using/about-dynamic-reports.md)を参照してください。

## 配信の監視 {#monitoring-deliveries}

メッセージダッシュボードから配信ログにアクセスできます。**[!UICONTROL Sending logs]**、**[!UICONTROL Exclusion logs]**、**[!UICONTROL Exclusion causes]**、**[!UICONTROL Tracking logs]**、**[!UICONTROL Tracked URLs]**&#x200B;の3つの値を指定します。 送信の詳細、除外されたターゲットとその理由、および開封数やクリック数などの追跡情報が表示されます。

詳しくは、[配信の監視](../../sending/using/monitoring-a-delivery.md)を参照してください。

![](assets/sending_delivery1.png)

## アラートの受信 {#receiving-alerts}

**[!UICONTROL Delivery alerting]**&#x200B;機能は、配信の実行に関する情報を含む通知をユーザーのグループが自動的に受け取れるようにするアラート管理システムです。

詳しくは、[エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)を参照してください。

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
