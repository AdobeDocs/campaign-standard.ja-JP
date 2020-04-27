---
title: Data StandardのデータモデルのベストプラクティスAdobe Campaign標準
description: Adobe Campaign標準データモデルを設計する際のベストプラクティスを説明します。
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
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# データモデルのベストプラクティス{#data-model-best-practices}

このドキュメントでは、データモデルを設計する際の主要な推奨Adobe Campaignについて説明します。


>[!NOTE]
>
>リソースの作成と変更を行って、事前定義のAdobe Campaignモデルを拡張するには、この節を参照 [してください](../../developing/using/key-steps-to-add-a-resource.md)。
>
>このページには、組み込みリソースのデータモデル表現が表 [示されます](../../developing/using/datamodel-introduction.md)。

## 概要 {#overview}

Adobe Campaignシステムは非常に柔軟性が高く、初期実装を超えて拡張できます。 ただし、可能性は無限ですが、賢明な判断を下し、データモデルを設計する開始の強力な基盤を築くことが重要です。

このドキュメントでは、Adobe Campaignツールを適切に設計する方法を学ぶための一般的な使用例とベストプラクティスを示します。

## データモデルのアーキテクチャ {#data-model-architecture}

Adobe Campaign標準は、オンラインおよびオフラインの戦略を調整して、パーソナライズされた顧客体験を作り出すのに役立つ、強力なクロスチャネルキャンペーン管理システムです。

### 顧客中心アプローチ {#customer-centric-approach}

ほとんどの電子メールサービスプロバイダーは、リスト中心アプローチを通じて顧客と通信していますが、Adobe Campaignは、顧客とその属性の幅広い表示を活用するために、リレーショナルデータベースに依存しています。

この顧客中心アプローチは、次の図のとおりです。 灰色の **プロファイル** ・リソースは、すべてが構築される主要な顧客テーブルを表します。

![](assets/customer-centric-data-model.png)

Adobe Campaignのデフォルトのデータモデルは、この節で説 [明します](../../developing/using/datamodel-introduction.md)。

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the master record. This master record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a master customer record which will be sent to Adobe Campaign.-->

### Adobe Campaign {#data-for-campaign}

どのデータをAdobe Campaignに送るか マーケティングアクティビティに必要なデータを判断することが重要です。

>[!NOTE]
>
>Adobe CampaignはData Warehouseではありません。 したがって、可能な顧客とその関連情報をすべてAdobe Campaignにインポートしない。

属性をAdobe Campaignに必要とするかどうかを決定するには、次のいずれかのカテゴリに該当するかどうかを決定します。
* セグメント化に使用する **属性**
* 属性を使用した **データ管理** (集計計算など)
* パーソナライゼーションに使用され **る属性**
* 属性を使用して **レポート** (カスタムデータに基づいてレポートをプロファイル可能)

これらのいずれにも該当しない場合は、この属性がAdobe Campaignで必要になりません。

### データタイプ {#data-types}

システムの優れたアーキテクチャとパフォーマンスを確保するには、次のベストプラクティスに従って、Adobe Campaignでデータを設定します。
* 文字列フィールドの長さは、常に列で定義する必要があります。 デフォルトでは、Adobe Campaignの最大長は255文字ですが、サイズが短い長さを超えないことが既にわかっている場合は、フィールドを短くすることをお勧めします。
* ソース・システムのサイズが過大評価され、到達しないことが確実な場合、ソース・システムのAdobe Campaignよりもフィールドの方が小さくなることは許容できる。 これは、文字列が短いか、整数が小さいことを意味します。Adobe Campaignは

## データ構造の設定 {#configuring-data-structure}

ここでは、リソースのデータ構造を設定す [る際のベストプラクティスについて説明します](../../developing/using/configuring-the-resource-s-data-structure.md)。

### 識別子 {#identifiers}

Adobe Campaignリソースには3つの識別子があり、識別子を追加できます。

次の表に、これらの識別子とその目的を示します。

>[!NOTE]
>
>表示名は、ユーザーのユーザーインターフェイスを介して表示されるAdobe Campaignの名前です。 技術的な名前は、リソース定義の実際のフィールド名（およびテーブルの列名）です。

| 表示名 | 技術名 | 説明 | ベストプラクティス |
|--- |--- |--- |--- |
|  | 主キー | <ul><li>PKeyは、Adobe Campaignテーブルの物理主キーです。</li><li>この識別子は、通常、特定のAdobe Campaignインスタンスに対して一意です。</li><li>Adobe Campaign標準では、この値はエンドユーザーに対しては表示されません（URLを除く）。</li></ul> | <ul><li>[APIシステムを介して](../../api/using/about-campaign-standard-apis.md)、PKey値（物理キーではなく生成/ハッシュ値）を取得できます。</li><li>APIを使用してレコードを取得、更新、削除する以外の目的で使用することはお勧めしません。</li></ul> |
| ID | nameまたはinternalName | <ul><li>この情報は、テーブル内のレコードの一意の識別子です。 この値は手動で更新できます。</li><li>この識別子は、別のインスタンスのデプロイ時に値を保持します。Adobe Campaign 生成された値とは異なる名前を持ち、パッケージを介してエクスポートできる必要があります。</li><li>これは、テーブルの実際の主キーではありません。</li></ul> | <ul><li>スペース&quot;&quot;、セミコロン&quot;:&quot;、ハイフン&quot;-&quot;などの特殊文字は使用しないでください。</li><li>これらの文字はすべて、アンダースコア「_」（文字を使用できます）で置き換えられます。 例えば、「abc-def」と「abc:def」は「abc_def」として保存され、相互に上書きされます。</li></ul> |
| ラベル | label | <ul><li>ラベルは、オブジェクトまたはレコードのビジネス識別子です(Adobe Campaign内)。</li><li>このオブジェクトでは、スペースと特殊文字を使用できます。</li><li>レコードの一意性を保証するものではありません。</li></ul> | <ul><li>オブジェクトのラベルの構造を決定することをお勧めします。</li><li>これは、ユーザーにとってレコードやオブジェクトを識別する、最も使いやすいAdobe Campaignです。</li></ul> |
| ACS ID | acsId | <ul><li>追加の識別子を生成できます。acs [ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。</li><li>PKeyはAdobe Campaignユーザーインターフェイスで使用できないので、プロファイルレコードの挿入時に生成される一意の値を取得するソリューションです。</li><li>この値は、レコードがリソースに挿入される前にリソースでこのオプションが有効になっている場合にのみ、自動的に生成されます。Adobe Campaign</li></ul> | <ul><li>このUUIDは、紐付けキーとして使用できます。</li><li>自動生成されたACS IDは、ワークフローまたはパッケージ定義の参照として使用できません。</li><li>この値は、1つのAdobe Campaignインスタンスに固有です。</li></ul> |

### 識別キー {#keys}

リソースで作成される各Adobe Campaignには、少なくとも1つの一意の識別キーが [必要です](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

カスタムリソースを作成する場合は、次の2つのオプションがあります。

* 自動生成されたキーと内部カスタムキーの組み合わせ。 このオプションは、システムキーが複合キーであるか、整数でない場合に興味深いものです。 整数は、大きなテーブルで高いパフォーマンスを得るとともに、他のテーブルとの結合を行います。
* プライマリ・キーを外部システムのプライマリ・キーとして使用する。 異なるシステム間で一貫したキーを使用して、データのインポートとエクスポートのアプローチを簡素化するので、このソリューションをお勧めします。

識別キーは、参照として使用しないでください(ワークフロー)。

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### インデックス {#indexes}

Adobe Campaignは、リソースで定 [義された](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) 、すべての主キーと内部キーにインデックスを自動的に追加します。

* パフォーマンスが向上する可能性があるので、追加のインデックスを定義することをお勧めします。
* ただし、インデックスがデータベース上の領域を使用するので、追加するインデックスの数は多すぎないでください。 また、多数のインデックスがパフォーマンスに悪影響を与える場合もあります。
* 定義するインデックスを慎重に選択します。

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### リンク {#links}

他のリソースを使用したリンクの定義については、この節で [説明しま](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)す。

* ワークフロー内の任意のテーブルを結合できますが、リソース間の共通リンクをデータ構造の定義で直接定義することをお勧めします。
* リンクは、テーブル内の実際のデータと整列して定義する必要があります。 誤った定義は、例えば予期せぬレコードの複製など、リンクを介して取得したデータに影響を与える可能性があります。
* リソース名を使用して、リンクに一貫した名前を付けます。リンク名は、遠隔テーブルの内容を理解するのに役立ちます。
* 「id」をサフィックスとしてリンクに名前を付けないでください。 例えば、「transactionId」ではなく「transaction」という名前を付けます。

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## パフォーマンス {#performance}

パフォーマンスをいつでも向上させるには、次のベストプラクティスに従ってください。

### 一般的な推奨事項 {#general-recommendations}

* 「次を含む」などの操作は使用しないでください。クエリ 何を求め、フィルタリングを行うかがわかっている場合は、「EQUAL TO」などの特定のフィルタ演算子を使用して同じ条件を適用します。
* データをインデックスで作成する際は、インデックスのないフィールドとの結合を避けてください。ワークフローで。
* インポートやエクスポートのようなプロセスが業務時間外に発生することを確認します。
* すべての日別アクティビティのスケジュールがあることを確認し、スケジュールに従います。
* 日別のプロセスの1つまたは複数が失敗し、その同じ日に実行する必要がある場合は、手動プロセスが開始されたときに競合するプロセスが実行されていないことを確認します。システムのパフォーマンスに影響を与える可能性があります。
* 読み込みプロセス中、または手動のキャンペーンが実行されている場合は、毎日のプロセスが実行されないことを確認します。
* 各行のフィールドを複製する代わりに、1つまたは複数の参照テーブルを使用します。 キーと値のペアを使用する場合は、数値キーを選択することをお勧めします。
* 短い文字列は引き続き使用できます。 参照テーブルが外部システムに既に配置されている場合、同じテーブルを再利用すると、データをシステムと統合しやすくなります。Adobe Campaign

### 1対多の関係 {#one-to-many-relationships}

* データデザインは、ユーザビリティと機能に影響を与えます。 多くの1対多の関係を使用してデータモデルを設計する場合、ユーザーがアプリケーションで意味のあるロジックを作成するのが難しくなります。 1対多のフィルターロジックは、技術的でないマーケターが正しく構築し、理解するのが困難な場合があります。
* すべての重要なフィールドを1つのテーブルに含めると、ユーザーが必要なフィールドを簡単に作成できるので、便利です。クエリ また、結合を避けることができる場合に、一部のフィールドをテーブルに重複するのも、パフォーマンスが向上する場合があります。
* 組み込み機能の中には、1対多の関係(オファーの重み付けの式や配信など)を参照できないものもあります。

### 大きいテーブル {#large-tables}

大きなテーブルと複雑な結合を使用してデータモデルを設計する際に従うべきベストプラクティスを、以下に示します。

* 特に未使用の列を識別して、列の数を減らします。
* 複数の条件や複数の列での結合など、複雑な結合を避け、データモデルの関係を最適化します。
* 結合キーの場合、文字列ではなく常に数値データを使用します。
* ログの保存の深さをできる限り減らします。 より深い履歴が必要な場合は、集計の計算やカスタムログテーブルの処理を行って、より大きな履歴を保存できます。