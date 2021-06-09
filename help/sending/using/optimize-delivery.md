---
solution: Campaign Standard
product: campaign
title: メッセージ配信の最適化
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: 送信プロセスのアップストリームを保護し最適化する方法を説明します。
feature: 配信品質
role: Business Practitioner
level: Intermediate
exl-id: 28b0cf6d-c1f1-4d55-b9bc-0d6bfb063471
source-git-commit: 8a62ee661b77c3e3062e46477bfce5911e9415ff
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 81%

---

# 配信の最適化 {#optimize-delivery}

配信の作成に入る前に、送信プロセスを保証し、最適化するためにいくつかの作業をおこないます。

以下の節では、Adobe Campaign を最適に設定するためのベストプラクティスと推奨手順について説明します。このベストプラクティスに従えば、後で問題が発生する可能性を最小限に抑えることができます。

## プラットフォームのパフォーマンス

いくつかの要因がサーバーのパフォーマンスに直接影響し、プラットフォームの速度が低下することがあります。

* パーソナライゼーション要素の数とタイプ：E メールのパーソナライゼーションでは、各受信者のデータベースからデータを取り出します。パーソナライゼーション要素が多数ある場合は、配信の準備に必要なデータの量もそれだけ多くなります。Eメールのパーソナライゼーションについて詳しくは、[この節](../../designing/using/personalization.md)を参照してください。

* サーバーの負荷：キャンペーンが様々なタスクを同時に処理している場合、パフォーマンスが低下する可能性があります。 サーバーは、すべての配信ですべての受信および送信データを調整し、データが正しく、時間通りに正しいことを確認する必要があります。

   **ヒント**：パフォーマンスの低下を避けるには、他のチームメンバーと話し合い、最適なパフォーマンスが得られるように配信スケジュールを調整します。

* [ワークフローの実行](../../automating/using/about-workflow-execution.md):ワークフローの監視は、プラットフォームのパフォーマンスの問題を回避するために必要です。 このページ](../../automating/using/monitoring-workflow-execution.md)に示すガイドラインに従います。 [詳しくは、[ワークフローのベストプラクティス](../../automating/using/best-practices-workflows.md)の節を参照してください。

* [Campaignコントロールパネルの](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=ja)機能を利用して、[パフォーマンス監視](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=ja)機能を使用して、プラットフォームを監視できます。

## ネットワーク設定の確認 {#network-config}

大量の E メールを配信してもスパム送信者と間違えられないようにするために、サーバーの身元を隠そうとしない適切なネットワーク設定を使用する必要があります。

**ヒント**：ブランドの Web サイトに対応する、透明性の高い送信者アドレスを使用します。例えば、TravelAgency 社は Valentino ホテルチェーンを経営しています。同社は、そのホテルチェーン用の Web サイトドメインとして valentino.com を所有しています。また、パリの Valentino ホテルの販促には paris.valentino.com サブドメインを使用しています。したがって、適切な送信者アドレスは hotel@paris.valentino.com などとなります。

## 配信品質の管理 {#deliverability-management}

バウンスメールが返ってきたり、スパムに指定されたりすることなく、E メールを受信者の受信ボックスに確実に届けるには、メッセージの配信品質の割合を向上させる必要があります。

* 配信品質とは何でしょうか。

   * 配信品質とは、受信者のサーバーが E メールを許可する能力を測定するためのファクターです。ISP（インターネットサービスプロバイダー）は、スパムとして識別した E メールを除外するか、E メール内の画像のダウンロードを禁止します。ISP は、特定のドメインから大量の E メールが送信されていると判断すると、その送信者から送られる E メールの許可数に上限を設定します。

   * E メールの配信品質を確認するときは、データ品質、メッセージとコンテンツ、送信インフラストラクチャ、レピュテーションという 4 つの主要カテゴリを中心に調べます。このトピックについて詳しくは、[この節](../../sending/using/about-deliverability.md)を参照してください。

* 新しいプラットフォームを開始する際は、[このページ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html#transition-process)で説明されている推奨事項を適用します。

* サポートが必要な場合は、アドビ担当者にお問い合わせください。

## 強制隔離の管理 {#quarantine-management}

強制隔離の管理プロセスを適切に維持することをお勧めします。

新しいプラットフォームで E メールの送信を開始するときは、まだ選定が十分でないアドレスのリストを使用することがあります。無効なアドレスやハニーポットアドレス（スパム送信者を誘き寄せるために作成されたメールボックス）に送信すると、プラットフォームのレピュテーションの低下につながります。適切な強制隔離の管理プロセスがあれば、アドレスの品質の維持、インターネットアクセスプロバイダーによるブロックリストへの登録の回避、エラー率の低減、配信とスループットの向上を期待できます。

**ヒント**

* アドレスが強制隔離されている受信者は、配信分析時にデフォルトで除外され、ターゲティングされません。これによって配信が迅速になります。エラー率は配信の速度に大きく影響するからです。例えば、受信ボックスの容量が超過している場合や、アドレスが存在しない場合などに、E メールアドレスを強制隔離できます。[詳細情報](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign では、返されるエラーのタイプに応じて不正なアドレスを管理します。詳しくは、[この節](../../sending/using/understanding-quarantine-management.md)を参照してください。

* 一部のインターネットアクセスプロバイダーは、無効なアドレスの割合が高すぎる場合、E メールを自動的にスパムと見なします。したがって、強制隔離を使用すると、これらのプロバイダーによってブロックリストに追加されるのを回避できます。

* 強制隔離管理は、誤りのある電話番号を配信から除外することで、SMS の送信コスト削減にも役立ちます。

## 二重のオプトインのメカニズム {#double-opt-in}

無効なアドレスにメッセージが送信されるのを回避し、不適切な通信を規制し、送信者のレピュテーションを向上させるには、購読後の確認をおこなう二重のオプトインのメカニズムを実装することをお勧めします。これにより、受信者が意図的に購読したことを確認できます。

このメカニズムの実装の詳細については、[この節](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)で説明します。

詳しくは、[プロファイルとオーディエンスの使用を開始する](../../audiences/using/get-started-profiles-and-audiences.md)を参照してください。
