---
solution: Campaign Standard
product: campaign
title: フィールドがエンリッチメントされた E メールの送信
description: 次の例は、「ファイル読み込み」アクティビティで外部ファイルから取得した追加データを使用して電子メールを送信する方法を示しています。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 75%

---


# フィールドがエンリッチメントされた E メールの送信 {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

「ファイル読み込み」アクティビティを使用すると、同じワークフロー内の外部ファイルからの追加データを使用して、強化された電子メールを送信することもできます。

次の例は、「ファイル読み込み」アクティビティで外部ファイルから取得した追加データを使用して電子メールを送信する方法を示しています。この例では、プロファイルと、関連付けられているアカウント番号のリストが、外部ファイルに格納されています。このデータをインポートして、各プロファイルに、アカウント番号を通知する E メールを送信します。

![](assets/load_file_workflow_ex2.png)

ワークフローを構築するには、次の手順に従います。

1. [クエリ](../../automating/using/query.md)アクティビティをワークフローにドラッグ&amp;ドロップし、開いてメインターゲットを定義します。

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. [ファイル](../../automating/using/load-file.md)を読み込みアクティビティをドラッグ&amp;ドロップして、一部のデータをプロファイルに割り当てます。 この例では、データベースの一部のプロファイルに対応するアカウント番号が含まれているファイルを読み込みます。

   ![](assets/load_file_activity.png)

1. [エンリッチメント](../../automating/using/enrichment.md)アクティビティをワークフローにドラッグ&amp;ドロップし、ロードファイルとクエリアクティビティをそのワークフローにリンクします。

1. エンリッチメントアクティビティの「**[!UICONTROL Advanced relations]**」タブで、「**[!UICONTROL 0 or 1 cardinality simple link]**」を選択し、紐付けに使用するフィールドを定義します。ここでは、姓を使用してデータをデータベースプロファイルに紐付けします。

   ![](assets/load_file_enrichment_relation.png)

1. 「**[!UICONTROL Additional data]**」タブで、E メールに使用する要素を選択します。次に、アカウント番号（「ファイル読み込み」アクティビティから取得したファイルの列）を選択します。

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   詳しくは、[エンリッチメント](../../automating/using/enrichment.md)の節を参照してください。

1. [セグメント化](../../automating/using/segmentation.md)アクティビティをワークフローにドラッグ&amp;ドロップし、開いてメインターゲットを絞り込みます。

   ![](assets/load_file_segmentation.png)

   詳しくは、[セグメント化](../../automating/using/segmentation.md)の節を参照してください。

1. [電子メール配信](../../automating/using/email-delivery.md)アクティビティをワークフローにドラッグ&amp;ドロップして開きます。

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. パーソナライゼーションフィールドを追加し、エンリッチメントアクティビティで定義した追加データ（ここでは「アカウント番号」）を「**[!UICONTROL Additional data (targetData)]**」ノードから選択します。これにより、E メールコンテンツ内の各プロファイルのアカウント番号を動的に取得できます。

   ![](assets/load_file_perso_field.png)

1. E メールを保存し、ワークフローを開始します。

E メールがターゲットに送信されます。各プロファイルは、該当するアカウント番号が記載された E メールを受信します。

![](assets/load_file_email.png)
