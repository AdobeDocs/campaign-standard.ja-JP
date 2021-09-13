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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---

# ワークフローインターフェイス{#workflow-interface}

ワークフローを作成して、キャンペーンおよびプログラムのプロセス全体を管理できます。

ワークフロー編集画面は、次の要素で構成されています。

* [パレット](#palette)。使用可能なアクティビティを参照します。
* アクティビティが設定および整理される[Workspace](#workspace)。
* [アクションバー](#action-bar)は、ワークフローやそのコンポーネントを操作するためのボタンで構成されています。
* [クイックアクション](#quick-actions)は、選択したアクティビティの周囲に表示され、操作できます。

![](assets/wkf_overview.png)

## パレット {#palette}

パレットは画面の左側に表示されます。 使用可能なすべてのアクティビティは、次のように複数のカテゴリに分類されます。

* [ターゲット設定](../../automating/using/about-targeting-activities.md):アクティビティ（ターゲット設定、母集団データの操作、フィルターアクティビティに固有）
* [実行](../../automating/using/about-execution-activities.md):ワークフローの整理と実行に固有のアクティビティ
* [チャネル](../../automating/using/about-channel-activities.md):様々な使用可能な通信チャネルを表すアクティビティ
* [データ管理(ETL)](../../automating/using/about-data-management-activities.md):データの操作に特有のアクティビティ

ワークフローのパレットの「 」アクティビティを使用するには、ワークスペースに「 」アクティビティをドラッグ&amp;ドロップします。

ワークフローを開始する前に、パレットから追加した各アクティビティを設定する必要があります。

![](assets/workflow_palette.png)

## ワークスペース {#workspace}

ワークスペースは、ワークフローエディターの中央ゾーンです。 このゾーンでは、アクティビティをドロップし、トランジションを使用してリンクし、設定できます。

2つのアクティビティをリンクするには、最初のアクティビティの矢印の終わりを次のアクティビティに移動して、接続します。 前のアクティビティにリンクするために、アクティビティを後ろの矢印の点に向かって移動することもできます。 いずれかのアクティビティを移動すると、そのアクティビティはリンクされたままになります。

データを処理するアクティビティに続くトランジションには、中間母集団が含まれます。 ワークフロープロパティの「**[!UICONTROL Execution]**」セクションで「**[!UICONTROL Keep interim results]**」オプションをオンにすると、これらのオプションにアクセスできます。

>[!CAUTION]
>
>このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。実稼働インスタンスでは、このチェックボックスをオフのままにします。


アクティビティを選択すると、そのアクティビティの周囲にクイックアクションが表示され、アクティビティを操作できます。 例えば、アクティビティを設定するには、アクティビティを選択し、クイックアクションの![](assets/edit_darkgrey-24px_table.png)ボタンを使用して開きます。

特定の関数はワークスペースでのみ有効です。

* 複数のアクティビティとトランジションを選択し、その周りにゾーンを描画します。
* **Ctrl**&#x200B;キーを押しながら左クリックして、複数のアクティビティやトランジションを選択します。
* **Enter**&#x200B;キーを押して、現在選択されているアクティビティまたはトランジションの詳細を表示します。
* **Delete**&#x200B;キーを押すと、現在選択されているアクティビティが削除されます。
* **Ctrl + C**&#x200B;キーを押して選択したアクティビティをコピーし、**Ctrl + V**&#x200B;キーを押してワークスペースに貼り付けます。

![](assets/workflow_workspace.png)

## アクションバー {#action-bar}

ワークスペースで選択した要素またはワークフローの実行ステータスに応じて、アクションバーで使用できるボタンが異なる場合があります。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>ワークフローのプロパティを編集できます。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>ワークフローを開始します。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>ワークフローを一時停止します。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>ワークフローの実行を中断します。停止した場所から再開できません。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>ワークフローを再起動します。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>ワークフローの実行ログを開きます。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>複数選択モードを有効にします。ワークフローは、少なくとも2つのアクティビティで構成する必要があります。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>複数選択モードを無効にします。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>選択したトランジションを開きます。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>選択が無効になっているか、一時停止とマークされている場合、再度有効にします。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>コピーしたアクティビティを貼り付けます。

## クイックアクション {#quick-actions}

アクティビティを選択すると、アクティビティの周囲にクイックアクションボタンが表示され、アクティビティを操作できます。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>選択したアクティビティを開きます。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>選択したEメールまたはSMS配信アクティビティの詳細オプションを開きます。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>選択が無効になっているか、一時停止とマークされている場合、再度有効にします。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>選択を即時に処理します。このボタンは、<span class="uicontrol">スケジューラー</span>および<span class="uicontrol">待機</span>アクティビティでのみ使用できます。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。

## ワークフローアクティビティの複製 {#duplicating-workflow-activities}

ワークスペースでは、ワークフローアクティビティをコピー&amp;ペーストして、同じワークフローに複製したり、同じCampaignインスタンスから別のワークフローに複製したりできます。

アクティビティを複製すると、その設定全体が保持されます。 配信アクティビティ（Eメール、SMS、プッシュ通知など）の場合は、アクティビティに添付された配信オブジェクトを複製します。

>[!NOTE]
>
>ワークフローアクティビティは、インスタンスから別のインスタンスに複製できません。 テクニカルワークフローのアクティビティは複製できません。

アクティビティを複製するには、次の手順に従います。

1. アクティビティを選択し、クイックアクションの「**[!UICONTROL Copy selection]**」ボタンをクリックします。

   **Ctrl + C**&#x200B;キーボードショートカットを使用することもできます。

   ![](assets/wkf_copypaste1.png)

1. ターゲットワークフローワークスペース内を右クリックし、「**[!UICONTROL Paste]**」ボタンをクリックします。

   **CTRL + V**&#x200B;キーボードショートカットを使用することもできます。

   ![](assets/wkf_copypaste2.png)

1. アクティビティが複製され、最初に設定されたすべての設定が反映されます。

複数のアクティビティをコピー&amp;ペーストして、ワークフロー全体を複製することもできます。

それには、アクティビティの周りにゾーンを描いて、アクティビティを選択します。 次に、アクションバーの「**[!UICONTROL Copy selection]**」ボタンをクリックします（または&#x200B;**Ctrl + C**&#x200B;キーを押します）。 その後、目的の場所に貼り付けることができます。

![](assets/wkf_copypaste3.png)
