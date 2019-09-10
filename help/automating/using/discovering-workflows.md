---
title: ワークフローの検出
seo-title: ワークフローの検出
description: ワークフローの検出
seo-description: Adobe Campaignは、プロセスを設計および自動化できる包括的なグラフィカル環境を提供します。
page-status-flag: 決して活性化されていない
uuid: 7c1e8sic-90d0-491f- ab8f-6cd9a6c3b
contentOwner: ソビア
products: SG_キャンペーン/標準
audience: 自動化
content-type: 参照
topic-tags: ワークフローとデータ管理について
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98EC87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# ワークフローの検出{#discovering-workflows}

Adobe Campaignは、 [セグメント化、キャンペーン実行、](../../automating/using/workflow-interface.md) ファイル処理、承認など [、複雑なプロセス](../../automating/using/workflow-operating-principles.md) を設計できる包括的なグラフィカル環境を提供します。このセクションで [は、原理とベストプラクティスについて](../../automating/using/building-a-workflow.md)説明します。

たとえば、ワークフローを使用してサーバーからファイルをダウンロードし、解凍して、そのレコードをAdobe Campaignデータベースにインポートできます。

ワークフローは、タスクを割り当てたり、実行されたタスクを承認することによって、ユーザーに関連付けることもできます。つまり、1人または複数のユーザーにタスクを割り当てて、コンテンツを操作したり、ターゲットを指定したり、メッセージを送信する前に証明書を承認したりできます。

ワークフローは、次のように **異なるコンテキスト**&#x200B;で使用できます。

* 対象者を管理したりメッセージを送信したりするためのターゲット。詳細については、 [チャネルアクティビティ](../../automating/using/about-channel-activities.md) と [ターゲットアクティビティ](../../automating/using/about-targeting-activities.md)を参照してください。
* データを操作するためのデータ管理（ETL）。詳細については [、データ管理活動](../../automating/using/about-data-management-activities.md)を参照してください。
* データをCampaignデータベースにインポートしています。詳細については、「データ [のインポートとエクスポート」を](../../automating/using/about-data-import-and-export.md)参照してください。
* データベースのクリーンアップ、追跡情報のリカバリなどの技術プロセスこのセクションの [テクニカルワークフローの詳細について](../../administration/using/technical-workflows.md)は、こちらをご覧ください。

ワークフローには、Adobe Campaign Standard APIからもアクセスできます。詳細については [、専用ドキュメント](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#managing-workflows)を参照してください。

**関連トピック:**

* [ワークフローの運用原則](../../automating/using/workflow-operating-principles.md)
* [データのインポートとエクスポートについて](../../automating/using/about-data-import-and-export.md)
* [ユースケース:1週間の電子メール配信を作成する](../../automating/using/workflow-weekly-offer.md)
* [ユースケース:場所にセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [ユースケース:補足を使用した搬送の作成](../../automating/using/workflow-created-query-with-complement.md)
* [ユースケース:新しい配送を非公開者に送信するワークフローの再ターゲット](../../automating/using/workflow-cross-channel-retargeting.md)
