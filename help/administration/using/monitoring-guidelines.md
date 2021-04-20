---
solution: Campaign Standard
product: campaign
title: 監視のガイドライン
description: ここでは、Campaign Standardの監視に関する一般的なガイドラインを示します。
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: Access Management
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 15%

---


# 監視のガイドライン {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">システムの監視</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">ワークフローの監視</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">配信の監視</a></p></td></tr>
</table>

Campaign Standardでは、インスタンスを監視して、システムが正常であることを確認し、ワークフローのセットアップ時、配信の送信時などに発生する可能性のある問題のトラブルシューティングを行う方法がいくつか用意されています。

## システムの監視{#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**システム通知**

Campaign Standardインターフェイスには、システムで発生していることを通知する通知ペインが用意されています。イベントのステータス、システムの更新、必要なアクションなど [詳細情報](../../start/using/interface-description.md#top-bar)


**テクニカルワークフロー**

テクニカルワークフローは、サーバー上で定期的に実行されるようにスケジュールされた処理またはジョブです。インスタンスが正常に機能し、正常に動作することを確認するには、インスタンスが常に起動および実行されていることを確認する必要があります。 [詳細情報](../../administration/using/technical-workflows.md)

**Campaign コントロールパネル**

このCampaign コントロールパネルでは、インスタンスのいくつかの設定を管理できます。URL権限、サーバーのビルドバージョンなどのインスタンスの詳細を確認したり、アクティブなプロファイルの使用状況を監視したりします。 また、インスタンスに接続されているSFTPサーバーの使用可能な領域を監視することもできます。 [詳細を表示](https://docs.adobe.com/content/help/ja-JP/control-panel/using/control-panel-home.html)。

>[!NOTE]
>
>Campaign コントロールパネルは、すべての管理者ユーザーがアクセスできます。 ユーザーに管理者アクセスを許可する手順については、[このページ](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel)を参照してください。

**技術的なオブジェクト**

**[!UICONTROL Diagnosis]**&#x200B;メニューは、アプリケーションが生成する様々な技術オブジェクトを監視および分析するための主要なツールです。データスキーマ、Webページ、バッチジョブなど [詳細情報](../../developing/using/monitoring-data-model-changes.md)

**監査のエクスポート**

エクスポート監査を使用すると、インスタンスに対して実行されるエクスポートを監視できます。ワークフロー、リストのエクスポート、ダイレクトメールからダウンロードしたファイルからアップロードできます。
[詳細情報](../../administration/using/auditing-export-logs.md)

**ライセンス**

**[!UICONTROL Licenses]**メニューを使用して、インスタンスに関する情報を監視します。インストール済みのライセンス、バージョンの作成、および利用条件に関する同意書。
[詳細情報](../../administration/using/licenses.md)

## ワークフローの監視 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**ベストプラクティスとトラブルシューティング**

ワークフローを使用する際のベストプラクティスとトラブルシューティングのガイドラインに従うと、パフォーマンスの向上に役立ちます。
[詳細情報](../../automating/using/best-practices-workflows.md)

**ログとタスク**

ワークフローログの監視は、ワークフローを分析し、正しく実行されていることを確認するための重要な手順です。
[詳細情報](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standardを使用すると、ワークフローの実行を監視し、注意を必要とするエラーがないかどうかを確認するために、スーパーバイザーに通知を送信できます。
[詳細情報](../../automating/using/monitoring-workflow-execution.md#error-management)

## 配信の監視 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**配信品質**

Campaign Standardには、正常に配信されたメッセージの数を改善するための配信品質ツールがいくつか用意されています。配信・スループット・レポート、送信時間の最適化、メッセージプレビュー、Eメール・レンダリング、強制隔離管理など
[詳細情報](../../sending/using/about-deliverability.md)

**配信**

メッセージが送信されると、詳細ログを使用して、配信を監視し、キャンペーンの成功を測定したり、メッセージ受信者の動作を追跡したりできます。
[詳細情報](../../sending/using/monitoring-a-delivery.md)

**配信警告**

配信アラート機能を使用すると、配信の実行に関してユーザーのグループに自動的に送信されるアラートを設定できます。送信または準備に失敗、バウンス率、低スループットなど
[詳細情報](../../sending/using/receiving-alerts-when-failures-happen.md)

**動的レポート**

動的なレポートには、配信のパフォーマンスを常に把握できるよう、様々なレポートが用意されています。バウンス、受信者別の最も多く閲覧された配信、配信のスループットなど
[詳細情報](../../reporting/using/about-dynamic-reports.md)
