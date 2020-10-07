---
title: ファイルに含まれるデータによるプロファイルデータのエンリッチメント
description: この例では、ファイルに含まれている購入データを使用してプロファイルデータのエンリッチメントをおこなう方法を示します。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 78%

---


# ファイルに含まれるデータによるプロファイルデータのエンリッチメント {#enriching-profile-data-with-data-contained-in-a-file}

この例では、プロファイルデータをファイルに含まれる購入データと共に拡張する方法を示します。ここでは、購入データがサードパーティのシステムに保存されることを考慮します。 各プロファイルでは、複数の購入をファイルに保存できます。ワークフローの最終目標は、少なくとも 2 つの商品を購入したターゲットプロファイルに E メールを送信して愛顧に感謝することです。

ワークフローは次のように設定します。

![](assets/enrichment_example_workflow.png)

* A [Query](../../automating/using/query.md) activity that targets the profiles who will receive the message.
* A [Load file](../../automating/using/load-file.md) activity that loads the purchase data. 次に例を示します。

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   このサンプルファイルでは、E メールアドレスを使用して、データとデータベースプロファイルを紐付けます。また、[こちらのドキュメント](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)で説明するように、一意の ID を有効にすることもできます。

* An [Enrichment](../../automating/using/enrichment.md) activity that creates a link between the transaction data loaded from the file and the profiles selected in the **[!UICONTROL Query]**. リンクは、アクティビティの「**[!UICONTROL Advanced relations]**」タブで定義します。リンクは、「**[!UICONTROL Load file]**」アクティビティからのトランジションに基づいています。プロファイルリソースの「email」フィールドとインポートされたファイルの「customer」列を紐付け条件として使用します。

   ![](assets/enrichment_example_workflow2.png)

   リンクが作成されると、次の 2 つの&#x200B;**[!UICONTROL Additional data]**&#x200B;セットが追加されます。

   * 各プロファイルの 2 つの最終トランザクションに対応する 2 行のコレクション。このコレクションの場合は、製品名、トランザクション日、製品の価格が追加データとして追加されます。データに降順ソートが適用されます。コレクションを作成するには、「**[!UICONTROL Additional data]**」タブで次の操作を実行します。

      アクティビティの「**[!UICONTROL Advanced relations]**」タブで既に定義されているリンクを選択します。

      ![](assets/enrichment_example_workflow3.png)

      「**[!UICONTROL Collection]**」を選択して、取得する行数を指定します（この例では 2）。この画面で、コレクションの「**[!UICONTROL Alias]**」と「**[!UICONTROL Label]**」をカスタマイズできます。ワークフローの後続のアクティビティでこのコレクションを参照する際に、これらの値が表示されます。

      ![](assets/enrichment_example_workflow4.png)

      コレクション用に保持する「**[!UICONTROL Data]**」として、最終配信で使用する列を選択します。

      ![](assets/enrichment_example_workflow6.png)

      トランザクション日に降順ソートを適用して、最新のトランザクションを確実に取得します。

      ![](assets/enrichment_example_workflow7.png)

   * 各プロファイルのトランザクションの合計数をカウントする集計。この集計は、後で、少なくとも 2 つのトランザクションが記録されたプロファイルをフィルターするために使用されます。集計を作成するには、「**[!UICONTROL Additional data]**」タブで次の操作を実行します。

      アクティビティの「**[!UICONTROL Advanced relations]**」タブで既に定義されているリンクを選択します。

      ![](assets/enrichment_example_workflow3.png)

      「**[!UICONTROL Aggregate]**」を選択します。

      ![](assets/enrichment_example_workflow8.png)

      保持する「**[!UICONTROL Data]**」として、「**Count All**」集計を定義します。必要に応じて、後続のアクティビティですばやく見つけられるように、カスタムエイリアスを指定します。

      ![](assets/enrichment_example_workflow9.png)

* A [Segmentation](../../automating/using/segmentation.md) activity with only one segment, that retrieves profiles of the initial target that have at least two transactions recorded. 1 つのトランザクションのみのプロファイルは除外されます。そのために、セグメント化のクエリは、既に定義されている集計に対して実行されます。

   ![](assets/enrichment_example_workflow5.png)

* An [Email delivery](../../automating/using/email-delivery.md) activity that uses the additional data defined in the **[!UICONTROL Enrichment]** to dynamically retrieve the two last purchases made by the profile. 追加データは、パーソナライゼーションフィールドを追加する際に「**Additional data (TargetData)**」ノードに表示されます。

   ![](assets/enrichment_example_workflow10.png)

**関連トピック：**

* [外部データを使用した顧客プロファイルのエンリッチメント](https://helpx.adobe.com/jp/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
