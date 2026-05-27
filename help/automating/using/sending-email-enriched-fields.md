---
title: フィールドがエンリッチメントされたメールの送信
description: 次の例は、「ファイル読み込み」アクティビティで外部ファイルから取得した追加データを使用してメールを送信する方法を示しています。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5ca7571d-d4d2-4b59-86d4-4f1f3a620b54
TQID: https://experienceleague.adobe.com/5psJbqwsciRlctfnGyptzlEMWppn1-ueo57L8NUEgpE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 351
ht-degree: 75%

---

# フィールドがエンリッチメントされたメールの送信 {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

「ファイル読み込み」アクティビティを使用すると、同じワークフロー内の外部ファイルからの追加データを使用して、強化されたメールを送信することもできます。

次の例は、「ファイル読み込み」アクティビティで外部ファイルから取得した追加データを使用してメールを送信する方法を示しています。 この例では、プロファイルと、関連付けられているアカウント番号のリストが、外部ファイルに格納されています。 このデータをインポートして、各プロファイルに、アカウント番号を通知するメールを送信します。

![](assets/load_file_workflow_ex2.png)

ワークフローを構築するには、次の手順に従います。

1. [&#x200B; クエリ &#x200B;](../../automating/using/query.md) アクティビティをワークフローにドラッグ&amp;ドロップし、それを開いてメイン ターゲットを定義します。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. [&#x200B; ファイルを読み込み](../../automating/using/load-file.md) アクティビティをドラッグ&amp;ドロップして、一部のデータをプロファイルに割り当てます。 この例では、データベースの一部のプロファイルに対応するアカウント番号が含まれているファイルを読み込みます。

   ![](assets/load_file_activity.png)

1. [Enrichment](../../automating/using/enrichment.md) アクティビティをワークフローにドラッグ&amp;ドロップし、読み込みファイルとクエリアクティビティをそれにリンクします。

1. エンリッチメントアクティビティの「**[!UICONTROL Advanced relations]**」タブで、「**[!UICONTROL 0 or 1 cardinality simple link]**」を選択し、紐付けに使用するフィールドを定義します。 ここでは、姓を使用してデータをデータベースプロファイルに紐付けします。

   ![](assets/load_file_enrichment_relation.png)

1. 「**[!UICONTROL Additional data]**」タブで、メールに使用する要素を選択します。 次に、アカウント番号（「ファイル読み込み」アクティビティから取得したファイルの列）を選択します。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   詳しくは、[エンリッチメント](../../automating/using/enrichment.md)の節を参照してください。

1. [&#x200B; セグメント化](../../automating/using/segmentation.md) アクティビティをワークフローにドラッグ&amp;ドロップし、それを開いてメインターゲットを調整します。

   ![](assets/load_file_segmentation.png)

   詳しくは、[セグメント化](../../automating/using/segmentation.md)の節を参照してください。

1. [&#x200B; メール配信](../../automating/using/email-delivery.md) アクティビティをワークフローにドラッグ&amp;ドロップして開きます。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. パーソナライゼーションフィールドを追加し、エンリッチメントアクティビティで定義した追加データ（ここでは「アカウント番号」）を「**[!UICONTROL Additional data (targetData)]**」ノードから選択します。 これにより、メールコンテンツ内の各プロファイルのアカウント番号を動的に取得できます。

   ![](assets/load_file_perso_field.png)

1. メールを保存し、ワークフローを開始します。

メールがターゲットに送信されます。 各プロファイルは、該当するアカウント番号が記載されたメールを受信します。

![](assets/load_file_email.png)
