---
title: データを更新
description: Updateデータアクティビティを使用すると、データベース内のフィールドに対して一括更新を実行できます。
page-status-flag: 非活性化の
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: データ管理活動
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# データを更新{#update-data}

## 説明 {#description}

![](assets/data_update.png)

アクテ **[!UICONTROL Update data]** ィビティを使用すると、データベース内のフィールドに対して一括更新を実行できます。

## 使用状況 {#context-of-use}

「 **Update data** 」アクティビティは、ファイルのインポート後に使用して、Adobe Campaignデータベースに回復されたデータを挿入できます。 いくつかのオプションを使用して、データの更新をパーソナライズできます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Update data]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. 実行する **[!UICONTROL Operation type]** 対象を指定します。

   * **[!UICONTROL Insert or update]**:データを挿入するか、データベースにレコードが既に存在する場合はデータを更新します。
   * **[!UICONTROL Insert only]**:データのみを挿入します。 既に存在するレコードは更新されません。 調整条件が定義されている場合、非調整レコードのみが追加されます。

      エラーを避けるた **[!UICONTROL Generate an outbound transition for rejects]** めに、インポートするデータにデータベースに既に存在する特定のレコードが含まれている場合は、このボックスをオンにします。

   * **[!UICONTROL Update]**:データベースに既に存在するレコードのみのデータを更新します。
   * **[!UICONTROL Delete]**:データを削除します。
   >[!NOTE]
   >
   >このフ **[!UICONTROL Batch size]** ィールドでは、アップロードするデータの最大バッチサイズを定義できます。

1. タブで、 **[!UICONTROL Identification]** データベース内のレコードの識別方法を指定します。

   * **[!UICONTROL Using the targeting dimension]**:を選択し **[!UICONTROL Dimension to update]** て、を指定しま **[!UICONTROL Keys for finding records]**&#x200B;す。 詳しくは、ディメンションとリソースのターゲ [ット設定を参照してくださ](../../automating/using/query.md#targeting-dimensions-and-resources)い。
   * 入力したデータが既存のターゲットディメンションと一致する場合は、このオプションを選択 **[!UICONTROL Using one or more links]** します。 次に、を選択しま **[!UICONTROL Dimension to update]**&#x200B;す。
   選択した操作タイプで更新が必要な場合は、調整キーを使用する必要があります。

1. タブで、 **[!UICONTROL Fields to update]** 更新を適用するフィールドを指定し、必要に応じて条件を追加して、この更新を実行します。 これを行うには、列を使用し **[!UICONTROL Taken into account if]** ます。 条件がリスト順に適用されます。 右側の矢印を使用して、更新の順序を変更します。 同じリンク先フィールドを複数回使用できます。

   ボタンを使用して、フィールドを自動的にリンクさせること ![](assets/wkf_magic_wand-24px.png) ができます。 自動リンクは、同じ名前のフィールドを検出します。

   タイプ操作 **[!UICONTROL Insert or update]** 中に、各フィールドに適用する操作を個別に選択できます。 これを行うには、列で値を選択し **[!UICONTROL Operation]** ます。

   >[!NOTE]
   >
   >**更新の管理** ：更新データアクティビティの実行時に、 **[!UICONTROL lastModified]**、 **[!UICONTROL modifiedBy]****[!UICONTROL created]****[!UICONTROL createdBy]** およびフィールドが自動的に更新されます。ただし、フィールドの設定がフィールド更新テーブルで明示的に行われる場合を除きます。 更新は、少なくとも1つの違いが検出されたレコードに対してのみ行われます。 値が同じ場合、更新は実行されません。

1. 必要に応じて、アクティビティの遷移を管理し [て](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) 、アウトバウンド母集団のアドバンスオプションにアクセスします。

   を選択した場合、インポー **[!UICONTROL Insert only]** トするデータにデータベースに既に存在するレコードが含まれている可能性がある場合は、エラーが発生しな **[!UICONTROL Generate an outbound transition for the rejects]** いように、このボックスをオンにします。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次のアクティビティは、アクティビティに続くア **[!UICONTROL Update data]** クティビティの設定を示 **[!UICONTROL Load file]** します。 このワークフローの目的は、ファイルから回復したデータを使用して、Adobe Campaignデータベースにプロファイルを追加または更新することです。 使用される調整キーは電子メールアドレスです。

読み込まれるファイルは **.txt形式のファイルで** 、次の例のデータが含まれています。

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

アクティビテ **[!UICONTROL Update data]** ィは次のように設定します。

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

