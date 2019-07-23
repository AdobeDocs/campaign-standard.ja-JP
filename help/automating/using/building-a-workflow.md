---
title: ワークフローの作成
seo-title: ワークフローの作成
description: ワークフローの作成
seo-description: ここでは、新しいワークフロー作成の主な原則とベストプラクティスについて説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow- general- operation
discoiquuid: c26fcb0e-19d5-4bd5- b7d6-2d22ce92ad90
context-tags: ワークフロー、ウィザード、ワークフロー、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51154892b2d5bd5685272735cdd6e7d9474e09a6

---


# Building a workflow{#building-a-workflow}

ここでは、新しいワークフローを作成する際の主な原則とベストプラクティスについて説明します。

* ワークフローを作成します。
* アクティビティの追加とリンク。
* アクティビティの設定を参照してください。

## Creating a workflow {#creating-a-workflow}

プログラム、キャンペーンまたはマーケティングアクティビティリストからワークフローを作成できます。

Creating a marketing activity is detailed in the [Creating marketing activities](../../start/using/marketing-activities.md#creating-a-marketing-activity) section.

1. ワークフロータイプのマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >各マーケティングアクティビティには、デフォルトでいくつかのタイプがあります。これらにより、ニーズに応じて特定のパラメーターを事前設定できます。For more information, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. ワークフローの一般的なプロパティを入力します。

   ![](assets/workflow_creation_2.png)

   **「ラベル」** フィールドに名前を入力し、IDを変更できます。アクティビティ名とそのIDはインターフェイスに表示されますが、メッセージの受信者によって表示されません。

   >[!NOTE]
   >
   >マーケティングアクティビティのリストから、親キャンペーン内でワークフローを作成できます。既に作成されているキャンペーンを選択して、このワークフローをキャンペーンにリンクできます。

   キャンペーンコンテンツでユーザーに表示できる説明を追加できます。

   予期した方法で動作しない場合、見つけやすくトラブルシューティングが簡単になるため、ワークフローに適切な名前とラベルを付けることをお勧めします。ワークフローの説明フィールドに入力して、演算子が簡単に理解できるようにプロセスを要約します。

1. アクティビティの作成を確認し、そのアクティビティのダッシュボードを表示します。For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

**関連トピック:**

[ワークフロー](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) ビデオの作成

## Adding and linking activities {#adding-and-linking-activities}

これで、様々なアクティビティを定義し、それらのアクティビティを図内でリンクする必要があります。

>[!NOTE]
>
>パレットが表示されていない場合は、ツールバーの最初のボタンをクリックして表示します。

アクティビティは、パレットの別のセクションのカテゴリごとにグループ化されます。

* 最初のセクションには、ターゲットアクティビティが含まれています。
* 2番目のセクションには、主に他のアクティビティの調整に使用される実行アクティビティが含まれています。
* 3番目のセクションには、様々なチャネルにメッセージを送信するために使用できるアクティビティが含まれています。このセクションのアクティビティは、インスタンスで有効になっているチャネルによって異なる可能性があります。
* 4番目のセクションには、ファイル操作およびデータ管理アクティビティが含まれています。

図を作成するには:

1. アクティビティを追加するには、パレットからドラッグして、図にドロップします。

   For example, add a **Start** activity and then an **Email delivery** activity on the diagram.

1. **開始** アクティビティのトランジションをドラッグして **、電子メール配信** アクティビティにドロップして、アクティビティをリンクします。

   >[!NOTE]
   >
   >以前のアクティビティをトランジションの最後に配置することで、アクティビティを自動的に前のアクティビティにリンクできます。

1. 必要なアクティビティを追加し、連携してワークフローを完了します。

   >[!NOTE]
   >
   >コピー&amp;ペーストで既存のアクティビティを複製することもできます。このようにして、当初定義されていた設定を維持します。For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Once your workflow activities are linked together, you can personalize the transitions between them with the **label** of your choice. そのためには、トランジションをダブルクリックしてプロパティにアクセスします。

**[!UICONTROL Targeting]****[!UICONTROL Data management (ETL)]** また、アクティビティによって、アウトバウンドトランジションの **セグメントコード** を定義できます。その後、マーケティングキャンペーンの効率を測定するために、これらのセグメントコードに基づいてレポートを作成できます。For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

## Configuring activities {#configuring-activities}

デフォルトでは、アクティビティは設定されず、設定されていない場合はデータが正しく処理されません。各アクティビティには、特定の設定や、アウトバウンドトランジション、ラベルなどのアクティビティの汎用オプションを管理するためのいくつかのタブが含まれています。

1. すべてのアクティビティが正しく接続されていることを確認します。一部のアクティビティでは、入力データの構造または特性を検出して、適切な設定オプションを提供する必要があります。
1. Double-click an activity or select it and click the **[!UICONTROL Edit]** contextual action to open its configuration window.
1. アクティビティのラベルを編集します。
1. データの処理に必要なすべてのオプションを定義します。各アクティビティについて可能なオプションを学習するには、このドキュメントのアクティビティの具体的なセクションを参照してください。
1. アクティビティを保存し、ワークフローのアクティビティごとにこれらの操作を繰り返します。
1. ワークフローを保存します。

