---
title: ワークフローインターフェイス
description: ワークフローを作成、編集、実行するためのインターフェイスとオプションについて説明します。
page-status-flag: never-activated
uuid: aafe33ed-fa07-4dd9-825e-242099334f1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 147fbb0d-17d2-444b-a215-9ad14179c549
context-tags: workflow,main;workflow,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---


# ワークフローインターフェイス{#workflow-interface}

ワークフローを作成して、キャンペーンーとプログラムのプロセス全体を管理できます。

ワークフロー編集画面は、次の要素で構成されています。

* 使用可能な [アクティビティを参照するパレット](#palette)。
* アクティビティが設定および編成される [ワークスペース](#workspace)。
* ア [クションバー](#action-bar)。ワークフローやそのコンポーネントを操作するためのボタンで構成されています。
* ク [イックアクション](#quick-actions)(選択したアクティビティの周りに表示される)を使用して、操作を行うことができます。

![](assets/wkf_overview.png)

## パレット {#palette}

パレットは画面の左側に表示されます。 使用可能なすべてのアクティビティは、次の複数のカテゴリに分類されます。

* [ターゲット](../../automating/using/about-targeting-activities.md):訪問者データのターゲット設定、操作、アクティビティのフィルタリングに固有のアクティビティ
* [実行](../../automating/using/about-execution-activities.md):ワークフローの編成と実行に固有のアクティビティ
* [チャネル](../../automating/using/about-channel-activities.md):様々な通信チャネルを表すアクティビティ
* [データ管理(ETL)](../../automating/using/about-data-management-activities.md):データの操作に固有のアクティビティ

ワークフロー内のパレットのアクティビティを使用するには、ワークスペースにドラッグ&amp;ドロップします。

ワークフローを開始する前に、パレットから追加した各アクティビティを設定する必要があります。

![](assets/workflow_palette.png)

## ワークスペース {#workspace}

ワークスペースは、ワークフローエディターの中央ゾーンです。 このゾーンでは、トランジションをドロップし、アクティビティを使用してリンクし、構成することができます。

2つのアクティビティをリンクするには、矢印の端を最初のアクティビティから次のアクティビティに移動して、接続します。 アクティビティを後ろの矢印の点に向けて移動して、前のアクティビティにリンクさせることもできます。 いずれかのアクティビティを移動しても、リンクは維持されます。

データを処理するアクティビティに続くトランジションには、中間の訪問者が含まれます。 ワークフロープロパティのセクションで **[!UICONTROL Keep interim results]** オプションをオンにすると、これら **[!UICONTROL Execution]** にアクセスできます。

>[!CAUTION]
>
>このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。実稼働インスタンスでは、このチェックボックスをオフのままにします。


アクティビティを選択すると、アクティビティの周りにクイックアクションが表示され、ユーザーが操作できるようになります。 例えば、アクティビティを設定するには、そのユーザーを選択し、クイックアクションの ![](assets/edit_darkgrey-24px_table.png) ボタンを使用して開きます。

特定の機能は、ワークスペースでのみ有効になります。

* 複数のアクティビティとトランジションの周りにゾーンを描画して選択します。
* 複数のアクティビティまたはトランジションを選択するには、 **Ctrl** +左クリックを押します。
* Enter **キーを押して** 、現在選択されているアクティビティまたはトランジションの詳細を表示します。
* 現在選択されているアクティビティを削除するには、 **Delete** キーを押します。
* 選択したアクティビティをコピーするには **Ctrl + C** 、ワークスペースに貼り付けるには **Ctrl + V** 。

![](assets/workflow_workspace.png)

## アクションバー {#action-bar}

ワークスペースで選択した要素、またはワークフローの実行ステータスに応じて、アクションバーで使用できるボタンは異なる場合があります。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>ワークフローのプロパティを編集できます。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>ワークフローを開始します。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>ワークフローを一時停止します。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>ワークフローの実行を中断します。 停止した場所から再開できません。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>ワークフローを再開します。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>ワークフローの実行ログを開きます。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>複数選択モードを有効にします。 ワークフローは、2つ以上のアクティビティで構成する必要があります。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>複数選択モードを無効にします。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>選択したトランジションを開きます。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>選択が無効になっているか一時停止としてマークされている場合は、選択を再有効にします。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>コピーされたアクティビティを貼り付けます。

## クイックアクション {#quick-actions}

アクティビティを選択すると、アクティビティの周りにクイックアクションボタンが表示され、ユーザーが操作できるようになります。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>選択したアクティビティを開きます。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>選択した電子メールまたはSMS配信アクティビティの詳細オプションを開きます。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>選択が無効になっているか一時停止としてマークされている場合は、選択を再有効にします。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>選択範囲を直ちに処理します。 このボタンは、<span class="uicontrol">スケジューラー</span>および<span class="uicontrol">待機</span>アクティビティでのみ使用できます。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。

## ワークフローアクティビティの複製 {#duplicating-workflow-activities}

ワークスペースを使用すると、ワークフローアクティビティをコピーして同じワークフロー内に貼り付けたり、同じキャンペーンインスタンスから別のワークフロー内に貼り付けたりして重複できます。

アクティビティを複製すると、その設定全体が保持されます。 配信アクティビティ（電子メール、SMS、プッシュ通知など）の場合、アクティビティに関連付けられている配信オブジェクトが複製されます。

>[!NOTE]
>
>ワークフローアクティビティをインスタンス間で複製することはできません。 テクニカルワークフローからのアクティビティは複製できません。

アクティビティを重複するには、次の手順に従います。

1. アクティビティを選択し、クイックアクションの **[!UICONTROL Copy selection]** ボタンをクリックします。

   キーボードショートカットの **Ctrl + C** (C)を使用することもできます。

   ![](assets/wkf_copypaste1.png)

1. ターゲットワークフローワークスペース内で右クリックし、 **[!UICONTROL Paste]** ボタンをクリックします。

   [ **Ctrl] + [V** ]キーボードショートカットを使用することもできます。

   ![](assets/wkf_copypaste2.png)

1. アクティビティは複製され、最初に設定されたすべての設定が反映されます。

複数のアクティビティをコピー&amp;ペーストして、ワークフロー全体を重複することもできます。

これを行うには、アクティビティの周りにゾーンを描画して選択します。 次に、アクションバーの **[!UICONTROL Copy selection]** ボタンをクリックします(または、 **Ctrl + C**)。 その後、それらを目的の場所に貼り付けることができます。

![](assets/wkf_copypaste3.png)

