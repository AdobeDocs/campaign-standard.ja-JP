---
title: 紐付けを使用したデータの更新
description: 次の例は、新しいクライアントを含むインポート済みのファイルから直接プロファイルのオーディエンスを作成するワークフローを示しています。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
TQID: https://experienceleague.adobe.com/cEXfESw1LZcrQVlLsgrlDB8J2aGz4zCoSUrIAshECo0
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 128
ht-degree: 49%

---

# 紐付けを使用したデータの更新 {#data-update-reconciliation}

次の例は、新しいクライアントを含むインポート済みのファイルから直接プロファイルのオーディエンスを作成するワークフローを示しています。 このワークフローは、次のアクティビティで構成されています。

![](assets/identification_example2.png)

* 読み込むファイルのデータを読み込んで検出する[&#x200B; ファイルを読み込む](../../automating/using/load-file.md) アクティビティ。 インポートされたファイルには、次のデータが含まれています。

  ```
  lastname;firstname;email;dateofbirth
  jackman;megan;megan.jackman@testmail.com;07/08/1975
  phillips;edward;phillips@testmail.com;09/03/1986
  weaver;justin;justin_w@testmail.com;11/15/1990
  martin;babeth;babeth_martin@testmail.net;11/25/1964
  reese;richard;rreese@testmail.com;02/08/1987
  cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
  xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
  grimes;daryl;daryl_890@testmail.com;12/06/1979
  tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
  ```

* 読み込まれたファイルの各列をプロファイルディメンション列にリンクする[紐付け](../../automating/using/reconciliation.md) アクティビティ。 特定できないファイルレコード（データが欠落している、互換性のないデータタイプなど） 最終的なオーディエンスデータの整合性を保つために無視されます。

  ![](assets/identification_example1.png)

* プロファイルのオーディエンスを保存する[&#x200B; オーディエンスを保存](../../automating/using/save-audience.md) アクティビティ。

  ![](assets/identification_example3.png)
