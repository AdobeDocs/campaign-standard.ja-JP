---
title: データの更新
seo-title: データの更新
description: データの更新
seo-description: 更新データアクティビティを使用すると、データベース内のフィールドの一括更新を実行できます。
page-status-flag: 常にアクティブ化されていない
uuid: 1dc55db5- afd-4688- b673- adfb8c1338b5
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: data- management- activity
discoiquuid: 4db83c95-4b75-4a16-8dbf- bd8940431fa9
context-tags: ライター、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Update data{#update-data}

## 説明 {#description}

![](assets/data_update.png)

**[!UICONTROL Update data]** このアクティビティにより、データベース内のフィールドの一括更新を実行できます。

## Context of use {#context-of-use}

**データを更新した後、Adobe Campaignデータベースに回復したデータを挿入するために、更新データ** アクティビティを使用できます。いくつかのオプションを使用して、データをカスタマイズすることができます。

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Operation type]** to be carried out:

   * **[!UICONTROL Insert or update]**:データを挿入するか、データベースにレコードが既に存在する場合は更新します。
   * **[!UICONTROL Insert only]**:データのみを挿入します。既に存在するレコードは更新されていません。紐付け条件が定義されている場合、紐付けされていないレコードのみが追加されます。

      Check the **[!UICONTROL Generate an outbound transition for rejects]** box if the data imported contains certain records that already exist in the database to avoid any possible errors.

   * **[!UICONTROL Update]**:データベースにのみ存在するレコードのデータを更新します。
   * **[!UICONTROL Delete]**:データを削除します。
   >[!NOTE]
   >
   >**[!UICONTROL Batch size]** このフィールドでは、アップロードするデータの最大バッチサイズを定義できます。

1. **[!UICONTROL Identification]** タブで、データベース内のレコードを識別する方法を指定します。

   * **[!UICONTROL Using the targeting dimension]**:を選択 **[!UICONTROL Dimension to update]****[!UICONTROL Keys for finding records]**&#x200B;して、を指定します。For more this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * If the data entered matches an existing targeting dimension, select the **[!UICONTROL Using one or more links]** option. Then select the **[!UICONTROL Dimension to update]**.
   選択した操作タイプに更新が必要な場合は、紐付けキーを使用する必要があります。

1. **[!UICONTROL Fields to update]** タブで、更新を適用するフィールドを指定し、必要に応じて、このアップデートが実行されるように条件を追加します。To do this, use the **[!UICONTROL Taken into account if]** column. 条件はリスト順で1つずつ適用されます。右側の矢印を使用して、更新の順序を変更します。同じ宛先フィールドを複数回使用できます。

   ![](assets/wkf_magic_wand-24px.png) ボタンを使用してフィールドを自動的にリンクできます。自動リンクは、フィールドを同じ名前で検出します。

   **[!UICONTROL Insert or update]** タイプ操作では、各フィールドに適用する操作を個別に選択できます。To do this, select the value you would like in the **[!UICONTROL Operation]** column.

   >[!NOTE]
   >
   >**更新の** 管理 **[!UICONTROL lastModified]**: **[!UICONTROL modifiedBy]**&#x200B;フィールド **[!UICONTROL created]** 更新テーブルで設定が明示的に実行されない限り、更新データアクティビティが実行されると **[!UICONTROL createdBy]** 、自動的に更新されます。この更新は、少なくとも1つの違いが検出されたレコードでのみ実行されます。値が同じ場合、更新は実行されません。

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.

   If you have selected **[!UICONTROL Insert only]** and the data imported may contain records that are already present in the database, check the **[!UICONTROL Generate an outbound transition for the rejects]** box to avoid any possible errors.

1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

The following activity shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. このワークフローの目的は、ファイルから回復したデータを使用してAdobe Campaignデータベースにプロファイルを追加または更新することです。使用される紐付けキーは電子メールアドレスです。

The file loaded is a **.txt** format file containing the following example data:

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

**[!UICONTROL Update data]** アクティビティは次のように設定されます。

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

