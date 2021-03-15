---
solution: Campaign Standard
product: campaign
title: 紐付けを使用したデータの更新
description: 次の例は、新しいクライアントを含むインポート済みのファイルから直接プロファイルのオーディエンスを作成するワークフローを示しています。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: ワークフロー
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 67%

---


# 紐付けを使用したデータの更新 {#data-update-reconciliation}

次の例は、新しいクライアントを含むインポート済みのファイルから直接プロファイルのオーディエンスを作成するワークフローを示しています。このワークフローは、次のアクティビティで構成されています。

![](assets/identification_example2.png)

* [読み込むファイル](../../automating/using/load-file.md)アクティビティ。読み込むファイルのデータを読み込んで検出します。 インポートされたファイルには、次のデータが含まれています。

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

* [調整](../../automating/using/reconciliation.md)アクティビティ。ロードされたファイルの各列をプロファイル次元の列にリンクします。 識別できないファイルレコード（データが見つからない、互換性のないデータタイプなど）は無視され、最終的なオーディエンスデータの整合性が維持されます。

   ![](assets/identification_example1.png)

* [保存オーディエンス](../../automating/using/save-audience.md)アクティビティ。プロファイルのオーディエンスを保存します。

   ![](assets/identification_example3.png)
