---
title: パネルの追加
description: 動的レポートを使用すると、選択した期間に応じて、パネルを追加し、データをより適切にフィルタリングできます。
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

レポートを開始するには、一連のパネルを標準のレポートまたはカスタムレポートに追加します。 各パネルには、異なるデータセットが含まれ、フリーフォームテーブルとビジュアライゼーションで構成されます。

このパネルを使用すると、必要に応じてレポートを作成できます。 レポートに追加できるパネルの数に制限はありません。これにより、期間ごとにデータをフィルタリングできます。

1. **パネル**&#x200B;アイコンをクリックします。 **「挿入」タブ**&#x200B;をクリックし、「**新しい空のパネル**」を選択して、パネルを追加することもできます。

   ![](assets/dynamic_report_panel_1.png)

1. **空のパネル**&#x200B;をダッシュボードにドラッグ&amp;ドロップします。

   ![](assets/dynamic_report_panel.png)

これで、フリーフォームテーブルをパネルに追加して、データのターゲティングを開始できます。

## フリーフォームテーブルの追加 {#adding-a-freeform-table}

フリーフォームテーブルを使用すると、**コンポーネント**&#x200B;テーブルで使用可能な様々な指標およびディメンションを使用して、データを分析するテーブルを作成できます。

各テーブルとビジュアライゼーションはサイズ変更が可能で、移動してレポートをより適切にカスタマイズできます。

1. **[!UICONTROL Panels]**&#x200B;アイコンをクリックします。

   ![](assets/dynamic_report_panel_1.png)

1. **[!UICONTROL Freeform]**&#x200B;項目をダッシュボードにドラッグ&amp;ドロップします。

   また、「**[!UICONTROL Insert]**」タブをクリックして「**[!UICONTROL New Freeform]**」を選択するか、空のパネルで「**[!UICONTROL Add a freeform table]**」をクリックして、テーブルを追加することもできます。

   ![](assets/dynamic_report_panel_2.png)

1. **[!UICONTROL Drop a segment here]**&#x200B;フィールドで、**[!UICONTROL Components]**&#x200B;タブから上部のバーに&#x200B;**[!UICONTROL Segment]**&#x200B;を追加します。

   ![](assets/dynamic_report_panel_3.png)

1. 「**[!UICONTROL Components]**」タブから列と行に項目をドラッグ&amp;ドロップして、テーブルを作成します。

   ![](assets/dynamic_report_freeform_3.png)

1. **[!UICONTROL Settings]**&#x200B;アイコンをクリックして、列でのデータの表示方法を変更します。

   ![](assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]**&#x200B;は、次の要素で構成されます。

   * **[!UICONTROL Number]**:列内の概要番号の表示と非表示を切り替えることができます。
   * **[!UICONTROL Percent]**:列で割合の表示と非表示を切り替えることができます。
   * **[!UICONTROL Interpret zero as no value]**:値がゼロの場合に表示/非表示を切り替えることができます。
   * **[!UICONTROL Background]**:セル内の水平方向のプログレスバーの表示/非表示を切り替えます。
   * **[!UICONTROL Include retries]**:結果に再試行を含めることができます。これは&#x200B;**[!UICONTROL Sent]**&#x200B;と&#x200B;**[!UICONTROL Bounces + Errors]**&#x200B;に対してのみ使用できます。

1. 1つまたは複数の行を選択し、「**[!UICONTROL Visualize]**」アイコンをクリックします。 選択した行を反映するビジュアライゼーションが追加されます。

   ![](assets/dynamic_report_freeform_5.png)

必要な数のコンポーネントを追加できるようになりました。また、ビジュアライゼーションを追加して、データをグラフィカルに表示することもできます。
