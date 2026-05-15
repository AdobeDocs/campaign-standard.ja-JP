---
title: オーディエンスの閲覧
description: 「オーディエンスの閲覧」アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用してそのオーディエンスを絞り込むことができます。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 9a77a2c7-cc1c-416f-8103-bb7d5c84a373
TQID: https://experienceleague.adobe.com/mPVqmIC2ovLQdipvGbwI7GCZXejCTyCgwBYWFbCeTRg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 206
ht-degree: 86%

---

# オーディエンスを読み取り{#read-audience}

## 説明 {#description}

![](assets/prefill.png)

「**[!UICONTROL Read audience]**」アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用してそのオーディエンスを絞り込むことができます。

## Context of use {#context-of-use}

「**[!UICONTROL Read audience]**」アクティビティは「**[!UICONTROL Query]**」アクティビティを単純にしたもので、既存のオーディエンスの選択だけが必要な場合に使用します。

**関連トピック**

* [ユースケース：ふたつの洗練されたオーディエンスで統合](../../automating/using/union-on-two-refined-audiences.md)
* [ユースケース：ファイルオーディエンスとデータベースの紐付け](../../automating/using/reconcile-file-audience-with-database.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Read audience]**」アクティビティをドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 「**[!UICONTROL Properties]**」タブから取得するオーディエンスを選択します。

   取得できるオーディエンスのタイプは **[!UICONTROL List]**、**[!UICONTROL Query]**、**[!UICONTROL File]**、**[!UICONTROL Experience Cloud]** です。 オーディエンスのタイプの詳細については、[オーディエンス](../../audiences/using/about-audiences.md)のドキュメントを参照してください。

   「**[!UICONTROL Use a dynamic audience]**」オプションを使用すると、ワークフローのイベント変数に基づいて、ターゲットにするオーディエンスの名前を定義できます。 詳しくは、[このページ &#x200B;](../../automating/using/customizing-workflow-external-parameters.md)の節を参照してください。

   ![](assets/readaudience_activity1.png)

1. 選択したオーディエンスに追加のフィルターを適用する場合は、アクティビティの「**[!UICONTROL Source filtering]**」タブで条件を追加します。

   フィルター条件の作成について詳しくは、[クエリの作成](../../automating/using/editing-queries.md#creating-queries)のドキュメントを参照してください。

1. アクティビティの設定を確認し、ワークフローを保存します。
