---
title: プロセスとデータ管理の基本を学ぶ
description: ワークフローを使用すれば、データおよびオーディエンスの管理やメッセージの送信などのプロセスを自動化できます。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: c7c4826f69ac988911b9d72a3e06240ed9582862
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 30%

---

# プロセスとデータ管理の基本を学ぶ {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">ワークフローアクティビティ</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">ユースケース</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">データのフィルタリング</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">データのインポート/エクスポート</a></p></td></tr>
</table>

Adobe Campaign は、セグメント化、キャンペーン実行、ファイル処理などの複雑なプロセスを設計できる包括的なグラフィカル環境を提供します。 例えば、ワークフローを使用して、サーバーからファイルをダウンロードした後、ファイルを解凍し、ファイル内のレコードを Adobe Campaign データベースに読み込むことができます。

ワークフローは、次のように異なるコンテキストで使用できます。

* オーディエンスを管理したり、メッセージを送信したりするためのターゲティング。
* データを操作するためのデータ管理（ETL）。
* Campaign データベースへのデータの読み込み。
* データベースのクリーンアップ、トラッキング情報の復元などの技術的プロセス。

>[!IMPORTANT]
>
> Adobeでは、20 を超えるアクティブなワークフローの実行を同時に実行せず、ワークフローの実行を時間の経過と共に優先順位を付けて分散することをお勧めします。 詳しくは、[ このページ ](../../automating/using/best-practices-workflows.md) に記載されているベストプラクティスを参照してください。

## ワークフローアクティビティ {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="10px">

ワークフローの設計に役立つ様々なアクティビティを利用できます。

[ ターゲティングアクティビティ ](../../automating/using/about-targeting-activities.md) では、セットを定義するか、積集合、和集合、除外の各操作を使用して分割または結合することで、1 つまたは複数のターゲットを作成できます。

[ 実行アクティビティ ](../../automating/using/about-execution-activities.md) を使用すると、ワークフローとそのアクティビティを調整でき、[ チャネルアクティビティ ](../../automating/using/about-channel-activities.md) を使用すると、Campaign Standardのコミュニケーションチャネルを組み合わせて、クロスチャネルワークフローを作成できます。

最後に、[ データ管理アクティビティ ](../../automating/using/about-data-management-activities.md) を使用して、データベースからデータを操作できます。

詳しくは、以下を参照してください。

* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [ワークフローの実行](../../automating/using/about-workflow-execution.md)
* [ワークフローのベストプラクティス](../../automating/using/best-practices-workflows.md)

## データのフィルタリング {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="15px">

**クエリエディター** を活用してデータベースのデータをフィルタリングし、受信者をより適切にターゲット設定できる母集団を作成します。 クエリエディターを使用して、クエリタイプのオーディエンスの作成、配信ターゲットの定義、ワークフローアクティビティの母集団の定義など、複数のアクションをCampaign Standardで実行できます。

クエリエディターには、すばやく簡単にフィルタリングできる **定義済みフィルターとルール** が付属しています。 ただし、高度な式の編集 **機能を使用するこ** もできます。 これにより、手動で条件を入力し、関数を使用して、独自のルールを作成できます。

詳しくは、以下を参照してください。

* [クエリの編集](../../automating/using/editing-queries.md)
* [高度な式の編集](../../automating/using/advanced-expression-editing.md)
* [関数のリスト](../../automating/using/list-of-functions.md)

## データのインポート/エクスポート {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="20px">

Campaign Standardには、データのインポートとエクスポートを行うための **データ管理機能** がいくつか付属しています。

[ ワークフローデータ管理アクティビティ ](../../automating/using/about-data-management-activities.md) を使用すると、データのインポート、フィールドの一括更新の実行、ファイルの送受信、未識別データの既存リソースへのリンクなどを行うことができます。

[ インポートテンプレート ](../../automating/using/importing-data-with-import-templates.md) を使用すると、管理者が定義した特定のタイプのインポートを、簡略化されたインポート機能を使用して管理できます。

[ ログのエクスポート ](../../automating/using/exporting-logs.md) を使用すると、シンプルなワークフローでログデータをエクスポートでき、独自のレポートまたは BI ツールでマーケティングキャンペーンの結果を分析できます。

[ パッケージ ](../../automating/using/managing-packages.md) を活用して、異なる Campaign インスタンス間でリソースを交換します。例えば、インスタンスの設定をレプリケートしたり、サーバーからカスタムリソースを含む別のサーバーにデータを転送したりします。

最後に、[ リストの書き出し ](../../automating/using/exporting-lists.md) を使用すると、テストプロファイルのリストや強制隔離のメールアドレスのリストなど、Campaign Standardから任意のリストを書き出すことができます。

詳しくは、以下を参照してください。

* [データのインポートおよびエクスポート](../../automating/using/about-data-import-and-export.md)
* [ユースケース：カスタムリソースのエクスポート／インポート](../../automating/using/exporting-importing-custom-resources.md)

## その他のリソース

* [ プロセスとデータ管理のチュートリアルビデオ ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=ja)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [Campaign Standard データモデルの基本を学ぶ](../../developing/using/get-started-data-model.md)
