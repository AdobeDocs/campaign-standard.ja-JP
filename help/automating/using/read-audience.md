---
solution: Campaign Standard
product: campaign
title: オーディエンスの閲覧
description: 「オーディエンスの閲覧」アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用してそのオーディエンスを絞り込むことができます。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 87%

---


# オーディエンスの閲覧{#read-audience}

## 説明 {#description}

![](assets/prefill.png)

「**[!UICONTROL Read audience]**」アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用してそのオーディエンスを絞り込むことができます。

## 使用状況 {#context-of-use}

「**[!UICONTROL Read audience]**」アクティビティは「**[!UICONTROL Query]**」アクティビティを単純にしたもので、既存のオーディエンスの選択だけが必要な場合に使用します。

**関連トピック**

* [使用例：2つの洗練されたオーディエンスの和集合](../../automating/using/union-on-two-refined-audiences.md)
* [使用例：ファイルオーディエンスとデータベースとの調整](../../automating/using/reconcile-file-audience-with-database.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Read audience]**」アクティビティをドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 「**[!UICONTROL Properties]**」タブから取得するオーディエンスを選択します。

   取得できるオーディエンスのタイプは **[!UICONTROL List]**、**[!UICONTROL Query]**、**[!UICONTROL File]**、**[!UICONTROL Experience Cloud]** です。オーディエンスのタイプの詳細については、[オーディエンス](../../audiences/using/about-audiences.md)のドキュメントを参照してください。

   「**[!UICONTROL Use a dynamic audience]**」オプションを使用すると、ワークフローのイベント変数に基づいて、ターゲットにするオーディエンスの名前を定義できます。詳しくは、[このページ](../../automating/using/customizing-workflow-external-parameters.md)の節を参照してください。

   ![](assets/readaudience_activity1.png)

1. 選択したオーディエンスに追加のフィルターを適用する場合は、アクティビティの「**[!UICONTROL Source filtering]**」タブで条件を追加します。

   フィルター条件の作成について詳しくは、[クエリの作成](../../automating/using/editing-queries.md#creating-queries)のドキュメントを参照してください。

1. アクティビティの設定を確認し、ワークフローを保存します。
