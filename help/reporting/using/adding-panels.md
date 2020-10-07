---
title: パネルの追加
description: 動的レポートを使用すると、選択した期間に応じてデータをより適切にフィルターするパネルを追加できます。
page-status-flag: never-activated
uuid: 8e76e837-5efc-4250-8192-dee1a0bd62fe
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: customizing-reports
discoiquuid: f4e1e676-5ca2-4a58-96d7-d378ff803710
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 1%

---


# パネルの追加{#adding-panels}

## 空のパネルの追加 {#adding-a-blank-panel}

レポートを開始するには、パネルのセットを追加してあらかじめ用意されているレポートやカスタムレポートに追加します。 各パネルには異なるデータセットが含まれ、フリーフォームテーブルとビジュアライゼーションで構成されます。

このパネルでは、必要に応じてレポートを作成できます。 様々な期間でデータをフィルターするために、レポートに必要な数のパネルを追加できます。

1. Click the **Panels** icon. 「 **挿入」タブをクリックし** 、「 **新しい空白パネル」を選択してパネルを追加することもできます**。

   ![](assets/dynamic_report_panel_1.png)

1. **空白のパネルをダッシュボードにドラッグ&amp;ドロップします** 。

   ![](assets/dynamic_report_panel.png)

パネルにフリーフォームテーブルを開始のターゲット設定データに追加できるようになりました。

## フリーフォームテーブルの追加 {#adding-a-freeform-table}

フリーフォームテーブルを使用すると、 **コンポーネントテーブルで使用できる様々な指標やディメンションを使用して、データを分析するテーブルを作成できます** 。

各テーブルとビジュアライゼーションはサイズ変更が可能で、移動してレポートをより適切にカスタマイズできます。

1. Click the **Panels** icon.

   ![](assets/dynamic_report_panel_1.png)

1. フリー **フォーム** アイテムをダッシュボードにドラッグ&amp;ドロップします。

   「 **挿入** 」タブをクリックし、「 **新規フリーフォーム** 」を選択するか、空のパネルでフリーフォームテーブル **** 追加をクリックして、テーブルを追加することもできます。

   ![](assets/dynamic_report_panel_2.png)

1. セグメントは既にデフォルトで選択されています。 **[!UICONTROL Exclude proof]** 必要に応じて、タブ **[!UICONTROL Segments]** からいずれかのタブを上部バーにドラッグ&amp;ドロップして、 **[!UICONTROL Components]** 変更できます。

   ![](assets/dynamic_report_panel_3.png)

1. 「 **コンポーネント** 」タブから列と行に項目をドラッグ&amp;ドロップして、テーブルを作成します。

   ![](assets/dynamic_report_freeform_3.png)

1. 列でのデータの表示方法を変更するには、 **設定** アイコンをクリックします。

   ![](assets/dynamic_report_freeform_4.png)

   は、次 **[!UICONTROL Column settings]** の要素で構成されます。

   * **[!UICONTROL Number]**:列内の概要番号を表示または非表示にできます。
   * **[!UICONTROL Percent]**:列内のパーセントの表示/非表示を切り替えることができます。
   * **[!UICONTROL Interpret zero as no value]**:値がゼロの場合は表示/非表示を切り替えます。
   * **[!UICONTROL Background]**:セル内の水平方向の進捗バーの表示/非表示を切り替えます。
   * **[!UICONTROL Include retries]**:結果に再試行を含めることができます。 これは、 **[!UICONTROL Sent]** およびでのみ使用でき **[!UICONTROL Bounces + Errors]**&#x200B;ます。

1. 1つまたは複数の行を選択し、 **視覚化** アイコンをクリックします。 選択した行を反映するビジュアライゼーションが追加されます。

   ![](assets/dynamic_report_freeform_5.png)

必要な数のコンポーネントを追加でき、ビジュアライゼーションを追加してデータをグラフィカルに表示できるようになりました。
