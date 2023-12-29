---
title: 監視のガイドライン
description: このページでは、Campaign Standardの監視に関する一般的なガイドラインを示します
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

Campaign Standardでは、インスタンスを監視して、システムの正常性を確認し、ワークフローの設定や配信の送信など時に発生する可能性のある問題のトラブルシューティングをおこなう方法がいくつか用意されています。

## システムの監視 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**システム通知**

Campaign Standardインターフェイスには、イベントのステータス、システムの更新、必要なアクションなど、システムで発生していることを常に知らせる通知ウィンドウが用意されています。 [詳細情報](../../start/using/interface-description.md#top-bar)


**テクニカルワークフロー**

テクニカルワークフローは、サーバー上で定期的に実行されるようにスケジュールされた操作またはジョブです。 インスタンスが正常に機能し、正常に動作していることを確認するには、インスタンスが常に起動して動作していることを確認する必要があります。 [詳細情報](../../administration/using/technical-workflows.md)

**コントロールパネル**

このCampaign コントロールパネルを使用すると、URL 権限、サーバーのビルドバージョンなどのインスタンスの詳細の確認、アクティブなプロファイルの使用状況の監視など、インスタンスの複数の設定を管理できます。 また、インスタンスに接続されている SFTP サーバーの使用可能な領域を監視することもできます。 [詳細情報](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)。

>[!NOTE]
>
>コントロールパネルは、すべての管理者ユーザーがアクセスできます。 ユーザーに管理者アクセス権を付与する手順については、[このページ](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=ja#discover-control-panel)で詳しく説明しています。

**技術オブジェクト**

The **[!UICONTROL Diagnosis]** メニューは、データスキーマ、web ページ、バッチジョブなど、アプリケーションによって生成される様々な技術オブジェクトを監視および分析するための重要なツールです。 [詳細情報](../../developing/using/monitoring-data-model-changes.md)

**監査の書き出し**

エクスポートの監査を使用すると、ワークフローからアップロードされたファイル、リストエクスポート、ダイレクトメールメッセージからダウンロードされたファイルなど、インスタンスで実行されたエクスポートを監視できます。
[詳細情報](../../administration/using/auditing-export-logs.md)

**ライセンス**

を使用 **[!UICONTROL Licenses]** メニュー、インスタンスに関する情報を監視します。インストール済みライセンス、ビルドバージョン、利用規約同意書です。
[詳細情報](../../administration/using/licenses.md)

## ワークフローの監視 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**ベストプラクティスとトラブルシューティング**

ワークフローを使用する際に、ベストプラクティスとトラブルシューティングのガイドラインに従うと、パフォーマンスを向上できます。
[詳細情報](../../automating/using/best-practices-workflows.md)

**ログとタスク**

ワークフローログの監視は、ワークフローを分析し、正しく実行されていることを確認するための重要な手順です。
[詳細情報](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standardでは、ワークフローの実行を監視し、注意が必要なエラーがあるかどうかをスーパーバイザーに通知して確認できます。
[詳細情報](../../automating/using/monitoring-workflow-execution.md#error-management)

## 配信の監視 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**配信品質**

Campaign Standardには、配信スループットレポート、送信時間の最適化、メッセージのプレビュー、E メールのレンダリング、強制隔離管理など、正常に配信されたメッセージの数を改善するための配信品質ツールがいくつか用意されています。
[詳細情報](../../sending/using/about-deliverability.md)

**配信**

メッセージが送信されると、詳細なログで、配信を監視し、キャンペーンの成功を測定したり、メッセージ受信者の行動をトラッキングしたりできます。
[詳細情報](../../sending/using/monitoring-a-delivery.md)

**配信アラート**

配信アラート機能を使用すると、配信の実行に関してユーザーのグループに自動的に送信されるアラート（送信の失敗または準備の失敗、バウンス率の無効、低スループットなど）を設定できます。
[詳細情報](../../sending/using/receiving-alerts-when-failures-happen.md)

**動的レポート**

動的レポートには、バウンス、受信者が最も閲覧した配信、配信のスループットなど、配信のパフォーマンスを常に把握できる様々なレポートが用意されています。
[詳細情報](../../reporting/using/about-dynamic-reports.md)
