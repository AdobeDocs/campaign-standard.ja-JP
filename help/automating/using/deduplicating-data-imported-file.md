---
title: インポートされたファイルからのデータの重複排除
description: この例は、データをデータベースに読み込む前に、インポートしたファイルからデータの重複を除外する方法を示します。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 631eb661-a696-4352-aa58-9097b391723e
TQID: https://experienceleague.adobe.com/7zC8CU4kl3WkPT6l2QM-dN3fFsKTrS2lEpGQUaV2GI8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 329
ht-degree: 89%

---

# インポートされたファイルからのデータの重複排除 {#deduplicating-the-data-from-an-imported-file}

この例は、データをデータベースに読み込む前に、インポートしたファイルからデータの重複を除外する方法を示します。 このプロセスにより、データベースに読み込まれたデータの品質が向上します。

このワークフローは次の要素で構成されます。

![](assets/deduplication_example2_workflow.png)

* プロファイルのリストを含むファイルは、[&#x200B; ファイルを読み込み](../../automating/using/load-file.md) アクティビティを使用して読み込まれます。 この例では、インポートされるファイルは .csv 形式で、10 個のプロファイルを含んでいます。

  ```
  lastname;firstname;dateofbirth;email
  Smith;Hayden;23/05/1989;hayden.smith@example.com
  Mars;Daniel;17/11/1987;dannymars@example.com
  Smith;Clara;08/02/1989;hayden.smith@example.com
  Durance;Allison;15/12/1978;allison.durance@example.com
  Lucassen;Jody;28/03/1988;jody.lucassen@example.com
  Binder;Tom;19/01/1982;tombinder@example.com
  Binder;Tommy;19/01/1915;tombinder@example.com
  Connor;Jade;10/10/1979;connor.jade@example.com
  Mack;Clarke;02/03/1985;clarke.mack@example.com
  Ross;Timothy;04/07/1986;timross@example.com
  ```

  このファイルは、列の形式を検出および定義するためのサンプルファイルとしても使用できます。 「**[!UICONTROL Column definition]**」タブで、インポートしたファイルの各列が正しく設定されていることを確認します。

  ![](assets/deduplication_example2_fileloading.png)

* [重複排除](../../automating/using/deduplication.md) アクティビティ。 ファイルをインポートした後、データベースにデータを挿入する前に重複排除が直接実行されます。 したがって、「**[!UICONTROL Load file]**」アクティビティの「**[!UICONTROL Temporary resource]**」に基づいている必要があります。

  この例では、ファイルに含まれている一意のメールアドレスごとに 1 つのエントリを保持します。 そのため、重複の識別は一時リソースの **email** 列に対しておこなわれます。 ただし、2 つのメールアドレスがファイルに 2 回出現します。 したがって、2 行が重複と見なされます。

  ![](assets/deduplication_example2_dedup.png)

* [&#x200B; データを更新](../../automating/using/update-data.md) アクティビティを使用すると、重複排除プロセスから保持されているデータをデータベースに挿入できます。 インポートされたデータがプロファイルディメンションに属していると識別されるのは、データの更新時のみです。

  ここでは、「**[!UICONTROL Insert only]**」を指定して、データベースにまだ存在しないプロファイルだけを挿入します。 それには、ファイルの email 列と&#x200B;**プロファイル**&#x200B;ディメンションのメールフィールドを紐付けキーとして使用します。

  ![](assets/deduplication_example2_writer1.png)

  データの挿入元となるファイル列と「**[!UICONTROL Fields to update]**」タブのデータベースフィールドとのマッピングを指定します。

  ![](assets/deduplication_example2_writer2.png)

そのあと、ワークフローを開始します。 重複排除プロセスで保存されたレコードがデータベース内のプロファイルに追加されます。
