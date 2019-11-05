---
title: オーディエンスの作成
description: Adobe Campaignでオーディエンスを作成する方法を説明します。
page-status-flag: 非活性化の
uuid: fe99b31b-a949-4832-b0e6-2b36d1c8be80
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参照
topic-tags: 管理対象
discoiquuid: df8bdcfb-be5e-4044-bc26-aa3466accbe
context-tags: readAudience,main;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# オーディエンスの作成{#creating-audiences}

## クエリオーディエンスの作成 {#creating-query-audiences}

ここでは、クエリオーディエンスの作成方法につ **いて** 、説明します。 また、ファイルのインポートやワークフローでのターゲット設定からオーディエンスを作成すること [もできま](../../automating/using/discovering-workflows.md)す。

オーディエンスリストから、Adobe Campaignプロファイルに対してクエリを実行するか、Adobe Experience cloudオーディエンスをインポートすることで、オーディエンスを作成できます。

1. タブまたはカードを使用してオーディエンス **[!UICONTROL Audiences]** リストに移動します。

   ![](assets/audiences_query_1.png)

1. 新しいオ **[!UICONTROL Create]** ーディエンスを作成する画面にアクセスする場合に選択します。

   ![](assets/audiences_query.png)

1. オーディエンスに名前を付けます。 オーディエンスラベルは、オーディエンスのリストとクエリツールのパレットで使用されます。
1. オーディエンスの **[!UICONTROL Query]** タイプを選択します。クエリによって定義されたオーディエンスは、それ以降の使用のたびに再計算されます。

   ![](assets/audience_type_selection.png)

1. 次に、顧客 **[!UICONTROL Targeting dimension]** のフィルターに使用する対象を選択します。 各オーディエンスは、1つのターゲットディメンションで構成されます。 例えば、プロファイル、テストプロファイル、サブスクライバーの両方で構成されるオーディエンスを作成することはできません。 For more on targeting dimensions, refer to [this page](../../automating/using/query.md#targeting-dimensions-and-resources).
1. クエリを作成して、オーディエンスの母集団を定義します。 クエリの編集に関する節を参 [照してください](../../automating/using/editing-queries.md)。
1. ボタンをクリッ **[!UICONTROL Create]** クして、オーディエンスを保存します。

>[!NOTE]
>
>このオーディエンスに説明を追加し、アイコンを使用してアクセス承認を定義で **[!UICONTROL Edit properties]** きます。

## リストオーディエンスの作成 {#creating-list-audiences}

ここでは、ワークフローでターゲット化した後に **リスト** オーディエンスを作成する方法について説明します。 また、ワークフローにファイルをインポートするか、メニューから [クエリ](../../automating/using/discovering-workflows.md) を使用してオーディエンスを作成することもで **[!UICONTROL Audiences]** きます。

To create a **List** audience, the steps are as follows:

1. 「マーケティング **アクティビティ** 」タブで「作成」をクリック **し、「ワークフロー** 」を **選択します**。

   ![](assets/audiences_list_1.png)

1. ドラッグ&amp;ドロップして、既知のディメンションを持つ訪問者を選択できるターゲットアクティビティを設 **定します** 。 使用可能なアクティビティのリストとその設定について詳しくは、「ターゲットアクティビティ [」セクション](../../automating/using/about-targeting-activities.md) を参照してください。

   アクティビティを使用し **[!UICONTROL Query]** たり、アクティビティを使用してデータをインポートした後で、ア **[!UICONTROL Load file]** クティビティを使用し **[!UICONTROL Reconciliation]** てインポートしたデータのディメンションを特定したりできます。 ここでは、スポーツニュースレターを購読した受信者をアクティビティでターゲットにし **[!UICONTROL Query]** ます。

   ![](assets/audiences_list_2.png)

1. ターゲット設定後、アクティビティをワークフローにド **[!UICONTROL Save audience]** ラッグ&amp;ドロップします。 例えば、新しいデータを使用してオーデ **[!UICONTROL Create or update an audience]**&#x200B;ィエンスを作成し、自動的に更新することができます。 この場合、ワークフローの最 **[!UICONTROL Scheduler]** 初にアクティビティを追加します。

   このアクティビティの設定について詳しくは、「オーディエンスを保存」の節を [参照してくださ](../../automating/using/save-audience.md) い。

   ![](assets/audiences_list_3.png)

1. ワークフローを保存して開始します。

   が既知のディメ **[!UICONTROL Save audience]** ンションを持つターゲット設定の後に配置されるので、このアクティビティを介して作成されるオーディエンスはリストオーディエ **ンスで** す。

   保存したオーディエンスのコンテンツは、オーディエンスの詳細ビューで使用でき、オーディエンスのリストを介してアクセスできます。 このビューで使用できる列は、ワークフローの保存アクティビティの受信トランジションの列に対応します。 例：インポートされたファイルの列、およびクエリーから追加された追加データ。

   ![](assets/audiences_list_4.png)

## ファイルオーディエンスの作成 {#creating-file-audiences}

この節では、ファイルをワークフローに読み込 **んで** 、ファイルオーディエンスを作成する方法について説明します。 また、ワークフロー内のターゲティングアクティビティから、またはメ [ニューから](../../automating/using/discovering-workflows.md) 、クエリを使用して、オーディエンスを作成することも **[!UICONTROL Audiences]** できます。

To create a **File** audience, the steps are as follows:

1. 「マーケティング **アクティビティ** 」タブで「作成」をクリック **し、「ワークフロー** 」を **選択します**。
1. ドラッグ&amp;ドロップし、ワークフローの実 **[!UICONTROL Load file]** 行時に不明なディメンションを持つ母集団をインポ **ートで** きるアクティビティを設定します。 このアクティビティの設定の詳細については、「ファイルの読み込み」の節を参 [照してくださ](../../automating/using/load-file.md) い。

   ![](assets/audience_files_1.png)

1. アクティビティの後にアクティビティ **[!UICONTROL Save audience]** をドラッグ&amp;ドロッ **[!UICONTROL Load file]** プします。 このアクティビティの設定について詳しくは、「オーディエンスを保存」の節を [参照してくださ](../../automating/using/save-audience.md) い。
1. ワークフローを保存して開始します。

   ![](assets/audience_files_2.png)

   がインポート **[!UICONTROL Save audience]** の後に配置されるので、データディメンションは不明で、このアクティビティを介して作成されたオーディエンスは **File** オーディエンスです。

   保存したオーディエンスのコンテンツは、オーディエンスの詳細ビューで使用でき、オーディエンスのリストを介してアクセスできます。 このビューで使用できる列は、ワークフローの保存アクティビティの受信トランジションの列に対応します。 例：インポートしたファイルの列、およびクエリーから追加された追加データ。

   ![](assets/audience_files_3.png)

## Experience cloudオーディエンスの作成 {#creating-experience-cloud-audiences}

Adobe Campaignを使用すると、オーディエンスをAdobe Experience cloudと共有し、交換できます。 Experience cloudタイプのオーディエンスは **、技術的なワークフローを使用して、PeopleコアサービスからAdobe Campaignに直接インポ****[!UICONTROL Import shared audience]** ートされます。

Adobe Campaignから **プロファイルをクエリする** Queryタイプのオーディエンスとは異なり、 **** Experience cloudオーディエンスは訪問者IDのリストで構成されます。

この統合を機能させるには、まず統合を設定する必要があります。 設定およびPeopleコアサービスを使用したオーディエンスのインポートまたはエクスポートの方法について詳しくは、次の節を参照して [くださ](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)い。

![](assets/audience_peoplecore.png)

## オーディエンスの編集 {#editing-audiences}

オーディエンスを編集する方法は、オーディエンスのタイプに応じて異なります。

* クエリオーディエン **スを編集するには** 、メニューからオーディエンスのリストに移動するか、Adobe Campaignのホ **[!UICONTROL Audiences]** ームページか **[!UICONTROL Audiences]** らカードに移動します。

   関連するオーディエンスを開きます。 以前に作成したオーディエンスのすべての要素を編集できます。

   >[!CAUTION]
   >
   >クエリ内のを変 **[!UICONTROL Filtering dimension]** 更すると、以前に定義されたルールは失われます。

* リストオーディエンス **また** はファイルオーディエンスを編集するには **、作成元のワークフローを編集し、アクティビティを変更****[!UICONTROL Save audience]** します。 オーディエンスが変更されるようにワークフローを開始します。
* **Experience cloudオーディエンスを編集するには** 、「Peopleコアサービスでのオーデ [ィエンスのインポート](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) /エクスポート」の節を参照してください。

## オーディエンスの削除 {#deleting-audiences}

1つまたは複数のオーディエンスを削除する方法は2つあります。 まず、オーディエンスに有効期限を追加します

これをおこなうには：

1. オーディエンスの1つにアクセスします。
1. ボタンをクリ ![](assets/edit_darkgrey-24px.png) ックして、オーディエンスの設定にアクセスします。

   ![](assets/audience_delete_2.png)

1. このフィールド **[!UICONTROL Expires on]** で、オーディエンスに有効期限を追加します。

   ![](assets/audience_delete_3.png)

1. 「&gt;」をク **[!UICONTROL Confirm]** リックしま **[!UICONTROL Save]**&#x200B;す。

有効期限が設定されました。 この日付に達すると、オーディエンスは自動的に削除されます。

または、オーディエンスを削除する必要がある場合は、1つまたは複数のオーディエンスを選択して、ボタンをクリック **[!UICONTROL Delete element]** します。

![](assets/audience_delete_1.png)

