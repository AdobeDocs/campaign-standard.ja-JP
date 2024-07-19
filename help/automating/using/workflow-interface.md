---
title: ワークフローインターフェイス
description: ワークフローを作成、編集、実行するためのインターフェイスとオプションについて説明します。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
role: Data Architect
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---

# ワークフローインターフェイス{#workflow-interface}

ワークフローを作成して、キャンペーンとプログラムのプロセス全体を管理できます。

ワークフロー編集画面は、次の要素で構成されています。

* 使用可能なアクティビティを参照する [ パレット ](#palette)。
* アクティビティが設定および整理される ](#workspace)0}Workspace}。[
* [ アクションバー ](#action-bar) は、ワークフローやそのコンポーネントを操作できるボタンで構成されています。
* 選択したアクティビティの周囲に表示される [ クイックアクション ](#quick-actions) を使用して、アクティビティを操作できます。

![](assets/wkf_overview.png)

## パレット {#palette}

パレットは画面の左側にあります。 使用可能なすべてのアクティビティは、複数のカテゴリに分類されます。

* [ ターゲティング ](../../automating/using/about-targeting-activities.md)：ターゲティング、母集団データの操作およびフィルタリングアクティビティに固有のアクティビティ
* [ 実行 ](../../automating/using/about-execution-activities.md)：ワークフローの整理と実行に固有のアクティビティ
* [ チャネル ](../../automating/using/about-channel-activities.md)：使用可能な様々な通信チャネルを表すアクティビティ
* [ データ管理（ETL） ](../../automating/using/about-data-management-activities.md)：データの操作に固有のアクティビティ

ワークフローでパレットのアクティビティを使用するには、アクティビティをワークスペースにドラッグ&amp;ドロップします。

ワークフローを開始する前に、パレットから追加した各アクティビティを設定する必要があります。

![](assets/workflow_palette.png)

## ワークスペース {#workspace}

ワークスペースは、ワークフローエディターの中心にあるゾーンです。 アクティビティをこのゾーンにドロップすると、トランジションを使用してリンクし、設定できます。

2 つのアクティビティをリンクするには、矢印の終点を最初のアクティビティから次のアクティビティに、それらが接続するまで移動します。 前のアクティビティにリンクするために、アクティビティをその背後にある矢印の点に向かって移動することもできます。 いずれかのアクティビティを移動すると、そのアクティビティのリンクが維持されます。

データを処理するアクティビティ以降のトランジションには、中間母集団が含まれます。 ワークフローのプロパティの「**[!UICONTROL Execution]**」セクションで「**[!UICONTROL Keep interim results]**」オプションをオンにすると、これらのプロパティにアクセスできます。

>[!CAUTION]
>
>このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。実稼働インスタンスでは、このチェックボックスをオフのままにします。


アクティビティを選択すると、アクティビティの周囲にクイックアクションが表示され、アクティビティを操作できます。 例えば、アクティビティを設定するには、アクティビティを選択してから、クイックアクションの「![](assets/edit_darkgrey-24px_table.png)」ボタンを使用して開きます。

次の特定の関数は、ワークスペースでのみ有効になります。

* 複数のアクティビティとトランジションを選択するには、それらを囲むゾーンを描画します。
* 複数のアクティビティやトランジションを選択するには、**Ctrl**+左クリックを押します。
* **Enter** キーを押して、現在選択されているアクティビティまたはトランジションの詳細を表示します。
* 現在選択されているアクティビティを削除するには、「**削除**」を押します。
* 選択したアクティビティをコピーするには **Ctrl + C** を押し、ワークスペースに貼り付けるには **Ctrl + V** を押します。

![](assets/workflow_workspace.png)

## アクションバー {#action-bar}

ワークスペースまたはワークフローの実行ステータスで選択した要素に応じて、アクションバーで使用できるボタンは異なる場合があります。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>ワークフローのプロパティを編集できます。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>ワークフローを開始。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>ワークフローを一時停止します。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>ワークフローの実行を中断します。 を停止した位置から再開することはできません。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>ワークフローを再開します。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>ワークフローの実行ログを開きます。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>複数選択モードを有効にします。 ワークフローは、少なくとも 2 つのアクティビティで構成されている必要があります。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>複数選択モードを無効にします。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>選択したトランジションを開きます <br />。

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>以前に無効または一時停止としてマークされていた場合、選択を再度有効にします。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択されているアクティビティを削除します。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>コピーされたアクティビティを貼り付けます。

## クイックアクション {#quick-actions}

アクティビティを選択すると、アクティビティの周囲にクイックアクションボタンが表示され、アクティビティを操作できます。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>選択したアクティビティを開きます。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>選択したメールまたは SMS 配信アクティビティの詳細オプションを開きます。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>以前に無効または一時停止としてマークされていた場合、選択を再度有効にします。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>選択範囲の処理を強制的に即座に行います。 このボタンは、<span class="uicontrol"> スケジューラー </span> アクティビティと <span class="uicontrol"> 待機 </span> アクティビティでのみ使用できます。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択されているアクティビティを削除します。

## ワークフローアクティビティの複製 {#duplicating-workflow-activities}

ワークスペースでは、ワークフローアクティビティを複製できます。複製するには、同じワークフローまたは同じ Campaign インスタンスから別のワークフローにアクティビティをコピーして貼り付けます。

アクティビティが重複しても、設定全体が保持されます。 配信アクティビティ（メール、SMS、プッシュ通知など）の場合は、アクティビティに添付された配信オブジェクトが複製されます。

>[!NOTE]
>
>ワークフローアクティビティを 1 つのインスタンスから別のインスタンスに複製することはできません。 テクニカルワークフローのアクティビティは複製できません。

アクティビティを複製するには、次の手順に従います。

1. アクティビティを選択し、クイックアクションから「**[!UICONTROL Copy selection]**」ボタンをクリックします。

   **Ctrl + C** キーボードショートカットも使用できます。

   ![](assets/wkf_copypaste1.png)

1. ターゲットのワークフローワークスペースを右クリックしてから、「**[!UICONTROL Paste]**」ボタンをクリックします。

   **Ctrl + V** キーボードショートカットを使用することもできます。

   ![](assets/wkf_copypaste2.png)

1. アクティビティが複製され、最初に設定されたすべての設定が含まれます。

複数のアクティビティをコピーして貼り付けることもできます。これにより、ワークフロー全体を複製できます。

それには、アクティビティの周囲にゾーンを描画して、アクティビティを選択します。 次に、アクションバーの「**[!UICONTROL Copy selection]**」ボタンをクリックします（または **Ctrl+C** キーを押します）。 その後、目的の場所に貼り付けることができます。

![](assets/wkf_copypaste3.png)
