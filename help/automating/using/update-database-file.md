---
title: 外部データを使用したデータベースの更新
description: このユースケースでは、ファイルから復元したデータを使用して、Adobe Campaign データベースにプロファイルを追加または更新する方法を示します。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2df7fbed-b979-4706-bd56-83f712cc3070
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 11%

---

# 外部データを使用したデータベースの更新 {#update-database-file}

次の例は、**[!UICONTROL Load file]** アクティビティに続く **[!UICONTROL Update data]** アクティビティの設定を示しています。 このワークフローの目的は、ファイルから復元されたデータを使用して、Adobe Campaign データベースにプロファイルを追加または更新することです。

この例で使用される紐付けキーは **メールアドレス** です。 [ ファイルを読み込み ](../../automating/using/load-file.md) アクティビティで読み込まれるファイルは、次のサンプルデータを含んだ **.txt** 形式のファイルです。

```
lastname;firstname;email;birthdate
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

[ データを更新 ](../../automating/using/update-data.md) アクティビティは、次のように設定されます。

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
