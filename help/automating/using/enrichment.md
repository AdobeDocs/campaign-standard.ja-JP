---
title: エンリッチメント
description: 「エンリッチメント」アクティビティは、ワークフローで処理する追加のデータを定義できる高度なアクティビティです。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 96%

---


# エンリッチメント{#enrichment}

## 説明{#description}

![](assets/enrichment.png)

「**[!UICONTROL Enrichment]**」アクティビティは、ワークフローで処理する追加のデータを定義できる高度なアクティビティです。

## 使用状況 {#context-of-use}

「**[!UICONTROL Enrichment]**」アクティビティは、通常、ターゲティングアクティビティの後またはファイルをインポートした後、およびターゲットデータを使用できるアクティビティの前に使用されます。

このアクティビティには、「**[!UICONTROL Query]**」アクティビティよりも高度なエンリッチメント機能が含まれています。単純なエンリッチメントの場合は、[「クエリ」アクティビティ](../../automating/using/query.md#enriching-data)で直接実行できます。

「**[!UICONTROL Enrichment]**」アクティビティでは、インバウンドトランジションを利用し、追加のデータで出力トランジションを補完するようにアクティビティを設定できます。複数のセットからのデータを組み合わせたり、一時的なリソースへのリンクを作成したりできます。

**関連トピック**

* [使用例：プロファイルデータをファイルに含まれるデータで富化します](../../automating/using/enriching-profile-data-file.md)。
* [使用例：強化されたフィールドを含む電子メールの送信](../../automating/using/sending-email-enriched-fields.md)

## 設定 {#configuration}

「**[!UICONTROL Enrichment]**」アクティビティを設定するには：

1. ワークフローに「**[!UICONTROL Enrichment]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アクティビティに複数のインバウンドトランジションがある場合は、「**[!UICONTROL Primary set]**」を選択します。このアクティビティで設定された追加データは、アウトバウンドトランジションのこのプライマリセットに追加されます。

   プライマリセットに既に追加のデータが含まれている場合は、保持するか、削除するかを選択できます。この「**[!UICONTROL Keep all additional data from the main set]**」オプションのチェックを外すと、**[!UICONTROL Enrichment]**&#x200B;で設定された追加データのみがアウトバウンドトランジションに保持されます。

1. 複数のインバウンドトランジションがある場合は、アクティビティの「**[!UICONTROL Advanced Relations]**」タブで、プライマリセットと他のインバウンドデータとの関係を定義します。この「**[!UICONTROL Add element]**」ボタンを使用すると、複数の関係を追加できます。

   新しい関係を定義する場合、プライマリセットにリンクするインバウンドデータのセットを選択します。次に、関係のタイプを定義します。インバウンドデータとデータモデルに応じて、いくつかのタイプの関係を使用できます。

   * **[!UICONTROL 1 cardinality simple link]**：受信データの各レコードは、プライマリセット内の 1 つのレコードにのみ関連付けられています。プライマリセット内の各レコードには、リンクされたデータ内の 1 つのレコードが関連付けられています。
   * **[!UICONTROL N cardinality collection link]**：リンクされたデータの 0、1、または複数（N）個のレコードを、プライマリセットの 1 つのレコードに関連付けることができます。
   * **[!UICONTROL 0 or 1 cardinality simple link]**：プライマリセットのレコードは、リンクされたデータの 0 または 1 個のレコードに関連付けることができますが、複数のレコードに関連付けることはできません。

   「**[!UICONTROL Cardinality]**」を定義したら、「**[!UICONTROL Reconciliation criteria]**」を定義します。紐付け条件の「**[!UICONTROL Source expression]**」は、ターゲットリソースのフィールド、[式](../../automating/using/advanced-expression-editing.md)、引用符で囲んで直接指定した値のいずれかにすることができます。

   後でワークフローで識別しやすい「**[!UICONTROL Label]**」と「**[!UICONTROL ID]**」を定義します。

   >[!NOTE]
   >
   >プライマリセットと、「**[!UICONTROL Enrichment]**」アクティビティに接続されている他のインバウンドトランジションとの関係のみを定義できます。データベースリソースとの関係の定義を目的とした、よりシンプルなケースでは、「[紐付け](../../automating/using/reconciliation.md)」アクティビティを使用します。

1. アクティビティの「**[!UICONTROL Additional data]**」タブで追加データを定義します。プライマリセットのターゲティングディメンションに関連する追加データ（単純フィールド、集計、コレクション）を定義するか、「**[!UICONTROL Enrichment]**」アクティビティの「**[!UICONTROL Advanced relations]**」タブで作成したリンクに基づいて追加データを定義できます。

   [データのエンリッチメント](../../automating/using/query.md#enriching-data)の節を参照してください。

1. アクティビティの設定を確認し、ワークフローを保存します。

これで、**[!UICONTROL Enrichment]**&#x200B;の後に接続されたアクティビティでデータが使用できるようになりました。例えば、E メールコンテンツのパーソナライゼーションフィールドエクスプローラーの「**[!UICONTROL Additional data (targetData)]**」リンクの下に表示されます。
