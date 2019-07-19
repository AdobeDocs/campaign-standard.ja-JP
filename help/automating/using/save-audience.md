---
title: オーディエンスの保存
seo-title: オーディエンスの保存
description: オーディエンスの保存
seo-description: オーディエンスの保存アクティビティを使用すると、既存のオーディエンスを更新したり、ワークフローでアップストリームで計算された母集団から新しいオーディエンスを作成したりできます。
page-status-flag: 常にアクティブ化されていない
uuid: 8babb173- fa59-44a7- a2a5-49f45ba6bf99
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: ターゲットアクティビティ
discoiquuid: 1f6bb048-7abd-499b- a4b0-187f9492dc47
context-tags: SaveAudience、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Save audience{#save-audience}

## 説明 {#description}

![](assets/save_audience.png)

**[!UICONTROL Save audience]** アクティビティにより、既存のオーディエンスを更新したり、ワークフローでアップストリームで計算された母集団から新しいオーディエンスを作成したりできます。The audiences created or updated from this activity are **List** or **File** audiences. They are added to the list of application audiences, and are made available via the **[!UICONTROL Audiences]** menu.

>[!NOTE]
>
>**[!UICONTROL Save audience]** アクティビティを通じて作成されたオーディエンスが追加データで強化されている場合、これらのデータを使用してスタンドアロンの配信をパーソナライズすることはできません。ワークフローで実行された配信からのみ使用できます。

また、このアクティビティでは、Adobe Experience Cloudオーディエンス/セグメントとしてプロファイルをエクスポートできます。これにより、他のAdobe Experience Cloudソリューションでこれらのオーディエンスを活用できます。For more information about shared audiences, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Context of use {#context-of-use}

**[!UICONTROL Save audience]** アクティビティは、基本的に、再利用可能なオーディエンスに変換することによって、同じワークフロー内の母集団グループを維持するために使用されます。

## Configuration {#configuration}

1. Drop a **[!UICONTROL Save audience]** activity into your workflow.
1. クエリ、交差、統合、除外などのターゲット設定アクティビティの後に、それを接続します。
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. 実行するアクションを選択します。

   * **[!UICONTROL Update an existing audience]**:既存のオーディエンスを選択し、更新のタイプを選択します。

      * **[!UICONTROL Replace audience content with new data]**:オーディエンスコンテンツ全体が置換されます。古いデータは失われます。保存オーディエンスアクティビティの受信移行のデータのみが保持されます。
      * **[!UICONTROL Complete audience with new data]**:古いオーディエンスデータが保持され、保存オーディエンスアクティビティのインバウンドトランジションのデータが追加されます。
   * **[!UICONTROL Create then update an audience]**:オーディエンスの名前を入力し、更新タイプを選択します。オーディエンスがまだ存在しない場合は、作成されます。既に存在する場合は、選択したモードに応じて更新されます。

      * **[!UICONTROL Replace audience content with new data]**:オーディエンスコンテンツ全体が置換されます。古いデータは失われます。保存オーディエンスアクティビティの受信移行のデータのみが保持されます。

         警告、このオプションを選択すると、更新されたオーディエンスのオーディエンスタイプとターゲットディメンションが消去されます。

      * **[!UICONTROL Complete audience with new data]**:古いオーディエンスデータが保持され、保存オーディエンスアクティビティのインバウンドトランジションのデータが追加されます。

         警告:オーディエンスタイプまたはオーディエンスのターゲットディメンションがワークフローの現在の設定と互換性がない場合、このオプションによってエラーが発生します。例えば、クエリーからのプロファイルを持つファイルタイプオーディエンスを完了することはできません。
   * **[!UICONTROL Create a new audience]**:作成するオーディエンスの名前を入力します。オーディエンスが作成された日時は、オーディエンス名に自動的に追加されます。これにより、ワークフローが実行されるたびにオーディエンスが一意になります。
   * **[!UICONTROL Share in Adobe Experience Cloud]**:ターゲットプロファイルがあり、オーディエンスをAdobe Experience Cloudにエクスポートする場合は、このオプションを選択して、既存の共有オーディエンスを選択するか、新しいオーディエンスを作成します。

      Also select a **[!UICONTROL Shared Data source]** that corresponds to the resource of the data contained in the audience so that the data is correctly reconciled in Adobe Experience Cloud.

      Using this option, the shared audience is not added to the list of Adobe Campaign audiences available via the **[!UICONTROL Audiences]** menu.

      >[!NOTE]
      >
      >このオプションは、Adobe Experience Cloudの共有オーディエンス機能が管理者によって設定されている場合にのみ使用できます。For more information, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   更新中に保存または利用可能なオーディエンスのタイプは、ワークフローにアップアップしたアクティビティによって異なります。

   If the targeting dimension of the audience is unknown when it is saved (for example if it is from an imported file), the audience is created or updated as a **[!UICONTROL File]** type audience.

   If the targeting dimension of the saved audience is already defined when it is saved (for example, if it comes from a targeting, after a query, etc.), then the audience is saved or updated as a **[!UICONTROL List]** type audience.

   The content of the saved audience is then available in the detail view of the audience, which can be accessed from the **[!UICONTROL Audiences]** menu. このビューで使用できる列は、ワークフローの保存オーディエンスアクティビティのインバウンドトランジションの列に対応します。次に例を示します。インポートされたファイルの列で、クエリーから追加された追加データが表示されます。

1. アクティビティの設定を確認し、ワークフローを保存します。

## Example {#example}

この例で定義したワークフローは、ターゲット設定からの通常のオーディエンスの更新を示しています。

* It is automatically executed once a month using a **[!UICONTROL Scheduler]**.
* You can use a **[!UICONTROL Query]** to recover all the profiles subscribed to the different application services available.
* **[!UICONTROL Save audience]** アクティビティは、最後のワークフローの実行以降、および新しく登録されたプロファイルを追加して、サービスから登録解除されたプロファイルを削除することで、オーディエンスを更新します。

![](assets/save_audience_example_1.png)

**[!UICONTROL Save audience]** アクティビティは次のように設定されます。

![](assets/save_audience_example_2.png)

