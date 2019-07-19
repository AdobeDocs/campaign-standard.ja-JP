---
title: ワークフローインターフェイス
seo-title: ワークフローインターフェイス
description: ワークフローインターフェイス
seo-description: ワークフローを作成、編集、実行するためのインターフェイスとオプションについて説明します。
page-status-flag: 常にアクティブ化されていない
uuid: aafe33ed- fa07-4dd9-825e-242099334f1a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: about- workflows- and- data- management
discoiquuid: 147fbb0d-17d2-444b- a215-9ad14179c549
context-tags: workflow， main;ワークフロー、概要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff0b995533f34dd8eab7a9a82feaab3ceed4ff29

---


# Workflow interface{#workflow-interface}

ワークフローを作成して、キャンペーンおよびプログラムでプロセス全体を管理できます。

ワークフロー編集画面は、次の要素で構成されています。

* [使用](../../automating/using/workflow-interface.md#palette)可能なアクティビティを参照するパレット
* The [Workspace](../../automating/using/workflow-interface.md#workspace), in which the activities are configured and organized
* [アクションバー](../../automating/using/workflow-interface.md#action-bar)は、ワークフローやそのコンポーネントを操作できるボタンで構成されています。
* [選択したアクティビティの周囲に表示されるクイックアクション](../../automating/using/workflow-interface.md#quick-actions)は、操作できます。

![](assets/wkf_overview.png)

## Palette {#palette}

パレットは画面の左側にあります。使用可能なすべてのアクティビティは、次のカテゴリに分類されます。

* [ターゲット](../../automating/using/about-targeting-activities.md)設定:ターゲット設定に固有のアクティビティ、訪問者データの操作、アクティビティのフィルタリング
* [実行](../../automating/using/about-execution-activities.md):ワークフローの整理と実行に固有のアクティビティ
* [チャネル](../../automating/using/about-channel-activities.md):利用可能な様々な通信チャネルを表すアクティビティ
* [Data Management（ETL）](../../automating/using/about-data-management-activities.md):データの操作に固有のアクティビティ

ワークフローのパレットからアクティビティを使用するには、ワークスペースにドラッグ&amp;ドロップします。

ワークフローを開始する前に、パレットから追加された各アクティビティを設定する必要があります。

![](assets/workflow_palette.png)

## Workspace {#workspace}

ワークスペースはワークフローエディターの中央ゾーンです。このゾーンには、アクティビティをドロップし、トランジションを使用してリンクし、設定を行うことができます。

2つのアクティビティをリンクするには、最初のアクティビティから次のアクティビティまで矢印の終わりを移動して、接続するまで移動します。また、前のアクティビティにリンクするために、その後ろの矢印のポイントに対してアクティビティを移動することもできます。いずれかのアクティビティを移動すると、リンクはリンクされます。

データを処理するアクティビティによって、中間の訪問者が含まれます。You can access them if you check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

アクティビティを選択すると、クイックアクションがアクティビティの周囲に表示され、操作を行うことができます。For example, to configure an activity, select it then open it using the ![](assets/edit_darkgrey-24px_table.png) button in the quick actions.

一部の関数は、ワークスペースでのみ有効です。

* 複数のアクティビティとトランジションを選択するには、それらの周りのゾーンを描画します。
* **Ctrl** キーを押しながら左クリックして、複数のアクティビティまたはトランジションを選択します。
* **現在** 選択されているアクティビティまたはトランジションの詳細を表示するには、Enterキーを押します。
* **現在** 選択されているアクティビティを削除するには、Deleteキーを押します。
* Press **Ctrl + C** to copy the selected activities, and **Ctrl + V** to paste them into the workspace.

![](assets/workflow_workspace.png)

## Action bar {#action-bar}

ワークスペースで選択した要素やワークフローの実行ステータスによっては、アクションバーで使用できるボタンが異なる場合があります。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>ワークフローのプロパティを編集できます。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>ワークフローを開始します。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>ワークフローを一時停止します。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>ワークフローの実行を中断します。停止元の場所から再開できません。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>ワークフローを再起動します。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>ワークフローの実行ログを開きます。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>複数選択モードを有効にします。ワークフローは少なくとも2つのアクティビティで構成されている必要があります。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>複数選択モードを無効にします。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>選択したトランジションを開きます。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>選択が無効になっているか、一時停止としてマークされている場合は、選択を再有効化します。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>コピーされたアクティビティを貼り付けます。

## Quick actions {#quick-actions}

アクティビティを選択すると、アクティビティの周囲にクイックアクションボタンが表示され、操作を行うことができます。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>選択したアクティビティを開きます。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>選択した電子メール配信アクティビティまたはSMS配信アクティビティのアドバンスオプションを開きます。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>選択が無効になっているか、一時停止としてマークされている場合は、選択を再有効化します。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>選択範囲を即座に処理します。This button is only available for the <span class="uicontrol">Scheduler</span> and <span class="uicontrol">Wait</span> activities.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。

## Duplicating workflow activities {#duplicating-workflow-activities}

ワークスペースを使用すると、同じワークフローにコピー&amp;ペーストしたり、同じキャンペーンインスタンスから別のワークフローにコピーしてワークフローアクティビティを複製したりできます。

アクティビティが複製されると、その設定全体が維持されます。配信アクティビティ（電子メール、SMS、プッシュ通知…）の場合、アクティビティに添付された配信オブジェクトが複製されます。

>[!NOTE]
>
>ワークフローアクティビティをインスタンスから別のインスタンスに複製することはできません。技術ワークフローのアクティビティを複製することはできません。

アクティビティを複製するには、次の手順に従います。

1. Select the activity, then click the **[!UICONTROL Copy selection]** button from the quick actions.

   **Ctrl+ C** キーボードショートカットも使用できます。

   ![](assets/wkf_copypaste1.png)

1. Right-click in the target workflow workspace, then click the **[!UICONTROL Paste]** button.

   **Ctrl+ V** キーボードショートカットも使用できます。

   ![](assets/wkf_copypaste2.png)

1. アクティビティは複製され、最初に設定されたすべての設定が使用されます。

複数のアクティブ化をコピー&amp;ペーストして、フロー全体を複製することもできます。

これを行うには、その周囲にゾーンを描画して、アクティビティを選択します。then click the **[!UICONTROL Copy selection]** button from the action bar (or press **Ctrl + C**). その後、目的の場所にペーストできます。

![](assets/wkf_copypaste3.png)

