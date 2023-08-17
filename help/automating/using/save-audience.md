---
title: オーディエンスの保存
description: 「オーディエンスの保存」アクティビティを使用すると、既存のオーディエンスを更新したり、ワークフローの上流で計算された母集団から新しいオーディエンスを作成することができます。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: saveAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c3f029d7-779e-47e7-a925-1e8f672da4dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 100%

---

# オーディエンスを保存{#save-audience}

## 説明 {#description}

![](assets/save_audience.png)

「**[!UICONTROL Save audience]**」アクティビティを使用すると、既存のオーディエンスを更新したり、ワークフローの上流で計算された母集団から新しいオーディエンスを作成することができます。このアクティビティから作成または更新されるオーディエンスは、**リスト**&#x200B;オーディエンスと&#x200B;**ファイル**&#x200B;オーディエンスです。これらはアプリケーションオーディエンスのリストに追加され、**[!UICONTROL Audiences]** メニューから使用できるようになります。

>[!NOTE]
>
>「**[!UICONTROL Save audience]**」アクティビティを通じて作成されたオーディエンスが追加データで強化された場合、これらのデータを使用してスタンドアロン配信をパーソナライズすることはできません。ワークフローで実行される配信からのみ使用できます。

また、このアクティビティでは、プロファイルを Adobe Experience Cloud のオーディエンス／セグメントとして書き出すこともできます。これにより、他の Adobe Experience Cloud ソリューションでこれらのオーディエンスを活用できます。共有オーディエンスの詳細については、[Campaign と People コアサービスの使用](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)を参照してください。

## 使用状況 {#context-of-use}

「**[!UICONTROL Save audience]**」アクティビティは基本的に、同じワークフローで計算された母集団グループを再利用可能なオーディエンスに変換することで、このグループを維持するために使用されます。

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Save audience]**」アクティビティをドロップします。
1. それを、クエリ、積集合、和集合、除外などのその他のターゲティングアクティビティの後に連結します。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. 実行するアクションを選択します。

   * **[!UICONTROL Update an existing audience]**：既存のオーディエンスを選択し、更新の種類を選択します。

      * **[!UICONTROL Replace audience content with new data]**：オーディエンスコンテンツ全体を置き換えます。古いデータは失われます。「オーディエンスの保存」アクティビティのインバウンドトランジションからのデータのみが保持されます。
      * **[!UICONTROL Complete audience with new data]**：古いオーディエンスデータは保持され、「オーディエンスの保存」アクティビティのインバウンドトランジションのデータが追加されます。

   * **[!UICONTROL Create then update an audience]**：オーディエンスの名前を入力し、更新タイプを選択します。オーディエンスが存在しない場合は、作成されます。既に存在する場合は、選択したモードに従って更新されます。

      * **[!UICONTROL Replace audience content with new data]**：オーディエンスコンテンツ全体を置き換えます。古いデータは失われます。「オーディエンスの保存」アクティビティのインバウンドトランジションからのデータのみが保持されます。

        警告：このオプションを選択すると、オーディエンスの種類と、更新されたオーディエンスのターゲティングディメンションが削除されます。

      * **[!UICONTROL Complete audience with new data]**：古いオーディエンスデータは保持され、「オーディエンスの保存」アクティビティのインバウンドトランジションのデータが追加されます。

        警告：このオプションを選択すると、更新されたオーディエンスの種類またはターゲティングディメンションが現在のワークフローの設定と互換性がない場合、エラーが発生します。例えば、クエリーからのプロファイルを含むファイルタイプオーディエンスを完了することはできません。

   * **[!UICONTROL Create a new audience]**：作成するオーディエンスの名前を入力します。オーディエンスの作成日時が、オーディエンス名に自動的に追加されます。これにより、ワークフローが実行されるたびにオーディエンスが一意になります。
   * **[!UICONTROL Share in Adobe Experience Cloud]**：ターゲットプロファイルがあり、オーディエンスを Adobe Experience Cloud に書き出す場合は、このオプションを選択し、その後既存の共有オーディエンスを選択するか、新しいオーディエンスを作成します。

     また、データが Adobe Experience Cloud で正しく調整されるように、オーディエンスに含まれるデータのリソースに対応する **[!UICONTROL Shared Data source]** を選択します。

     このオプションを使用した場合、共有オーディエンスは **[!UICONTROL Audiences]** メニューから使用できる Adobe Campaign オーディエンスのリストに追加されません。

     >[!NOTE]
     >
     >このオプションは、Adobe Experience Cloud の共有オーディエンス機能が管理者によって設定されている場合にのみ使用できます。詳しくは、[Campaign と People コアサービスの使用](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)を参照してください。

   更新時に保存または使用できるオーディエンスのタイプは、ワークフローの上流に配置されているアクティビティによって異なります。

   オーディエンスのターゲティングディメンションが、保存時に不明な場合（インポートしたファイルからの場合など）は、オーディエンスはタイプが **[!UICONTROL File]** のオーディエンスとして作成または更新されます。

   保存されたオーディエンスのターゲティングディメンションが、保存時に既に定義されている場合（ターゲティングからの場合、クエリ後の場合など）、オーディエンスはタイプが **[!UICONTROL List]** のオーディエンスとして保存または更新されます。

   保存したオーディエンスの内容は、そのオーディエンスの詳細表示で利用できます。詳細表示は **[!UICONTROL Audiences]** メニューからアクセスできます。この表示で使用できる列は、ワークフローの「オーディエンスの保存」アクティビティのインバウンドトランジションの列に対応します（例：インポートしたファイルの列、クエリから追加された追加データの列）。

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

この例で定義したワークフローは、ターゲティングからの定期的なオーディエンス更新を示しています。

* これは 1 か月に 1 回、**[!UICONTROL Scheduler]** を使用して自動的に実行されます。
* **[!UICONTROL Query]** を使用すると、使用可能な複数のアプリケーションサービスに登録されているすべてのプロファイルを回復できます。
* 「**[!UICONTROL Save audience]**」アクティビティでは、前回のワークフロー実行以降にサービスから登録解除されたプロファイルを削除し、新たに登録されたプロファイルを追加することで、オーディエンスが更新されます。

![](assets/save_audience_example_1.png)

「**[!UICONTROL Save audience]**」アクティビティは次のように設定します。

![](assets/save_audience_example_2.png)
