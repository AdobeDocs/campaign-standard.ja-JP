---
title: Adobe Campaign Standardのデータモデルのベストプラクティス
description: Adobe Campaign Standardデータモデルをデザインする際のベストプラクティスについて説明します。
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0aa1089ee744a86a95d344235feba7adb9150a4

---


# データモデルのベストプラクティス{#data-model-best-practices}

このドキュメントでは、Adobe Campaignデータモデルをデザインする際の主な推奨事項について説明します。


>[!NOTE]
>
>Adobe Campaignの事前定義データモデルを拡張するためのリソースを作成および変更するには、この節を参照 [してください](../../developing/using/key-steps-to-add-a-resource.md)。
>
>標準搭載のリソースのデータモデル表現は、こちらで確認でき [ます](../../developing/using/datamodel-introduction.md)。

## 概要 {#overview}

Adobe Campaignシステムは非常に柔軟性が高く、初期実装を超えて拡張できます。 ただし、可能性は無限ですが、賢明な判断を下し、強力な基盤を構築してデータモデルの設計を始めることが重要です。

このドキュメントでは、Adobe Campaignツールを適切に設計する方法を学ぶための一般的な使用例とベストプラクティスを紹介します。

## データモデルのアーキテクチャ {#data-model-architecture}

Adobe Campaign Standardは、オンラインおよびオフラインの戦略を調整して、パーソナライズされた顧客エクスペリエンスを作成するのに役立つ、強力なクロスチャネルキャンペーン管理システムです。

### 顧客中心アプローチ {#customer-centric-approach}

ほとんどの電子メールサービスプロバイダーはリスト中心アプローチを使用して顧客と通信していますが、Adobe Campaignは顧客とその属性の幅広いビューを活用するためにリレーショナルデータベースに依存しています。

この顧客中心アプローチを次の表に示します。 灰色の **Profile** リソースは、すべての作成が行われている主要顧客テーブルを表します。

![](assets/customer-centric-data-model.png)

この節では、Adobe Campaignのデフォルトのデータモデルについて説明 [します](../../developing/using/datamodel-introduction.md)。

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the master record. This master record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a master customer record which will be sent to Adobe Campaign.-->

### Adobe Campaignのデータ {#data-for-campaign}

Adobe Campaignに送信するデータは何ですか。 マーケティング活動に必要なデータを決定することが重要です。

>[!NOTE]
>
>Adobe CampaignはData Warehouseではありません。 したがって、可能な顧客とその関連情報をすべてAdobe Campaignにインポートしないでください。

属性がAdobe Campaignで必要かどうかを判断するには、次のいずれかのカテゴリに該当するかどうかを決定します。
* セグメント化に使用する **属性**
* データ管理プロ **セスに使用する属性** （集計計算など）
* パーソナライゼーションに使用さ **れる属性**
* レポートに使用する **属性** （カスタムプロファイルデータに基づいてレポートを作成可能）

これらのいずれにも該当しない場合、Adobe Campaignでこの属性は必要ない可能性が高くなります。

### データタイプ {#data-types}

システムのアーキテクチャとパフォーマンスを確実に向上させるには、以下のベストプラクティスに従ってAdobe Campaignでデータを設定します。
* 文字列フィールドの長さは、常に列で定義する必要があります。 デフォルトでは、Adobe Campaignの最大長は255文字ですが、サイズが短くならないことが既にわかっている場合は、フィールドを短くすることをお勧めします。
* ソースシステムのサイズが過大評価され、サイズに達しないことが確実な場合は、Adobe Campaignのフィールドをソースシステムのフィールドよりも短くすることが許容されます。 これは、Adobe Campaignの文字列が短いか、整数が小さい可能性があります。

## データ構造の設定 {#configuring-data-structure}

ここでは、リソースのデータ構造を設定す [る際のベストプラクティスについて説明します](../../developing/using/configuring-the-resource-s-data-structure.md)。

### 識別子 {#identifiers}

Adobe Campaignリソースには3つの識別子があり、別の識別子を追加できます。

次の表に、これらの識別子とその目的を示します。

>[!NOTE]
>
>表示名は、Adobe Campaignユーザーインターフェイスを介してユーザーに表示されるフィールドの名前です。 技術名は、リソース定義内の実際のフィールド名（およびテーブルの列名）です。

| 表示名 | 技術名 | 説明 | ベストプラクティス |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKeyは、Adobe Campaignテーブルの物理主キーです。</li><li>この識別子は、通常、特定のAdobe Campaignインスタンスに対して一意です。</li><li>Adobe Campaign Standardでは、この値はエンドユーザーには表示されません。</li></ul> | <ul><li>[APIシステムを介して](../../api/using/about-campaign-standard-apis.md)、PKey値（物理キーではなく生成/ハッシュ値）を取得できます。</li><li>APIを使用してレコードを取得、更新、削除する以外の目的で使用することはお勧めしません。</li></ul> |
| ID | nameまたはinternalName | <ul><li>この情報は、テーブル内のレコードの一意の識別子です。 この値は手動で更新できます。</li><li>このIDは、Adobe Campaignの別のインスタンスにデプロイする場合に値を保持します。 生成された値とは異なる名前を持ち、パッケージを介してエクスポートできるようにする必要があります。</li><li>これは、テーブルの実際の主キーではありません。</li></ul> | <ul><li>スペース&quot;&quot;、セミコラム&quot;:&quot;、ハイフン&quot;-&quot;などの特殊文字は使用しないでください。</li><li>これらの文字はすべて、アンダースコア「_」に置き換えられます（使用できる文字）。 例えば、「abc-def」と「abc:def」は「abc_def」として保存され、相互に上書きされます。</li></ul> |
| ラベル | label | <ul><li>ラベルは、Adobe Campaignのオブジェクトまたはレコードのビジネス識別子です。</li><li>このオブジェクトでは、スペースと特殊文字を使用できます。</li><li>レコードの独自性を保証するものではありません。</li></ul> | <ul><li>オブジェクトのラベルの構造を決定することをお勧めします。</li><li>これは、Adobe Campaignユーザーのレコードやオブジェクトを識別するための、最も使いやすいソリューションです。</li></ul> |
| ACS ID | acsId | <ul><li>追加の識別子を生成できます。acs [ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。</li><li>Adobe CampaignユーザーインターフェイスではPKeyを使用できないので、これはプロファイルレコードの挿入中に生成される一意の値を取得するためのソリューションです。</li><li>この値は、レコードがAdobe Campaignに挿入される前にリソースでこのオプションが有効になっている場合にのみ、自動的に生成できます。</li></ul> | <ul><li>このUUIDは、調整キーとして使用できます。</li><li>自動生成されたACS IDは、ワークフローまたはパッケージ定義の参照として使用できません。</li><li>この値は、Adobe Campaignインスタンスに固有の値です。</li></ul> |

### 識別キー {#keys}

Adobe Campaignで作成される各リソースには、少なくとも1つの一意の識別キーが [必要です](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

カスタムリソースを作成する場合は、次の2つの方法があります。

* 自動生成されたキーと内部カスタムキーの組み合わせ。 このオプションは、システムキーが複合キーであるか、整数でない場合に興味深いものです。 整数は、大きいテーブルで高いパフォーマンスを提供し、他のテーブルと結合します。
* 外部システムのプライマリキーとしてプライマリキーを使用する。 異なるシステム間で一貫したキーを使用して、データのインポートとエクスポートのアプローチを簡素化するため、通常、このソリューションをお勧めします。

IDキーは、ワークフローでの参照として使用しないでください。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### 索引 {#indexes}

Adobe Campaignは、リソースに定義され [たすべての](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) 、プライマリキーと内部キーに自動的にインデックスを追加します。

* パフォーマンスが向上する可能性があるので、追加のインデックスを定義することをお勧めします。
* ただし、インデックスがデータベース上の領域を使用するので、追加するインデックスの数を増やさないでください。 また、多数のインデックスがパフォーマンスに悪影響を及ぼす場合もあります。
* 定義する必要があるインデックスを慎重に選択します。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### リンク {#links}

他のリソースを使用したリンクの定義については、この節 [で説明しま](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)す。

* ワークフロー内の任意のテーブルを結合できますが、リソース間の共通リンクをデータ構造の定義で直接定義することをお勧めします。
* リンクは、テーブル内の実際のデータに合わせて定義する必要があります。 誤った定義は、例えば予期せぬレコードの複製など、リンクを介して取得したデータに影響を与える可能性があります。
* リソース名を使用して、リンクに一貫した名前を付けます。リンク名は、遠隔テーブルの内容を理解するのに役立ちます。
* 「id」をサフィックスとして含むリンクに名前を付けないでください。 例えば、「transactionId」ではなく「transaction」という名前を付けます。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## パフォーマンス {#performance}

パフォーマンスをいつでも向上させるには、次のベストプラクティスに従ってください。

### 一般的な推奨事項 {#general-recommendations}

* クエリーで「CONTAINS」などの操作を使用しないでください。 何を求め、フィルターを適用するかがわかっている場合は、「EQUAL TO」などの特定のフィルター演算子を使用して同じ条件を適用します。
* ワークフローでデータを作成する際に、インデックスが付いていないフィールドとの結合を避けます。
* インポートやエクスポートなどのプロセスが業務時間外に発生することを確認します。
* すべての日次アクティビティのスケジュールがあることを確認し、スケジュールに従ってください。
* 日別のプロセスの1つまたは複数が失敗し、その同じ日に実行する必要がある場合は、手動プロセスを開始する際に競合するプロセスが実行されていないことを確認します。システムのパフォーマンスに影響を与える可能性があります。
* インポートプロセス中、または手動のプロセスが実行されている場合は、毎日のキャンペーンが実行されないことを確認します。
* 各行のフィールドを複製するのではなく、1つまたは複数の参照テーブルを使用します。 キーと値のペアを使用する場合は、数値キーを選択することをお勧めします。
* 短い文字列は引き続き使用できます。 参照テーブルが既に外部システムに配置されている場合は、同じテーブルを再利用すると、Adobe Campaignとのデータ統合が容易になります。

### 1対多の関係 {#one-to-many-relationships}

* データデザインは、ユーザビリティと機能に影響を与えます。 多くの1対多の関係を使用してデータモデルを設計すると、ユーザーがアプリケーションで意味のあるロジックを作成するのが難しくなります。 1対多のフィルターロジックは、技術的でないマーケターが正しく構築し、理解するのが困難な場合があります。
* すべての必須フィールドを1つのテーブルに配置すると、クエリを簡単に作成できるので、便利です。 また、結合を避けることができる場合に、テーブル間で一部のフィールドを複製するのもパフォーマンスが向上する場合があります。
* 特定の組み込み機能は、オファーの重み付けの数式や配信など、1対多の関係を参照できません。

### 大きいテーブル {#large-tables}

大きなテーブルと複雑な結合を使用してデータモデルを設計する際に従うべきベストプラクティスを以下に示します。

* 特に未使用の列を識別することで、列の数を減らします。
* 複数の条件や複数の列に対する結合など、複雑な結合を避け、データモデルの関係を最適化します。
* 結合キーには、文字列ではなく常に数値データを使用します。
* ログ保存の深さをできるだけ減らします。 より深い履歴が必要な場合は、計算を集計したり、カスタムログテーブルを処理してより大きな履歴を保存したりできます。