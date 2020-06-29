---
title: オーディエンスの閲覧
description: オーディエンスを読み取りアクティビティを使用すると、追加のフィルター条件を適用して既存のオーディエンスを取得し、それを絞り込むことができます。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# オーディエンスの閲覧{#read-audience}

## 説明 {#description}

![](assets/prefill.png)

この **[!UICONTROL Read audience]** アクティビティを使用すると、既存のオーディエンスを取得し、追加のフィルター条件を適用して絞り込むことができます。

## 使用状況 {#context-of-use}

この **[!UICONTROL Read audience]****[!UICONTROL Query]** アクティビティは、既存のアクティビティを選択するだけで済むように設計された、オーディエンスをよりシンプルにしたものです。

**関連トピック**

* [使用例： 2つの洗練されたオーディエンスの和集合](../../automating/using/union-on-two-refined-audiences.md)
* [使用例： ファイルオーディエンスとデータベースとの調整](../../automating/using/reconcile-file-audience-with-database.md)

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Read audience]** アクティビティをドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. タブから取得するオーディエンスを選択し **[!UICONTROL Properties]** ます。

   次のタイプのオーディエンスを取得できます。 **[!UICONTROL List]**、 **[!UICONTROL Query]**、 **[!UICONTROL File]** および **[!UICONTROL Experience Cloud]**。 オーディエンスタイプの詳細については、 [オーディエンスのドキュメントを参照してください](../../audiences/using/about-audiences.md) 。

   この **[!UICONTROL Use a dynamic audience]** オプションを使用すると、ワークフローのイベント変数に基づいて、ターゲットに対するオーディエンスの名前を定義できます。 詳しくは、「イベント変数を使用したアクティビティの [カスタマイズ](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) 」を参照してください。

   ![](assets/readaudience_activity1.png)

1. 選択したオーディエンスに追加のフィルターを適用する場合は、アクティビティの **[!UICONTROL Source filtering]** タブで条件を追加します。

   フィルタリング条件の作成について詳しくは、『 [クエリの作成](../../automating/using/editing-queries.md#creating-queries) 』のドキュメントを参照してください。

1. アクティビティの設定を確認し、ワークフローを保存します。
