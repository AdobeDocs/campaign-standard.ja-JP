---
solution: Campaign Standard
product: campaign
title: 監視のガイドライン
description: ここでは、Campaign Standardの監視に関する一般的なガイドラインを示します。
audience: production
content-type: reference
topic-tags: introduction
index: y
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 9%

---


# 監視のガイドライン {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">システムの監視</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">ワークフローの監視</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">配信の監視</a></p></td></tr>
</table>

Campaign Standardでは、インスタンスを監視して、システムが正常であることを確認し、ワークフローのセットアップ時、配信の送信時などに発生する可能性のある問題のトラブルシューティングを行う方法がいくつか用意されています。

## システムの監視 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**システム通知** Campaign Standardインターフェイスには、システムで発生していることを通知する通知ペインが用意されています。イベントのステータス、システムの更新、必要なアクションなど [詳細を表示](../../start/using/interface-description.md#top-bar)


**テクニカルワークフロー**&#x200B;テクニカルワークフローとは、サーバに基づいて定期的に実行されるようにスケジュールされた操作またはジョブのことです。 インスタンスが正常に機能し、正常に動作することを確認するには、インスタンスが常に起動および実行されていることを確認する必要があります。 [詳細を表示](../../administration/using/technical-workflows.md)

**Campaign コントロールパネル**:Campaign コントロールパネルを使用すると、インスタンスのいくつかの設定を管理できます。URL権限、サーバーのビルドバージョンなどのインスタンスの詳細を確認したり、アクティブなプロファイルの使用状況を監視したりします。 また、インスタンスに接続されているSFTPサーバーの使用可能な領域を監視することもできます。 [詳細を表示](https://docs.adobe.com/content/help/ja-JP/control-panel/using/control-panel-home.html)

>[!NOTE]
>
>Campaign コントロールパネルは管理者ユーザーのみがアクセスでき、Adobe Managed Servicesを使用するすべてのお客様が利用できます。

**技術オブジェクト****[!UICONTROL Diagnosis]** メニューは、アプリケーションが生成する様々な技術オブジェクトを監視および分析するための主要なツールです。データスキーマ、Webページ、バッチジョブなど [詳細を表示](../../developing/using/monitoring-data-model-changes.md)

**監査のエクスポート**エクスポート監査では、インスタンスに対して実行されたエクスポートを監視できます。ワークフロー、リストのエクスポート、ダイレクトメールからダウンロードしたファイルからアップロードできます。
[詳細を表示](../../administration/using/auditing-export-logs.md)

**ライセンス**&#x200B;メニューを使用して **[!UICONTROL Licenses]** 、インスタンスに関する情報を監視します。インストール済みのライセンス、バージョンの作成、および利用条件に関する同意書。
[詳細を表示](../../administration/using/licenses.md)

## ワークフローの監視 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**ベストプラクティスとトラブルシューティング**ワークフローを使用する際のベストプラクティスとトラブルシューティングのガイドラインに従うことで、パフォーマンスを改善できます。
[詳細を表示](../../automating/using/best-practices-workflows.md)

**ログとタスク**ワークフローログの監視は、ワークフローを分析し、正しく実行されていることを確認するための重要な手順です。
[詳細を表示](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**Campaign Standardを使用すると、スーパーバイザーに通知を送信して、ワークフローの実行を監視し、注意を必要とするエラーがないかどうかを確認できます。
[詳細を表示](../../automating/using/monitoring-workflow-execution.md#error-management)

## 配信の監視 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**配信品質**Campaign Standardには、配信に成功したメッセージの数を改善するための配信品質ツールがいくつか用意されています。配信の考慮されたレポート、送信時間の最適化、メッセージプレビュー、電子メールのレンダリング、強制隔離管理など
[詳細を表示](../../sending/using/about-deliverability.md)

**配信**メッセージが送信されると、詳細ログを使用して、配信を監視し、キャンペーンの成功を測定できるほか、メッセージ受信者の動作を追跡できます。
[詳細を表示](../../sending/using/monitoring-a-delivery.md)

**配信警告**配信警告機能を使用すると、配信の実行に関してユーザーのグループに自動的に送信されるアラートを設定できます。送信または準備に失敗、バウンス率、低スループットなど
[詳細を表示](../../sending/using/receiving-alerts-when-failures-happen.md)

**動的なレポート**動的なレポートには、配信のパフォーマンスを常に把握できるよう、様々なレポートが用意されています。バウンス、受信者別に最も多く閲覧された配信量、配信のスループットなど
[詳細を表示](../../reporting/using/about-dynamic-reports.md)
