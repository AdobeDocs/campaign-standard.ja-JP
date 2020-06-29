---
title: 読み込んだファイルからのデータの重複を除外する
description: この例では、データをデータベースにロードする前にインポートしたファイルからデータの重複除外を行う方法を示します。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# 読み込んだファイルからのデータの重複を除外する {#deduplicating-the-data-from-an-imported-file}

この例では、データをデータベースにロードする前にインポートしたファイルからデータの重複除外を行う方法を示します。 この手順により、データベースに読み込まれるデータの品質が向上します。

ワークフローは次の要素で構成されます。

![](assets/deduplication_example2_workflow.png)

* プロファイルのリストを含むファイルは、 [Load file](../../automating/using/load-file.md) アクティビティを使用して読み込みます。 この例では、インポートされるファイルは.csv形式で、10プロファイルが含まれています。

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

   このファイルは、列の形式を検出および定義するためのサンプルファイルとしても使用できます。 タブから、読み込んだファイルの各列が正しく設定されていることを確認し **[!UICONTROL Column definition]** ます。

   ![](assets/deduplication_example2_fileloading.png)

* [重複排除 - 重複](../../automating/using/deduplication.md) アクティビティ。 重複排除 - 重複は、ファイルのインポート後、およびデータベースにデータを挿入する前に、直接実行されます。 したがって、この値は **[!UICONTROL Temporary resource]****[!UICONTROL Load file]** アクティビティの値に基づく必要があります。

   この例では、ファイルに含まれる一意の電子メールアドレスごとに1つのエントリを保持します。 したがって、重複識別は、一時リソースの **email** 列で行われます。 ただし、2つの電子メールアドレスがファイル内に2回出現します。 したがって、2行が重複と見なされます。

   ![](assets/deduplication_example2_dedup.png)

* 「 [Update data](../../automating/using/update-data.md) 」アクティビティを使用すると、重複排除 - 重複プロセスから保持されたデータをデータベースに挿入できます。 インポートされたデータがプロファイルディメンションに属していると識別されるのは、データが更新された場合のみです。

   ここでは、データベースにまだ存在し **[!UICONTROL Insert only]** ないプロファイルを使用します。 これを行うには、ファイルの電子メール列と **プロファイル** ディメンションの電子メールフィールドを紐付けキーとして使用します。

   ![](assets/deduplication_example2_writer1.png)

   データの挿入元となるファイルの列と、 **[!UICONTROL Fields to update]** タブのデータベースフィールドとの間のマッピングを指定します。

   ![](assets/deduplication_example2_writer2.png)

次に、ワークフローを開始します。 次に、重複排除 - 重複プロセスから保存されたレコードがデータベース内のプロファイルに追加されます。
