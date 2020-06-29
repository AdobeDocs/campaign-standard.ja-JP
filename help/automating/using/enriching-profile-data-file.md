---
title: ファイルに含まれるデータをプロファイルデータに含める
description: この例では、プロファイルデータをファイルに含まれる購入データに拡張する方法を示します。
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---


# ファイルに含まれるデータをプロファイルデータに含める {#enriching-profile-data-with-data-contained-in-a-file}

この例では、プロファイルデータをファイルに含まれる購入データと共に拡張する方法を示します。ここでは、購入データがサードパーティのシステムに保存されることを考慮します。 各プロファイルは、ファイルに複数の購入を保存できます。 ワークフローの最後の目的は、少なくとも2つの商品を購入したターゲットプロファイルに電子メールを送信し、ユーザーの忠誠度に感謝することです。

ワークフローは次のように設定します。

![](assets/enrichment_example_workflow.png)

* メッセージを受信するプロファイルをターゲットする [クエリ](../../automating/using/query.md) アクティビティ。
* 購入データを読み込む [Load file](../../automating/using/load-file.md) アクティビティ。 次に例を示します。

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   この例のファイルでは、電子メールアドレスを使用して、データとデータベースプロファイルを調整します。 また、 [このドキュメントで説明するように、一意のIDを有効にすることもで](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)きます。

* ファイルから読み込まれたトランザクションデータと、で選択されたエンリッチメントとの間にリンクを作成する [プロファイル](../../automating/using/enrichment.md) アクティビティ **[!UICONTROL Query]**。 リンクはアクティビティの **[!UICONTROL Advanced relations]** タブで定義します。 リンクは、 **[!UICONTROL Load file]** アクティビティからのトランジションに基づいています。 調整条件として、プロファイルリソースの「電子メール」フィールドと、インポートしたファイルの「顧客」列を使用します。

   ![](assets/enrichment_example_workflow2.png)

   リンクが作成されると、2セットのリンク **[!UICONTROL Additional data]** が追加されます。

   * 各プロファイルの最後の2つのトランザクションに対応する2行の集まり。 このコレクションの場合、製品名、取引日、および製品の価格が追加データとして追加されます。 データに降順の並べ替えが適用されます。 コレクションを作成するには、 **[!UICONTROL Additional data]** タブで次の操作を行います。

      アクティビティの **[!UICONTROL Advanced relations]** タブで既に定義されているリンクを選択します。

      ![](assets/enrichment_example_workflow3.png)

      取得 **[!UICONTROL Collection]** する行数をチェックして指定します（この例では2）。 この画面で、コレクションのおよ **[!UICONTROL Alias]** びをカスタマイズでき **[!UICONTROL Label]** ます。 これらの値は、このコレクションを参照する際に、ワークフローの次のアクティビティに表示されます。

      ![](assets/enrichment_example_workflow4.png)

      コレクション **[!UICONTROL Data]** を保持するには、最終配信で使用する列を選択します。

      ![](assets/enrichment_example_workflow6.png)

      取引日に降順の並べ替えを適用して、最新の取引を確実に取得します。

      ![](assets/enrichment_example_workflow7.png)

   * 各プロファイルのトランザクションの合計数をカウントする集計。 この集計は、後で、少なくとも2つのトランザクションが記録されたプロファイルをフィルターするために使用されます。 集計を作成するには、 **[!UICONTROL Additional data]** タブで次の操作を行います。

      アクティビティの **[!UICONTROL Advanced relations]** タブで既に定義されているリンクを選択します。

      ![](assets/enrichment_example_workflow3.png)

      選択 **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      保持 **[!UICONTROL Data]** するには、「すべてを **カウント** 」集計を定義します。 必要に応じて、次のアクティビティですばやく見つけられるように、カスタムエイリアスを指定します。

      ![](assets/enrichment_example_workflow9.png)

* 1つのセグメントのみを含む [セグメント化](../../automating/using/segmentation.md) アクティビティ。最低2つのトランザクションが記録されている最初のターゲットのプロファイルを取得します。 1つのトランザクションのみのプロファイルは除外されます。 そのために、セグメントのクエリは、前に定義した集計に対して行われます。

   ![](assets/enrichment_example_workflow5.png)

* プロファイルが最後に行った2回の購入を動的に取得するために、で定義された追加データ [を使用する電子メール配信](../../automating/using/email-delivery.md)**[!UICONTROL Enrichment]** アクティビティ。 追加のデータは、パーソナライゼーションフィールドを追加する際に **Additional data (TargetData)** ノードで確認できます。

   ![](assets/enrichment_example_workflow10.png)

**関連トピック:**

* [外部データによる顧客プロファイルの強化](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
