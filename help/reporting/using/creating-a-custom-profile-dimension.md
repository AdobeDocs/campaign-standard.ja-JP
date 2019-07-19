---
title: カスタムプロファイルディメンションの作成
seo-title: カスタムプロファイルディメンションの作成
description: カスタムプロファイルディメンションの作成
seo-description: カスタムプロファイルデータに基づいてカスタムプロファイルディメンションを作成する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: カスタマイズ-レポート
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e9a4d99ddf311898c48b2b352fa13f5b59ed1fbe

---


# Creating a custom profile dimension{#creating-a-custom-profile-dimension}

また、カスタムプロファイルのカスタム拡張機能で作成されたカスタムプロファイルデータに基づいて作成および管理することもできます。

In this example, we want to create the custom profile field **Loyalty programs** which will be divided into three levels: gold, silver and bronze. このカスタムプロファイルは、動的レポートのカスタムプロファイルディメンションとして使用できるように拡張されます。

* [手順1:新しいプロファイルフィールドの作成](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [手順2:プロファイルフィールドを使用した送信ログの拡張](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [手順3:ロイヤルティプログラムに登録されている配信ターゲット受信者の作成](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [手順4:カスタムプロファイルディメンションを使用して受信者をフィルターする動的レポートを作成します](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Step 1: Create a new profile field {#step-1--create-a-new-profile-field}

We first need to create the new profile field **Loyalty program** that will assign loyalty level to our recipients: gold, silver or bronze.

>[!NOTE]
>
>カスタムリソースは管理者のみが管理できます。

そのためには、次の手順を実行します。

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** then the **[!UICONTROL Profile (profile)]** custom resource.

   ![](assets/custom_profile_1.png)

1. **[!UICONTROL Data structure]** タブの **[!UICONTROL Fields]** カテゴリで、ボタンを **[!UICONTROL Add field]** クリックします。

   ![](assets/custom_profile_2.png)

1. Enter the **[!UICONTROL Label]**, **[!UICONTROL ID]** and select the custom resource **[!UICONTROL Type]**. Here, we selected **[!UICONTROL Text]** since recipients will have the choice between gold, silver and bronze.

   ![](assets/custom_profile_3.png)

1. ![](assets/custom_profile_22.png) アイコンをクリックして、フィールドを定義します。

   ![](assets/custom_profile_12.png)

1. Here, we need to specify the authorized values by checking **[!UICONTROL Specify a list of authorized valued]** and create each value by clicking **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Enter the **[!UICONTROL Label]** and **[!UICONTROL Value]** then click **[!UICONTROL Add]**. この例では、ゴールド、シルバー、ブロンズの値を作成する必要があります。Click **[!UICONTROL Confirm]** when done.

   ![](assets/custom_profile_14.png)

1. **[!UICONTROL Screen definition]** タブを選択します。**[!UICONTROL Detail screen configuration]** ドロップダウンで **[!UICONTROL Add personalized fields]** 、プロファイルに新しいセクションを作成します。

   ![](assets/custom_profile_4.png)

1. Click the **[!UICONTROL Add an element]** button to create your new section. Select the **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** or **[!UICONTROL List]**, then the field to add in this new section.

   ![](assets/custom_profile_5.png)

1. You can also add a title to your section in the field **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Click **[!UICONTROL Save]** when the configuration is done.

   ![](assets/custom_profile_6.png)

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** to start publishing your custom resource.
1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button.

   ![](assets/custom_profile_7.png)

新しいプロファイルフィールドを受信者によって使用および選択できるようになりました。

![](assets/custom_profile_8.png)

## Step 2: Extend the sending logs with the profile field {#step-2--extend-the-sending-logs-with-the-profile-field}

プロファイルフィールドが作成されたら、プロファイルフィールドと共に送信ログを拡張して、動的レポートに関連付けられたカスタムプロファイルディメンションを作成する必要があります。

Before extending the log with our profile field, make sure that the PII window was accepted to have access to the **[!UICONTROL Sending logs extension]** tab. For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>ログは、管理者がプロファイルフィールドを使用してのみ拡張できます。

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** then the **[!UICONTROL Profile (profile)]** custom resource.
1. **[!UICONTROL Sending logs extension]** ドロップダウンを開きます。
1. Click the **[!UICONTROL Create element]** button.

   ![](assets/custom_profile_9.png)

1. Select your previously created field and click **[!UICONTROL Confirm]**.
1. Check **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** to create your custom profile dimension.

   ![](assets/custom_profile_10.png)

   このオプションは、PIIウィンドウが受け入れられた場合にのみ使用できます。For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Click **[!UICONTROL Add]** then save your custom resource.
1. カスタムリソースは変更されたので、新しい変更を実装するには公開する必要があります。

   From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** to start publishing your custom resource.

1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button.

   ![](assets/custom_profile_7.png)

カスタムプロファイルがレポート内のカスタムプロファイルディメンションとして使用できるようになりました。

これで、フィールドが作成され、ログの送信がこのプロファイルフィールドによって拡張されたので、配信中にターゲットを設定することができます。

## Step 3: Create a delivery targeting recipients enrolled in the loyalty program {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

プロファイルフィールドが公開されたら、配信を開始できます。この例では、ロイヤルティプログラムに登録されているすべての受信者をターゲットにします。

1. **[!UICONTROL Marketing activities]** タブから、をクリック **[!UICONTROL Create]****[!UICONTROL Email]**&#x200B;します。
1. Choose an **[!UICONTROL Email type]** then enter your email's properties.
1. To target recipient enrolled in the loyalty program, drag and drop the **[!UICONTROL Profiles (attributes)]** activity.
1. **[!UICONTROL Field]** ドロップダウンから前に作成したフィールドを選択します。

   ![](assets/custom_profile_16.png)

1. Select your **[!UICONTROL Filter conditions]**. ここでは、3つの忠誠プログラムのレベルの一部である受信者をターゲットにします。

   ![](assets/custom_profile_17.png)

1. Click **[!UICONTROL Confirm]** then when done filtering, click **[!UICONTROL Next]**.
1. メッセージコンテンツ、送信者名および件名を定義してパーソナライズします。For more information on email creation refer to this [page](../../designing/using/about-email-content-design.md#about-the-email-designer).

   Then, click **[!UICONTROL Create]**.

1. 準備ができたら、メッセージをプレビューして送信できます。For more information on how to prepare and send your message, refer to this [page](../../sending/using/preparing-the-send.md).

選択した受信者に電子メールが正しく送信されると、データのフィルタを開始し、レポートで配信の成功を追跡できます。

## Step 4: Create a dynamic report to filter recipients with the custom profile dimension {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

After sending your delivery, you can breakdown reports using your custom profile dimension from the **[!UICONTROL Profile]** table.

1. From the **[!UICONTROL Reports]** tab, select an out-of-the-box report or click the **[!UICONTROL Create]** button to start one from scratch.

   ![](assets/custom_profile_18.png)

1. **[!UICONTROL Dimensions]** カテゴリで、 **[!UICONTROL Profile]** カスタム **ロイヤルティプログラム** プロファイルディメンションをクリックしてフリーフォームテーブルにドロップ&amp;ドロップします。

   ![](assets/custom_profile_19.png)

1. Drag and drop the **[!UICONTROL Processed/Sent]** and **[!UICONTROL Open]** metrics to start filtering your data.

   ![](assets/custom_profile_20.png)

1. 必要に応じてワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/custom_profile_21.png)

