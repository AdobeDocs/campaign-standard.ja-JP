---
title: プロセスとデータ管理に取り組む
description: ワークフローを使用すれば、データおよびオーディエンスの管理やメッセージの送信などのプロセスを自動化できます。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
TQID: https://experienceleague.adobe.com/iTJyQV-76oRhjJ4vDLKfSMpYTA27UcYt9UmVW-9YVq4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: b5f0aaf4-1e48-400d-95ac-6eb3078cf22f
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 22%

---

# プロセスとデータ管理に取り組む {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">ワークフローアクティビティ</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">ユースケース</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">データのフィルタリング</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">データのインポート/エクスポート</a></p></td></tr>
</table>

Adobe Campaignは、セグメンテーション、キャンペーンの実行、ファイル処理などの複雑なプロセスを設計できる包括的なグラフィック環境を提供します。例えば、ワークフローを使用してサーバーからファイルをダウンロードし、解凍してから、そのレコードをAdobe Campaign データベースに読み込むことができます。

ワークフローは、次のように異なるコンテキストで使用できます。

* オーディエンスを管理したり、メッセージを送信したりするためのターゲティング。
* データを操作するためのデータ管理（ETL）。
* Campaign データベースへのデータの読み込み。
* データベースのクリーンアップ、トラッキング情報の復元などの技術的プロセス。

>[!IMPORTANT]
>
> Adobeでは、20個を超えるアクティブなワークフローを同時に実行しないようにし、ワークフローの実行を時間の経過に沿って優先順位付けして広げることをお勧めします。 詳しくは、[このページ &#x200B;](../../automating/using/best-practices-workflows.md)で提供されているベストプラクティスを参照してください。

## ワークフローアクティビティ {#workflow-activities}

ワークフローの設計に役立つ様々なアクティビティを利用できます。

[&#x200B; ターゲティングアクティビティ &#x200B;](../../automating/using/about-targeting-activities.md)を使用すると、セットを定義し、積集合、和集合、除外演算を使用してこれらのセットを分割または組み合わせることで、1つ以上のターゲットを作成できます。

[実行アクティビティ &#x200B;](../../automating/using/about-execution-activities.md)では、ワークフローとそのアクティビティを調整し、[&#x200B; チャネルアクティビティ &#x200B;](../../automating/using/about-channel-activities.md)では、Campaign Standard コミュニケーションチャネルを組み合わせてクロスチャネルワークフローを作成できます。

最後に、[&#x200B; データ管理アクティビティ &#x200B;](../../automating/using/about-data-management-activities.md)を使用すると、データベースからデータを操作できます。

詳しくは、以下を参照してください。

* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [ワークフローの実行](../../automating/using/about-workflow-execution.md)
* [ワークフローのベストプラクティス](../../automating/using/best-practices-workflows.md)

## データのフィルタリング {#filter-data}

**クエリエディター**&#x200B;を利用して、データベースからデータをフィルタリングし、母集団を構築して受信者をより適切にターゲティングします。 クエリエディターは、Campaign Standardでクエリタイプのオーディエンスの作成、配信目標の定義、ワークフローアクティビティの母集団など、いくつかのアクションを実行できます。

クエリエディターには、**定義済みのフィルターとルール**&#x200B;が付属しており、すばやく簡単にフィルタリングできます。 ただし、**高度な式の編集**&#x200B;機能を使用することもできます。 これにより、独自のルールを作成するために、条件を手動で入力し、関数を使用できます。

詳しくは、以下を参照してください。

* [クエリの編集](../../automating/using/editing-queries.md)
* [高度な式の編集](../../automating/using/advanced-expression-editing.md)
* [関数のリスト](../../automating/using/list-of-functions.md)

## データのインポート/エクスポート {#import-export-data}

Campaign Standardには、データの読み込みと書き出しを行うための&#x200B;**データ管理機能**&#x200B;が搭載されています。

[&#x200B; ワークフローデータ管理アクティビティ &#x200B;](../../automating/using/about-data-management-activities.md)を使用すると、データの読み込み、フィールドの一括更新の実行、ファイルの受信または送信、または未識別のデータを既存のリソースにリンクできます。

[&#x200B; テンプレートの読み込み](../../automating/using/importing-data-with-import-templates.md)を使用すると、簡単な読み込み関数を使用して、管理者が定義した特定の種類の読み込みを管理できます。

[&#x200B; ログの書き出し](../../automating/using/exporting-logs.md)を使用すると、シンプルなワークフローでログデータを書き出すことができ、独自のレポートまたはBI ツールでマーケティングキャンペーンの結果を分析できます。

[&#x200B; パッケージ &#x200B;](../../automating/using/managing-packages.md)を活用して、異なるキャンペーンインスタンス間でリソースを交換します。例えば、インスタンスの設定をレプリケートしたり、カスタムリソースを含むサーバーから別のサーバーにデータを転送したりできます。

最後に、[&#x200B; リストの書き出し](../../automating/using/exporting-lists.md)を使用すると、テストプロファイルのリスト、強制隔離メールアドレスのリストなど、Campaign Standardから任意のリストを書き出すことができます。

詳しくは、以下を参照してください。

* [データのインポートおよびエクスポート](../../automating/using/about-data-import-and-export.md)
* [ユースケース：カスタムリソースのエクスポート／インポート](../../automating/using/exporting-importing-custom-resources.md)

## その他のリソース

* [プロセスとデータ管理のチュートリアルビデオ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=ja)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [Campaign Standard データモデルの基本を学ぶ](../../developing/using/get-started-data-model.md)
