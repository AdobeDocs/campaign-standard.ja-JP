---
title: プロファイルリソースの新しいフィールドへの拡張
seo-title: プロファイルリソースの新しいフィールドへの拡張
description: プロファイルリソースの新しいフィールドへの拡張
seo-description: プロファイルリソースを拡張する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 9b99e95c-93ff-4187-90f7- db0baf5369ad
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: use- case——拡張リソース
discoiquuid: 1e0f8945- fc3c-46a9- a8e5- b181a1f5ffcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Extending the profile resource with a new field{#extending-the-profile-resource-with-a-new-field}

## About extending profiles {#about-extending-profiles}

この使用例では、プロファイルを拡張し、専用フィールドを使用してテストプロファイルを拡張します。

ここでは、ランディングページを使用してプロファイルを更新し、関心に特有のニュースレターを使用してプロファイルをターゲット化します。

そのためには、次の手順に従います。

* [手順1:プロファイルリソースの拡張](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource)
* [手順2:テストプロファイルの拡張](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-2--extend-the-test-profile)
* [手順3:カスタムリソースの公開](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-3--publish-your-custom-resource)
* [手順4:ワークフローを使用したプロファイルの更新とターゲット化](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-4--update-and-target-profiles-with-a-workflow)

次のフィールドがプロファイルに追加され、配信の対象となります。

![](assets/schema_extension_uc20.png)

関連トピック:

* [カスタムリソースについて](../../developing/using/data-model-concepts.md)
* [プロファイルの管理](../../audiences/using/about-profiles.md)
* [テストプロファイルの管理](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)

## Step 1: Extend the profile resource {#step-1--extend-the-profile-resource}

To create the new **Interest** field for our profiles, you first need to extend the out-of-the-box **[!UICONTROL Profiles (profile)]** resource.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. If you have not extended the **[!UICONTROL Profiles]** resource yet, click **[!UICONTROL Create]**.
1. **[!UICONTROL Extend an existing resource]** オプションを選択します。
1. **[!UICONTROL Profile (profile)]** リソースを選択します。
1. **[!UICONTROL Create]**&#x200B;をクリックします。

   ![](assets/schema_extension_uc5.png)

1. In the **[!UICONTROL Fields]** category of the **[!UICONTROL Data structure]** tab, click **[!UICONTROL Create element]**.

   >[!NOTE]
   >
   >Note that if you already extended the **[!UICONTROL Profile]** resource for previous purposes, you can start at this step by clicking **[!UICONTROL Add field]**.

   ![](assets/schema_extension_uc6.png)

1. Add a **[!UICONTROL Label]** and an **[!UICONTROL ID]**. **[!UICONTROL Text]** タイプを選択して、をクリック **[!UICONTROL Add]**&#x200B;します。

   ![](assets/schema_extension_uc9.png)

1. フィールドを設定するには、「**[!UICONTROL Data structure]** ドロップダウンの下にある「**[!UICONTROL Fields]**」タブで、![](assets/schema_extension_uc8.png) をクリックしてから、以前作成したフィールドの ![](assets/schema_extension_uc7.png) をクリックします。
1. In this example we want to add specific values, to do so click **[!UICONTROL Specify a list of authorized values]**.

   ![](assets/schema_extension_uc10.png)

1. Click **[!UICONTROL Add an element]** then add as many value as needed by adding a **[!UICONTROL Label]** and an **[!UICONTROL ID]** and clicking **[!UICONTROL Add]**.

   ここでは、これらのオプションの選択に使用するプロファイルの書籍、展覧会、映画、および該当なしの値を作成します。

   ![](assets/schema_extension_uc11.png)

1. To add this field in the **[!UICONTROL Profile]** screen, click the **[!UICONTROL Screen definition]** tab.
1. **[!UICONTROL Detail screen configuration]** ドロップダウンで、をクリック **[!UICONTROL Add a personalized fields section]** してクリック **[!UICONTROL Create element]**&#x200B;します。

   ![](assets/schema_extension_uc12.png)

1. Select a **[!UICONTROL Type]**. ここでは、入力フィールドを追加します。Then, select your previously created field and click **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc2.png)

1. To add a separator to better organize your profile window, click **[!UICONTROL Create an element]** and select **[!UICONTROL Separator]** from the **[!UICONTROL Type]** drop-down.

   ![](assets/schema_extension_uc19.png)

これでフィールドが設定されます。これで、テストプロファイルに拡張する必要があります。

>[!NOTE]
>
>テストプロファイルリソースを拡張する必要がない場合は、発行手順にジャンプできます。

## Step 2: Extend the test profile {#step-2--extend-the-test-profile}

新しく作成したフィールドが正しく構成されているかどうかをテストするには、テストプロファイルに配信を送信してテストします。最初に、新しいフィールドもテストプロファイルに実行する必要があります。

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. If you have not extended the **[!UICONTROL Profiles]** resource yet, click **[!UICONTROL Create]**.
1. **[!UICONTROL Extend an existing resource]** オプションを選択します。
1. **[!UICONTROL Test profile (seedMember)]** リソースを選択します。
1. **[!UICONTROL Create]**&#x200B;をクリックします。

   ![](assets/schema_extension_uc13.png)

1. **[!UICONTROL Data structure]** タブで、をクリック **[!UICONTROL Create element]**&#x200B;します。

   ![](assets/schema_extension_uc15.png)

1. Select your previously created resource field and click **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc16.png)

1. Carry out the same steps from step 11 to 13 as the extend profile walkthrough above to add this field in the **[!UICONTROL Test profile]** screen.
1. **[!UICONTROL Save]**&#x200B;をクリックします。

プロファイルとテストプロファイルの両方に、新しいフィールドが使用可能になります。正しく設定するには、カスタムリソースを公開する必要があります。

## Step 3: Publish your custom resource {#step-3--publish-your-custom-resource}

変更をリソースに適用して使用できるようにするには、データベースの更新を実行する必要があります。

1. From the advanced menu, select **Administration** &gt; **Development**, then **Publishing**.
1. By default, the option **[!UICONTROL Determine modifications since the last publication]** is checked, which means that only the changes carried out since the last update will be applied.

   ![](assets/schema_extension_uc14.png)

1. Click **[!UICONTROL Prepare publication]** to start the analysis which will update your database.
1. Once the publication has been carried out, click the **Publish** button to apply your new configurations.

   ![](assets/schema_extension_uc17.png)

1. Once published, the **Summary** pane of each resource indicates that the status is now **Published** and specifies the date of the last publication.

   ![](assets/schema_extension_uc18.png)

1. **[!UICONTROL Profiles]** タブを選択して、 **[!UICONTROL New]** 変更が正しく実装されているかどうかを確認します。

   ![](assets/schema_extension_uc20.png)

例えば、新しいリソースフィールドを使用できるようになり、配信の対象となりました。

## Step 4: Update and target profiles with a workflow {#step-4--update-and-target-profiles-with-a-workflow}

To update profiles with data for the new custom field, you can create a landing page using the **[!UICONTROL Profile acquisition]** template. For more information on landing pages, refer to this [page](../../channels/using/about-landing-pages.md).

ここでは、このフィールドに入力しなかったワークフロープロファイルのターゲットを設定します。個人用のニュースレターやオファーを受信するようにプロファイルを更新するように指示する電子メールが送信されます。各プロファイルは、選択した興味に応じてパーソナライズされたニュースレターを受け取ります。

First, we need to create a landing page that will update the **Interest** fields of the targeted profiles:

1. From the **[!UICONTROL Marketing activities]**, click **[!UICONTROL Create]** then select **[!UICONTROL Landing page]**.
1. ランディングページタイプを選択します。Here, since we want to update our profiles, select **[!UICONTROL Profile acquisition]**.
1. **[!UICONTROL Create]**&#x200B;をクリックします。
1. Click the **[!UICONTROL Content]** block to start editing the content of your landing page.

   ![](assets/schema_extension_uc21.png)

1. 必要に応じてランディングページをカスタマイズします。
1. プロファイルに設定されているフィールドをクリックして、興味の選択範囲を選択します。In the left pane, select your previously created **Interest** custom resource.

   ![](assets/schema_extension_uc22.png)

1. ランディングページを保存してテストし、フィールドが正しく構成されていることを確認します。
1. Click **[!UICONTROL Publish]** when your landing page is ready.

ランディングページが準備されました。プロファイルを更新するには、選択した興味に応じて特別なオファーを送信するワークフローを作成します。

1. **[!UICONTROL Marketing activities]** タブから、をクリック **[!UICONTROL Create]****[!UICONTROL Workflow]**&#x200B;します。
1. Drag and drop a **[!UICONTROL Query]** activity to target the profiles or audiences you need.
1. Drag and drop an **[!UICONTROL Email delivery]** activity to start configuring your email which will contain a link to the landing page. Select the **[!UICONTROL Add an outbound transition with the population]**.

   ![](assets/schema_extension_uc3.png)

1. 必要に応じて電子メールを作成してデザインします。For more information on email personalization, refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).
1. プロファイルをランディングページにリダイレクトするボタンを電子メールに追加します。
1. Select the added button and click ![](assets/schema_extension_uc7.png) in the **[!UICONTROL Link]** section in the left pane.

   ![](assets/schema_extension_uc23.png)

1. **[!UICONTROL Insert link]** ウィンドウで、ドロップダウン **[!UICONTROL Landing page]** から **[!UICONTROL Link type]** 選択して、以前に作成したランディングページを選択します。

   ![](assets/schema_extension_uc24.png)

1. **[!UICONTROL Save]**&#x200B;をクリックします。電子メールが準備され、ワークフローに戻ることができます。
1. **[!UICONTROL Wait]** アクティビティを追加して、プロファイルの一部の時間をランディングページに入力します。
1. **[!UICONTROL Segmentation]** アクティビティを追加して **、関心に応じてアウトバウンドトランジションを分割**&#x200B;します。
1. **各関心のアウトバウンドセグメントを作成**&#x200B;します。

   ![](assets/schema_extension_uc4.png)

1. Add an **[!UICONTROL Email delivery]** activity after each transition and create a personalized email depending on the chosen **Interest**.
1. 設定が完了したら、ワークフローを開始します。

   ![](assets/schema_extension_uc25.png)

選択した値に応じて、この興味フィールドに続けてパーソナライズされた電子メールが入力されるように、プロファイルに電子メールが送信されるようになりました。
