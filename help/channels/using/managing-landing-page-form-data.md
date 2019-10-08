---
title: ランディングページフォームデータの管理
seo-title: ランディングページフォームデータの管理
description: ランディングページフォームデータの管理
seo-description: ランディングページのフォームデータを管理する方法を説明します。
page-status-flag: 非活性化の
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: レメイト
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ランディングページ
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9cdfafad7a2ac2db59b037962a84aa03568a55e6

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

## サービスへのフォームのリンク {#linking-a-form-to-a-service}

フォームをサービスにリンクして、ランディングページを検証する際にプロファイルが特定のサービスに登録できるようにすることができます。

ランディングページをリンクするパラメーターを使用すると、実行するアクションのタイプと、ランディングページが単一のサービスに具体的にリンクされているか、汎用であるかを指定できます。

リンクするサービスを選択するには、次の操作を行う必要があります。

1. ランディングページのダッシュボードのアイコンを使用し ![](assets/edit_darkgrey-24px.png) てアクセスしたランディングページのプロパティを編集し、パラメータを表示 **[!UICONTROL Job]** します。

   ![](assets/lp_edit_properties_button.png)

1. ドロッ **[!UICONTROL Subscription]** プダウンリスト **[!UICONTROL Specific actions]** からを選択します。

   ![](assets/lp_parameters_5.png)

1. ランディング **[!UICONTROL Specific service]** ページを単一のサービスにリンクする場合に選択します。 ランディングページで複数のサービスを使用する場合は、このオプションを選択しないでください。

   このオプション **[!UICONTROL Specified service in the URL]** を使用して、ランディングページを複数のサービスで使用できるようにします。 したがって、サービスを設定する際は、ランディングページを参照する必要があります。

## データの保存と調整{#data-storage-and-reconciliation}

データ調整パラメーターを使用すると、ランディングページに入力したデータがユーザーによって送信された後の管理方法を定義できます。

手順は次のとおりです。

1. ランディングページのダッシュボードのアイコンを使用し ![](assets/edit_darkgrey-24px.png) てアクセスしたランディングページのプロパティを編集し、パラメータを表示 **[!UICONTROL Job]** します。

   ![](assets/lp_parameters_4.png)

1. 以下を選択しま **[!UICONTROL Reconciliation key]**&#x200B;す。次のデータベース・フィールド(例：電子メール、名、姓)は、Adobe Campaignデータベースに既に存在するプロファイルが訪問者に存在するかどうかを判断するために使用されます。 これにより、定義された更新方法パラメーターに従って、プロファイルを更新または作成できます。
1. 次を定義しま **[!UICONTROL Form parameter mapping]**&#x200B;す。このセクションでは、ランディングページのフィールドパラメーターと、調整キーで使用されるパラメーターをマップできます。
1. 以下を選択しま **[!UICONTROL Update strategy]**&#x200B;す。調整キーが既存のデータベースプロファイルを回復した場合は、フォームに入力されたデータを使用してこのプロファイルを更新するか、この更新を行わないかを選択できます。
