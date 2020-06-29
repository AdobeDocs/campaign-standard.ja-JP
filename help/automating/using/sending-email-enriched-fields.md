---
title: 強化されたフィールドを含む電子メールの送信
description: 次の例は、ロードファイルアクティビティを介して外部ファイルから取得した追加データを使用して電子メールを送信する方法を示しています。
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# 強化されたフィールドを含む電子メールの送信 {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

ロードファイルアクティビティを使用すると、同じワークフロー内の外部ファイルから追加データを追加してリンチされた電子メールを送信することもできます。

次の例は、ロードファイルアクティビティを介して外部ファイルから取得した追加データを使用して電子メールを送信する方法を示しています。 この例では、外部ファイルにプロファイルのリストと関連するアカウント番号が含まれています。 このデータをインポートして、各プロファイルにアカウント番号と共に電子メールを送信する場合。

![](assets/load_file_workflow_ex2.png)

ワークフローを構築するには、次の手順に従います。

1. ワークフロー内に [クエリ](../../automating/using/query.md) アクティビティをドラッグ&amp;ドロップし、それを開いてメインターゲットを定義します。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. 「 [ファイルをロード](../../automating/using/load-file.md) 」アクティビティをドラッグ&amp;ドロップして、一部のデータをプロファイルに割り当てます。 この例では、データベースの一部のプロファイルに対応するアカウント番号を含むファイルを読み込みます。

   ![](assets/load_file_activity.png)

1. ワークフローに [エンリッチメント](../../automating/using/enrichment.md) アクティビティをドラッグ&amp;ドロップし、ロードファイルとクエリアクティビティをそのワークフローにリンクします。

1. エンリッチメントアクティビティの **[!UICONTROL Advanced relations]** タブで、調整に使用するフィールドを選択 **[!UICONTROL 0 or 1 cardinality simple link]** し、定義します。 ここでは、姓を使用してデータをデータベースプロファイルと調整します。

   ![](assets/load_file_enrichment_relation.png)

1. タブで、電子メールに使用する要素を選択し **[!UICONTROL Additional data]** ます。 次に、アカウント番号(ファイルの読み込みアクティビティから取得したファイルの列)を選択します。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   For more on this, see the [Enrichment](../../automating/using/enrichment.md) section.

1. セグメント化 [アクティビティをワークフローにドラッグ&amp;ドロップして開き](../../automating/using/segmentation.md) 、メインターゲットを絞り込みます。

   ![](assets/load_file_segmentation.png)

   For more on this, see the [Segmentation](../../automating/using/segmentation.md) section.

1. 「 [電子メール配信](../../automating/using/email-delivery.md) 」アクティビティをワークフローにドラッグ&amp;ドロップして開きます。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. パーソナライゼーション追加フィールドを選択し、エンリッチメントアクティビティ（ここでは「アカウント番号」）で定義された追加データを **[!UICONTROL Additional data (targetData)]** ノードから選択します。 これにより、電子メールコンテンツ内の各プロファイルのアカウント番号を動的に取得できます。

   ![](assets/load_file_perso_field.png)

1. 電子メールと開始をワークフローに保存します。

電子メールがターゲットに送信されます。 各プロファイルは、対応するアカウント番号を持つ電子メールを受信します。

![](assets/load_file_email.png)
