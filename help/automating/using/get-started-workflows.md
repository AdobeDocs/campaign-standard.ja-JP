---
title: プロセスとデータ管理の概要
description: ワークフローを使用すれば、データおよびオーディエンスの管理やメッセージの送信などのプロセスを自動化できます。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 35%

---

# プロセスとデータ管理の概要 {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">ワークフローアクティビティ</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">ユースケース</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">データのフィルタリング</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">データのインポート/エクスポート</a></p></td></tr>
</table>

Adobe Campaign は、セグメント化、キャンペーン実行、ファイル処理などの複雑なプロセスを設計できる包括的なグラフィカル環境を提供します。 例えば、ワークフローを使用して、サーバーからファイルをダウンロードした後、ファイルを解凍し、ファイル内のレコードを Adobe Campaign データベースに読み込むことができます。

ワークフローには、ユーザーにタスクを割り当てたり、実行されたタスクを承認させることによって、ユーザーの関与を促すこともできます。 つまり、1 人または複数のユーザーにタスクを割り当ててコンテンツで作業したり、ターゲットを指定したり、メッセージを送信する前に本配信前確認を承認したりできます。

ワークフローは、次のように異なるコンテキストで使用できます。

* オーディエンスを管理したり、メッセージを送信したりするためのターゲティング。
* データを操作するためのデータ管理（ETL）。
* Campaign データベースへのデータの読み込み。
* データベースのクリーンアップ、トラッキング情報の復元などの技術的プロセス。

>[!IMPORTANT]
>
> Adobeでは、20 個を超えるアクティブなワークフローを同時に実行しないようにし、時間の経過と共にワークフローの実行を優先し、広げることをお勧めします。 詳しくは、 [このページ](../../automating/using/best-practices-workflows.md).

## ワークフローアクティビティ {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

ワークフローの設計に役立つ様々なアクティビティを利用できます。

[ターゲティングアクティビティ](../../automating/using/about-targeting-activities.md) では、セットを定義し、積集合、和集合、除外の各操作を使用して分割または組み合わせることで、1 つ以上のターゲットを作成できます。

を使用 [実行アクティビティ](../../automating/using/about-execution-activities.md)を使用して、ワークフローとそのアクティビティを調整します。 [チャネルアクティビティ](../../automating/using/about-channel-activities.md) では、Campaign Standardの通信チャネルを組み合わせて、クロスチャネルのワークフローを作成できます。

最後に [データ管理アクティビティ](../../automating/using/about-data-management-activities.md) を使用すると、データベースのデータを操作できます。

詳しくは、以下を参照してください。

* [ワークフローの作成](../../automating/using/building-a-workflow.md)
* [ワークフローの実行](../../automating/using/about-workflow-execution.md)
* [ワークフローのベストプラクティス](../../automating/using/best-practices-workflows.md)

## データのフィルタリング {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

以下を利用する： **クエリエディター** データベースのデータをフィルタリングし、受信者をより適切にターゲティングするための母集団を作成します。 クエリエディターを使用して、Campaign Standardで複数のアクション（クエリタイプのオーディエンスの作成、配信ターゲットの定義、ワークフローアクティビティでの母集団）を実行できます。

クエリエディターには、 **定義済みフィルターとルール** 迅速で簡単なフィルタリングのために。 ただし、 **高度な式の編集** 機能。 これにより、独自のルールを作成するために、条件を手動で入力し、関数を使用することができます。

詳しくは、以下を参照してください。

* [クエリの編集](../../automating/using/editing-queries.md)
* [高度な式の編集](../../automating/using/advanced-expression-editing.md)
* [関数のリスト](../../automating/using/list-of-functions.md)

## データのインポート/エクスポート {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standardには複数の **データ管理機能** をクリックして、データのインポートとエクスポートを行います。

[ワークフローのデータ管理アクティビティ](../../automating/using/about-data-management-activities.md) では、データのインポート、フィールドの一括更新、ファイルの受信と送信、または識別されていないデータの既存のリソースへのリンクを行うことができます。

を使用 [テンプレートのインポート](../../automating/using/importing-data-with-import-templates.md)では、管理者が定義した特定のタイプのインポートを、簡易インポート機能を使用して管理できます。

[ログの書き出し](../../automating/using/exporting-logs.md) を使用すると、シンプルなワークフローでログデータをエクスポートし、独自のレポートまたは BI ツールでマーケティングキャンペーンの結果を分析できます。

活用 [パッケージ](../../automating/using/managing-packages.md) 別のキャンペーンインスタンス間でリソースを交換する場合（例えば、インスタンスの設定をレプリケートする場合、またはカスタムリソースを含むサーバー間でデータを転送する場合）。

最後に [リストの書き出し](../../automating/using/exporting-lists.md) を使用すると、Campaign Standardから任意のリストを書き出すことができます（例：テストプロファイルのリスト、強制隔離 E メールアドレスのリストなど）。

詳しくは、以下を参照してください。

* [データのインポートおよびエクスポート](../../automating/using/about-data-import-and-export.md)
* [ユースケース：カスタムリソースのエクスポート／インポート](../../automating/using/exporting-importing-custom-resources.md)

## その他のリソース

* [プロセスとデータ管理のチュートリアルビデオ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=ja)
* [テクニカルワークフロー](../../administration/using/technical-workflows.md)
* [Campaign Standard データモデルの基本を学ぶ](../../developing/using/get-started-data-model.md)
