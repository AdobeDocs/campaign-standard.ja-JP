---
title: ランディングページフォームデータの管理
description: フォームデータのランディングページを管理する方法。
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8c24e048c698f7ad699e83a753c114fcfd25f6a0

---


# ランディングページフォームデータの管理{#managing-landing-page-form-data}

## フォームデータのランディングページプロパティの変更{#changing-a-landing-page-form-data-properties}

データベースフィールドは、入力ゾーン、ラジオボタン、チェックボックスタイプブロックにリンクできます。 これを行うには、ブロックを選択し、パレットにを **[!UICONTROL Form data]** 入力します。

![](assets/delivery_content_9.png)

* **Field** Inputゾーンを使用すると、フォームフィールドにリンクするデータベースフィールドを選択できます。
* The **Mandatory** option lets you only authorize the page&#39;s submission if the user has filled in the field. 必須フィールドが入力されていない場合は、エラーメッセージが表示されます。

## フォームフィールドのマッピング {#mapping-form-fields}

入力フィールドは、データベースにデータを格納または更新するキャンペーンです。 この場合、データベースフィールドを入力ゾーン、ラジオボタンまたはチェックボックスタイプブロックにリンクする必要があります。 手順は次のとおりです。

1. ブロックを選択します。ランディングページ内で
1. パレットのパ **[!UICONTROL Form data]** ーツを完成させます。

   ![](assets/editing_lp_content_4.png)

1. データベースフィールドを選択し、選択ゾーンのフォームフィールドとリン **[!UICONTROL Field]** クします。 ランディングページは **プロファイルとのみマップできます**。

1. 必要に応じて、このオ **[!UICONTROL Mandatory]** プションを選択します。 ページは、ユーザーがこのフィールドを完了した場合にのみ送信できます。 必須フィールドが未入力の場合は、ユーザーがページを検証する際にエラーメッセージが表示されます。

1. フィールドの種類を定義するには、例えば、 **[!UICONTROL Text]**&#x200B;または **[!UICONTROL Number]**&#x200B;選択領域 **[!UICONTROL Date]** でを選択 **[!UICONTROL HTML type of the field]** します。
必須を選択する場合は、そ **[!UICONTROL Checkbox]**&#x200B;のタイプであることを確認し **[!UICONTROL Field]** ます。

>[!NOTE]
>
>組み込みフィールドのデフォルトのランディングページは事前に設定されています。 必要に応じて変更できます。

## データのストレージと調整{#data-storage-and-reconciliation}

データ調整パラメーターを使用すると、ランディングページに入力されたデータを、ユーザーが送信した後で管理する方法を定義できます。

手順は次のとおりです。

1. アイコンを使用してアクセスするランディングページ ![](assets/edit_darkgrey-24px.png) のプロパティを編集し、ランディングページダッシュボードを表示 **[!UICONTROL Job]** します。

   ![](assets/lp_parameters_4.png)

1. 以下を選択しま **[!UICONTROL Reconciliation key]**&#x200B;す。これらのデータベースフィールド(例：電子メール、名、姓)は、訪問者に既知のプロファイルがあるかどうかを判断するために使用されます。 これにより、定義された更新方法のプロファイルに従って、戦略を更新または作成できます。
1. 次を定義しま **[!UICONTROL Form parameter mapping]**&#x200B;す。この節では、ランディングページフィールドパラメーターと、そのパラメーターで使用されるパラメーターをマッピングできます。紐付けキー
1. 以下を選択しま **[!UICONTROL Update strategy]**&#x200B;す。紐付けキーが既存のデータベースプロファイルを回復した場合は、このプロファイルをフォームに入力されたデータで更新するか、この更新を行わないかを選択できます。
