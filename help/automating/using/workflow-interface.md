---
title: ワークフローインターフェイス
description: ワークフローを作成、編集、実行するためのインターフェイスとオプションについて説明します。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
TQID: https://experienceleague.adobe.com/yE5oFC7pHpJPh1NC0jMvVu-VfY-sFhgbSB4tqw55R-M
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: a4671286-a59f-47e3-b97b-90627a1977d5id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 845
ht-degree: 5%

---

# ワークフローインターフェイス{#workflow-interface}

ワークフローを作成して、キャンペーンやプログラムのプロセス全体を管理できます。

ワークフロー編集画面は、次の要素で構成されます。

* 使用可能なアクティビティを参照する[ パレット ](#palette)。
* アクティビティが設定および整理された[Workspace](#workspace)。
* [ アクションバー](#action-bar)は、ワークフローやそのコンポーネントを操作できるボタンで構成されています。
* 選択したアクティビティの周囲に表示される[ クイックアクション ](#quick-actions)を使用すると、このアクティビティを操作できます。

![](assets/wkf_overview.png)

![](assets/do-not-localize/how-to-video.png) [ ビデオでワークフローを作成する方法を確認](#video)

## パレット {#palette}

パレットは画面の左側にあります。 使用可能なすべてのアクティビティは、次のカテゴリに分類されます。

* [ ターゲティング ](../../automating/using/about-targeting-activities.md)：ターゲティング、母集団データの操作、およびアクティビティのフィルタリングに固有のアクティビティ
* [実行](../../automating/using/about-execution-activities.md): ワークフローの整理と実行に固有のアクティビティ
* [ チャネル ](../../automating/using/about-channel-activities.md)：使用可能な様々なコミュニケーションチャネルを表すアクティビティ
* [ データ管理（ETL） ](../../automating/using/about-data-management-activities.md)：データ操作に固有のアクティビティ

ワークフローのパレットからアクティビティを使用するには、それをワークスペースにドラッグ&amp;ドロップします。

ワークフローを開始する前に、パレットから追加された各アクティビティを設定する必要があります。

![](assets/workflow_palette.png)

## ワークスペース {#workspace}

ワークスペースは、ワークフローエディターの中央ゾーンです。 このゾーンでは、アクティビティをドロップし、トランジションを使用してアクティビティをリンクし、設定できます。

2つのアクティビティをリンクするには、最初のアクティビティから次のアクティビティまで、矢印の端を接続するまで移動します。 アクティビティを前のアクティビティにリンクするために、その後ろの矢印のポイントに向かってアクティビティを移動することもできます。 いずれかのアクティビティを移動しても、リンクされたままになります。

データを処理するアクティビティに続くトランジションには、中間母集団が含まれます。 ワークフロープロパティの「**[!UICONTROL Execution]**」セクションの「**[!UICONTROL Keep interim results]**」オプションをオンにすると、アクセスできます。

>[!CAUTION]
>
>このオプションは、多くのディスク領域を消費しますが、ワークフローの作成と適切な設定および動作の確保に役立つように設計されています。 実稼働インスタンスでは、このチェックボックスをオフのままにします。


アクティビティを選択すると、アクティビティの周囲にクイックアクションが表示され、アクティビティを操作できます。 例えば、アクティビティを設定するには、アクティビティを選択し、クイックアクションの「![](assets/edit_darkgrey-24px_table.png)」ボタンを使用してアクティビティを開きます。

特定の機能は、ワークスペースでのみ有効になります。

* その周りにゾーンを描画して、いくつかのアクティビティとトランジションを選択します。
* **Ctrl** +左クリックを押して、複数のアクティビティやトランジションを選択します。
* 現在選択されているアクティビティまたはトランジションの詳細を表示するには、**Enter**&#x200B;を押します。
* 現在選択されているアクティビティを削除するには、**削除**&#x200B;を押します。
* 選択したアクティビティをコピーするには&#x200B;**Ctrl + C**&#x200B;を押し、ワークスペースに貼り付けるには&#x200B;**Ctrl + V**&#x200B;を押します。

![](assets/workflow_workspace.png)

## アクションバー {#action-bar}

ワークスペースまたはワークフローの実行ステータスで選択した要素によって、アクションバーで使用できるボタンが異なる場合があります。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>ワークフローのプロパティを編集できます。

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>ワークフローを開始します。

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>ワークフローを一時停止します。

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>ワークフローの実行を中断します。 停止した場所から再開できません。

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>ワークフローを再起動します。

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>ワークフローの実行ログを開きます。

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>複数選択モードを有効にします。 ワークフローは、少なくとも2つのアクティビティで構成する必要があります。

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>複数選択モードを無効にします。<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>選択したトランジションを開きます。<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>以前に無効化または一時停止としてマークされている場合は、選択を再度有効にします。<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>コピーしたアクティビティを貼り付けます。

## クイックアクション {#quick-actions}

アクティビティを選択すると、アクティビティの周囲にクイックアクションボタンが表示され、アクティビティを操作できます。

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>選択したアクティビティを開きます。

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>選択したアクティビティをコピーします。

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>選択した電子メールまたはSMS配信アクティビティの詳細オプションを開きます。

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>以前に無効化または一時停止としてマークされている場合は、選択を再度有効にします。

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>選択したアクティビティでワークフローを一時停止します。

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>アクティビティを無効にします。

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>選択を直ちに処理します。 このボタンは、<span class="uicontrol"> スケジューラー</span>および<span class="uicontrol">待機</span> アクティビティでのみ使用できます。

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>選択したアクティビティを削除します。

## ワークフローアクティビティの複製 {#duplicating-workflow-activities}

ワークスペースを使用すると、ワークフローアクティビティを同じワークフローにコピー&amp;ペーストしたり、同じCampaign インスタンスから別のワークフローにコピーしたりして、ワークフローアクティビティを複製できます。

アクティビティが複製されると、その設定全体が保持されます。 配信アクティビティ（電子メール、SMS、プッシュ通知など）の場合、アクティビティに添付された配信オブジェクトが複製されます。

>[!NOTE]
>
>ワークフローアクティビティをインスタンスから別のインスタンスに複製することはできません。 テクニカルワークフローのアクティビティは複製できません。

アクティビティを複製するには、次の手順に従います。

1. アクティビティを選択し、クイックアクションから「**[!UICONTROL Copy selection]**」ボタンをクリックします。

   **Ctrl + C** キーボードショートカットを使用することもできます。

   ![](assets/wkf_copypaste1.png)

1. 対象のワークフローワークスペースで右クリックし、**[!UICONTROL Paste]** ボタンをクリックします。

   **CTRL + V** キーボードショートカットを使用することもできます。

   ![](assets/wkf_copypaste2.png)

1. アクティビティが複製され、最初に設定されたすべての設定が複製されます。

複数のアクティビティをコピー&amp;ペーストして、ワークフロー全体を複製することもできます。

これを行うには、アクティビティの周囲にゾーンを描画してアクティビティを選択します。 次に、アクションバーから&#x200B;**[!UICONTROL Copy selection]** ボタンをクリックします（または&#x200B;**Ctrl + C** キーを押します）。 次に、それらを目的の場所に貼り付けることができます。

![](assets/wkf_copypaste3.png)

## チュートリアルビデオ {#video}

このビデオでは、ワークフローの作成方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/23937?quality=12)

その他のCampaign Standardのハウツー動画は[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)でご覧いただけます。
