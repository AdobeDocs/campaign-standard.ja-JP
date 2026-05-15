---
title: 監視のガイドライン
description: このページでは、Campaign Standardのモニタリングに関する一般的なガイドラインを示します
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
TQID: https://experienceleague.adobe.com/4hy5-pubF9F2FDQGaC7GF-BfMHqMDykC4mtypRc-zsk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 19%

---

# 監視のガイドライン {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">システムの監視</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">ワークフローの監視</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">配信の監視</a></p></td></tr>
</table>

Campaign Standardでは、いくつかの方法でインスタンスを監視して、システムが正常であることを確認し、ワークフローの設定や配信の送信時に発生する可能性のある問題を最終的にトラブルシューティングできます。

## システムの監視 {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**システム通知**

Campaign Standard インターフェイスには、システムで何が起こっているかを常に把握できる通知ペインが用意されています。イベントのステータス、システムの更新、必要なアクションなど、[詳細情報](../../start/using/interface-description.md#top-bar)


**テクニカルワークフロー**

テクニカルワークフローは、サーバー上で定期的に実行されるようにスケジュールされた処理またはジョブです。 インスタンスが正常に機能していることを確認するには、インスタンスが常に起動して動作していることを確認する必要があります。 [詳細情報](../../administration/using/technical-workflows.md)

**コントロールパネル**

このCampaign コントロールパネルでは、URL権限、サーバーのビルドバージョンなどのインスタンスの詳細の確認、アクティブプロファイルの使用状況のモニタリングなど、インスタンスの複数の設定を管理できます。また、インスタンスに接続されているSFTP サーバーの空き容量を監視することもできます。 [詳細情報](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)。

>[!NOTE]
>
>コントロールパネルは、すべての管理者ユーザーがアクセスできます。 ユーザーに管理者アクセス権を付与する手順については、[このページ](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=ja#discover-control-panel)で詳しく説明しています。

**テクニカルオブジェクト**

**[!UICONTROL Diagnosis]** メニューは、アプリケーションによって生成されたさまざまなテクニカルオブジェクト（データスキーマ、web ページ、バッチジョブなど）を監視および分析するための重要なツールです。[詳細情報](../../developing/using/monitoring-data-model-changes.md)

**監査のエクスポート**

書き出し監査を使用すると、ワークフローからアップロードされたファイル、リスト書き出し、ダイレクトメールメッセージからダウンロードされたファイルなど、インスタンスで実行された書き出しを監視できます。
[詳細情報](../../administration/using/auditing-export-logs.md)

**ライセンス**

**[!UICONTROL Licenses]** メニューを使用して、インスタンスに関する情報（インストール済みライセンス、ビルド バージョン、契約条件の承認）を監視します。
[詳細情報](../../administration/using/licenses.md)

## ワークフローの監視 {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**ベストプラクティスとトラブルシューティング**

ワークフローを使用する際に、ベストプラクティスとトラブルシューティングガイドラインに従うことで、パフォーマンスを向上させることができます。
[詳細情報](../../automating/using/best-practices-workflows.md)

**ログとタスク**

ワークフローログの監視は、ワークフローを分析し、適切に実行されていることを確認するための重要な手順です。
[詳細情報](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**通知**

Campaign Standardでは、ワークフローの実行を監視し、注意が必要なエラーがあるかどうかを確認するために、スーパーバイザーに通知を送信できます。
[詳細情報](../../automating/using/monitoring-workflow-execution.md#error-management)

## 配信の監視 {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**配信品質**

Campaign Standardには、正常に配信されたメッセージの数を増やすのに役立つ配信品質ツールがいくつか用意されています。配信スループットレポート、送信時間の最適化、メッセージのプレビュー、メールのレンダリング、強制隔離の管理など、メッセージの配信数を増やすことができます。
[詳細情報](../../sending/using/about-deliverability.md)

**配信**

メッセージが送信されると、詳細なログにより、配信を監視し、キャンペーンの成功を測定したり、メッセージ受信者の行動を追跡したりできます。
[詳細情報](../../sending/using/monitoring-a-delivery.md)

**配信アラート**

配信アラート機能を使用すると、配信の実行に関するユーザーのグループ（送信または準備の失敗、バウンス率の低下、スループットの低下など）に自動的に送信されるアラートを設定できます。
[詳細情報](../../sending/using/receiving-alerts-when-failures-happen.md)

**動的レポート**

動的レポートでは、バウンス、受信者による最も閲覧された配信、配信のスループットなど、配信のパフォーマンスに関する情報を常に把握するのに役立つ様々なレポートが提供されます。
[詳細を表示](../../reporting/using/about-dynamic-reports.md)
