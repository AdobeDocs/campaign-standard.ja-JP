---
solution: Campaign Standard
product: campaign
title: カスタムプロファイルディメンションの作成
description: カスタムプロファイルデータに基づいてカスタムプロファイルディメンションを作成する方法を説明します。
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---


# カスタムプロファイルディメンションの作成{#creating-a-custom-profile-dimension}

また、プロファイルのカスタムリソース拡張で作成されたカスタムプロファイルデータに基づいて、レポートの作成や管理を行うこともできます。

この例では、3つのレベルに分けられるカスタムプロファイルフィールド **忠誠度プログラム** (Loyalty Expers)を作成します。金、銀、青銅。 その後、このカスタムプロファイルを拡張して、動的レポートでカスタムプロファイルディメンションとして使用できるようにします。

* [手順1:新しいプロファイルフィールドの作成](#step-1--create-a-new-profile-field)
* [手順2:プロファイルフィールドを使用して送信ログを拡張する](#step-2--extend-the-sending-logs-with-the-profile-field)
* [手順3:忠誠度プログラムに登録されている配信をターゲットにする受信者の作成](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [手順4:カスタムプロファイルディメンションを使用して受信者をフィルターする動的レポートの作成](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 手順1:新しいプロファイルフィールドの作成 {#step-1--create-a-new-profile-field}

まず、受信者に忠誠度レベルを割り当てる新しいプロファイルフィールド **忠誠度プログラム** を作成する必要があります。金、銀、青銅。

>[!NOTE]
>
>カスタムリソースは管理者のみが管理できます。

それには、次の手順に従います。

1. 詳細設定メニューで、/ **[!UICONTROL Administration]** /カスタムリソース **[!UICONTROL Development]** を選択し **[!UICONTROL Custom resources]****[!UICONTROL Profile (profile)]** ます。

   ![](assets/custom_profile_1.png)

1. タブの **[!UICONTROL Data structure]** カテゴリで、 **[!UICONTROL Fields]****[!UICONTROL Add field]** ボタンをクリックします。

   ![](assets/custom_profile_2.png)

1. を入力し **[!UICONTROL Label]**、カスタムリソース **[!UICONTROL ID]** を選択し **[!UICONTROL Type]**&#x200B;ます。 ここでは、受信者が金、銀、青銅のどちらを選ぶか **[!UICONTROL Text]** を選ぶので、私たちは選んだ。

   ![](assets/custom_profile_3.png)

1. アイコンをクリックして、フィールドを定義します。 ![](assets/custom_profile_22.png)

   ![](assets/custom_profile_12.png)

1. ここでは、をクリックして、承認された値を確認し **[!UICONTROL Specify a list of authorized valued]** 、各値を作成する必要があり **[!UICONTROL Create element]**&#x200B;ます。

   ![](assets/custom_profile_13.png)

1. を入力 **[!UICONTROL Label]** し、を **[!UICONTROL Value]** クリックし **[!UICONTROL Add]**&#x200B;ます。 この例では、値gold、silver、bronzeを作成する必要があります。 Click **[!UICONTROL Confirm]** when done.

   ![](assets/custom_profile_14.png)

1. 「**[!UICONTROL Screen definition]**」タブを選択します。ドロップダウンで、セクションをチェックして、プロファイルに新しいセクションを作成し **[!UICONTROL Detail screen configuration]****[!UICONTROL Add personalized fields]** ます。

   ![](assets/custom_profile_4.png)

1. ボタンをクリックして、新しいセクションを作成し **[!UICONTROL Add an element]** ます。 以下を選択し **[!UICONTROL Type]**&#x200B;ます。 **[!UICONTROL Input field]**、 **[!UICONTROL Value]** または、 **[!UICONTROL List]**&#x200B;を使用して、この新しいセクションに追加するフィールドを選択します。

   ![](assets/custom_profile_5.png)

1. フィールド内のセクションにタイトルを追加することもでき **[!UICONTROL Customize the title of the section where the fields will be displayed]**&#x200B;ます。

   設定が完了 **[!UICONTROL Save]** したら、をクリックします。

   ![](assets/custom_profile_6.png)

1. 詳細設定メニューで、/ **[!UICONTROL Administration]****[!UICONTROL Development]** /カスタムリソースの公開 **[!UICONTROL Publication]** 開始を選択します。
1. 準備が完了 **[!UICONTROL Prepare publication]** したら、をクリックし、 **[!UICONTROL Publish]** ボタンをクリックします。

   ![](assets/custom_profile_7.png)

これで、新しいプロファイルフィールドを使用し、受信者が選択できる状態になります。

![](assets/custom_profile_8.png)

## 手順2:プロファイルフィールドを使用して送信ログを拡張する {#step-2--extend-the-sending-logs-with-the-profile-field}

プロファイルフィールドが作成されたら、送信ログをプロファイルフィールドと共に拡張し、動的レポートで関連付けられたカスタムプロファイルディメンションを作成する必要があります。

プロファイルフィールドでログを拡張する前に、PIIウィンドウが **[!UICONTROL Sending logs extension]** タブへのアクセス権を持つように許可されていることを確認してください。 詳しくは、この[ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)を参照してください。

>[!NOTE]
>
>ログは、管理者がプロファイルフィールドを使用してのみ拡張できます。

1. 詳細設定メニューで、/ **[!UICONTROL Administration]** /カスタムリソース **[!UICONTROL Development]** を選択し **[!UICONTROL Custom resources]****[!UICONTROL Profile (profile)]** ます。
1. ドロップダウンを開 **[!UICONTROL Sending logs extension]** きます。
1. 「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/custom_profile_9.png)

1. Select your previously created field and click **[!UICONTROL Confirm]**.
1. カスタムプロファイルディメンション **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** を作成する場合にオンにします。

   ![](assets/custom_profile_10.png)

   このオプションは、PIIウィンドウが受け入れられた場合にのみ使用できます。 詳しくは、この[ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)を参照してください。

1. をクリック **[!UICONTROL Add]** して、カスタムリソースを保存します。
1. カスタムリソースが変更されたので、それを発行して新しい変更を実装する必要があります。

   詳細設定メニューで、/ **[!UICONTROL Administration]****[!UICONTROL Development]** /カスタムリソースの公開 **[!UICONTROL Publication]** 開始を選択します。

1. 準備が完了 **[!UICONTROL Prepare publication]** したら、をクリックし、 **[!UICONTROL Publish]** ボタンをクリックします。

   ![](assets/custom_profile_7.png)

これで、カスタムプロファイルが、レポートでカスタムプロファイルディメンションとして使用できるようになります。

フィールドが作成され、送信ログがこのプロファイルフィールドで拡張されたので、配信で開始のターゲット設定受信者を使用できます。

## 手順3:忠誠度プログラムに登録されている配信をターゲットにする受信者の作成 {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

プロファイルフィールドが公開されると、配信を開始できます。 この例では、忠誠度プログラムに登録されているすべての受信者をターゲットします。

1. 「**[!UICONTROL Marketing activities]**」タブで「**[!UICONTROL Create]**」をクリックし、「**[!UICONTROL Email]**」を選択します。
1. を選択 **[!UICONTROL Email type]** し、電子メールのプロパティを入力します。
1. 忠誠度プログラムに登録されているターゲット受信者に対して、 **[!UICONTROL Profiles (attributes)]** アクティビティをドラッグ&amp;ドロップします。
1. 以前に作成したフィールドをドロップダウンから選択 **[!UICONTROL Field]** します。

   ![](assets/custom_profile_16.png)

1. を選択し **[!UICONTROL Filter conditions]**&#x200B;ます。 ここでは、3つの忠誠度プログラムのレベルの1つに含まれる受信者をターゲットします。

   ![](assets/custom_profile_17.png)

1. フィルターが完了 **[!UICONTROL Confirm]** したら、「次へ」をクリックし、をクリックし **[!UICONTROL Next]**&#x200B;ます。
1. メッセージの内容、送信者名、件名を定義してパーソナライズします。 For more information on email creation refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

   Then, click **[!UICONTROL Create]**.

1. 準備が整ったら、プレビューしてメッセージを送信できます。 メッセージの準備と送信の方法の詳細については、この [ページを参照してください](../../sending/using/preparing-the-send.md)。

選択した受信者に電子メールが正しく送信されたら、開始によるデータのフィルタリングを行い、レポートを使用して配信の成功を追跡できます。

## 手順4:カスタムプロファイルディメンションを使用して受信者をフィルターする動的レポートの作成 {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

配信を送信した後、表のカスタムプロファイルディメンションを使用してレポートを分類でき **[!UICONTROL Profile]** ます。

1. タブからあらかじめ用意されているレポートを選択するか、 **[!UICONTROL Reports]** ボタンをクリックしてレポートを最初から開始 **[!UICONTROL Create]** します。

   ![](assets/custom_profile_18.png)

1. カテゴリで、をクリック **[!UICONTROL Dimensions]** して、カスタムの **[!UICONTROL Profile]** 忠誠度プログラム **** プロファイルディメンションをフリーフォームテーブルにドラッグ&amp;ドロップします。

   ![](assets/custom_profile_19.png)

1. データのフィルタリングを行う開始に、 **[!UICONTROL Processed/Sent]** および **[!UICONTROL Open]** 指標をドラッグ&amp;ドロップします。

   ![](assets/custom_profile_20.png)

1. 必要に応じて、ワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/custom_profile_21.png)

**関連トピック：**

* [カスタムプロファイルデータを使用した洞察に富んだレポートの作成](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
