---
title: カスタムプロファイルディメンションの作成
seo-title: カスタムプロファイルディメンションの作成
description: カスタムプロファイルディメンションの作成
seo-description: カスタムプロファイルデータに基づいてカスタムプロファイルディメンションを作成する方法について説明します。
page-status-flag: 非活性化の
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: レポートのカスタマイズ
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# カスタムプロファイルディメンションの作成{#creating-a-custom-profile-dimension}

また、プロファイルのカスタムリソース拡張時に作成されたカスタムプロファイルデータに基づいて、レポートを作成および管理することもできます。

この例では、次の3つのレベルに分けられるカスタムプロファイル **フィールド** 「忠誠度プログラム」を作成します。金、銀、青銅。 その後、このカスタムプロファイルが拡張され、動的レポートでカスタムプロファイルディメンションとして使用できるようになります。

* [手順1:新しいプロファイルフィールドの作成](#step-1--create-a-new-profile-field)
* [手順2:プロファイルフィールドを使用して送信ログを拡張する](#step-2--extend-the-sending-logs-with-the-profile-field)
* [手順3:忠誠度プログラムに登録した受信者をターゲットとする配信の作成](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [手順4:動的レポートを作成して、カスタムプロファイルディメンションで受信者をフィルターします](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 手順1:新しいプロファイルフィールドの作成 {#step-1--create-a-new-profile-field}

まず、受信者に忠誠度レベルを割り当てる新しいプロフ **ァイルフィールド** 「忠誠度」プログラムを作成する必要があります。金、銀、青銅。

>[!NOTE]
>
>カスタムリソースは管理者のみが管理できます。

これをおこなうには：

1. 詳細メニューで、//カスタム **[!UICONTROL Administration]** リソース **[!UICONTROL Development]** を選 **[!UICONTROL Custom resources]** 択し **[!UICONTROL Profile (profile)]** ます。

   ![](assets/custom_profile_1.png)

1. タブのカ **[!UICONTROL Data structure]** テゴリで、ボ **[!UICONTROL Fields]** タンをクリックし **[!UICONTROL Add field]** ます。

   ![](assets/custom_profile_2.png)

1. と入力し、 **[!UICONTROL Label]**&#x200B;カスタ **[!UICONTROL ID]** ムリソースを選択しま **[!UICONTROL Type]**&#x200B;す。 ここでは、受け手が金、 **[!UICONTROL Text]** 銀、青銅のどちらを選ぶかを選ぶので選びました。

   ![](assets/custom_profile_3.png)

1. アイコンをクリ ![](assets/custom_profile_22.png) ックして、フィールドを定義します。

   ![](assets/custom_profile_12.png)

1. ここでは、承認された値を確認して指定し、をクリックして各 **[!UICONTROL Specify a list of authorized valued]** 値を作成する必要がありま **[!UICONTROL Create element]**&#x200B;す。

   ![](assets/custom_profile_13.png)

1. を入力し、を **[!UICONTROL Label]** クリッ **[!UICONTROL Value]** クしま **[!UICONTROL Add]**&#x200B;す。 この例では、値gold、silver、bronzeを作成する必要があります。 完了したら、 **[!UICONTROL Confirm]** をクリックします。

   ![](assets/custom_profile_14.png)

1. Select the **[!UICONTROL Screen definition]** tab. ドロップダウ **[!UICONTROL Detail screen configuration]** ンで、セクションをチェ **[!UICONTROL Add personalized fields]** ックして、プロファイルに新しいセクションを作成します。

   ![](assets/custom_profile_4.png)

1. ボタンをクリ **[!UICONTROL Add an element]** ックして、新しいセクションを作成します。 以下を選択しま **[!UICONTROL Type]**&#x200B;す。また **[!UICONTROL Input field]**&#x200B;は、 **[!UICONTROL Value]****[!UICONTROL List]**&#x200B;を選択して、この新しいセクションに追加するフィールドを選択します。

   ![](assets/custom_profile_5.png)

1. フィールド内のセクションにタイトルを追加することもできま **[!UICONTROL Customize the title of the section where the fields will be displayed]**&#x200B;す。

   設定が **[!UICONTROL Save]** 完了したら、をクリックします。

   ![](assets/custom_profile_6.png)

1. 詳細メニューで//を選択し **[!UICONTROL Administration]** て、カス **[!UICONTROL Development]** タム **[!UICONTROL Publication]** リソースの公開を開始します。
1. 準備が **[!UICONTROL Prepare publication]** 完了したら、をクリックし、ボタンをクリック **[!UICONTROL Publish]** します。

   ![](assets/custom_profile_7.png)

これで、新しいプロファイルフィールドを使用し、受信者が選択できる状態になりました。

![](assets/custom_profile_8.png)

## 手順2:プロファイルフィールドを使用して送信ログを拡張する {#step-2--extend-the-sending-logs-with-the-profile-field}

プロファイルフィールドが作成されたら、送信ログをプロファイルフィールドと共に拡張し、動的レポートで関連付けられたカスタムプロファイルディメンションを作成する必要があります。

プロファイルフィールドを使用してログを拡張する前に、PIIウィンドウがタブへのアクセス権を持つことを確認してく **[!UICONTROL Sending logs extension]** ださい。 詳しくは、この[ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)を参照してください。

>[!NOTE]
>
>ログは、管理者がプロファイルフィールドを使用してのみ拡張できます。

1. 詳細メニューで、//カスタム **[!UICONTROL Administration]** リソース **[!UICONTROL Development]** を選 **[!UICONTROL Custom resources]** 択し **[!UICONTROL Profile (profile)]** ます。
1. ドロップダウ **[!UICONTROL Sending logs extension]** ンを開きます。
1. Click the **[!UICONTROL Create element]** button.

   ![](assets/custom_profile_9.png)

1. 以前に作成したフィールドを選択し、をクリックしま **[!UICONTROL Confirm]**&#x200B;す。
1. カスタムプ **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** ロファイルディメンションを作成する場合に選択します。

   ![](assets/custom_profile_10.png)

   このオプションは、PIIウィンドウが受け入れられた場合にのみ使用できます。 詳しくは、この[ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)を参照してください。

1. をクリック **[!UICONTROL Add]** して、カスタムリソースを保存します。
1. カスタムリソースが変更されたので、新しい変更を実装するには、そのリソースを発行する必要があります。

   詳細メニューで//を選択し **[!UICONTROL Administration]** て、カス **[!UICONTROL Development]** タム **[!UICONTROL Publication]** リソースの公開を開始します。

1. 準備が **[!UICONTROL Prepare publication]** 完了したら、をクリックし、ボタンをクリック **[!UICONTROL Publish]** します。

   ![](assets/custom_profile_7.png)

カスタムプロファイルが、レポートでカスタムプロファイルディメンションとして使用できるようになりました。

フィールドが作成され、このプロファイルフィールドを使用して送信ログが拡張されたので、配信で受信者をターゲット設定できます。

## 手順3:忠誠度プログラムに登録した受信者をターゲットとする配信の作成 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

プロファイルフィールドが公開されたら、配信を開始できます。 この例では、忠誠度プログラムに登録されているすべての受信者をターゲットにします。

1. タブでをク **[!UICONTROL Marketing activities]** リックし、を **[!UICONTROL Create]** 選択しま **[!UICONTROL Email]**&#x200B;す。
1. 電子メールのプ **[!UICONTROL Email type]** ロパティを選択し、入力します。
1. 忠誠度プログラムに登録された受信者をターゲットにするには、アクティビティをドラッグ&amp;ドロップ **[!UICONTROL Profiles (attributes)]** します。
1. 以前に作成したフィールドをドロップダ **[!UICONTROL Field]** ウンから選択します。

   ![](assets/custom_profile_16.png)

1. を選択しま **[!UICONTROL Filter conditions]**&#x200B;す。 ここでは、3つの忠誠度プログラムのレベルの1つに含まれる受信者をターゲットにします。

   ![](assets/custom_profile_17.png)

1. フィルタリ **[!UICONTROL Confirm]** ングが完了したら、をクリックし、をクリックしま **[!UICONTROL Next]**&#x200B;す。
1. メッセージの内容、送信者名、件名を定義してパーソナライズします。 For more information on email creation refer to this [page](../../designing/using/overview.md).

   次に、をクリックしま **[!UICONTROL Create]**&#x200B;す。

1. 準備が整ったら、メッセージをプレビューして送信できます。 メッセージの準備と送信の方法について詳しくは、このページを参照してく [ださい](../../sending/using/preparing-the-send.md)。

選択した受信者に電子メールが正しく送信されたら、データのフィルタリングを開始し、レポートを使用して配信の成功を追跡できます。

## 手順4:動的レポートを作成して、カスタムプロファイルディメンションで受信者をフィルターします {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

配信を送信した後、表のカスタムプロファイルディメンションを使用してレポートを分類で **[!UICONTROL Profile]** きます。

1. タブから **[!UICONTROL Reports]** あらかじめ用意されているレポートを選択するか、ボタンをクリックして **[!UICONTROL Create]** 最初からレポートを開始します。

   ![](assets/custom_profile_18.png)

1. カテゴリ内で、 **[!UICONTROL Dimensions]** をクリックし、カス **[!UICONTROL Profile]** タムの忠誠度プログラムプロファイルディメンションをフリ **** ーフォームテーブルにドラッグ&amp;ドロップします。

   ![](assets/custom_profile_19.png)

1. 指標と指標をドラッグ&amp;ドロ **[!UICONTROL Processed/Sent]** ップし **[!UICONTROL Open]** て、データのフィルタリングを開始します。

   ![](assets/custom_profile_20.png)

1. 必要に応じて、ワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/custom_profile_21.png)

**関連トピック：**

* [カスタムプロファイルデータを使用した洞察に富んだレポートの作成](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
