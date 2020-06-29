---
title: ファイルオーディエンスとデータベースとの調整
description: この例では、オーディエンスの読み取りアクティビティを使用して、ファイルのインポートから直接作成されたオーディエンスを調整する方法を示します。
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# ファイルオーディエンスとデータベースとの調整 {#example--reconcile-a-file-audience-with-the-database}

この例では、 **[!UICONTROL Read audience]** アクティビティを使用して、ファイルインポートから直接作成されたオーディエンスを調整する方法を示します。

ファイルの読み込みを実行する場合、その内容をオーディエンスに直接保存できます。 このオーディエンスはFileオーディエンスで、そのデータはデータベースリソースにリンクされていません。

読み込みワークフローは、次のように設計されています。

![](assets/readaudience_activity_example3.png)

* ファイルの [読み込み](../../automating/using/load-file.md) アクティビティは、外部ツールから抽出されたプロファイルデータを含むファイルをアップロードします。

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

* オーディエンス [の保存](../../automating/using/save-audience.md) アクティビティは、入力データをオーディエンスとして保存します。 データはまだ調整されていないので、オーディエンスはファイルオーディエンスで、そのデータはまだプロファイルデータとして認識されていません。

調整ワークフローは、次のように設計されています。

![](assets/readaudience_activity_example2.png)

* 読み込みオーディエンス [](../../automating/using/read-audience.md) アクティビティは、読み込みワークフローで作成されたファイルオーディエンスをアップロードします。 オーディエンスデータは、Adobe Campaignデータベースとまだ一致していません。
* 「 [調整](../../automating/using/reconciliation.md) 」アクティビティは、受信データをプロファイルとしてタ **[!UICONTROL Identification]** ブから識別します。 例えば、 **email** フィールドを調整条件として使用します。
* Update data [](../../automating/using/update-data.md) アクティビティは、受信データを使用して、データベースのプロファイルリソースを挿入し、更新する。 データが既にプロファイルとして識別されているので、 **[!UICONTROL Directly using the targeting dimension]** アクティビティを選択し、オプションの「 **[!UICONTROL Profiles]****[!UICONTROL Identification]** 」タブでを選択できます。 次に、「基準」タブで更新する必要のあるフィールドのリストを追加するだけです。
