---
title: ワークフローの作成
description: ここでは、新しいワークフローを作成するための主な原則とベストプラクティスについて説明します。
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 422f5eb7011dfcc1d923079e7346394a64934a9a
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 10%

---


# ワークフローの作成{#building-a-workflow}

ここでは、新しいワークフローを作成するための主な原則とベストプラクティスについて説明します。

## ワークフローの運用原則{#workflow-operating-principles}

ワークフローは設定可能なアクティビティの **シーケンス**。 各アクティビティはプロセス内で特定の役割を持ちます。 各アクティビティの結果は、矢印で表された **トランジション**、次のアクティビティに転送されます。

あるアクティビティと別のアクティビティとの間でやり取りされるデータのタイプは、次のの設定方法に影響を与える可能性があります。 例えば、電子メール配信アクティビティの前に訪問者が確立された場合、その訪問者は該当する電子メールのターゲットとして機能します。

アクティビティを開いて、ワークフローの実行前または実行後に、パラメーターを確認または編集できます。

トランジションを開いて、ワークフローの実行中または実行後に送信されたデータが正しいかどうかを確認できます。 トランジションの詳細表示にアクセスするには、ワークフロープロパティの **[!UICONTROL Keep interim results]****[!UICONTROL Execution]** セクションでオプションを確認する必要があります。

![](assets/workflow_overview.png)


## ワークフローの作成 {#creating-a-workflow}

ワークフローは、プログラム、キャンペーン、またはマーケティングアクティビティリストから作成できます。

マーケティングアクティビティの作成について詳しくは、「マーケティングアクティビティの [作成](../../start/using/marketing-activities.md#creating-a-marketing-activity) 」の節を参照してください。

1. ワークフロータイプのマーケティングアクティビティの作成を開始したら、使用するテンプレートを選択します。

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >各マーケティングアクティビティオファーは、デフォルトで複数のタイプをします。 これらを使用すると、ニーズに応じて特定のパラメーターを事前設定できます。 For more information, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. ワークフローの一般的なプロパティを入力します。

   ![](assets/workflow_creation_2.png)

   「 **ラベル** 」フィールドに名前を入力し、IDを変更できます。 アクティビティ名とそのIDはインターフェイスに表示されますが、メッセージ受信者には表示されません。

   >[!NOTE]
   >
   >マーケティングアクティビティのリストから、親キャンペーン内にワークフローを作成できます。 既に作成済みのワークフローを選択して、このキャンペーンをワークフローにリンクさせることができます。

   ユーザーがキャンペーンのコンテンツで表示できる説明を追加できます。

   ワークフローには、適切な名前とラベルを付けることをお勧めします。そうすると、正常に機能していないワークフローを簡単に見つけてトラブルシューティングできるようになります。また、オペレーターが理解しやすいように、実行される処理の概要をワークフローの説明フィールドに記述してください。

1. アクティビティの作成を確認し、そのアクティビティのダッシュボードが表示されます。 For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

1. ワークフローを設定する準備が整ったら、 **[!UICONTROL Edit properties]** ボタンをクリックして追加のオプションにアクセスできます。 例えば、デフォルトで使用する特定のタイムゾーンをワークフローのすべてのアクティビティに定義できます。 デフォルトでは、ワークフローのタイムゾーンは、現在のキャンペーン演算子に対して定義されたタイムゾーンです。

   ![](assets/workflow_properties.png)

**関連トピック:**

* [ワークフロー](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html) ・ビデオの作成
* [ワークフローのプロパティ](../../automating/using/managing-execution-options.md)

## アクティビティの追加とリンク {#adding-and-linking-activities}

ここでは、各種アクティビティを定義し、ダイアグラム内で互いにリンクする必要があります。

>[!NOTE]
>
>パレットが表示されていない場合は、ツールバーの最初のボタンをクリックして表示します。

アクティビティは、パレットの異なるセクション内でカテゴリ別にグループ化されます。

* 最初の節には、ター [ゲティングのアクティビティが含まれています](../../automating/using/about-targeting-activities.md)
* The second section contains the [execution activities](../../automating/using/about-execution-activities.md), which are mainly used for coordinating other activities.
* 3つ目の節には、異なる [チャネルでのメッセージの送信に使用できるアクティビティが含まれています](../../automating/using/about-channel-activities.md)。 このセクションのアクティビティは、インスタンスで有効になっているチャネルによって異なります。
* 4つ目のセクションには、 [ファイル操作とデータ管理アクティビティが含まれています](../../automating/using/about-data-management-activities.md)。

ダイアグラムを作成するには:

1. アクティビティ追加を表示します。

   例えば、図に **[開始](../../automating/using/start-and-end.md)**アクティビティを追加し、**[&#x200B;電子メール配信](../../automating/using/email-delivery.md)** アクティビティを追加します。

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >新しいアクティビティを前のアクティビティの最後に置くと、そのトランジションを自動的に前のフォルダにリンクできます。

1. 必要な追加アクティビティとそれらをリンクし、ワークフローを完了します。

   >[!NOTE]
   >
   >既存のアクティビティをコピー&amp;ペーストして重複することもできます。 これにより、最初に定義した設定を保持できます。 For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

ワークフローアクティビティを相互にリンクしたら、選択した **ラベルを使用して、トランジション間のユーザーをパーソナライズできます** 。 これを行うには、トランジションを重複クリックしてプロパティにアクセスします。

さらに、 **[!UICONTROL Targeting]** および **[!UICONTROL Data management (ETL)]** アクティビティでは、送信トランジションの **セグメントコードを定義できます** 。 その後、これらのセグメントコードに基づいてレポートを作成し、マーケティングキャンペーンの効率性を測定できます。 詳しくは、[この節](../../reporting/using/creating-a-report-workflow-segment.md)を参照してください。

**ワークフローの使用例：**

* [使用例： 週に1回の電子メール配信の作成](../../automating/using/workflow-weekly-offer.md)
* [使用例： 場所でセグメント化された配信の作成](../../automating/using/workflow-segmentation-location.md)
* [使用例： 補完的な配信の作成](../../automating/using/workflow-created-query-with-complement.md)
* [使用例： 非開封者に新しい配信を送信する再ターゲティングワークフロー](../../automating/using/workflow-cross-channel-retargeting.md)

## アクティビティの設定 {#configuring-activities}

デフォルトでは、アクティビティは設定されておらず、設定されていない場合はデータは正しく処理されません。 各アクティビティには、特定の設定や、アウトバウンドトランジション、ラベルなどのアクティビティの汎用オプションを管理するためのいくつかのタブが含まれています。

1. すべてのアクティビティが正しく接続されていることを確認します。 一部のアクティビティでは、正しい設定オプションをオファーするために、入力データの構造または特性を検出する必要があります。
1. アクティビティを重複クリックするか、選択し、コンテキストアクションをクリックして、設定ウィンドウを開きます。 **[!UICONTROL Edit]**
1. アクティビティのラベルを編集します。
1. データの処理に必要なすべての様々なオプションを定義します。 各アクティビティで使用できるオプションについては、アクティビティ固有のこのドキュメントのセクションを参照してください。
1. アクティビティを保存し、ワークフローの各アクティビティに対してこれらの操作を繰り返します。
1. ワークフローを保存します。
