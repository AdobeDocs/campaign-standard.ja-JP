---
title: 監視のガイドライン
description: ここでは、Campaign Standardのモニタリングに関する一般的なガイドラインを示します
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 13%

---

# 監視のガイドライン {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">システムの監視</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">ワークフローの監視</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">配信の監視</a></p></td></tr>
</table>

Campaign Standardでは、システムが正常であることを確認するためにインスタンスを監視する方法をいくつか提供しており、最終的には、ワークフローの設定や配信の送信などで発生する可能性のある問題のトラブルシューティングを行います。

## システムの監視 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**システム通知**

Campaign Standardインターフェイスには、イベントのステータス、システムのアップデート、必要なアクションなど、システムで何が起きているかを常に把握できる通知ペインが用意されています。 [詳細情報](../../start/using/interface-description.md#top-bar)


**テクニカルワークフロー**

テクニカルワークフローは、サーバーで定期的に実行するようにスケジュールされた操作またはジョブです。 インスタンスが正常で正常に機能するようにするには、インスタンスが常に起動し実行中であることを確認する必要があります。 [詳細情報](../../administration/using/technical-workflows.md)

**コントロールパネル**

Campaign コントロールパネルを使用すると、インスタンスの複数の設定を管理できます。URL 権限、サーバーのビルドバージョンなどのインスタンスの詳細の確認、アクティブなプロファイルの使用状況の監視などです。 また、インスタンスに接続されている SFTP サーバーの使用可能な領域を監視することもできます。 [詳細情報](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)

>[!NOTE]
>
>コントロールパネルは、すべての管理者ユーザーがアクセスできます。 ユーザーに管理者アクセス権を付与する手順については、[このページ](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=ja#discover-control-panel)で詳しく説明しています。

**技術的目標**

**[!UICONTROL Diagnosis]** メニューは、アプリケーションによって生成される様々な技術的オブジェクト（データスキーマ、web ページ、バッチジョブなど）を監視および分析するための重要なツールです。 [詳細情報](../../developing/using/monitoring-data-model-changes.md)

**輸出監査**

書き出し監査を使用すると、ワークフローからアップロードされたファイル、リスト書き出し、ダイレクトメールメッセージからダウンロードされたファイルなど、インスタンスで実行された書き出しを監視できます。
[詳細情報](../../administration/using/auditing-export-logs.md)

**ライセンス**

**[!UICONTROL Licenses]** メニューを使用して、インストールされているライセンス、ビルドバージョン、利用条件の同意など、インスタンスに関する情報を監視します。
[詳細情報](../../administration/using/licenses.md)

## ワークフローの監視 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**ベストプラクティスとトラブルシューティング**

ワークフローを使用する際に、ベストプラクティスとトラブルシューティングガイドラインに従うと、パフォーマンスの向上に役立ちます。
[詳細情報](../../automating/using/best-practices-workflows.md)

**ログとタスク**

ワークフローログの監視は、ワークフローを分析し、正しく実行されていることを確認するための重要な手順です。
[詳細情報](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standardを使用すると、スーパーバイザーに通知を送信し、ワークフローの実行を監視し、注意を要するエラーがあるかどうかを確認できます。
[詳細情報](../../automating/using/monitoring-workflow-execution.md#error-management)

## 配信の監視 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**配信品質**

Campaign Standardには、正常に配信されたメッセージ数を増やすのに役立つ、配信品質ツールがいくつか用意されています（配信スループットレポート、送信時間の最適化、メッセージのプレビュー、メールのレンダリング、強制隔離管理など）。
[詳細情報](../../sending/using/about-deliverability.md)

**配信**

メッセージが送信されると、詳細なログで配信を監視したり、キャンペーンの成功を測定したり、メッセージ受信者の行動をトラッキングしたりできます。
[詳細情報](../../sending/using/monitoring-a-delivery.md)

**配信アラート**

配信アラート機能を使用すると、配信の実行に関して、ユーザーのグループ（送信または準備の失敗、無効なバウンス率、低スループットなど）に自動的に送信されるアラートを設定できます。
[詳細情報](../../sending/using/receiving-alerts-when-failures-happen.md)

**動的レポート**

動的レポートには、配信のパフォーマンスに関する情報を常に把握するのに役立つ様々なレポートが用意されています。バウンス、受信者が最も表示した配信、配信のスループットなどです。
[詳細情報](../../reporting/using/about-dynamic-reports.md)
