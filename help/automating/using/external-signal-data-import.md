---
title: 外部の信号とデータのインポート
description: 次の例は、データのインポートで使用される外部シグナルアクティビティを示しています。
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# 外部の信号とデータのインポート {#external-signal-data-import}

次の例は、一般的な使用例の **[!UICONTROL External signal]** アクティビティを示しています。 データのインポートは、ソースワークフローで実行されます。 インポートが完了し、データベースが更新されると、2番目のワークフローがトリガされます。 この2つ目のワークフローは、読み込んだデータの集計を更新するために使用します。

ソースワークフローは次のとおりです。

* ファイルの [読み込み](../../automating/using/load-file.md) アクティビティは、新しい購入データを含むファイルをアップロードします。 購入データがデフォルトでデータマートに存在しないので [、](../../developing/using/data-model-concepts.md) データベースはデータマートに応じて拡張されています。

   次に例を示します。

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* 取引データがプロファイルと製品に正しく接続されるように、 [調整](../../automating/using/reconciliation.md) アクティビティは、インポートされたデータとデータベースの間にリンクを作成します。
* 「 [Update data](../../automating/using/update-data.md) 」アクティビティは、データベースのトランザクションリソースを入力データで挿入し、更新します。
* エンド [](../../automating/using/start-and-end.md) アクティビティは、集計の更新に使用される宛先ワークフローをトリガーします。

![](assets/signal_example_source1.png)

宛先ワークフローは次のとおりです。

* [外部シグナル](../../automating/using/external-signal.md) アクティビティは、ソースワークフローが正常に終了するのを待ちます。
* 「 [クエリ](../../automating/using/query.md#enriching-data) アクティビティ」ターゲットは、プロファイルをし、最終購入日を取得するためのコレクションセットを含めます。
* データの [更新](../../automating/using/update-data.md) アクティビティは、追加のデータを専用のカスタムフィールドに格納します。 プロファイルリソースが拡張され、 **最後の購入日** フィールドが追加されたことに注意してください。

![](assets/signal_example_source2.png)
