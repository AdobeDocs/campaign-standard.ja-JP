---
title: パネルの追加
description: 動的レポートを使用すると、パネルを追加して、選択した期間に応じてデータをより適切にフィルタリングできます。
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

レポートを開始するには、一連のパネルを標準またはカスタムレポートに追加します。 各パネルには、様々なデータセットが含まれ、フリーフォームテーブルおよびビジュアライゼーションで構成されます。

このパネルを使用すると、必要に応じてレポートを作成できます。 異なる期間でデータをフィルタリングするために、レポートに必要な数のパネルを追加できます。

1. **パネル** アイコンをクリックします。 また、「挿入」タブをクリックして **新しい空のパネル** を選択することで、パネルを追加す **こともでき** す。

   ![](assets/dynamic_report_panel_1.png)

1. **空のパネル** をダッシュボードにドラッグ&amp;ドロップします。

   ![](assets/dynamic_report_panel.png)

これで、フリーフォームテーブルをパネルに追加して、データのターゲット設定を開始できます。

## フリーフォームテーブルの追加 {#adding-a-freeform-table}

フリーフォームテーブルを使用すると、**コンポーネント** テーブルで使用できる様々な指標やディメンションを使用して、データを分析するテーブルを作成できます。

各テーブルとビジュアライゼーションはサイズ変更可能で、移動してレポートをカスタマイズできます。

1. **[!UICONTROL Panels]** アイコンをクリックします。

   ![](assets/dynamic_report_panel_1.png)

1. **[!UICONTROL Freeform]** の項目をダッシュボードにドラッグ&amp;ドロップします。

   「テーブル」タブをクリックして選択するか、空のパネ **[!UICONTROL Insert]** で **[!UICONTROL New Freeform]** をクリックして、テー **[!UICONTROL Add a freeform table]** ルを追加することもできます。

   ![](assets/dynamic_report_panel_2.png)

1. 「**[!UICONTROL Drop a segment here]**」フィールドで、「**[!UICONTROL Components]**」タブの **[!UICONTROL Segment]** を上部のバーに追加します。

   ![](assets/dynamic_report_panel_3.png)

1. 「**[!UICONTROL Components]**」タブから列と行に項目をドラッグ&amp;ドロップして、テーブルを作成します。

   ![](assets/dynamic_report_freeform_3.png)

1. **[!UICONTROL Settings]** アイコンをクリックして、列でのデータの表示方法を変更します。

   ![](assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]** は、次の要素で構成されます。

   * **[!UICONTROL Number]**：列の概要数値の表示と非表示を切り替えることができます。
   * **[!UICONTROL Percent]**：列のパーセントの表示と非表示を切り替えることができます。
   * **[!UICONTROL Interpret zero as no value]**：値が 0 に等しい場合に表示または非表示にできます。
   * **[!UICONTROL Background]**: セル内の水平プログレスバーの表示と非表示を切り替えることができます。
   * **[!UICONTROL Include retries]**：再試行を結果に含めることができます。 これは、**[!UICONTROL Sent]** と **[!UICONTROL Bounces + Errors]** でのみ使用できます。

1. 1 つまたは複数の行を選択して、「**[!UICONTROL Visualize]**」アイコンをクリックします。 ビジュアライゼーションが追加され、選択した行が反映されます。

   ![](assets/dynamic_report_freeform_5.png)

必要な数のコンポーネントを追加し、ビジュアライゼーションを追加して、データをグラフで表示できるようになりました。
