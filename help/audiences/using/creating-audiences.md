---
solution: Campaign Standard
product: campaign
title: オーディエンスの作成
description: Adobe Campaign でオーディエンスを作成する方法について説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: readAudience,main;audience,overview;delivery,audience,back
feature: オーディエンス
role: 開業医
level: 初心者
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '973'
ht-degree: 99%

---


# オーディエンスの作成{#creating-audiences}

## クエリオーディエンスの作成 {#creating-query-audiences}

この節では、**クエリ**&#x200B;オーディエンスを作成する方法について説明します。オーディエンスは、ファイルのインポートや[ワークフロー](../../automating/using/get-started-workflows.md)でのターゲティングからも作成できます。

オーディエンスリストからオーディエンスを作成するには、Adobe Campaign プロファイルでクエリを実行するか、Adobe Experience Cloud オーディエンスをインポートします。

1. 「**[!UICONTROL Audiences]**」タブまたはカードからオーディエンスリストに移動します。

   ![](assets/audiences_query_1.png)

1. 新しいオーディエンスを作成する画面にアクセスするには、「**[!UICONTROL Create]**」を選択します。

   ![](assets/audiences_query.png)

1. オーディエンスに名前を付けます。オーディエンスラベルは、オーディエンスのリストとクエリツールのパレットで使用されます。
1. **[!UICONTROL Query]** オーディエンスタイプを選択します。クエリが定義するオーディエンスは、それ以降使用されるたびに再計算されます。

   ![](assets/audience_type_selection.png)

1. 次に、顧客のフィルタリングに使用する **[!UICONTROL Targeting dimension]** を選択します。各オーディエンスは単一のターゲティングディメンションで構成されます。例えば、プロファイル、テストプロファイル、購読者すべてを使用してオーディエンスを作成することはできません。ターゲティングディメンションについて詳しくは、[このページ](../../automating/using/query.md#targeting-dimensions-and-resources)を参照してください。
1. オーディエンス母集団を定義するクエリを作成します。[クエリの編集](../../automating/using/editing-queries.md)の節を参照してください。
1. オーディエンスを保存するには、「**[!UICONTROL Create]**」ボタンをクリックします。

>[!NOTE]
>
>**[!UICONTROL Edit properties]** アイコンを使用してこのオーディエンスに説明を追加し、アクセス認証を定義できます。

## リストオーディエンスの作成 {#creating-list-audiences}

ここでは、ワークフロー内でターゲティングした後に&#x200B;**リスト**&#x200B;オーディエンスを作成する方法について説明します。オーディエンスは、[ワークフロー](../../automating/using/get-started-workflows.md)にファイルをインポートして作成することも **[!UICONTROL Audiences]** メニューでクエリを使用して作成することもできます。

**リスト**&#x200B;オーディエンスを作成する手順は、次のとおりです。

1. 「**Marketing activities**」タブで「**Create**」をクリックし、「**Workflow**」を選択します。

   ![](assets/audiences_list_1.png)

1. ドラッグ＆ドロップして、**既知の**&#x200B;ディメンションを持つ母集団を選択できるようにターゲティングアクティビティを設定します。使用可能なアクティビティのリストとその設定について詳しくは、[ターゲティングアクティビティ](../../automating/using/about-targeting-activities.md)の節を参照してください。

   「**[!UICONTROL Reconciliation]**」アクティビティを使用してインポートされたデータのディメンションを識別する前に、「**[!UICONTROL Query]**」アクティビティを使用するか、「**[!UICONTROL Load file]**」アクティビティを使用してデータをインポートできます。ここでは、スポーツニュースレターを購読した受信者を「**[!UICONTROL Query]**」アクティビティでターゲットに指定します。

   ![](assets/audiences_list_2.png)

1. ターゲティングが終わったら、ワークフローに「**[!UICONTROL Save audience]**」アクティビティをドラッグ＆ドロップします。例えば、**[!UICONTROL Create or update an audience]** を実行すると、新しいデータを使用してオーディエンスを作成し、自動的に更新することができます。この場合、ワークフローの先頭に「**[!UICONTROL Scheduler]**」アクティビティを追加します。

   このアクティビティの設定について詳しくは、[オーディエンスの保存](../../automating/using/save-audience.md)の節を参照してください。

   ![](assets/audiences_list_3.png)

1. 保存して、ワークフローを開始します。

   **[!UICONTROL Save audience]** は既知のディメンションでのターゲティングの後に配置されるので、このアクティビティを介して作成されるオーディエンスは&#x200B;**リスト**&#x200B;オーディエンスです。

   保存されたオーディエンスのコンテンツは、オーディエンスの詳細表示で利用でき、オーディエンスのリストを介してアクセスできます。この表示で使用できる列は、ワークフローの保存アクティビティのインバウンドトランジションの列に対応します（例：インポートしたファイルの列、クエリから追加された追加データの列）。

   ![](assets/audiences_list_4.png)

## ファイルオーディエンスの作成 {#creating-file-audiences}

この節では、ファイルをワークフローにインポートして&#x200B;**ファイル**&#x200B;オーディエンスを作成する方法について説明します。オーディエンスは、[ワークフロー](../../automating/using/get-started-workflows.md)内のターゲティングアクティビティから作成することも **[!UICONTROL Audiences]** メニューでクエリを使用して作成することもできます。

**ファイル**&#x200B;オーディエンスを作成する手順は、次のとおりです。

1. 「**Marketing activities**」タブで「**Create**」をクリックし、「**Workflow**」を選択します。
1. ドラッグ＆ドロップして、ワークフローの実行時に&#x200B;**不明な**&#x200B;ディメンションを持つ母集団をインポートできるように「**[!UICONTROL Load file]**」アクティビティを設定します。このアクティビティの設定について詳しくは、[ファイルの読み込み](../../automating/using/load-file.md)の節を参照してください。

   ![](assets/audience_files_1.png)

1. 「**[!UICONTROL Load file]**」アクティビティの後に「**[!UICONTROL Save audience]**」アクティビティをドラッグ＆ドロップします。このアクティビティの設定について詳しくは、[オーディエンスの保存](../../automating/using/save-audience.md)の節を参照してください。
1. 保存して、ワークフローを開始します。

   ![](assets/audience_files_2.png)

   **[!UICONTROL Save audience]** はインポートの後に配置されるので、データディメンションは不明で、このアクティビティを介して作成されるオーディエンスは&#x200B;**ファイル**&#x200B;オーディエンスです。

   保存されたオーディエンスのコンテンツは、オーディエンスの詳細表示で利用でき、オーディエンスのリストを介してアクセスできます。この表示で使用できる列は、ワークフローの保存アクティビティのインバウンドトランジションの列に対応します（例：インポートしたファイルの列、クエリから追加された追加データの列）。

   ![](assets/audience_files_3.png)

## Experience Cloud オーディエンスの作成 {#creating-experience-cloud-audiences}

Adobe Campaign を使用すると、Adobe Experience Cloud とオーディエンスを共有し、交換できます。**Experience Cloud** タイプのオーディエンスは、**[!UICONTROL Import shared audience]** テクニカルワークフローで、People コアサービスから Adobe Campaign に直接インポートされます。

Adobe Campaign からのプロファイルに対してクエリをおこなう&#x200B;**クエリ**&#x200B;タイプのオーディエンスとは異なり、**Experience Cloud** オーディエンスは、訪問者 ID のリストで構成されます。

この統合を機能させるには、まず統合を設定する必要があります。設定および People コアサービスを使用したオーディエンスのインポートまたはエクスポート方法について詳しくは、次の[節](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)を参照してください。

![](assets/audience_peoplecore.png)

## オーディエンスの編集 {#editing-audiences}

オーディエンスを編集する方法は、オーディエンスのタイプに応じて異なります。

* **クエリ**&#x200B;オーディエンスを編集するには、**[!UICONTROL Audiences]** メニューからオーディエンスのリストに移動するか、Adobe Campaign ホームページから **[!UICONTROL Audiences]** カードに移動します。

   関連オーディエンスを開きます。以前に作成したオーディエンスのすべての要素を編集できます。

   >[!CAUTION]
   >
   >クエリで **[!UICONTROL Filtering dimension]** を変更すると、以前に定義されたルールは失われます。

* **リスト**&#x200B;オーディエンスまたは&#x200B;**ファイル**&#x200B;オーディエンスを編集するには、作成元のワークフローを編集し、「**[!UICONTROL Save audience]**」アクティビティを変更します。ワークフローを開始すると、オーディエンスが変更されます。
* **Experience Cloud** オーディエンスを編集するには、[People コアサービスを使用したオーディエンスのインポートとエクスポート](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)の節を参照してください。

## オーディエンスの削除 {#deleting-audiences}

オーディエンスを削除する方法は 2 つあります。まず、オーディエンスに有効期限を追加します。

それには、次の手順に従います。

1. オーディエンスの 1 つにアクセスします。
1. ![](assets/edit_darkgrey-24px.png) ボタンをクリックして、オーディエンスの設定にアクセスします。

   ![](assets/audience_delete_2.png)

1. 「**[!UICONTROL Expires on]**」フィールドで、オーディエンスに有効期限を追加します。

   ![](assets/audience_delete_3.png)

1. 「**[!UICONTROL Confirm]**」、「**[!UICONTROL Save]**」の順にクリックします。

有効期限が設定されました。この日付に達すると、オーディエンスは自動的に削除されます。

オーディエンスを手動で削除する必要がある場合は、1 つまたは複数のオーディエンスを選択して「**[!UICONTROL Delete element]**」ボタンをクリックします。

![](assets/audience_delete_1.png)

