---
title: クエリ
description: クエリアクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '1725'
ht-degree: 1%

---


# クエリ{#query}

## 説明 {#description}

![](assets/query.png)

この **[!UICONTROL Query]** アクティビティを使用すると、Adobe Campaignデータベースから要素の母集団をフィルタリングして抽出できます。 専用タブ **[!UICONTROL Additional data]** を使用して、ターゲット母集団を定義できます。 このデータは追加の列に保存され、進行中のワークフローでのみ使用できます。

アクティビティはクエリエディタツールを使用します。 このツールの詳細は、 [専用のセクション](../../automating/using/editing-queries.md#about-query-editor)。

**関連トピック：**

* [クエリのサンプル](../../automating/using/query-samples.md)
* [使用例： 非開封者に新しい配信を送信する再ターゲティングワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)

## 使用状況 {#context-of-use}

この **[!UICONTROL Query]** アクティビティは、次の様々な用途に使用できます。

* 個人をセグメント化して、メッセージ、オーディエンスなどのターゲットを定義する
* Adobe Campaignデータベーステーブル全体のデータを拡充します。
* データのエクスポート.

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Query]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。 デフォルトでは、アクティビティはプロファイルを検索するように事前設定されています。
1. プロファイルリソース以外のリソースに対してクエリを実行する場合は、アクティビティの **[!UICONTROL Properties]** タブに移動し、とを選択し **[!UICONTROL Resource]** ま **[!UICONTROL Targeting dimension]**&#x200B;す。

   パレットに表示されるフィルター **[!UICONTROL Resource]** を調整できます。一方、 **[!UICONTROL Targeting dimension]**&#x200B;選択したリソースに関するコンテキストは、取得する母集団のタイプ(特定されたプロファイル、配信、選択したリソースにリンクされたデータなど)に対応します。

   詳しくは、「 [ターゲティングディメンションとリソース](#targeting-dimensions-and-resources)」を参照してください。

1. タブで、ルールを定義 **[!UICONTROL Target]** して組み合わせてクエリを実行します。
1. 専用タブ **[!UICONTROL Additional data]** を使用して、ターゲット母集団を定義できます。 このデータは追加の列に保存され、進行中のワークフローでのみ使用できます。 特に、クエリのターゲティングディメンションにリンクされたAdobe Campaignデータベーステーブルからデータを追加できます。 「 [データの富化](#enriching-data) 」の節を参照してください。

   >[!NOTE]
   >
   >デフォルトでは、この **[!UICONTROL Remove duplicate rows (DISTINCT)]** クエリは、の **[!UICONTROL Advanced options]** タブ **[!UICONTROL Additional data]** にあるオプションがオンになっています。 パフォーマンス上の理由から、（100からの）追加のデータがアクティビティに多数含まれている場合は、このオプションの選択を解除することをお勧めします。 **[!UICONTROL Query]** このオプションをオフにすると、クエリーされたデータに応じて重複が取得される可能性があるので注意してください。

1. この **[!UICONTROL Transition]****[!UICONTROL Enable an outbound transition]** タブでは、クエリアクティビティの後に、データを取得しない場合でも、送信トランジションを追加できます。

   送信トランジションのセグメントコードは、標準の式変数とイベント変数を使用してパーソナライズできます(イベント変数を使用したアクティビティの [カスタマイズを参照](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables))。

1. アクティビティの設定を確認し、ワークフローを保存します。

## ターゲティングディメンションとリソース {#targeting-dimensions-and-resources}

ターゲティングディメンションとリソースを使用すると、クエリが基にする配信のターゲットを定義できます。

ターゲティングディメンションはターゲットマッピングで定義されます。 詳しくは、[この節](../../administration/using/target-mappings-in-campaign.md)を参照してください。

ターゲティングディメンションとリソースは、クエリアクティビティの **[!UICONTROL Properties]** タブでワークフローを作成するときに定義されます。

>[!NOTE]
>
>ターゲティングディメンションは、オーディエンスの作成時にも定義できます( [この節を参照](../../audiences/using/creating-audiences.md))。

![](assets/targeting_dimension1.png)

ターゲティングディメンションとリソースはリンクされています。 したがって、使用可能なターゲティングディメンションは、選択したリソースによって異なります。

例えば、リソースの場合 **[!UICONTROL Profiles (profile)]**、次のターゲティングディメンションを使用できます。

![](assets/targeting_dimension2.png)

の場合、リスト **[!UICONTROL Deliveries (delivery)]**&#x200B;には次のターゲティングディメンションが含まれます。

![](assets/targeting_dimension3.png)

ターゲティングディメンションとリソースを指定すると、クエリで別のフィルターを使用できるようになります。

リソースに使用できるフィルターの例： **[!UICONTROL Profiles (profile)]**

![](assets/targeting_dimension4.png)

リソースに使用できるフィルターの例： **[!UICONTROL Deliveries (delivery)]**

![](assets/targeting_dimension5.png)

デフォルトでは、ターゲティングディメンションとリソースはターゲットプロファイルに設定されます。 ただし、遠隔テーブル内の特定のレコードを検索する場合は、ターゲティングディメンションとは別のリソースを使用すると便利です。

この方法の詳細については、次の使用例を参照してください。 [ターゲティングディメンションとは異なるリソースの使用](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## データのエンリッチメント {#enriching-data}

と **[!UICONTROL Additional data]****[!UICONTROL Query]****[!UICONTROL Incremental query]****[!UICONTROL Enrichment]** アクティビティのタブを使用すると、対象とするデータを拡張し、このデータを次のワークフローアクティビティに転送して利用できるようになります。 特に、以下を追加できます。

* 単純なデータ
* 集計
* コレクション

集計とコレクションの場合、は、複雑な式 **[!UICONTROL Alias]** に技術IDを与えるために自動的に定義されます。 このエイリアスは一意である必要があり、その後簡単に集計とコレクションを見つけることができます。 この名前を変更して、わかりやすい名前にすることができます。

>[!NOTE]
>
>エイリアスは、次の構文規則に従う必要があります。 英数字と「_」文字のみが許可されます。 エイリアスでは大文字と小文字が区別されます。 エイリアスは「@」文字で開始する必要があります。 「@」の直後の文字は数値にできません。 次に例を示します。 @myAlias_1と@_1Aliasは正しい。 一方、@myAlias#1と@1Aliasは正しくありません。

追加のデータを追加した後、定義した追加のデータに基づいて条件を作成することで、最初にターゲットにしたデータに追加のフィルターレベルを適用できます。

>[!NOTE]
>
>デフォルトでは、この **[!UICONTROL Remove duplicate rows (DISTINCT)]** クエリは、の **[!UICONTROL Advanced options]** タブ **[!UICONTROL Additional data]** にあるオプションがオンになっています。 パフォーマンス上の理由から、（100からの）追加のデータがアクティビティに多数含まれている場合は、このオプションの選択を解除することをお勧めします。 **[!UICONTROL Query]** このオプションをオフにすると、クエリーされたデータに応じて重複が取得される可能性があるので注意してください。

この節では、電子メールに追加のデータを含めて個人設定する方法に関する使用例 [を示し](../../automating/using/personalizing-email-with-additional-data.md)ます。

### 単純なフィールドの追加 {#adding-a-simple-field}

単純なフィールドを追加データとして追加すると、そのフィールドはアクティビティのアウトバウンドトランジションに直接表示されます。 これにより、例えば、クエリのデータが望ましいデータであるかを確認できます。

1. タブから、新しい要素を追加し **[!UICONTROL Additional data]** ます。
1. 開いたウィンドウのフィールドで、ターゲティングディメンションまたはリンクされたディメンションの1つで直接使用できるフィールドの1つを **[!UICONTROL Expression]** 選択します。 式を編集し、ディメンションフィールドから関数や単純な演算(集計を除く)を使用できます。

   単純なXPATHパスではない式を編集する **[!UICONTROL Alias]** と、が自動的に作成されます(例： &quot;Year(&lt;@birthDate>)&quot;). 必要に応じて、変更を加えることができます。 1つのフィールドのみを選択する場合(例： 「@age」)に置き換える必要があり **[!UICONTROL Alias]**&#x200B;ます。

1. 追加データ **[!UICONTROL Add]** へのフィールドの追加を確認する場合に選択します。 クエリを実行すると、追加されたフィールドに対応する追加の列が、アクティビティのアウトバウンドトランジションに表示されます。

![](assets/enrichment_add_simple_field.png)

### 集計の追加 {#adding-an-aggregate}

集計を使用すると、ターゲティングディメンションのフィールドまたはターゲティングディメンションにリンクされたディメンションのフィールドから値を計算できます。 次に例を示します。 プロファイルが購入した平均金額。
クエリとの集計を使用する場合、関数は0に戻り、NULLと見なされます。 クエリの **[!UICONTROL Output filtering]** タブを使用して、集計値をフィルターします。

* ゼロの値が必要な場合は、フィルタを適用 **[!UICONTROL is null]**&#x200B;します。
* を返し **[!UICONTROL is not null]**&#x200B;ます。

集計に並べ替えを適用する必要がある場合は、0の値を除外する必要があります。そうしないと、NULL値が最大値として表示されます。

1. タブから、新しい要素を追加し **[!UICONTROL Additional data]** ます。
1. 開いたウィンドウで、集計の作成に使用するコレクションを **[!UICONTROL Expression]** フィールドで選択します。

   が自動的 **[!UICONTROL Alias]** に作成されます。 必要に応じて、クエリの **[!UICONTROL Additional data]** タブに戻って変更できます。

   集計定義ウィンドウが開きます。

1. タブから集計を定義し **[!UICONTROL Data]** ます。 選択した集計の種類に応じて、データと互換性のある要素のみが **[!UICONTROL Expression]** フィールドで使用できます。 例えば、合計は数値データでのみ計算できます。

   ![](assets/enrichment_add_aggregate.png)

   選択したコレクションのフィールドに複数の集計を追加できます。 アクティビティの送信データの詳細の異なる列を区別するために、明示的なラベルを定義してください。

   また、各集計に対して自動的に定義されるエイリアスを変更することもできます。

   ![](assets/enrichment_add_aggregate2.png)

1. 必要に応じて、フィルターを追加し、考慮するデータを制限できます。

   Refer to the [Filtering added data](#filtering-added-data) section.

1. 集計 **[!UICONTROL Confirm]** を追加する場合に選択します。

>[!NOTE]
>
>集計を含む式は、ウィンドウの **[!UICONTROL Expression]** フィールドから直接作成できません **[!UICONTROL New additional data]** 。

### コレクションの追加 {#adding-a-collection}

1. タブから、新しい要素を追加し **[!UICONTROL Additional data]** ます。
1. 開いたウィンドウで、フィールドに追加するコレクションを選択し **[!UICONTROL Expression]** ます。 が自動的 **[!UICONTROL Alias]** に作成されます。 必要に応じて、クエリの **[!UICONTROL Additional data]** タブに戻って変更できます。
1. 選択 **[!UICONTROL Add]**. 新しいウィンドウが開き、表示するコレクションデータを絞り込むことができます。
1. タブで **[!UICONTROL Parameters]** 、追加するコレクションの行数を選択 **[!UICONTROL Collection]** して定義します。 例えば、各プロファイルが最近行った3回の購入を取得する場合は、フィールドに「3」と入力し **[!UICONTROL Number of lines to return]** ます。

   >[!NOTE]
   >
   >1以上の数値を入力する必要があります。

1. タブで、各行に表示するコレクションのフィールドを定義し **[!UICONTROL Data]** ます。

   ![](assets/enrichment_add_collection.png)

1. 必要に応じて、フィルタを追加して、使用する収集行を制限できます。

   Refer to the [Filtering added data](#filtering-added-data) section.

1. 必要に応じて、データの並べ替えを定義できます。

   例えば、 **[!UICONTROL Parameters]** タブに返す行を3行選択し、最近の購入を3回特定する場合、トランザクションに対応するコレクションの「日付」フィールドで降順の並べ替えを定義できます。

1. Refer to the [Sorting additional data](#sorting-additional-data) section.
1. コレクション **[!UICONTROL Confirm]** を追加する場合に選択します。

### 追加したデータのフィルタリング {#filtering-added-data}

集計またはコレクションを追加する場合は、追加のフィルターを指定して、表示するデータを制限できます。

例えば、50ドル以上の金額を持つ取引の収集行のみを処理する場合は、 **[!UICONTROL Filter]** タブから取引金額に対応するフィールドに条件を追加できます。

![](assets/enrichment_filter_data.png)

### 追加データの並べ替え {#sorting-additional-data}

集計またはコレクションをクエリのデータに追加する場合、フィールドの値や定義した式に基づいて、昇順と降順のどちらで並べ替えを適用するかを指定できます。

例えば、プロファイルが最近実行したトランザクションのみを保存する場合は、タブの **[!UICONTROL Number of lines to return]** フィールドに「1」を入力し、タブを介してトランザクション日に対応するフィールドに降順の並べ替えを適用し **[!UICONTROL Parameters]****[!UICONTROL Sort]** ます。

![](assets/enrichment_sort_data.png)

### 追加のデータに従ってターゲットデータをフィルターする {#filtering-the-targeted-data-according-to-additional-data}

データを追加すると、に新しい **[!UICONTROL Output filtering]** タブが表示され **[!UICONTROL Query]**&#x200B;ます。 このタブでは、追加されたデータを考慮して、最初にターゲット設定されたデータに追加のフィルターを適用でき **[!UICONTROL Target]** ます。

例えば、少なくとも1つの取引を行ったすべてのプロファイルをターゲットにし、各プロファイルに対して行われた平均取引金額を計算する集計をに追加した場合、この平均を使用して最初に計算した母集団を絞り込むことができ **[!UICONTROL Additional data]**&#x200B;ます。

これを行うには、 **[!UICONTROL Output filtering]** タブで、この追加データに条件を追加します。

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
