---
title: ワークフローインターフェイス
description: ワークフローを作成、編集、実行するためのインターフェイスとオプションについて説明します。
page-status-flag: 非活性化の
uuid: aafe33ed-fa07-4dd9-825e-242099334f1a
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: about-workflows-and-data-management
discoiquuid: 147fbb0d-17d2-444b-a215-9ad14179c549
context-tags: ワークフロー，メイン；ワークフロー，概要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ワークフローインターフェイス{#workflow-interface}

ワークフローを作成して、キャンペーンおよびプログラムのプロセス全体を管理できます。

ワークフロー編集画面は、次の要素で構成されています。

* 使用可能 [](#palette)なアクティビティを参照するパレット。
* アクテ [ィビティが設定](#workspace)、整理されるWorkspace。
* アクシ [ョンバー](#action-bar)。ワークフローやそのコンポーネントを操作するためのボタンで構成されています。
* 選択し [たアクティビティの周りに表示されるクイックアクション](#quick-actions)(Quick Actions)を使用して、アクティビティを操作できます。

![](assets/wkf_overview.png)

## パレット {#palette}

パレットは画面の左側に表示されます。 使用可能なすべてのアクティビティは、次のカテゴリに分類されます。

* [ターゲット](../../automating/using/about-targeting-activities.md):訪問者データのターゲット設定、操作、およびアクティビティのフィルタリングに固有のアクティビティ
* [実行](../../automating/using/about-execution-activities.md):ワークフローの編成と実行に固有のアクティビティ
* [チャネル](../../automating/using/about-channel-activities.md):様々な通信チャネルを表す活動
* [データ管理(ETL)](../../automating/using/about-data-management-activities.md):データ操作に固有のアクティビティ

ワークフローのパレットからアクティビティを使用するには、ワークスペースにアクティビティをドラッグ&amp;ドロップします。

ワークフローを開始する前に、パレットから追加した各アクティビティを設定する必要があります。

![](assets/workflow_palette.png)

## ワークスペース {#workspace}

ワークスペースは、ワークフローエディターの中央ゾーンです。 このゾーンでは、アクティビティをドロップし、トランジションを使用してアクティビティをリンクし、設定することができます。

2つのアクティビティをリンクするには、矢印の終わりを最初のアクティビティから次のアクティビティに移動し、接続するまで待ちます。 前のアクティビティにリンクするために、アクティビティを後ろの矢印の位置に移動することもできます。 いずれかのアクティビティを移動しても、そのアクティビティはリンクされたままになります。

データを処理するアクティビティに従って、中間訪問者を含む遷移が行われます。 ワークフロープロパティのセクションでオプションを **[!UICONTROL Keep interim results]** 選択すると、こ **[!UICONTROL Execution]** れらにアクセスできます。

アクティビティを選択すると、そのアクティビティに関するクイックアクションが表示され、アクティビティを操作できます。 例えば、アクティビティを設定するには、アクティビティを選択し、クイックアクションのボ ![](assets/edit_darkgrey-24px_table.png) タンを使用して開きます。

特定の関数は、ワークスペースでのみ有効になります。

* 複数のアクティビティとトランジションを選択し、その周囲にゾーンを描画します。
* Ctrl **** +左クリックを押して、複数のアクティビティまたはトランジションを選択します。
* Enterキーを **押すと** 、現在選択されているアクティビティまたはトランジションの詳細が表示されます。
* 現在選択さ **れているアクティビティを削除するには、Delete** （削除）を押します。
* 選択し **たアクティビティをコピーするにはCtrl + C** 、ワークスペー **スに貼り付けるにはCtrl + V** を押します。

![](assets/workflow_workspace.png)

## アクションバー {#action-bar}

ワークスペースで選択した要素やワークフローの実行ステータスに応じて、アクションバーで使用できるボタンが異なる場合があります。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>ワークフローのプロパティを編集できます。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>ワークフローを開始します。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>ワークフローを一時停止します。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>ワークフローの実行を中断します。 停止した場所からは再開できません。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>ワークフローを再開します。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>ワークフローの実行ログを開きます。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>複数選択モードを有効にします。 ワークフローは、少なくとも2つのアクティビティで構成されている必要があります。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>複数選択モードを無効にします。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>選択したトランジションを開きます。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>選択が無効になっているか、一時停止としてマークされている場合は、再び有効にします。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>コピーされたアクティビティを貼り付けます。

## クイックアクション {#quick-actions}

アクティビティを選択すると、そのアクティビティの周囲にクイックアクションボタンが表示され、アクティビティを操作できます。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>選択したアクティビティを開きます。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>選択した電子メールまたはSMS配信アクティビティの詳細オプションを開きます。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>選択が無効になっているか、一時停止としてマークされている場合は、再び有効にします。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>選択範囲を強制的に即時処理します。 このボタンは、スケジューラーおよび待機ア <span class="uicontrol">クティビティでの</span> み使用できます <span class="uicontrol"></span> 。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。

## ワークフローアクティビティの複製 {#duplicating-workflow-activities}

ワークスペースを使用すると、ワークフローアクティビティをコピーして同じワークフローに貼り付けたり、同じキャンペーンインスタンスから別のワークフローに貼り付けたりして、複製できます。

アクティビティが複製されると、その設定全体が保持されます。 配信アクティビティ（電子メール、SMS、プッシュ通知など）の場合、アクティビティに添付された配信オブジェクトが複製されます。

>[!NOTE]
>
>ワークフローアクティビティをインスタンスから別のインスタンスに複製することはできません。 技術ワークフローのアクティビティは複製できません。

アクティビティを複製するには、次の手順に従います。

1. アクティビティを選択し、クイックアクシ **[!UICONTROL Copy selection]** ョンからボタンをクリックします。

   また、キーボードショートカッ **トのCtrl + C** (C)を使用することもできます。

   ![](assets/wkf_copypaste1.png)

1. ターゲットワークフローワークスペース内で右クリックし、ボタンをクリック **[!UICONTROL Paste]** します。

   [Ctrl] + [V]キーボードシ **ョートカットを使用する** こともできます。

   ![](assets/wkf_copypaste2.png)

1. アクティビティが複製され、最初に設定されたすべての設定が反映されます。

また、複数のアクティビティをコピーして貼り付け、ワークフロー全体を複製することもできます。

これを行うには、アクティビティの周囲にゾーンを描画してアクティビティを選択します。 次に、アクショ **[!UICONTROL Copy selection]** ンバーからボタンをクリックします(または **Ctrl + cキーを押します**)。 その後、目的の場所に貼り付けることができます。

![](assets/wkf_copypaste3.png)

