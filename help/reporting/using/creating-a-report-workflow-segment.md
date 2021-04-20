---
solution: Campaign Standard
product: campaign
title: ワークフローセグメントに基づくレポートの作成
description: レポート内のワークフローのセグメントに応じて、配信の成功を確認する方法を説明します。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 3%

---


# ワークフローセグメントに基づくレポートの作成{#creating-a-report-workflow-segment}

ワークフローを作成し、訪問者を様々なターゲットオーディエンスにフィルタリングした後、このターゲット設定ワークフローで定義されたセグメントに基づいて、マーケティングキャンペーンの効率を測定できます。
レポートにこれらのセグメントをターゲットするには：

* [手順1:セグメントを含むプロファイルのカスタムリソースの更新](#step-1--update-profiles-custom-resource-segments)
* [手順2:セグメントを使用したワークフローの作成](#step-2--create-a-workflow-segments)
* [手順3:セグメントをフィルターする動的レポートの作成](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>動的なレポートの使用許諾契約は、これらのデータを収集する開始に対して受け入れられる必要があります。
>この契約の詳細については、[ページ](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)を参照してください。

## 手順1:セグメント{#step-1--update-profiles-custom-resource-segments}でプロファイルのカスタムリソースを更新

セグメントコードにレポートする前に、セグメントコードが保存されるように&#x200B;**[!UICONTROL Profiles]**&#x200B;カスタムリソースを更新する必要があります。

1. 詳細設定メニューのAdobe Campaignロゴから、**[!UICONTROL Administration]**/**[!UICONTROL Development]**/**[!UICONTROL Custom resources]**&#x200B;を選択し、**[!UICONTROL Profile (profile)]**&#x200B;リソースを選択します。
1. **[!UICONTROL Data structure]**&#x200B;タブの&#x200B;**[!UICONTROL Sending logs extension]**&#x200B;メニューで、**[!UICONTROL Add segment code]**&#x200B;をチェックして、ターゲットワークフローからセグメントコードをストレージできるようにし、動的レポートに送信します。

   **[!UICONTROL Segment code]**&#x200B;は、レポートの&#x200B;**[!UICONTROL Profile]**&#x200B;ディメンションセクションで使用できます。

   ![](assets/report_segment_4.png)

1. カスタムリソースを保存します。

1. 次に、カスタムリソースを発行する必要があります。
詳細設定メニューで、**[!UICONTROL Administration]**/**[!UICONTROL Development]**/**[!UICONTROL Publishing]**&#x200B;を選択します。

   ![](assets/custom_profile_7.png)

1. **[!UICONTROL Prepare publication]**&#x200B;をクリックし、準備が完了したら、**[!UICONTROL Publish]**&#x200B;ボタンをクリックします。 カスタムリソースの詳細については、[ページ](../../developing/using/updating-the-database-structure.md)を参照してください。

これで、セグメントコードを使用したワークフローの作成開始を作成できます。

セグメントコードは、**[!UICONTROL Sending logs extension]**&#x200B;でセグメントコードを有効にするとすぐに収集されます。

## 手順2:セグメント{#step-2--create-a-workflow-segments}を使用したワークフローの作成

>[!NOTE]
>電子メール配信の入力トランジションが空の場合、デフォルトでは、前のトランジションのセグメントコードが追加されます。

まず、異なるターゲット母集団のワークフローを作成する必要があります。 ここでは、オーディエンスの年齢に応じてパーソナライズされた電子メールを送信します。1人は20歳から30歳のプロファイルの配信で、もう1人は30歳から40歳のプロファイルの人です。

1. ワークフローを作成します。 ワークフローの作成方法の詳細については、[ページ](../../automating/using/building-a-workflow.md)を参照してください。

1. &lt;追加a0/>アクティビティを表示します。**[!UICONTROL Query]**

1. 20歳から40歳のターゲットプロファイルが、それらをより的を絞った集団に分類します。

   ![](assets/report_segment_1.png)

1. &lt;追加a0/>アクティビティを使用して、クエリ結果を2つのターゲット母集団に分割します。 **[!UICONTROL Segmentation]**&#x200B;セグメント化について詳しくは、[ページ](../../automating/using/segmentation.md)を参照してください。

1. 重複が&#x200B;**[!UICONTROL Segmentation]**&#x200B;アクティビティをクリックして設定します。 **[!UICONTROL Edit properties]**&#x200B;をクリックして、最初のセグメントを編集します。

   ![](assets/report_segment_7.png)

1. 20歳から30歳の間のクエリプロファイルが完了したら、**[!UICONTROL Confirm]**&#x200B;をクリックします。

   ![](assets/report_segment_8.png)

1. **[!UICONTROL Add an element]**&#x200B;をクリックして2番目のセグメントを作成し、上記の手順に従って30 ～ 40才のプロファイルをターゲットします。

1. 動的なレポートを介して渡される各母集団の&#x200B;**[!UICONTROL Segment code]**&#x200B;を編集します。

   >[!NOTE]
   >この手順は必須です。必須でない場合は、どのセグメントをレポートするかを理解できません。

   ![](assets/report_segment_9.png)

1. セグメントの後に&#x200B;**[!UICONTROL Email delivery]**&#x200B;アクティビティをドラッグ&amp;ドロップします。

   ![](assets/report_segment_3.png)

1. ターゲット母集団の種類に応じて配信をパーソナライズします。 電子メールの作成について詳しくは、[ページ](../../designing/using/designing-content-in-adobe-campaign.md)を参照してください。

1. ワークフローを保存します。

1. ワークフローの準備が整ったら、**[!UICONTROL Start]**&#x200B;をクリックします。

これで、レポートにアクセスしてセグメントコードを追跡できるようになります。

## 手順3:セグメントをフィルターする動的レポートの作成{#step-3--create-a-dynamic-report-filter-segments}

ワークフローで配信を送信した後、ワークフローのセグメントコードを使用してレポートを分類できます。

1. 「**[!UICONTROL Reports]**」タブからあらかじめ用意されているレポートを選択するか、**[!UICONTROL Create new project]**&#x200B;ボタンをクリックして最初から開始します。

   ![](assets/custom_profile_18.png)
1. フリーフォームテーブルに&#x200B;**[!UICONTROL Delivery]**&#x200B;ディメンションをドラッグ&amp;ドロップします。

   ![](assets/report_segment_5.png)

1. 様々な指標（**[!UICONTROL Open]**&#x200B;指標や&#x200B;**[!UICONTROL Click]**&#x200B;指標など）をテーブルにドラッグ&amp;ドロップして、データのフィルタリングに開始します。
1. **[!UICONTROL Dimensions]**&#x200B;カテゴリーで、**[!UICONTROL Profile]**&#x200B;ディメンションをクリックし、ワークフローの配信ーに&#x200B;**[!UICONTROL Segment code]**&#x200B;ディメンションをドラッグ&amp;ドロップして、ターゲット母集団に応じた電子メール配信の成功を測定します。

   ![](assets/report_segment_6.png)

1. 必要に応じて、ワークスペースにビジュアライゼーションをドラッグ&amp;ドロップします。

   ![](assets/report_segment_10.png)
