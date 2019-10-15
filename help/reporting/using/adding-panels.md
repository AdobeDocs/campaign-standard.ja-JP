---
title: パネルの追加
seo-title: パネルの追加
description: パネルの追加
seo-description: 動的レポートを使用すると、選択した期間に応じてデータをより適切にフィルタリングするためのパネルを追加できます。
page-status-flag: 非活性化の
uuid: 8e76e837-5efc-4250-8192-dee1a0bd62fe
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: レポートのカスタマイズ
discoiquuid: f4e1e676-5ca2-4a58-96d7-d378ff803710
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d3fca4c85f418a6a50bbf12f730990ad4b33a4cc

---


# パネルの追加{#adding-panels}

## 空のパネルの追加 {#adding-a-blank-panel}

レポートを開始するには、あらかじめ用意されているパネルまたはカスタムレポートに一連のパネルを追加します。 各パネルには様々なデータセットが含まれ、フリーフォームテーブルとビジュアライゼーションで構成されています。

このパネルでは、必要に応じてレポートを作成できます。 様々な期間でデータをフィルターするために、レポートに任意の数のパネルを追加できます。

1. Click the **Panels** icon. 「挿入」タブをクリックし、「新しい空白パネル」を選 **択して** 、パネルを追 **加することもできます**。

   ![](assets/dynamic_report_panel_1.png)

1. 空のパネルをダッシュボ **ードにドラッグ** &amp;ドロップします。

   ![](assets/dynamic_report_panel.png)

パネルにフリーフォームテーブルを追加して、データのターゲット設定を開始できるようになりました。

## フリーフォームテーブルの追加 {#adding-a-freeform-table}

フリーフォームテーブルを使用すると、コンポーネントテーブルで使用できる様々な指標やディメンションを使用して、データを分析するテーブルを作 **成でき** ます。

各テーブルとビジュアライゼーションはサイズ変更が可能で、移動してレポートをより適切にカスタマイズできます。

1. Click the **Panels** icon.

   ![](assets/dynamic_report_panel_1.png)

1. フリーフォームアイテムを **ダッシュボード** にドラッグ&amp;ドロップします。

   「挿入」タブをクリックして「新規フリーフォーム **」を選択するか、空のパネルで** 「フリ **ーフォームテーブルを追加****** 」をクリックして、テーブルを追加することもできます。

   ![](assets/dynamic_report_panel_2.png)

1. Campaign 19.4リリース以降、デフォルトでは **[!UICONTROL Exclude proof]** 既に選択されています。 必要に応じて、タブから上部バーにいずれかをドラッグ&amp;ドロ **[!UICONTROL Segments]** ップして、 **[!UICONTROL Components]** 変更することができます。

   ![](assets/dynamic_report_panel_3.png)

1. 「コンポーネント」タブから列 **と行に** 、項目をドラッグ&amp;ドロップして表を作成します。

   ![](assets/dynamic_report_freeform_3.png)

1. 列でのデータ **** の表示方法を変更するには、設定アイコンをクリックします。

   ![](assets/dynamic_report_freeform_4.png)

   は、次 **[!UICONTROL Column settings]** の要素で構成されます。

   * **[!UICONTROL Number]**:列内の概要番号の表示/非表示を切り替えます。
   * **[!UICONTROL Percent]**:列内の割合の表示/非表示を切り替えます。
   * **[!UICONTROL Interpret zero as no value]**:値がゼロの場合に表示/非表示を切り替えます。
   * **[!UICONTROL Background]**:セル内の水平プログレスバーの表示/非表示を切り替えます。
   * **[!UICONTROL Include retries]**:結果に再試行を含めることができます。 これは、とでのみ使用で **[!UICONTROL Sent]** きま **[!UICONTROL Bounces + Errors]**&#x200B;す。

1. 1つまたは複数の行を選択し、「視覚化」アイコンをク **リックします** 。 選択した行を反映するビジュアライゼーションが追加されます。

   ![](assets/dynamic_report_freeform_5.png)

必要な数のコンポーネントを追加でき、ビジュアライゼーションを追加してデータをグラフィカルに表示できるようになりました。
