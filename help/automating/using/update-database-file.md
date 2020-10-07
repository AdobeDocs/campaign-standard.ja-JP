---
title: 外部データを使用したデータベースの更新
description: この使用例では、ファイルからリカバリしたデータを使用して、Adobe Campaignデータベースにプロファイルを追加または更新する方法を示します。
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 33%

---


# 外部データを使用したデータベースの更新 {#update-database-file}

The following example shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. このワークフローの目的は、ファイルから回復したデータを使用して、Adobe Campaign データベースにプロファイルを追加または更新することです。

この例では、使用する紐付けキーは **電子メールアドレスです**。 「 [Load file](../../automating/using/load-file.md) 」アクティビティに読み込まれるファイルは、 **.txt** 形式のファイルで、次のデータ例が含まれています。

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

The [Update data](../../automating/using/update-data.md) activity is configured as follows:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
