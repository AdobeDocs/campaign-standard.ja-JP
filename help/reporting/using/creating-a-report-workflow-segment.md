---
solution: Campaign Standard
product: campaign
title: ワークフローセグメントに基づくレポートの作成
description: レポート内のワークフローのセグメントに応じて、配信の成功を確認する方法を説明します。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: レポート
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: c001aaba50bdce8d949acc6daf74f3c7738bd117
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# ワークフローセグメントに基づくレポートの作成{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**は、EメールおよびSMS配信のみをターゲットにできます。

ワークフローを作成し、母集団を異なるターゲットオーディエンスにフィルタリングした後、このターゲティングワークフローで定義されたセグメントに基づいて、マーケティングキャンペーンの効率を測定できます。
レポートでこれらのセグメントをターゲットにするには：

* [手順1:プロファイルのカスタムリソースをセグメントで更新する](#step-1--update-profiles-custom-resource-segments)
* [手順2:セグメントを含むワークフローの作成](#step-2--create-a-workflow-segments)
* [手順3:セグメントをフィルターする動的レポートの作成](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>これらのデータの収集を開始するには、動的レポートの使用契約に同意する必要があります。
>
>この契約について詳しくは、[ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)を参照してください。

## 手順1:プロファイルのカスタムリソースをセグメントで更新する{#step-1--update-profiles-custom-resource-segments}

セグメントコードのレポートを作成する前に、保存するセグメントコードの&#x200B;**[!UICONTROL Profiles]**&#x200B;カスタムリソースを更新する必要があります。

1. 詳細設定メニューのAdobe Campaignロゴから、**[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]**&#x200B;を選択し、**[!UICONTROL Profile (profile)]**&#x200B;リソースを選択します。
1. 「**[!UICONTROL Data structure]**」タブの&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;メニューで「**[!UICONTROL Add segment code]**」をオンにして、ターゲティングワークフローのセグメントコードを保存し、動的レポートに送信できるようにします。

   **[!UICONTROL Segment code]**&#x200B;がレポートの&#x200B;**[!UICONTROL Profile]**&#x200B;ディメンションセクションで使用できるようになります。

   ![](assets/report_segment_4.png)

1. カスタムリソースを保存します。

1. 次に、カスタムリソースを公開する必要があります。
詳細設定メニューから、**[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**&#x200B;を選択します。

   ![](assets/custom_profile_7.png)

1. **[!UICONTROL Prepare publication]**&#x200B;をクリックし、準備が完了したら、「**[!UICONTROL Publish]**」ボタンをクリックします。 カスタムリソースの詳細については、この[ページ](../../developing/using/updating-the-database-structure.md)を参照してください。

これで、セグメントコードを使用したワークフローの作成を開始できます。

セグメントコードは、**[!UICONTROL Sending logs extension]**&#x200B;でセグメントコードを有効にするとすぐに収集されます。

## 手順2:セグメントを含むワークフローの作成 {#step-2--create-a-workflow-segments}

>[!NOTE]
>Eメール配信の入力トランジションが空の場合、デフォルトでは、前のトランジションのセグメントコードが追加されます。

最初に、異なるターゲット母集団を持つワークフローを作成する必要があります。 ここでは、オーディエンスの年齢に応じてパーソナライズされるEメールを送信します。1つは20歳から30歳のプロファイル用、もう1つは30歳から40歳のプロファイル用です。

1. ワークフローを作成します。 ワークフローの作成方法について詳しくは、この[ページ](../../automating/using/building-a-workflow.md)を参照してください。

1. パレットから&#x200B;**[!UICONTROL Query]**&#x200B;アクティビティをドラッグし、ワークスペースにドロップして、アクティビティを追加します。

1. 20歳から40歳までのプロファイルをターゲット設定し、後でターゲット母集団にセグメント化します。

   ![](assets/report_segment_1.png)

1. **[!UICONTROL Segmentation]**&#x200B;アクティビティを追加して、クエリ結果を2つのターゲット母集団に分割します。 セグメント化について詳しくは、この[ページ](../../automating/using/segmentation.md)を参照してください。

1. **[!UICONTROL Segmentation]**&#x200B;アクティビティをダブルクリックして設定します。 「**[!UICONTROL Edit properties]**」をクリックして、最初のセグメントを編集します。

   ![](assets/report_segment_7.png)

1. 年齢が20歳から30歳までのプロファイルをクエリし、完了したら「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/report_segment_8.png)

1. **[!UICONTROL Add an element]**&#x200B;をクリックして2番目のセグメントを作成し、上記の手順に従って設定し、30歳から40歳までのプロファイルをターゲットにします。

1. 動的レポートで渡される各母集団の&#x200B;**[!UICONTROL Segment code]**&#x200B;を編集します。

   >[!NOTE]
   >この手順は必須です。そうしないと、レポートするセグメントを理解できなくなります。

   ![](assets/report_segment_9.png)

1. セグメントの後に&#x200B;**[!UICONTROL Email delivery]**&#x200B;アクティビティをドラッグ&amp;ドロップします。

   ![](assets/report_segment_3.png)

1. ターゲット母集団に応じて、配信をパーソナライズします。 Eメールの作成について詳しくは、この[ページ](../../designing/using/designing-content-in-adobe-campaign.md)を参照してください。

1. ワークフローを保存します。

1. ワークフローの準備が整ったら、「**[!UICONTROL Start]**」をクリックします。

これで、レポートにアクセスしてセグメントコードを追跡できます。

## 手順3:セグメントをフィルターする動的レポートの作成 {#step-3--create-a-dynamic-report-filter-segments}

ワークフローで配信を送信した後、ワークフローのセグメントコードを使用してレポートを分類できます。

1. 「**[!UICONTROL Reports]**」タブで、標準のレポートを選択するか、「**[!UICONTROL Create new project]**」ボタンをクリックして最初からレポートを開始します。

   ![](assets/custom_profile_18.png)
1. フリーフォームテーブルに&#x200B;**[!UICONTROL Delivery]**&#x200B;ディメンションをドラッグ&amp;ドロップします。

   ![](assets/report_segment_5.png)

1. **[!UICONTROL Open]**&#x200B;指標や&#x200B;**[!UICONTROL Click]**&#x200B;指標など、様々な指標をテーブルにドラッグ&amp;ドロップして、データのフィルタリングを開始します。
1. 「**[!UICONTROL Dimensions]**」カテゴリで&#x200B;**[!UICONTROL Profile]**&#x200B;ディメンションをクリックし、ワークフローの配信に&#x200B;**[!UICONTROL Segment code]**&#x200B;ディメンションをドラッグ&amp;ドロップして、ターゲット母集団に応じてEメール配信の成功を測定します。

   ![](assets/report_segment_6.png)

1. 必要に応じて、ワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/report_segment_10.png)
