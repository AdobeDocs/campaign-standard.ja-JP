---
title: パネルの追加
description: 動的レポートを使用すると、選択した期間に応じて、より適切にデータをフィルタリングするためのパネルを追加できます。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# パネルの追加{#adding-panels}

## 空のパネルの追加 {#adding-a-blank-panel}

レポートを開始するには、標準のレポートまたはカスタムレポートに一連のパネルを追加します。 各パネルには異なるデータセットが含まれ、フリーフォームテーブルとビジュアライゼーションで構成されます。

このパネルを使用すると、必要に応じてレポートを作成できます。 レポートに必要な数のパネルを追加して、様々な期間でデータをフィルタリングできます。

1. 次をクリック： **パネル** アイコン。 また、 **「挿入」タブ** および選択 **新しい空のパネル**.

   ![](assets/dynamic_report_panel_1.png)

1. 次をドラッグ&amp;ドロップ： **空のパネル** をダッシュボードに追加します。

   ![](assets/dynamic_report_panel.png)

これで、パネルにフリーフォームテーブルを追加して、データのターゲティングを開始できるようになりました。

## フリーフォームテーブルの追加 {#adding-a-freeform-table}

フリーフォームテーブルを使用すると、テーブルを作成して、 **コンポーネント** 表。

各テーブルとビジュアライゼーションはサイズ変更が可能で、レポートをより適切にカスタマイズするために移動できます。

1. 次をクリック： **[!UICONTROL Panels]** アイコン。

   ![](assets/dynamic_report_panel_1.png)

1. 次をドラッグ&amp;ドロップ： **[!UICONTROL Freeform]** 」項目をダッシュボードに追加します。

   また、 **[!UICONTROL Insert]** タブと選択 **[!UICONTROL New Freeform]** またはクリックして **[!UICONTROL Add a freeform table]** をクリックします。

   ![](assets/dynamic_report_panel_2.png)

1. Adobe Analytics の **[!UICONTROL Drop a segment here]** フィールド、 **[!UICONTROL Segment]** から **[!UICONTROL Components]** 」タブを上部のバーに移動します。

   ![](assets/dynamic_report_panel_3.png)

1. 項目を **[!UICONTROL Components]** タブを列と行に追加して、テーブルを作成します。

   ![](assets/dynamic_report_freeform_3.png)

1. 次をクリック： **[!UICONTROL Settings]** アイコンをクリックして、列でのデータの表示方法を変更します。

   ![](assets/dynamic_report_freeform_4.png)

   The **[!UICONTROL Column settings]** は、次の要素で構成されます。

   * **[!UICONTROL Number]**：列内の概要番号の表示/非表示を切り替えます。
   * **[!UICONTROL Percent]**：列で割合の表示と非表示を切り替えます。
   * **[!UICONTROL Interpret zero as no value]**：値がゼロに等しい場合に表示/非表示を切り替えます。
   * **[!UICONTROL Background]**：セル内の水平方向のプログレスバーの表示/非表示を切り替えます。
   * **[!UICONTROL Include retries]**：結果に再試行を含めることができます。 これは、次の場合にのみ使用できます。 **[!UICONTROL Sent]** および **[!UICONTROL Bounces + Errors]**.

1. 1 つまたは複数の行を選択し、 **[!UICONTROL Visualize]** アイコン。 選択した行を反映するビジュアライゼーションが追加されます。

   ![](assets/dynamic_report_freeform_5.png)

必要な数のコンポーネントを追加し、ビジュアライゼーションを追加して、データをグラフィカルに表示できるようになりました。
