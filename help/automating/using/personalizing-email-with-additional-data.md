---
title: 追加データによる E メールのパーソナライズ
description: この使用例では、様々なタイプの追加データをクエリに追加し、それを電子メールのパーソナライゼーションフィールドとして使用する方法を示します。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 86%

---


# 追加データによる E メールのパーソナライズ {#example--personalizing-an-email-with-additional-data}

次の例は、様々なタイプの追加データをクエリに追加し、E メールのパーソナライゼーションフィールドとして使用する方法を示しています。アクティビティがターゲットとするデータを拡張する方法について詳しくは、 **[!UICONTROL Query]** この節を参照し [てください](../../automating/using/query.md#enriching-data)。

この例では、[カスタムリソース](../../developing/using/data-model-concepts.md)を使用します。

* **プロファイル**&#x200B;リソースが拡張され、各プロファイルのロイヤルティポイントを保存できるフィールドを追加できます。
* **トランザクション**&#x200B;リソースが作成され、データベース内のプロファイルが実行したすべての購入を識別します。購入した日付、価格、商品は、トランザクションごとに保存されます。
* **商品**&#x200B;リソースが作成され、購入可能な商品を参照します。

この目的は、1 つ以上のトランザクションが保存されたプロファイルに E メールを送信することです。この E メールを通じて、クライアントは、最後に実行したトランザクションに関するリマインダーと、すべてのトランザクションの概要（購入した商品数、合計金額、発生したロイヤルティポイントの合計数を確認するメッセージ）を受け取ります。

ワークフローは次のとおりです。

![](assets/enrichment_example1.png)

1. Add a [Query](../../automating/using/query.md) activity, which allows you to target the profiles that have carried out at least one transaction.

   ![](assets/enrichment_example2.png)

1. クエリの「**[!UICONTROL Additional data]**」タブで、最後の E メールに表示する様々なデータを定義します。

   * ロイヤルティポイントに対応する&#x200B;**プロファイル**&#x200B;ディメンションのシンプルなフィールド。[シンプルなフィールドの追加](../../automating/using/query.md#adding-a-simple-field)の節を参照してください。
   * トランザクションコレクションに基づく 2 つの集計：購入した商品数と合計金額。これらは、**Count** 集計および **Sum** 集計を使用して、集計設定ウィンドウの「**[!UICONTROL Data]**」タブから追加できます。[集計の追加](../../automating/using/query.md#adding-an-aggregate)を参照してください。
   * 最後のトランザクションの合計金額、日付、および商品を返すコレクション。

      これをおこなうには、コレクション設定ウィンドウの「**[!UICONTROL Data]**」タブで、表示する別のフィールドを追加する必要があります。

      最近のトランザクションのみを返すには、「**[!UICONTROL Number of lines to return]**」に「1」と入力し、「**[!UICONTROL Sort]**」タブでコレクションの「**Date**」フィールドに降順の並べ替えを適用する必要があります。

      [コレクションの追加](../../automating/using/query.md#adding-a-collection)および[追加データの並べ替え](../../automating/using/query.md#sorting-additional-data)の節を参照してください。
   ![](assets/enrichment_example4.png)

1. データがアクティビティのアウトバウンドトランジションによって正しく転送されていることを確認するには、（「**[!UICONTROL Email delivery]**」アクティビティなしで）ワークフローを初めて開始するときに、クエリのアウトバウンドトランジションを開きます。

   ![](assets/enrichment_example5.png)

1. 追加 [電子メール配信](../../automating/using/email-delivery.md) アクティビティ。 E メールコンテンツに、クエリで計算されたデータに対応するパーソナライゼーションフィールドを挿入します。パーソナライゼーションフィールドエクスプローラーの **[!UICONTROL Additional data (targetData)]** リンクからアクセスできます。

   ![](assets/enrichment_example3.png)

これでワークフローを実行する準備が整いました。クエリでターゲットされたプロファイルは、トランザクションから計算されたデータを含むパーソナライズされた E メールを受信します。
