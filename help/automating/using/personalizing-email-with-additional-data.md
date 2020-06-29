---
title: 電子メールと追加データのパーソナライズ
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# 電子メールと追加データのパーソナライズ {#example--personalizing-an-email-with-additional-data}

次の例は、様々なタイプの追加データをクエリに追加し、電子メールのパーソナライゼーションフィールドとして使用する方法を示しています。 アクティビティがターゲットとするデータを拡張する方法について詳しくは、 **[!UICONTROL Query]** この節を参照し [てください](../../automating/using/query.md#enriching-data)。

この例では、 [カスタムリソース](../../developing/using/data-model-concepts.md) が使用されます。

* 各 **プロファイルの忠誠度ポイントを保存できるフィールドを追加するために、** プロファイルリソースが拡張されました。
* トランザクション **リソースが作成され** 、データベース内のプロファイルが実行したすべての購入を識別します。 購入した日付、価格、製品は、トランザクションごとに保存されます。
* 製 **品** リソースが作成され、購入可能な製品が参照されました。

目的は、1つ以上のトランザクションが保存されたプロファイルに電子メールを送信することです。 この電子メールを通じて、顧客は、最後に行われたトランザクションに関するリマインダと、すべてのトランザクションの概要を受け取ります。 購入した製品の数、滞在合計、発生したロイヤルティポイントの合計数を確認するメッセージ。

ワークフローは次のとおりです。

![](assets/enrichment_example1.png)

1. 1つ追加以上のトランザクションを実行したプロファイルをターゲットできる、クエリアクティビティ。 [](../../automating/using/query.md)

   ![](assets/enrichment_example2.png)

   クエリの **[!UICONTROL Additional data]** タブで、最終電子メールに表示する様々なデータを定義します。

   * 忠誠度ポイントに対応する **プロファイル** ディメンションの単純フィールド。 「単純なフィールドの [追加](../../automating/using/query.md#adding-a-simple-field) 」の節を参照してください。
   * 取引収集に基づく2つの集計: 購入した製品の数と合計滞在金額。 「カウント」および「 **[!UICONTROL Data]** 合計 **」****** 集計を使用して、集計設定ウィンドウの「タブ」からこれらを追加できます。 「集計の [追加](../../automating/using/query.md#adding-an-aggregate) 」を参照してください。
   * 最後のトランザクションに費やされた金額、日付、および製品を返すコレクション。

      これを行うには、コレクション設定ウィンドウの **[!UICONTROL Data]** タブから表示する別のフィールドを追加する必要があります。

      最新のトランザクションのみを返すには、に「1」を入力し、 **[!UICONTROL Number of lines to return]** タブからコレクションの「 **日付****[!UICONTROL Sort]** 」フィールドに降順の並べ替えを適用する必要があります。

      「コレクションの [追加](../../automating/using/query.md#adding-a-collection) 」および「追加のデータ [](../../automating/using/query.md#sorting-additional-data) 」セクションを参照してください。
   ![](assets/enrichment_example4.png)

   データがアクティビティのアウトバウンドトランジションによって正しく転送されていることを確認する場合は、ワークフローを初めて開始し( **[!UICONTROL Email delivery]** アクティビティなし)、クエリのアウトバウンドトランジションを開きます。

   ![](assets/enrichment_example5.png)

1. 追加 [電子メール配信](../../automating/using/email-delivery.md) アクティビティ。 電子メールコンテンツに、クエリで計算されたデータに対応するパーソナライゼーションフィールドを挿入します。 パーソナライゼーションフィールドエクスプローラーの **[!UICONTROL Additional data (targetData)]** リンクから見つけることができます。

   ![](assets/enrichment_example3.png)

これで、ワークフローを実行する準備が整いました。 クエリをターゲットにしたプロファイルは、トランザクションから計算されたデータを含むパーソナライズされた電子メールを受信します。
