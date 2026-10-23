---
title: 外部信号とデータ読み込み
description: 次の例は、データの読み込みに使用される外部信号アクティビティを示しています。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e2997cf5-861b-4202-aeb7-3a47c4d55bef
TQID: 'https://experienceleague.adobe.com/fQTQgLluJa5WPu4ju1gGs84gWfqQ-sWIWuJSTXgQYHA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%
---
# 外部信号とデータ読み込み {#external-signal-data-import}

以下に、「**[!UICONTROL External signal]**」アクティビティの一般的なユースケースを示します。 ソースワークフローでデータインポートが実行されます。 インポートが完了し、データベースが更新されると、2 番目のワークフローがトリガーされます。 この 2 番目のワークフローでは、インポートされたデータを対象として集計を更新します。

ソースワークフローは次のとおりです。

* 「[ファイル読み込み](../../automating/using/load-file.md)」アクティビティで、新規の購入データを含んだファイルをアップロードします。 なお、デフォルトではデータマートに購入データが存在しないので、適宜[データベースが拡張](../../developing/using/data-model-concepts.md)されています。

  例：

  ```
  tcode;tdate;customer;product;tamount
  aze123;21/05/2015;dannymars@example.com;A2;799
  aze124;28/05/2015;dannymars@example.com;A7;8
  aze125;31/07/2015;john.smith@example.com;A7;8
  aze126;14/12/2015;john.smith@example.com;A10;4
  aze127;02/01/2016;dannymars@example.com;A3;79
  aze128;04/03/2016;clara.smith@example.com;A8;149
  ```

* 「[紐付け](../../automating/using/reconciliation.md)」アクティビティで、インポートしたデータとデータベースの間にリンクが作成されます。その結果、トランザクションデータがプロファイルおよび製品に正しく接続されるようになります。
* 「[データ更新](../../automating/using/update-data.md)」アクティビティによって、データベースのトランザクションリソースが挿入され、受信データで更新されます。
* [終了](../../automating/using/start-and-end.md) アクティビティは、集計の更新に使用する宛先ワークフローをトリガーします。

![](assets/signal_example_source1.png)

宛先ワークフローは次のとおりです。

* ソース ワークフローが正常に完了するまで、[外部信号](../../automating/using/external-signal.md) アクティビティが待機します。
* 「[クエリ](../../automating/using/query.md#enriching-data)」アクティビティで、プロファイルをターゲットとし、コレクションセットでエンリッチメントを実行して最終購入日を取得します。
* 「[データ更新](../../automating/using/update-data.md)」アクティビティで、専用のカスタムフィールドに追加データを保存します。 なお、プロファイルリソースは、「**最終購入日**」フィールドを追加するために拡張されています。

![](assets/signal_example_source2.png)
