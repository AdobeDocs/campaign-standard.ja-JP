---
title: ワークフローの検索
seo-title: ワークフローの検索
description: ワークフローの検索
seo-description: Adobe Campaignは、プロセスを設計および自動化するための包括的なグラフィカル環境を提供します。
page-status-flag: 非活性化の
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# ワークフローの検索{#discovering-workflows}

Adobe Campaignは、セグメント化、キャンペ [ーンの実行](../../automating/using/workflow-interface.md)[](../../automating/using/workflow-operating-principles.md) 、ファイル処理、承認などの複雑なプロセスを設計できる、包括的なグラフィカル環境を提供します。 原則とベストプラクティスについては、この節で [説明します](../../automating/using/building-a-workflow.md)。

例えば、ワークフローを使用して、サーバーからファイルをダウンロードし、解凍してから、そのレコードをAdobe Campaignデータベースにインポートできます。

ワークフローは、ユーザーにタスクを割り当てたり、実行されたタスクを承認させたりすることで、ユーザーを関与させることもできます。 つまり、1人または複数のユーザーにタスクを割り当てて、メッセージを送信する前に、コンテンツの操作やターゲットの指定を行ったり、プルーフを承認したりできます。

ワークフローは、次のよう **に様々なコンテキスト**&#x200B;で使用できます。

* オーディエンスを管理またはメッセージを送信するターゲット設定。 詳しくは、「チャネルアクティビティとターゲッ [ト設定アクティビティ](../../automating/using/about-channel-activities.md) 」を参 [照してくださ](../../automating/using/about-targeting-activities.md)い。
* データ管理(ETL)を使用してデータを操作します。 詳しくは、「データ管理アクティビティ」 [を参照してください](../../automating/using/about-data-management-activities.md)。
* Campaignデータベースへのデータのインポートを参照してください。 詳しくは、「データの読み込みと書き出し」 [を参照してください](../../automating/using/about-data-import-and-export.md)。
* データベースのクリーンアップ、追跡情報の回復などの技術的なプロセス 技術ワークフローについて詳 [しくは](../../administration/using/technical-workflows.md)、

ワークフローは、Adobe Campaign Standard APIからもアクセスできます。 For more on this, refer to the [dedicated documentation](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#managing-workflows).

**関連トピック：**

* [ワークフローの運用原則](../../automating/using/workflow-operating-principles.md)
* [データのインポートとエクスポートについて](../../automating/using/about-data-import-and-export.md)
* [使用例：週に1回の電子メール配信の作成](../../automating/using/workflow-weekly-offer.md)
* [使用例：場所でセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [使用例：補完を含む配信の作成](../../automating/using/workflow-created-query-with-complement.md)
* [使用例：未開封者に新しい配信を送信する再ターゲットワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)
