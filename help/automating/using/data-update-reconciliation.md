---
title: 調整を使用したデータ更新
description: 次の例は、新しいクライアントを含む読み込みファイルから直接プロファイルのオーディエンスを作成するワークフローを示しています。
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# 調整を使用したデータ更新 {#data-update-reconciliation}

次の例は、新しいクライアントを含む読み込みファイルから直接プロファイルのオーディエンスを作成するワークフローを示しています。 これは次のアクティビティで構成されています。

![](assets/identification_example2.png)

* 読み込むファイルの [読み込み](../../automating/using/load-file.md) アクティビティ。読み込むファイルのデータを読み込んで検出します。 読み込まれたファイルには次のデータが含まれています。

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

* ロードされたファイルの各列をプロファイル次元列にリンクする [調整](../../automating/using/reconciliation.md) アクティビティ。 識別できないファイルレコード（データが見つからない、互換性のないデータタイプなど） は無視され、最終的なオーディエンスデータの整合性が維持されます。

   ![](assets/identification_example1.png)

* プロファイルの [オーディエンスを保存する「オーディエンス](../../automating/using/save-audience.md) 」アクティビティ。

   ![](assets/identification_example3.png)
