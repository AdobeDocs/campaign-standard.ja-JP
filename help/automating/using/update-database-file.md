---
solution: Campaign Standard
product: campaign
title: 外部データを使用したデータベースの更新
description: この使用例では、ファイルからリカバリしたデータを使用して、Adobe Campaignデータベースにプロファイルを追加または更新する方法を示します。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 33%

---


# 外部データを使用したデータベースの更新 {#update-database-file}

次の例は、**[!UICONTROL Load file]**&#x200B;アクティビティの後の&#x200B;**[!UICONTROL Update data]**&#x200B;アクティビティの設定を示しています。 このワークフローの目的は、ファイルから回復したデータを使用して、Adobe Campaign データベースにプロファイルを追加または更新することです。

この例で使用する紐付けキーは、**電子メールアドレス**&#x200B;です。 [ファイル](../../automating/using/load-file.md)の読み込みアクティビティに読み込まれたファイルは、次のデータ例を含む&#x200B;**.txt**&#x200B;形式のファイルです。

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

[Update data](../../automating/using/update-data.md)アクティビティは、次のように構成されます。

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
