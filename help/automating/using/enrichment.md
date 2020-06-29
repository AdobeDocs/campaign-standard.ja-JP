---
title: エンリッチメント
description: エンリッチメントアクティビティは、ワークフローで処理する追加のデータを定義できる高度なアクティビティです。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 1%

---


# エンリッチメント{#enrichment}

## 説明 {#description}

![](assets/enrichment.png)

この **[!UICONTROL Enrichment]** アクティビティは、ワークフローで処理する追加のデータを定義できる高度なアクティビティです。

## 使用状況 {#context-of-use}

この **[!UICONTROL Enrichment]** アクティビティは、通常、ターゲット設定アクティビティに従って、またはファイルを読み込んだ後、またはターゲット設定されたデータを使用できるアクティビティの前に使用されます。

このアクティビティには、 **[!UICONTROL Query]** アクティビティよりも高度なエンリッチメント関数が含まれています。 単純なエンリッチメントの場合は、 [クエリアクティビティで直接実行できます](../../automating/using/query.md#enriching-data)。

この **[!UICONTROL Enrichment]** アクティビティでは、受信トランジションを利用し、追加のデータを出力トランジションに入力するようにアクティビティを設定できます。 複数のセットからのデータを組み合わせたり、一時的なリソースへのリンクを作成したりできます。

**関連トピック**

* [使用例： プロファイルデータをファイルに含まれるデータで富化します](../../automating/using/enriching-profile-data-file.md)。
* [使用例： 強化されたフィールドを含む電子メールの送信](../../automating/using/sending-email-enriched-fields.md)

## 設定 {#configuration}

**[!UICONTROL Enrichment]** アクティビティを設定するには：

1. ワークフローに **[!UICONTROL Enrichment]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アクティビティに複数の受信トランジションがある場合は、を選択し **[!UICONTROL Primary set]**&#x200B;ます。 このアクティビティで構成された追加のデータは、アウトバウンドトランジションのこのプライマリセットに追加されます。

   プライマリセットに既に追加のデータが含まれている場合は、保持するか、削除するかを選択できます。 このオプションのチェックを外すと、で設定された追加のデータのみがアウトバウンドトランジション **[!UICONTROL Keep all additional data from the main set]****[!UICONTROL Enrichment]** に保持されます。

1. 複数の受信トランジションがある場合は、アクティビティの **[!UICONTROL Advanced Relations]** タブで、プライマリセットと他の受信データの間の関係を定義します。 ボタンを使用して複数のリレーションを追加でき **[!UICONTROL Add element]** ます。

   新しい関係を定義する場合、主セットにリンクする受信データのセットを選択します。 次に、関係のタイプを定義します。 インバウンドデータとデータモデルに応じて、いくつかのタイプのリレーションを使用できます。

   * **[!UICONTROL 1 cardinality simple link]**: 受信データの各レコードは、プライマリセットから1つのレコードに関連付けられ、1つのレコードのみになります。 プライマリセットの各レコードには、リンクされたデータ内の1つのレコードが関連付けられています。
   * **[!UICONTROL N cardinality collection link]**: リンクされたデータの0、1、または複数の(N)レコードを、プライマリセットの1レコードに関連付けることができます。
   * **[!UICONTROL 0 or 1 cardinality simple link]**: プライマリセットのレコードは、リンクされたデータの0または1レコードに関連付けることができますが、複数のレコードに関連付けることはできません。
   を定義 **[!UICONTROL Cardinality]** したら、を定義し **[!UICONTROL Reconciliation criteria]**&#x200B;ます。 調整条件 **[!UICONTROL Source expression]** のフィールドは、ターゲットリソース、 [式](../../automating/using/advanced-expression-editing.md) 、または引用符で囲んで指定した値のフィールドにすることができます。

   ワークフローの後半で簡単 **[!UICONTROL Label]****[!UICONTROL ID]** に識別できるANDを定義します。

   >[!NOTE]
   >
   >プライマリセットと、 **[!UICONTROL Enrichment]** アクティビティに接続されている他のインバウンドトランジションとの間のリレーションのみを定義できます。 データベース・リソースとの関係の定義を目的とした、よりシンプルなケースの場合は、 [調整](../../automating/using/reconciliation.md) アクティビティを使用します。

1. アクティビティの **[!UICONTROL Additional data]** タブで追加データを定義します。 プライマリセットのターゲティングディメンションに関連する追加のデータ(単純なフィールド、集計およびコレクション)を定義するか、 **[!UICONTROL Advanced relations]****[!UICONTROL Enrichment]** アクティビティのタブで作成したリンクに基づいて定義できます。

   「 [データの富化](../../automating/using/query.md#enriching-data) 」の節を参照してください。

1. アクティビティの設定を確認し、ワークフローを保存します。

これで、データは、の後に接続されたアクティビティで使用できるようになり **[!UICONTROL Enrichment]**&#x200B;ます。 例えば、電子メールコンテンツのパーソナライゼーションフィールドエクスプローラーの **[!UICONTROL Additional data (targetData)]** リンクの下に表示されます。
