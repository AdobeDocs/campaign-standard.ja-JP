---
title: カスタムプロファイルディメンションの作成
description: カスタムプロファイルデータに基づいてカスタムプロファイルディメンションを作成する方法を説明します。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---

# カスタムプロファイルディメンションの作成{#creating-a-custom-profile-dimension}

また、プロファイルのカスタムリソース拡張中に作成されたカスタムプロファイルデータに基づいて、レポートの作成と管理をおこなうこともできます。

この例では、カスタムプロファイルフィールドを作成します。 **ロイヤルティプログラム** それは金、銀、青銅の 3 つのレベルに分けられます。 次に、このカスタムプロファイルは、動的レポートでカスタムプロファイルディメンションとして使用できるように拡張されます。

* [手順 1：新しいプロファイルフィールドを作成する](#step-1--create-a-new-profile-field)
* [手順 2：プロファイルフィールドを使用して送信ログを拡張する](#step-2--extend-the-sending-logs-with-the-profile-field)
* [手順 3：ロイヤルティプログラムに登録された受信者をターゲティングした配信を作成します](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [手順 4：動的レポートを作成して、カスタムプロファイルディメンションで受信者をフィルターします](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## 手順 1：新しいプロファイルフィールドを作成する {#step-1--create-a-new-profile-field}

最初に、新しいプロファイルフィールドを作成する必要があります **ロイヤルティプログラム** これにより、受信者にロイヤルティレベル（ゴールド、シルバー、ブロンズ）が割り当てられます。

>[!NOTE]
>
>カスタムリソースは管理者のみが管理できます。

それには、次の手順に従います。

1. 詳細設定メニューから、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** その後、 **[!UICONTROL Profile (profile)]** カスタムリソース。

   ![](assets/custom_profile_1.png)

1. 次から： **[!UICONTROL Data structure]** タブ、 **[!UICONTROL Fields]** カテゴリの **[!UICONTROL Add field]** 」ボタンをクリックします。

   ![](assets/custom_profile_2.png)

1. 次を入力します。 **[!UICONTROL Label]**, **[!UICONTROL ID]** カスタムリソースを選択します。 **[!UICONTROL Type]**. ここでは、 **[!UICONTROL Text]** 受信者は金、銀、青銅から選択できるので

   ![](assets/custom_profile_3.png)

1. 次をクリック： ![](assets/custom_profile_22.png) アイコンを使用してフィールドを定義します。

   ![](assets/custom_profile_12.png)

1. ここでは、 **[!UICONTROL Specify a list of authorized valued]** をクリックして、各値を作成します。 **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. 次を入力します。 **[!UICONTROL Label]** および **[!UICONTROL Value]** 次に、「 **[!UICONTROL Add]**. この例では、値 gold、silver、bronze を作成する必要があります。 クリック **[!UICONTROL Confirm]** 完了したら、

   ![](assets/custom_profile_14.png)

1. 「**[!UICONTROL Screen definition]**」タブを選択します。Adobe Analytics の **[!UICONTROL Detail screen configuration]** ドロップダウン、チェック **[!UICONTROL Add personalized fields]** セクションを開いて、プロファイルに新しいセクションを作成します。

   ![](assets/custom_profile_4.png)

1. 次をクリック： **[!UICONTROL Add an element]** ボタンをクリックして、新しいセクションを作成します。 を選択します。 **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** または **[!UICONTROL List]**&#x200B;を選択し、この新しいセクションに追加するフィールドを選択します。

   ![](assets/custom_profile_5.png)

1. また、「 」フィールドでセクションにタイトルを追加することもできます **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   クリック **[!UICONTROL Save]** 設定が完了したとき。

   ![](assets/custom_profile_6.png)

1. 詳細設定メニューから、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** をクリックして、カスタムリソースの公開を開始します。
1. クリック **[!UICONTROL Prepare publication]** 準備が完了したら、 **[!UICONTROL Publish]** 」ボタンをクリックします。

   ![](assets/custom_profile_7.png)

これで、新しいプロファイルフィールドを使用して、受信者が選択できる状態になりました。

![](assets/custom_profile_8.png)

## 手順 2：プロファイルフィールドを使用して送信ログを拡張する {#step-2--extend-the-sending-logs-with-the-profile-field}

これで、プロファイルフィールドが作成されたので、送信ログをプロファイルフィールドで拡張して、動的レポートで関連するカスタムプロファイルディメンションを作成する必要があります。

プロファイルフィールドを使用してログを拡張する前に、PII ウィンドウが **[!UICONTROL Sending logs extension]** タブをクリックします。 詳しくは、この[ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)を参照してください。

>[!NOTE]
>
>ログは、管理者がプロファイルフィールドでのみ拡張できます。

1. 詳細設定メニューから、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** その後、 **[!UICONTROL Profile (profile)]** カスタムリソース。
1. を開きます。 **[!UICONTROL Sending logs extension]** 」ドロップダウンリストから選択できます。
1. 「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/custom_profile_9.png)

1. 以前に作成したフィールドを選択し、「 **[!UICONTROL Confirm]**.
1. チェック **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** をクリックして、カスタムプロファイルディメンションを作成します。

   ![](assets/custom_profile_10.png)

   このオプションは、PII ウィンドウが受け入れられた場合にのみ使用できます。 詳しくは、この[ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)を参照してください。

1. クリック **[!UICONTROL Add]** 次に、カスタムリソースを保存します。
1. カスタムリソースは変更されたので、新しい変更を実装するにはパブリッシュする必要があります。

   詳細設定メニューから、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** をクリックして、カスタムリソースの公開を開始します。

1. クリック **[!UICONTROL Prepare publication]** 準備が完了したら、 **[!UICONTROL Publish]** 」ボタンをクリックします。

   ![](assets/custom_profile_7.png)

これで、カスタムプロファイルが、レポートでカスタムプロファイルディメンションとして使用できるようになりました。

これで、フィールドが作成され、送信ログがこのプロファイルフィールドを使用して拡張されたので、配信で受信者のターゲティングを開始できます。

## 手順 3：ロイヤルティプログラムに登録された受信者をターゲティングした配信を作成します {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

プロファイルフィールドが公開されたら、配信を開始できます。 この例では、ロイヤリティープログラムに登録されたすべての受信者をターゲットにします。

1. 「**[!UICONTROL Marketing activities]**」タブで「**[!UICONTROL Create]**」をクリックし、「**[!UICONTROL Email]**」を選択します。
1. を選択します。 **[!UICONTROL Email type]** 次に、電子メールのプロパティを入力します。
1. ロイヤリティープログラムに登録された受信者をターゲットにするには、 **[!UICONTROL Profiles (attributes)]** アクティビティ。
1. 以前に作成したフィールドを **[!UICONTROL Field]** 」ドロップダウンリストから選択できます。

   ![](assets/custom_profile_16.png)

1. を選択します。 **[!UICONTROL Filter conditions]**. ここでは、3 つのロイヤリティープログラムのレベルの 1 つに属する受信者をターゲットにします。

   ![](assets/custom_profile_17.png)

1. クリック **[!UICONTROL Confirm]** 次に、フィルタリングが完了したら、「 **[!UICONTROL Next]**.
1. メッセージの内容、送信者名、件名を定義し、パーソナライズします。 E メール作成について詳しくは、 [ページ](../../designing/using/designing-content-in-adobe-campaign.md).

   次に、「 **[!UICONTROL Create]**.

1. 準備が整ったら、メッセージをプレビューして送信できます。 メッセージの準備と送信の方法について詳しくは、次を参照してください。 [ページ](../../sending/using/preparing-the-send.md).

選択した受信者に E メールが正しく送信されたら、データのフィルタリングを開始し、レポートを使用して配信の成功をトラッキングできます。

## 手順 4：動的レポートを作成して、カスタムプロファイルディメンションで受信者をフィルターします {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

配信を送信した後、 **[!UICONTROL Profile]** 表。

1. 次から： **[!UICONTROL Reports]** 」タブで、標準のレポートを選択するか、 **[!UICONTROL Create]** ボタンをクリックして、一から開始します。

   ![](assets/custom_profile_18.png)

1. Adobe Analytics の **[!UICONTROL Dimensions]** カテゴリ、クリック **[!UICONTROL Profile]** 次に、カスタムをドラッグ&amp;ドロップします **ロイヤルティプログラム** プロファイルディメンションをフリーフォームテーブルに追加します。

   ![](assets/custom_profile_19.png)

1. 次をドラッグ&amp;ドロップ： **[!UICONTROL Processed/Sent]** および **[!UICONTROL Open]** 指標を使用して、データのフィルタリングを開始します。

   ![](assets/custom_profile_20.png)

1. 必要に応じて、ワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/custom_profile_21.png)

**関連トピック：**

* [カスタムプロファイルデータを使用した洞察に富んだレポートの作成](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
