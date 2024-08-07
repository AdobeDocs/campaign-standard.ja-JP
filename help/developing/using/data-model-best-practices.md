---
title: Adobe Campaign Standardのデータモデルのベストプラクティス
description: Adobe Campaign Standard データモデルを設計する際のベストプラクティスについて説明します。
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 58d4e02f-3c9a-4e5d-a6aa-fdbcec0d8dda
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1557'
ht-degree: 51%

---

# データモデルのベストプラクティス{#data-model-best-practices}

このドキュメントでは、Adobe Campaign データモデルを設計する際の主なレコメンデーションの概要を説明します。


>[!NOTE]
>
>Adobe Campaignの事前定義済みデータモデルを拡張するためのリソースを作成および変更するには、[ この節 ](../../developing/using/key-steps-to-add-a-resource.md) を参照してください。
>
>ビルトインリソースのデータモデル表現については、[ このページ ](../../developing/using/datamodel-introduction.md) を参照してください。

## 概要 {#overview}

Adobe Campaign システムは非常に柔軟性が高く、初期の実装をさらに拡張可能です。 可能性は無限です。とはいえ、賢明な判断を下し、データモデルの設計を開始する前に強力な基盤を構築しておくことが不可欠です。

このドキュメントでは、Adobe Campaign ツールを適切に構築する方法を学ぶための一般的なユースケースとベストプラクティスを示します。

## データモデルアーキテクチャ {#data-model-architecture}

Adobe Campaign Standardは強力なクロスチャネルキャンペーン管理システムであり、オンラインとオフラインのマーケティング戦略を融合して、パーソナライズされたカスタマーエクスペリエンスを実現できます。

### 顧客中心のアプローチ {#customer-centric-approach}

ほとんどのメールサービスプロバイダーは、リスト中心アプローチを使用して顧客と通信していますが、Adobe Campaign は、リレーショナルデータベースに基づいて、顧客と顧客の属性を幅広く視野に入れて活用しています。

この顧客中心アプローチを次のグラフに示します。 グレー表示の **プロファイル** リソースは、すべてが構築されるメインの顧客テーブルを表します。

![](assets/customer-centric-data-model.png)

Adobe Campaignのデフォルトデータモデルについては、この [ 節 ](../../developing/using/datamodel-introduction.md) を参照してください。

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Adobe Campaign 用データ {#data-for-campaign}

Adobe Campaign に送信すべきデータマーケティングアクティビティに必要なデータを決定することがきわめて重要です。

>[!NOTE]
>
>Adobe Campaignはデータウェアハウスではありません。 そのため、考えられるすべての顧客とその関連情報をAdobe Campaignに読み込もうとしないでください。

Adobe Campaignで必要な属性であるかどうかを判断するには、次のカテゴリのいずれかに該当するかどうかを判断します。
* **セグメント化**&#x200B;に使用する属性
* **データ管理プロセス**&#x200B;に使用する属性（集計計算など）
* **パーソナライゼーション**&#x200B;に使用する属性
* **レポート** に使用する属性（レポートは、カスタムプロファイルデータに基づいて作成できます）

これらのいずれにも該当しない場合、その属性は Adobe Campaign でまず必要にならないと思われます。

### データタイプ {#data-types}

システムのアーキテクチャとパフォーマンスを適切な状態に保つには、次のベストプラクティスに従ってAdobe Campaignのデータを設定します。
* 文字列フィールドの長さは、常に列で定義する必要があります。 Adobe Campaignの最大長はデフォルトでは 255 文字ですが、Adobeでは、サイズが短くなることがあらかじめわかっている場合は、フィールドの長さを短くすることをお勧めします。
* 参照元のシステム内のフィールドサイズが過大に見積もられていて、データはそれほど長くないことが確実な場合は、Adobe Campaign のフィールドを参照元のシステムのフィールドより短くしても構いません。これにより、Adobe Campaign では短い文字列や小さい整数として扱うことができます。

## データ構造の設定 {#configuring-data-structure}

この節では、「リソースのデータ構造を設定 [ する際のベストプラクティスの概要を説明し ](../../developing/using/configuring-the-resource-s-data-structure.md) す。

### 識別子 {#identifiers}

Adobe Campaign リソースには 3 つの識別情報があり、別の識別情報を追加することもできます。

これらの識別子とその目的を次の表に示します。

>[!NOTE]
>
>表示名とは、Adobe Campaign ユーザーインターフェイスを通じてユーザーに表示されるフィールドの名前です。 技術名は、リソース定義の実際のフィールド名（およびテーブル列名）です。

| 表示名 | 技術名 | 説明 | ベストプラクティス |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey は、Adobe Campaign テーブルの物理的なプライマリキーです。</li><li>この ID は通常、特定のAdobe Campaign インスタンスに対して一意です。</li><li>Adobe Campaign Standardでは、この値は（URL 内を除いて）エンドユーザーには表示されません。</li></ul> | <ul><li>[API システム ](../../api/using/get-started-apis.md) を介して、PKey 値（物理キーではなく、生成/ハッシュ化された値）を取得できます。</li><li>API を使用してレコードの取得、更新、削除以外の目的で使用することはお勧めしません。</li></ul> |
| ID | name または internalName | <ul><li>この情報は、テーブル内のレコードの一意の識別子です。この値は手動で更新できます。</li><li>この識別子は、Adobe Campaignの別のインスタンスにデプロイされたときにその値を保持します。 パッケージを介して書き出すには、生成された値とは異なる名前を付ける必要があります。</li><li>これは、テーブルの実際のプライマリキーではありません。</li></ul> | <ul><li>スペース「」、セミコロン「:」、ハイフン「–」などの特殊文字は使用しないでください。</li><li>これらの文字はすべて、アンダースコア「_」（許可されている文字）に置き換えられます。例えば、「abc-def」と「abc:def」は「abc_def」として保存され、相互に上書きされます。</li></ul> |
| ラベル | ラベル | <ul><li>ラベルは、Adobe Campaign 内のオブジェクトまたはレコードのビジネス識別子です。</li><li>このオブジェクトでは、スペースと特殊文字も使用できます。</li><li>レコードの一意性は保証されません。</li></ul> | <ul><li>オブジェクトラベルの構造を決定することをお勧めします。</li><li>これは、Adobe Campaign ユーザーにとって、レコードまたはオブジェクトを識別するための最も使いやすい解決策です。</li></ul> |
| ACS ID | acsId | <ul><li>追加の識別子 [ACS ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) を生成できます。</li><li>PKey はAdobe Campaign ユーザーインターフェイスでは使用できないので、これは、プロファイルレコードの挿入中に生成された一意の値を取得するための解決策です。</li><li>値は、レコードがAdobe Campaignに挿入される前に、リソースでこのオプションが有効になっている場合にのみ、自動生成できます。</li></ul> | <ul><li>この UUID は、紐付けキーとして使用できます。</li><li>自動生成された ACS ID は、ワークフローやパッケージ定義で参照として使用することはできません。</li><li>この値は、Adobe Campaign インスタンスに固有です。</li></ul> |

### 識別キー {#keys}

Adobe Campaignで作成される各リソースには、一意の [ID キー ](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys) が少なくとも 1 つ必要です。

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

カスタムリソースを作成する場合、次の 2 つのオプションがあります。

* 自動生成されたキーと内部カスタムキーの組み合わせ。 このオプションは、システムキーが複合キーであるか、整数ではない場合に役立ちます。 整数は、大きいテーブルで高いパフォーマンスを提供し、他のテーブルと結合できます。
* プライマリキーを外部システムのプライマリキーとして使用します。 このソリューションは、異なるシステム間で一貫したキーを使用してデータのインポートとエクスポートのアプローチを簡素化するので、通常は推奨されます。

識別キーは、ワークフローで参照として使用しないでください。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### インデックス {#indexes}

Adobe Campaignは、リソースで定義されているすべてのプライマリキーと内部キーに [ インデックス ](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) を自動的に追加します。

* Adobeでは、パフォーマンスを向上させる可能性があるので、追加のインデックスを定義することをお勧めします。
* ただし、データベース上のスペースを使用するので、追加するインデックスが多くなりすぎないようにしてください。 多数のインデックスがあると、パフォーマンスに悪影響を及ぼす場合もあります。
* 定義する必要があるインデックスを慎重に選択します。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### リンク {#links}

他のリソースとのリンクの定義については、[ この節 ](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) を参照してください。

* ワークフロー内の任意のテーブルを結合できますが、リソース間の共通リンクをデータ構造の定義に直接定義することをお勧めします。
* リンクは、テーブル内の実際のデータと整合するように定義する必要があります。誤った定義は、レコードの予期しない複製など、リンクを介して取得したデータに影響を与える可能性があります。
* リンクには、リソース名と一致する名前を付けます。リンク名は遠隔テーブルの内容を理解するのに役立ちます。
* 「id」をサフィックスとして含む名前をリンクに付けないでください。例えば、「transactionId」ではなく「transaction」という名前を付けます。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## パフォーマンス {#performance}

常にパフォーマンスの向上を図るには、次のベストプラクティスに従います。

### 一般的なレコメンデーション {#general-recommendations}

* クエリで「CONTAINS」などの演算子は使用しません。フィルタリングしたい対象がはっきりしている場合は、「EQUAL TO」または他の特定のフィルター演算子を使用して同じ条件を適用します。
* ワークフローでデータを作成する際は、インデックスのないフィールドと結合しないでください。
* インポートやエクスポートなどのプロセスは営業時間外に行われるようにします。
* 日常のすべてのアクティビティがわかるスケジュールがあることを確認して、そのスケジュールに従います。
* 日常的なプロセスの 1 つまたはいくつかが失敗し、その同じ日に実行する必要がある場合があります。手動でプロセスを開始する際は、システムのパフォーマンスに影響を与える可能性があるので、競合するプロセスが実行されていないことを確認します。
* インポートプロセスを実行中、または手動プロセスを実行したときに、日常的なキャンペーンが実行されていないことを確認します。
* すべての行にフィールドを複製するのではなく、参照テーブルを使用します。キーと値のペアを使用する場合は、数値キーを選択することをお勧めします。
* 短い文字列は引き続き使用できます。参照テーブルが外部システムに配置されている場合、それを再利用すると、Adobe Campaign とのデータ統合が容易になります。

### 1 対多の関係 {#one-to-many-relationships}

* データ設計は使い勝手と機能性に影響を与えます。1 対多の関係を多く持つデータモデルを設計すると、ユーザーがアプリケーション内で意味のあるロジックを作成するのが難しくなります。マーケターが技術者でない場合は、1 対多のフィルターロジックを正しく理解して構築するのは困難なことがあります。
* 必須フィールドをすべて 1 つのテーブルにまとめておくと、クエリの作成が容易になります。結合を回避できれば、テーブル間でいくつかのフィールドを複製することもパフォーマンス的には良い場合があります。
* オファーの重み付けの式や配信などのように、1 対多の関係を参照できないビルトイン機能もあります。

### 大きいテーブル {#large-tables}

大きなテーブルと複雑な結合を使用したデータモデルを設計する場合は、以下のベストプラクティスに従う必要があります。

* 列の数を減らします。特に、未使用の列を特定して削減します。
* 複雑な結合を回避して、データモデルのリレーションを最適化します。たとえば、複数の条件や複数の列に対する結合を回避します。
* 結合キーには、文字列ではなく常に数値データを使用します。
* ログを保持する深さをできる限り減らします。 深い履歴が必要な場合は、集計の計算やカスタムログテーブルの処理を行うと、大きな履歴を保存できます。
