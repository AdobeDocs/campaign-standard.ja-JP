---
title: データ更新
description: '[データの更新]アクティビティを使用すると、データベース内のフィールドに対して一括更新を実行できます。'
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 1%

---


# データ更新{#update-data}

## 説明 {#description}

![](assets/data_update.png)

この **[!UICONTROL Update data]** アクティビティを使用すると、データベース内のフィールドに対して一括更新を実行できます。

## 使用状況 {#context-of-use}

「 **Update data** 」アクティビティは、ファイルのインポート後に使用して、リカバリされたデータをAdobe Campaign・データベースに挿入できます。 いくつかのオプションを使用して、データの更新をパーソナライズできます。

## 設定 {#configuration}

1. ワークフローに **[!UICONTROL Update data]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 実行す **[!UICONTROL Operation type]** る対象を指定します。

   * **[!UICONTROL Insert or update]**: データを挿入するか、データベースに既にレコードが存在する場合は更新します。
   * **[!UICONTROL Insert only]**: データのみ挿入します。 既に存在するレコードは更新されません。 調整条件が定義されている場合は、非調整レコードのみが追加されます。

      エラーを回避するために、インポートするデータにデータベースに既に存在する特定のレコードが含まれている場合は、この **[!UICONTROL Generate an outbound transition for rejects]** ボックスをオンにします。

   * **[!UICONTROL Update]**: データベースに既に存在するレコードのみを更新します。
   * **[!UICONTROL Delete]**: データを削除します。
   >[!NOTE]
   >
   >この **[!UICONTROL Batch size]** フィールドでは、アップロードするデータの最大バッチサイズを定義できます。

1. タブで、データベース内のレコードを識別する方法を指定し **[!UICONTROL Identification]** ます。

   * **[!UICONTROL Using the targeting dimension]**: を選択 **[!UICONTROL Dimension to update]** し、を指定し **[!UICONTROL Keys for finding records]**&#x200B;ます。 詳しくは、 [ターゲティングディメンションとリソースを参照してください](../../automating/using/query.md#targeting-dimensions-and-resources)。
   * 入力したデータが既存のターゲティングディメンションと一致する場合は、この **[!UICONTROL Using one or more links]** オプションを選択します。 次に、を選択し **[!UICONTROL Dimension to update]**&#x200B;ます。
   選択した操作タイプに更新が必要な場合は、紐付けキーを使用する必要があります。

1. タブで、更新を適用するフィールドを指定し、必要に応じて条件を追加して、更新を実行します。 **[!UICONTROL Fields to update]** これを行うには、 **[!UICONTROL Taken into account if]** 列を使用します。 条件はリスト順に順番に適用されます。 右側の矢印を使用して、更新の順序を変更します。 同じリンク先フィールドを複数回使用できます。

   この ![](assets/wkf_magic_wand-24px.png) ボタンを使用して、フィールドを自動的にリンクできます。 自動リンクでは、同じ名前のフィールドが検出されます。

   入力操作中に、各フィールドに適用する操作を個別に選択でき **[!UICONTROL Insert or update]** ます。 これを行うには、 **[!UICONTROL Operation]** 列で目的の値を選択します。

   >[!NOTE]
   >
   >**更新の管理** ：フィールドの設定がフィールド更新テーブルで明示的に行われない限り **[!UICONTROL lastModified]**、更新データアクティビティの実行時に、更新データ、お **[!UICONTROL modifiedBy]****[!UICONTROL created]****[!UICONTROL createdBy]** よびフィールドが自動的に更新されます。 更新は、少なくとも1つの違いが検出されたレコードに対してのみ行われます。 値が同じ場合は、更新は行われません。

1. 必要に応じて、アクティビティの [トランジションを管理し](../../automating/using/activity-properties.md) 、アウトバウンド母集団のアドバンスオプションにアクセスします。

   を選択した場合、インポートするデータ **[!UICONTROL Insert only]** に既にデータベースに存在するレコードが含まれている可能性がある場合は、このチェックボックスをオンにしてエラーを回避し **[!UICONTROL Generate an outbound transition for the rejects]** ます。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次のアクティビティは、 **[!UICONTROL Update data]** アクティビティ後の **[!UICONTROL Load file]** アクティビティの設定を示しています。 このワークフローの目的は、ファイルから回復したデータを使用して、Adobe Campaignデータベースにプロファイルを追加または更新することです。 使用する紐付けキーは、電子メールアドレスです。

読み込まれるファイルは、 **.txt** 形式のファイルで、次のデータ例が含まれています。

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

この **[!UICONTROL Update data]** アクティビティは次のように設定します。

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

