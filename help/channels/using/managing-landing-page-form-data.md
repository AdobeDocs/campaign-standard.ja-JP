---
solution: Campaign Standard
product: campaign
title: ランディングページフォームデータの管理
description: ランディングページフォームデータを管理する方法について説明します。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---


# ランディングページフォームデータの管理{#managing-landing-page-form-data}

## ランディングページフォームデータプロパティの変更{#changing-a-landing-page-form-data-properties}

データベースフィールドを入力ゾーン、ラジオボタンまたはチェックボックスタイプのブロックにリンクできます。これをおこなうには、ブロックを選択し、パレットに **[!UICONTROL Form data]** を入力します。

![](assets/delivery_content_9.png)

* **Field** 入力ゾーンを使用すると、フォームフィールドとリンクするためのデータベースフィールドを選択できます。
* 「**Mandatory**」オプションを使用すると、ユーザーがフィールドに入力した場合にのみページの送信を承認します。必須フィールドに入力されていない場合、エラーメッセージが表示されます。

## フォームフィールドのマッピング {#mapping-form-fields}

入力フィールドは、Campaign データベースにデータを格納または更新するために使用します。これをおこなうには、データベースフィールドを入力ゾーン、ラジオボタンまたはチェックボックスタイプのブロックにリンクする必要があります。手順は次のとおりです。

1. ランディングページでブロックを選択します。
1. パレットの **[!UICONTROL Form data]** 部分を完成させます。

   ![](assets/editing_lp_content_4.png)

1. データベースフィールドを選択し、**[!UICONTROL Field]** 選択ゾーンのフォームフィールドとリンクします。ランディングページとマッピングできるのは **Profiles** のみです。

1. 必要に応じて、「**[!UICONTROL Mandatory]**」オプションを選択します。ページは、ユーザーがこのフィールドに入力した場合にのみ送信できます。必須フィールドが未入力の場合、ユーザーがページを検証するとエラーメッセージが表示されます。

1. フィールドのタイプを定義するには、**[!UICONTROL HTML type of the field]** 選択領域で、「**[!UICONTROL Text]**」、「**[!UICONTROL Number]**」、「**[!UICONTROL Date]**」などを選択します。
必須の **[!UICONTROL Checkbox]** を選択する場合は、そのタイプが **[!UICONTROL Field]** であることを確認します。

>[!NOTE]
>
>組み込みランディングページのデフォルトのフィールドは事前に設定されています。必要に応じて変更できます。

## データのストレージと紐付け{#data-storage-and-reconciliation}

データ紐付けパラメーターを使用すると、ランディングページに入力されたデータが送信された後の管理方法を定義できます。

手順は次のとおりです。

1. ランディングページダッシュボードの ![](assets/edit_darkgrey-24px.png) アイコンを使用してアクセスするランディングページのプロパティを編集し、「**[!UICONTROL Job]**」パラメーターを表示します。

   ![](assets/lp_parameters_4.png)

1. **[!UICONTROL Reconciliation key]** を選択：これらのデータベースフィールド（例：E メール、名、姓）は、Adobe Campaign データベース内に訪問者のプロファイルが既に存在するかどうかを判断するために使用されます。これにより、定義した更新方法のパラメーターに従って、プロファイルを更新または作成できます。
1. **[!UICONTROL Form parameter mapping]** を定義：このセクションでは、ランディングページフィールドのパラメーターと、紐付けキーで使用するパラメーターをマップできます。
1. **[!UICONTROL Update strategy]** を選択：紐付けキーが既存のデータベースプロファイルを回復した場合、フォームに入力されたデータを使用してこのプロファイルを更新するか、この更新を実行しないかを選択できます。
