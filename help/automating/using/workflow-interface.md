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

ワークフローを作成して、キャンペーンおよびプログラムのプロセス全体を管理できます。

ワークフロー編集画面は、次の要素で構成されています。

* The [パレット](#palette)：使用可能なアクティビティを参照します。
* The [Workspace](#workspace)：アクティビティを設定および整理します。
* The [アクションバー](#action-bar)：ワークフローやそのコンポーネントを操作するためのボタンで構成されています。
* The [クイックアクション](#quick-actions)（選択したアクティビティの周囲に表示され、操作できます）

![](assets/wkf_overview.png)

## パレット {#palette}

パレットは画面の左側に表示されます。 使用可能なすべてのアクティビティは、次のように複数のカテゴリに分類されます。

* [ターゲット設定](../../automating/using/about-targeting-activities.md)：ターゲティング、母集団データの操作、フィルターアクティビティに固有のアクティビティ
* [実行](../../automating/using/about-execution-activities.md)：ワークフローの整理と実行に固有のアクティビティ
* [チャネル](../../automating/using/about-channel-activities.md)：使用可能な様々な通信チャネルを表すアクティビティ
* [データ管理 (ETL)](../../automating/using/about-data-management-activities.md)：データの操作固有のアクティビティ

ワークフローのパレットの「 」アクティビティを使用するには、ワークスペースに「 」アクティビティをドラッグ&amp;ドロップします。

ワークフローを開始する前に、パレットから追加した各アクティビティを設定する必要があります。

![](assets/workflow_palette.png)

## ワークスペース {#workspace}

ワークスペースは、ワークフローエディターの中央のゾーンです。 このゾーンでは、アクティビティをドロップし、トランジションを使用して相互にリンクし、設定できます。

2 つのアクティビティをリンクするには、最初のアクティビティの矢印の終わりを、接続するまで次のアクティビティに移動します。 また、前のアクティビティにリンクするために、アクティビティを後ろの矢印のポイントに向かって移動することもできます。 いずれかのアクティビティを移動しても、そのアクティビティはリンクされたままになります。

データを処理するアクティビティに続くトランジションには、中間母集団が含まれます。 これらにアクセスするには、 **[!UICONTROL Keep interim results]** オプションを **[!UICONTROL Execution]** 」セクションに表示されます。

>[!CAUTION]
>
>このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。実稼働インスタンスでは、このチェックボックスをオフのままにします。


アクティビティを選択すると、アクティビティの周囲にクイックアクションが表示され、操作できます。 例えば、アクティビティを設定するには、アクティビティを選択し、 ![](assets/edit_darkgrey-24px_table.png) ボタンをクリックします。

特定の関数は、ワークスペースでのみ有効です。

* 複数のアクティビティとトランジションを選択するには、それらのアクティビティとトランジションの周りにゾーンを描画します。
* 押す **Ctrl** +左クリックして、複数のアクティビティやトランジションを選択します。
* 押す **入力** ：現在選択されているアクティビティまたはトランジションの詳細を表示します。
* 押す **削除** をクリックして、現在選択しているアクティビティを削除します。
* 押す **Ctrl + C** 選択したアクティビティをコピーするには、 **Ctrl + V** をクリックして、ワークスペースに貼り付けます。

![](assets/workflow_workspace.png)

## アクションバー {#action-bar}

ワークスペースで選択した要素またはワークフローの実行ステータスに応じて、アクションバーに表示されるボタンが変わる場合があります。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>ワークフローのプロパティを編集できます。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>ワークフローを開始します。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>ワークフローを一時停止します。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>ワークフローの実行を中断します。 停止した場所から再開できません。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>ワークフローを再開します。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>ワークフローの実行ログを開きます。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>複数選択モードを有効にします。 ワークフローは、少なくとも 2 つのアクティビティで構成する必要があります。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>複数選択モードを無効にします。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>選択したトランジションを開きます。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>選択が以前に無効になっているか、一時停止とマークされている場合、再度有効にします。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>コピーしたアクティビティを貼り付けます。

## クイックアクション {#quick-actions}

アクティビティを選択すると、アクティビティの周囲にクイックアクションボタンが表示され、操作できます。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>選択したアクティビティを開きます。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>選択した「 E メールまたは SMS 配信」アクティビティの詳細オプションを開きます。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>選択が以前に無効になっているか、一時停止とマークされている場合、再度有効にします。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>選択を強制的に即時に処理します。 このボタンは、 <span class="uicontrol">スケジューラ</span> および <span class="uicontrol">待機</span> アクティビティ。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。

## ワークフローアクティビティの複製 {#duplicating-workflow-activities}

ワークスペースでは、同じワークフローにコピー&amp;ペーストすることで、または同じ Campaign インスタンスから別のワークフローにコピー&amp;ペーストすることで、ワークフローアクティビティを複製できます。

アクティビティを複製すると、その設定全体が保持されます。 配信アクティビティ（E メール、SMS、プッシュ通知など）の場合は、アクティビティに添付されている配信オブジェクトが複製されます。

>[!NOTE]
>
>ワークフローアクティビティは、インスタンスから別のインスタンスに複製できません。 テクニカルワークフローのアクティビティは複製できません。

アクティビティを複製するには、次の手順に従います。

1. アクティビティを選択し、 **[!UICONTROL Copy selection]** 」ボタンをクリックします。

   また、 **Ctrl + C** キーボードショートカット。

   ![](assets/wkf_copypaste1.png)

1. ターゲットワークフローワークスペース内で右クリックし、 **[!UICONTROL Paste]** 」ボタンをクリックします。

   また、 **Ctrl + V** キーボードショートカット。

   ![](assets/wkf_copypaste2.png)

1. アクティビティが複製され、最初に設定されたすべての設定が反映されます。

複数のアクティビティをコピー&amp;ペーストして、ワークフロー全体を複製することもできます。

それには、アクティビティの周りにゾーンを描いて、アクティビティを選択します。 次に、 **[!UICONTROL Copy selection]** アクションバーのボタン ( または **Ctrl + C**) をクリックします。 その後、それらを目的の場所に貼り付けることができます。

![](assets/wkf_copypaste3.png)
