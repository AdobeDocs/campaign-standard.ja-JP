---
title: ワークフローの作成
description: ここでは、新しいワークフローを作成する際の主な原則とベストプラクティスについて説明します。
page-status-flag: 非活性化の
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: ワークフロー，ウィザード；ワークフロー，メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ワークフローの作成{#building-a-workflow}

ここでは、新しいワークフローの作成に関する主な原則およびベストプラクティスについて説明します。

* ワークフローの作成.
* アクティビティの追加とリンク
* アクティビティの設定

## ワークフローの作成 {#creating-a-workflow}

プログラム、キャンペーンまたはマーケティングアクティビティリストからワークフローを作成できます。

マーケティングアクティビティの作成について詳しくは、「マーケテ [ィングアクティビティの作成](../../start/using/marketing-activities.md#creating-a-marketing-activity) 」の節を参照してください。

1. ワークフロータイプのマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >各マーケティングアクティビティには、デフォルトで複数のタイプがあります。 これにより、ニーズに合わせて特定のパラメーターを事前設定できます。 For more information, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. ワークフローの一般的なプロパティを入力します。

   ![](assets/workflow_creation_2.png)

   「ラベル」フィールドに名前を入力し **て** 、IDを変更できます。 アクティビティ名とそのIDはインターフェイスに表示されますが、メッセージの受信者には表示されません。

   >[!NOTE]
   >
   >マーケティングアクティビティのリストから親キャンペーン内にワークフローを作成できます。 既に作成済みのワークフローを選択すると、このワークフローをキャンペーンにリンクできます。

   キャンペーンのコンテンツでユーザーが表示できる説明を追加できます。

   ワークフローには、適切な名前とラベルを付けることをお勧めします。そうすると、正常に機能していないワークフローを簡単に見つけてトラブルシューティングできるようになります。また、オペレーターが理解しやすいように、実行される処理の概要をワークフローの説明フィールドに記述してください。

1. アクティビティの作成を確認し、そのアクティビティのダッシュボードが表示されます。 For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

**関連トピック：**

[ワークフロービデオの作成](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) （英語のみ）

## アクティビティの追加とリンク {#adding-and-linking-activities}

ここでは、各種アクティビティを定義し、ダイアグラム内で互いにリンクする必要があります。

>[!NOTE]
>
>パレットが表示されていない場合は、ツールバーの最初のボタンをクリックして表示します。

アクティビティは、パレットの異なるセクション内でカテゴリ別にグループ化されます。

* 最初のセクションには、ターゲット設定アクティビティが含まれています。
* 2つ目の節では、実行アクティビティについて説明します。このアクティビティは、主に他のアクティビティの調整に使用されます。
* 3つ目の節には、異なるチャネルでのメッセージの送信に使用できるアクティビティが含まれています。 このセクションのアクティビティは、インスタンスで有効になっているチャネルによって異なる場合があります。
* 4つ目のセクションには、ファイル操作とデータ管理アクティビティが含まれています。

ダイアグラムを作成するには:

1. アクティビティを追加するには、アクティビティをパレットからドラッグし、図にドロップします。

   例えば、図に開始アクティビティ **を追加し** 、次に **** 電子メール配信アクティビティを追加します。

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >前のアクティビティのトランジションの最後に新しいアクティビティを配置することで、アクティビティを前のアクティビティに自動的にリンクできます。

1. 必要なアクティビティを追加し、それらをリンクしてワークフローを完了します。

   >[!NOTE]
   >
   >既存のアクティビティをコピー&amp;ペーストして複製することもできます。 これにより、元々定義された設定を保持できます。 For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

ワークフローアクティビティをリンクしたら、選択したラベルを使用して、アクティビティ間の移行をパー **ソナライズ** できます。 これを行うには、トランジションをダブルクリックして、そのプロパティにアクセスします。

さらに、アクティビティ **[!UICONTROL Targeting]** では、ア **[!UICONTROL Data management (ETL)]** ウトバウンド遷移のセグメ **ントコードを定義できます** 。 その後、これらのセグメントコードに基づいてレポートを作成し、マーケティングキャンペーンの効率を測定できます。 詳しくは、[この節](../../reporting/using/creating-a-report-workflow-segment.md)を参照してください。

**ワークフローの使用例：**

* [使用例：週に1回の電子メール配信の作成](../../automating/using/workflow-weekly-offer.md)
* [使用例：場所でセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [使用例：補完を含む配信の作成](../../automating/using/workflow-created-query-with-complement.md)
* [使用例：未開封者に新しい配信を送信する再ターゲットワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)

## アクティビティの設定 {#configuring-activities}

デフォルトでは、アクティビティは設定されず、設定されていない場合はデータが正しく処理されません。 各アクティビティには、特定の設定およびアクティビティの汎用オプション（アウトバウンド遷移、ラベルなど）を管理するためのいくつかのタブが含まれています。

1. すべてのアクティビティが正しく接続されていることを確認します。 一部のアクティビティでは、正しい設定オプションを提供するために、受信データの構造または性質を検出する必要があります。
1. アクティビティをダブルクリックするか、選択し、コンテキストアクションをク **[!UICONTROL Edit]** リックして、設定ウィンドウを開きます。
1. アクティビティのラベルを編集します。
1. データの処理に必要なすべての様々なオプションを定義します。 各アクティビティで使用できるオプションについては、このドキュメントのアクティビティ固有の節を参照してください。
1. アクティビティを保存し、ワークフローの各アクティビティに対してこれらの操作を繰り返します。
1. ワークフローを保存します。
