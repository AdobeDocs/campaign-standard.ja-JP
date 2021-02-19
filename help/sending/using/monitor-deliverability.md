---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでの配信品質の監視
description: Adobe Campaign Standardが提供するツールを使用して、プラットフォームの配信品質を監視します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 58%

---


# 配信品質の監視{#monitor-deliverability}

**[!UICONTROL Delivery throughput]**&#x200B;レポートの詳細と、Adobe Campaignが提供する様々な監視ツールを以下に示します。 配信品質の監視に関する追加のガイドラインを示します。
* プラットフォーム全体で配信スループットを定期的にチェックして、元のセットアップと整合性が取れているかどうかを検証します。
* 配信テンプレートで再試行が適切に設定されていることを確認します（再試行期間が 30 分、再試行回数が 21 回以上）。
* バウンスメールボックスがアクセス可能で、アカウントの有効期限が近づいていないかを定期的に検証します。
* 各配信スループットをチェックして、配信コンテンツの有効期限と整合性が取れていることを確認します（例：「フラッシュセール」は数日ではなく、数分で配信される必要があります）。
* ウェーブを使用する場合、次のものがトリガーされる前に各ウェーブが完了するための十分な時間があることを検証します。
* エラーの数と新しい強制隔離が他の配信と整合性が取れていることをチェックします。
* 強調表示されるエラー(ブロックリスト配信ログ、DNSの問題、スパム対策ルールなど)の種類を確認するには、注意深くに問い合わせてください。

## 配信スループット {#delivery-throughput}

このレポートには、特定の期間のプラットフォーム全体の配信スループットに関する情報が含まれ、メッセージの配信速度を測定します。

詳しくは、[配信スループット](../../reporting/using/delivery-throughput.md)を参照してください。

![](assets/delivery_reports_1.png)

タイムスケールを変更して、表示する値を設定できます。

**[!UICONTROL Delivery summary]**&#x200B;や&#x200B;**[!UICONTROL Non-deliverables and bounces]**&#x200B;など、他のレポートも利用できます。 詳しくは、[動的レポート](../../reporting/using/about-dynamic-reports.md)を参照してください。

## 配信の監視 {#monitoring-deliveries}

メッセージダッシュボードから配信ログにアクセスできます。**[!UICONTROL Sending logs]**、**[!UICONTROL Exclusion logs]**、**[!UICONTROL Exclusion causes]**、**[!UICONTROL Tracking logs]**、**[!UICONTROL Tracked URLs]**。 送信の詳細、除外されたターゲットとその理由、および開封数やクリック数などの追跡情報が表示されます。

詳しくは、[配信の監視](../../sending/using/monitoring-a-delivery.md)を参照してください。

![](assets/sending_delivery1.png)

## アラートの受信{#receiving-alerts}

**[!UICONTROL Delivery alerting]**&#x200B;機能は、ユーザーのグループが、配信の実行に関する情報を含む通知を自動的に受信できるようにするアラート管理システムです。

詳しくは、[エラーが発生した場合のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)を参照してください。

## Signal Spam {#signal-spam}

Signal Spam は、フランスのサービスで、フランスの ISP（Orange、SFR）用の匿名化されたフィードバックループレポートを提供します。

このサービスを使用すると、フランスの ISP のレピュテーションをフォローし、顧客のアクティビティの進化をトラッキングできます。

また、Signal Spam は、専用インターフェンスを通じてエンドユーザーが記録した直接の苦情数を提供します。これらの苦情数は、E メールアドレスデータベースから強制隔離されます。

## 250ok {#solution-250ok}

250okは、IPとドメインのブロックリスト、および評価指標を提供する監視ソリューションです。

提供される情報はリアルタイムで、これにより先を見越した支援が可能です。250ok は、アドビの配信品質の内部ツールを補完するソリューションです。
