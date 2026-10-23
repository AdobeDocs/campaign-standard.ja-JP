---
title: パネルの追加
description: 動的レポートを使用すると、パネルを追加して、選択した期間に応じてデータをより適切にフィルターできます。
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
TQID: 'https://experienceleague.adobe.com/jQtNVS-IFlOGMS5RAfKfOU610fZGzLB2GjEWwOPJE84'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 60%
---
# パネルの追加{#adding-panels}

## 空のパネルの追加 {#adding-a-blank-panel}

レポートを開始するには、標準またはカスタムのレポートに一連のパネルを追加します。 各パネルは、様々なデータセットを含み、フリーフォームテーブルとビジュアライゼーションで構成されています。

このパネルを使用すると、必要に応じてレポートを作成できます。 異なる期間でデータをフィルタリングするために、レポートに必要な数のパネルを追加できます。

1. 「**パネル**」アイコンをクリックします。 また、「**タブを挿入**」をクリックして「**新しい空のパネルl**」を選択することで、パネルを追加することもできます。

   ![](assets/dynamic_report_panel_1.png)

1. **空のパネル**&#x200B;をダッシュボードにドラッグ＆ドロップします。

   ![](assets/dynamic_report_panel.png)

これで、パネルにフリーフォームテーブルを追加して、データのターゲティングを開始できるようになりました。

## フリーフォームテーブルの追加 {#adding-a-freeform-table}

フリーフォームテーブルでは、**コンポーネント**&#x200B;テーブルにある様々な指標やディメンションを使ってテーブルを作成し、データを分析できます。

各テーブルとビジュアライゼーションはサイズ変更したり、移動したりしてレポートをカスタマイズできます。

1. **[!UICONTROL Panels]** アイコンをクリックします。

   ![](assets/dynamic_report_panel_1.png)

1. **[!UICONTROL Freeform]**&#x200B;項目をダッシュボードにドラッグ&amp;ドロップします。

   テーブルを追加するには、**[!UICONTROL Insert]** タブをクリックして&#x200B;**[!UICONTROL New Freeform]**&#x200B;を選択するか、空のパネルで&#x200B;**[!UICONTROL Add a freeform table]**&#x200B;をクリックします。

   ![](assets/dynamic_report_panel_2.png)

1. **[!UICONTROL Drop a segment here]** フィールドで、**[!UICONTROL Components]** タブから&#x200B;**[!UICONTROL Segment]**&#x200B;を上部バーに追加します。

   ![](assets/dynamic_report_panel_3.png)

1. **[!UICONTROL Components]** タブから項目を列と行にドラッグ&amp;ドロップして、テーブルを作成します。

   ![](assets/dynamic_report_freeform_3.png)

1. **[!UICONTROL Settings]** アイコンをクリックして、列でのデータの表示方法を変更します。

   ![](assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]**&#x200B;は次の要素で構成されています：

   * **[!UICONTROL Number]**：列の要約番号を表示または非表示にできます。
   * **[!UICONTROL Percent]**：列のパーセントを表示または非表示にできます。
   * **[!UICONTROL Interpret zero as no value]**：値が0に等しい場合に表示または非表示にできます。
   * **[!UICONTROL Background]**: セルの水平方向の進行状況バーを表示または非表示にできます。
   * **[!UICONTROL Include retries]**：結果に再試行を含めることができます。 これは、**[!UICONTROL Sent]**&#x200B;と&#x200B;**[!UICONTROL Bounces + Errors]**&#x200B;でのみ使用できます。

1. 1つまたは複数の行を選択し、**[!UICONTROL Visualize]** アイコンをクリックします。 ビジュアライゼーションが追加され、選択した行が反映されます。

   ![](assets/dynamic_report_freeform_5.png)

必要な数のコンポーネントを追加し、ビジュアライゼーションを追加して、データをグラフで表示できるようになりました。
