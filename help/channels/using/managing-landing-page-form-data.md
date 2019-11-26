---
title: ランディングページフォームデータの管理
description: ランディングページのフォームデータを管理する方法を説明します。
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
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# ランディングページフォームデータの管理{#managing-landing-page-form-data}

## ランディングページフォームデータプロパティの変更{#changing-a-landing-page-form-data-properties}

データベースフィールドは、入力ゾーン、ラジオボタンまたはチェックボックスタイプブロックにリンクできます。 これを行うには、ブロックを選択し、パレットにを **[!UICONTROL Form data]** 入力します。

![](assets/delivery_content_9.png)

* The **Field** input zone lets you select a database field to link with the form field.
* The **Mandatory** option lets you only authorize the page's submission if the user has filled in the field. 必須フィールドが入力されていない場合は、エラーメッセージが表示されます。

## フォームフィールドのマッピング {#mapping-form-fields}

入力フィールドは、Campaignデータベースにデータを保存または更新するために使用します。 この場合、データベースフィールドを入力ゾーン、ラジオボタンまたはチェックボックスタイプブロックにリンクする必要があります。 手順は次のとおりです。

1. ランディングページのブロックを選択します。
1. パレットのパ **[!UICONTROL Form data]** ーツを完成させます。

   ![](assets/editing_lp_content_4.png)

1. 選択ゾーンのフォームフィールドとリンクするデータベースフィールドを **[!UICONTROL Field]** 選択します。

   このオプション **[!UICONTROL Mandatory]** をオンにした場合、ページは、ユーザーがこのフィールドを完了した場合にのみ送信できます。 必須フィールドが未入力の場合は、ユーザーがページを検証するときにエラーメッセージが表示されます。

   >[!NOTE]
   >
   >ランディングページはプロファイルにのみマッピング **できます**。

1. フィールドの種類を定義するには、例えば、選択 **[!UICONTROL Text]**&#x200B;領域で、 **[!UICONTROL Number]**&#x200B;または **[!UICONTROL Date]** を選択 **[!UICONTROL HTML type of the field]** します。

>[!NOTE]
>
>組み込みのランディングページのデフォルトフィールドは事前に設定されています。 必要に応じて変更できます。

## データの保存と調整{#data-storage-and-reconciliation}

データ調整パラメーターを使用すると、ランディングページに入力したデータがユーザーによって送信された後の管理方法を定義できます。

手順は次のとおりです。

1. ランディングページのダッシュボードのアイコンを使用し ![](assets/edit_darkgrey-24px.png) てアクセスしたランディングページのプロパティを編集し、パラメータを表示 **[!UICONTROL Job]** します。

   ![](assets/lp_parameters_4.png)

1. 以下を選択しま **[!UICONTROL Reconciliation key]**&#x200B;す。次のデータベース・フィールド(例：電子メール、名、姓)は、Adobe Campaignデータベースに既に存在するプロファイルが訪問者に存在するかどうかを判断するために使用されます。 これにより、定義された更新方法パラメーターに従って、プロファイルを更新または作成できます。
1. 次を定義しま **[!UICONTROL Form parameter mapping]**&#x200B;す。このセクションでは、ランディングページのフィールドパラメーターと、調整キーで使用されるパラメーターをマップできます。
1. 以下を選択しま **[!UICONTROL Update strategy]**&#x200B;す。調整キーが既存のデータベースプロファイルを回復した場合は、フォームに入力されたデータを使用してこのプロファイルを更新するか、この更新を行わないかを選択できます。
