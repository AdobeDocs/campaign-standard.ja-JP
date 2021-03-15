---
solution: Campaign Standard
product: campaign
title: ファイルオーディエンスとデータベースの紐付け
description: この例では、オーディエンスの読み取りアクティビティを使用して、ファイルのインポートから直接作成されたオーディエンスを調整する方法を示します。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: ワークフロー
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 86%

---


# ファイルオーディエンスとデータベースの紐付け {#example--reconcile-a-file-audience-with-the-database}

この例では、「**[!UICONTROL Read audience]**」アクティビティを使用して、ファイルインポートから直接作成されたオーディエンスを紐付ける方法を示します。

ファイルのインポートを実行する場合、その内容をオーディエンスに直接保存できます。このオーディエンスはファイルオーディエンスで、データはデータベースリソースにリンクされていません。

インポートワークフローは、次のように設計されています。

![](assets/readaudience_activity_example3.png)

* 「[ファイル読み込み](../../automating/using/load-file.md)」アクティビティは、外部ツールから抽出されたプロファイルデータが含まれるファイルをアップロードします。

   次に例を示します。

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* 「[オーディエンスの保存](../../automating/using/save-audience.md)」アクティビティは、読み込んだデータをオーディエンスとして保存します。データはまだ紐付けされていないので、オーディエンスはファイルオーディエンスで、そのデータはまだプロファイルデータとして認識されていません。

紐付けワークフローは、次のように設計されています。

![](assets/readaudience_activity_example2.png)

* [読み取りオーディエンス](../../automating/using/read-audience.md)アクティビティは、読み込みワークフローで作成されたファイルオーディエンスをアップロードします。 オーディエンスデータは、Adobe Campaign データベースとまだ紐付けされていません。
* 「[紐付け](../../automating/using/reconciliation.md)」アクティビティは、読み込んだデータをプロファイルとして「**[!UICONTROL Identification]**」タブから識別します。例えば、「**E メール**」フィールドを紐付け条件として使用します。
* 「[データ更新](../../automating/using/update-data.md)」アクティビティは、データベースのプロファイルリソースを挿入し、読み込んだデータを使用して更新します。データが既にプロファイルとして識別されているので、アクティビティの「**[!UICONTROL Identification]**」タブで「**[!UICONTROL Directly using the targeting dimension]**」オプションを選択し、「**[!UICONTROL Profiles]**」を選択できます。そして、当該タブで更新する必要のあるフィールドのリストを追加するだけです。
