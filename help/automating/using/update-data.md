---
title: データ更新
description: 「データ更新」アクティビティを使用すると、データベース内のフィールドに対して一括更新を実行できます。
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d362563f-5ab3-4f7f-ae9f-a42b6f0bb2b9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 98%

---

# データの更新{#update-data}

## 説明 {#description}

![](assets/data_update.png)

「**[!UICONTROL Update data]**」アクティビティを使用すると、データベース内のフィールドに対して一括更新を実行できます。

## 使用状況 {#context-of-use}

「**データ更新**」アクティビティは、ファイルのインポート後に使用して、復元されたデータを Adobe Campaign データベースに挿入できます。いくつかのオプションを使用して、データ更新をパーソナライズできます。

**関連トピック：**

* [使用例：ファイルに基づくデータの更新](../../automating/using/update-database-file.md)
* [ファイルの自動ダウンロードに基づくデータの更新](../../automating/using/update-data-automatic-download.md)

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Update data]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 実行する「**[!UICONTROL Operation type]**」を次のいずれかに指定します。

   * **[!UICONTROL Insert or update]**：データを挿入するか、データベースに既にレコードが存在する場合は更新します。
   * **[!UICONTROL Insert only]**：データのみ挿入します。既に存在するレコードは更新されません。紐付け条件が定義されている場合は、紐付けされていないレコードのみ追加されます。

      インポートしたデータに、データベースに既に存在する特定のレコードが含まれている場合は、「**[!UICONTROL Generate an outbound transition for rejects]**」チェックボックスをオンにして、起こり得るエラーを回避します。

   * **[!UICONTROL Update]**：データベースに既に存在するレコードのみを更新します。
   * **[!UICONTROL Delete]**：データを削除します。

   >[!NOTE]
   >
   >「**[!UICONTROL Batch size]**」フィールドでは、アップロードするデータの最大バッチサイズを定義できます。

1. **[!UICONTROL Identification]**&#x200B;タブで、データベース内のレコードを識別する方法を指定します。

   * **[!UICONTROL Using the targeting dimension]**：「**[!UICONTROL Dimension to update]**」を選択した後、「**[!UICONTROL Keys for finding records]**」を指定します。詳しくは、[ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)を参照してください。
   * 入力したデータが既存のターゲティングディメンションと一致する場合は、「**[!UICONTROL Using one or more links]**」オプションを選択します。次に、「**[!UICONTROL Dimension to update]**」を選択します。

   選択した操作タイプに更新が必要な場合は、紐付けキーを使用する必要があります。

1. 「**[!UICONTROL Fields to update]**」タブで、更新を適用するフィールドを指定し、必要に応じて条件を追加して、更新を実行します。それには、「**[!UICONTROL Taken into account if]**」列を使用します。条件はリスト順に順番に適用されます。更新の順序を変更するには、右側の矢印を使用します。同じ宛先フィールドを何度も使用できます。

   「![](assets/wkf_magic_wand-24px.png)」ボタンを使用すると、フィールドを自動的にリンクできます。自動リンクでは、同じ名前のフィールドが検出されます。

   「**[!UICONTROL Insert or update]**」タイプの操作時に、各フィールドに適用する操作を個別に選択できます。それには、「**[!UICONTROL Operation]**」列で目的の値を選択します。

   >[!NOTE]
   >
   >**更新の管理**：「**[!UICONTROL lastModified]**」、「**[!UICONTROL modifiedBy]**」、「**[!UICONTROL created]**」および「**[!UICONTROL createdBy]**」フィールドの設定がフィールド更新テーブルで明示的に実行されていない限り、「データ更新」アクティビティが実行されると、これらのフィールドが自動的に更新されます。更新は、少なくとも 1 つの差異が検出されたレコードに対してのみ実行されます。すべての値が同じ場合は、更新はおこなわれません。

1. 必要に応じて、アクティビティの[トランジション](../../automating/using/activity-properties.md)を管理して、アウトバウンド母集団の詳細設定オプションにアクセスします。

   「**[!UICONTROL Insert only]**」を選択した場合、インポートしたデータに、既にデータベースに存在するレコードが含まれている可能性がある場合は、「**[!UICONTROL Generate an outbound transition for the rejects]**」チェックボックスをオンにして、起こり得るエラーを回避します。

1. アクティビティの設定を確認し、ワークフローを保存します。
