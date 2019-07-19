---
title: オーディエンスの作成
seo-title: オーディエンスの作成
description: オーディエンスの作成
seo-description: Adobe Campaignでオーディエンスを作成する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: fe99b31b- a949-4832- b0e6-2b36d1c8be80
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: オーディエンス
content-type: 参照
topic-tags: 管理-オーディエンス
discoiquuid: df8bdcfb- be5e-4044- bc26- aa3466accbbe
context-tags: readAudience， main;オーディエンス、概要;配信、オーディエンス、戻る
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Creating audiences{#creating-audiences}

## Creating query audiences {#creating-query-audiences}

This section describes how to create a **Query** audience. You can also create audiences from importing a file or targeting in a [workflow](../../automating/using/discovering-workflows.md).

オーディエンスリストから、Adobe Campaignプロファイルのクエリを実行したり、Adobe Experience Cloudオーディエンスをインポートしてオーディエンスを作成したりできます。

1. **[!UICONTROL Audiences]** タブまたはカードを使用してオーディエンスリストに移動します。

   ![](assets/audiences_query_1.png)

1. Select **[!UICONTROL Create]** to access the screen to create a new audience.

   ![](assets/audiences_query.png)

1. オーディエンスに名前を付けます。オーディエンスラベルは、オーディエンスのリストおよびクエリーツールのパレットで使用されます。
1. **[!UICONTROL Query]** オーディエンスタイプを選択します。クエリによって定義されたオーディエンスは、その後の使用時に再計算されます。

   ![](assets/audience_type_selection.png)

1. Then select the **[!UICONTROL Targeting dimension]** that you would like to use to filter your customers. 各オーディエンスは、単一のターゲティングディメンションで構成されています。例えば、プロファイルとテストプロファイルとサブスクライバーの両方で構成されたオーディエンスを作成することはできません。For more on targeting dimensions, refer to [this page](../../automating/using/query.md#targeting-dimensions-and-resources).
1. オーディエンス母集団を定義するクエリを作成します。Refer to the section on [editing queries](../../automating/using/editing-queries.md).
1. Click the **[!UICONTROL Create]** button to save your audience.

>[!NOTE]
>
>You can add a description to this audience and define the access authorizations via the **[!UICONTROL Edit properties]** icon.

## Creating list audiences {#creating-list-audiences}

This section describes how to create a **List** audience after targeting in a workflow. You can also create audiences by importing a file into a [workflow](../../automating/using/discovering-workflows.md) or via a query from the **[!UICONTROL Audiences]** menu.

**リスト** オーディエンスを作成するには、次の手順を実行します。

1. **「マーケティングアクティビティ** »タブで?«作成?»をクリックし、?«ワークフロー?********

   ![](assets/audiences_list_1.png)

1. Drag and drop, and then configure the targeting activities which will allow you to select a population that has a **known** dimension. The list of available activities and their configuration are detailed in the [Targeting activities](../../automating/using/about-targeting-activities.md) section.

   You can use a **[!UICONTROL Query]** activity, or import data using a **[!UICONTROL Load file]** activity before using a **[!UICONTROL Reconciliation]** activity to identify the dimension of the data imported. Here, we want to target recipients who subscribed to the Sport Newsletter with a **[!UICONTROL Query]** activity .

   ![](assets/audiences_list_2.png)

1. After your targeting, drag and drop a **[!UICONTROL Save audience]** activity into your workflow. For example, you can chose to **[!UICONTROL Create or update an audience]**, this allows you to create then automatically update your audience with new data. In this case, add a **[!UICONTROL Scheduler]** activity at the beginning of your workflow.

   For more information on configuring this activity, refer to the [Save audience](../../automating/using/save-audience.md) section.

   ![](assets/audiences_list_3.png)

1. ワークフローを保存して開始します。

   As the **[!UICONTROL Save audience]** is placed after a targeting with a known dimension, the audiences created via this activity are **List** audiences.

   保存されたオーディエンスのコンテンツは、オーディエンスのリストからアクセスできるオーディエンスの詳細ビューで利用できます。このビューで使用できる列は、ワークフローの保存アクティビティのインバウンド移行の列に対応します。次に例を示します。ファイルの列がインポートされ、クエリーから追加されたデータが追加されます。

   ![](assets/audiences_list_4.png)

## Creating file audiences {#creating-file-audiences}

This section details how to create a **File** audience by importing a file into a workflow. [また、ワークフロー](../../automating/using/discovering-workflows.md) のターゲットアクティビティからオーディエンスを作成したり、メニューから **[!UICONTROL Audiences]** のクエリを使用したりできます。

**ファイル** オーディエンスを作成するには、次の手順を実行します。

1. **「マーケティングアクティビティ** »タブで?«作成?»をクリックし、?«ワークフロー?********
1. Drag and drop, and then configure a **[!UICONTROL Load file]** activity which will allow you to import a population that has an **unknown** dimension when the workflow is executed. For more information on configuring this activity, refer to the [Load file](../../automating/using/load-file.md) section.

   ![](assets/audience_files_1.png)

1. Drag and drop a **[!UICONTROL Save audience]** activity after the **[!UICONTROL Load file]** activity. For more information on configuring this activity, refer to the [Save audience](../../automating/using/save-audience.md) section.
1. ワークフローを保存して開始します。

   ![](assets/audience_files_2.png)

   As the **[!UICONTROL Save audience]** is placed after an import, the data dimension is unknown and the audiences created via this activity are **File** audiences.

   保存されたオーディエンスのコンテンツは、オーディエンスのリストからアクセスできるオーディエンスの詳細ビューで利用できます。このビューで使用できる列は、ワークフローの保存アクティビティのインバウンド移行の列に対応します。次に例を示します。インポートされたファイルの列で、クエリーから追加された追加データが表示されます。

   ![](assets/audience_files_3.png)

## Creating Experience Cloud audiences {#creating-experience-cloud-audiences}

Adobe Campaignでは、Adobe Experience Cloudでオーディエンスを共有および交換できます。**Experience Cloud** タイプのオーディエンスは **[!UICONTROL Import shared audience]** 、技術ワークフローを使用して、PeopleコアサービスからAdobe Campaignに直接インポートされます。

Unlike **Query** type audience which will query profiles from Adobe Campaign, the **Experience Cloud** audience is composed of a list of Visitor IDs.

この統合が機能するには、まず設定する必要があります。For more information on configuration and how to import or export audiences with People core service, refer to the following [section](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md).

![](assets/audience_peoplecore.png)

## Editing audiences {#editing-audiences}

オーディエンスのタイプに応じてオーディエンスを編集するには、様々な方法があります。

* **クエリ** オーディエンスを編集するには **[!UICONTROL Audiences]** 、メニューを使用してオーディエンスのリストを表示するか、Adobe Campaignホームページから **[!UICONTROL Audiences]** のカードを選択します。

   関連するオーディエンスを開きます。以前に作成したオーディエンスの要素はすべて編集できます。

   >[!CAUTION]
   >
   >If you change the **[!UICONTROL Filtering dimension]** in the query, the rules that have previously been defined will be lost.

* **リスト** また **はファイル** のオーディエンスを編集するには、そのオーディエンスが作成されたワークフローを編集し、 **[!UICONTROL Save audience]** アクティビティを変更します。オーディエンスが変更されるようにワークフローを開始します。
* **Experience Cloud** オーディエンスを編集するには、 [Peopleコアサービス](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) セクションでのオーディエンスの読み込み/書き出しを参照してください。

## Deleting audiences {#deleting-audiences}

1つまたは複数のオーディエンスを削除するには、2つの方法があります。まず、オーディエンスに有効期限を追加します

そのためには、次の手順を実行します。

1. オーディエンスの1つにアクセスします。
1. Click the ![](assets/edit_darkgrey-24px.png) button to access your audience's configuration.

   ![](assets/audience_delete_2.png)

1. **[!UICONTROL Expires on]** フィールドで、オーディエンスに有効期限を追加します。

   ![](assets/audience_delete_3.png)

1. **[!UICONTROL Confirm]****[!UICONTROL Save]**&#x200B;をクリックします。

有効期限が設定されました。この日になると、オーディエンスは自動的に削除されます。

Or if you need to delete an audience, you can simply select one or several audiences then click the **[!UICONTROL Delete element]** button.

![](assets/audience_delete_1.png)

