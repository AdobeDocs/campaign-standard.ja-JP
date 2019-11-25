---
title: 外部シグナル
description: 外部シグナルアクティビティは、別のワークフローで条件が満たされた場合にワークフローをトリガーします。
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# 外部シグナル{#external-signal}

## 説明 {#description}

![](assets/signal.png)

アクティビティ **[!UICONTROL External signal]** は、別のワークフローまたはREST API呼び出しから一部の条件が正常に満たされた場合に、ワークフローをトリガーします。

## 使用状況 {#context-of-use}

アクティビティ **[!UICONTROL External signal]** は、同じ顧客の様々なワークフローへの遍歴の一部である様々なプロセスを編成し、調整するために使用されます。 これにより、別のワークフローから開始でき、より複雑な顧客ジャーニーをサポートしながら、問題が発生した場合の監視と対応を改善できます。

アクテ **[!UICONTROL External signal]** ィビティは、ワークフローの最初のアクティビティとして配置されるように設計されています。 別のワークフローのアクティビティ **[!UICONTROL End]** またはREST API呼び出しからトリガーできます(詳しくは、 [APIのドキュメントを参照](../../api/using/managing-workflows.md))。

トリガーされると、外部パラメーターを定義し、ワークフローイベント変数で使用できるようになります。 外部パラメーターを使用してワークフローを呼び出すプロセスについては、この節 [で説明しま](../../automating/using/calling-a-workflow-with-external-parameters.md)す。

>[!NOTE]
>
>アクティビティは、10分に1回を超えてトリガーされることはできません。

アクティビティは、 **[!UICONTROL External signal]** 複数の異なるイベントからトリガーできます。 この場合、ソースワークフ **[!UICONTROL External signal]** ローまたはAPI呼び出しの1つが実行されるとすぐに、がトリガーされます。 すべてのソースワークフローを完了する必要はありません。

## 設定 {#configuration}

外部シグナルを設定する場合は、まず宛先ワークフローでアクティビティ **[!UICONTROL External signal]** を設定することが重要です。 この設定が完了すると、このワークフ **[!UICONTROL External signal]** ローのアクティビティを使用して、ソースワークフローのア **[!UICONTROL End]** クティビティを設定できます。

1. アクティビティを目的のワークフ **[!UICONTROL External signal]** ローにドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. アクティビティのラベルを編集します。 このラベルは、をトリガーするソースワークフローを設定する際に必要で **[!UICONTROL External signal]**&#x200B;す。

   パラメーターを使用してワークフローを呼び出す場合は、領域を使 **[!UICONTROL Parameters]** 用して宣言します。 詳しくは、[この節](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)を参照してください。

   ![](assets/external_signal_configuration.png)

1. アクティビティの設定を確認し、必要な他のアクティビティを追加して、ワークフローを保存します。

   >[!NOTE]
   >
   >別のワークフローから宛先ワークフローをトリガーする場合は、次の手順に従います。 REST API呼び出しから宛先ワークフローをトリガーする場合は、 [APIドキュメントを参照し](../../api/using/managing-workflows.md) 、詳細を確認してください。

1. ソースワークフローを開き、アクティビティを選 **[!UICONTROL End]** 択します。 使用できるアクティビティが **[!UICONTROL End]** ない場合は、ワークフローの分岐の最後のアクティビティの後に1つ追加します。

   一部のアクティビティには、デフォルトでアウトバウンドトランジションが設定されていません。 これらのアクテ **[!UICONTROL Properties]** ィビティのタブから、アウトバウンドトランジションを追加できます。

   例えば、アクティビティ **[!UICONTROL Update data]** で、タブに移動し、オ **[!UICONTROL Transitions]** プションを選択し **[!UICONTROL Add an outbound transition without the population]** ます。 このオプションを使用すると、データを含まず、システム上の不要な領域を消費しない移行を追加できます。 これは、宛先ワークフローをトリガーする追加のア **[!UICONTROL End]** クティビティを接続するために使用されます。

   ![](assets/external_signal_empty_transition.png)

1. アクティビティ **[!UICONTROL External signal]** のタブで、宛 **[!UICONTROL End]** 先ワークフローと、そのワークフロー内でトリガーするア **[!UICONTROL External signal]** クティビティを選択します。

   別のワークフローをトリガ **[!UICONTROL End]** ーするようにアクティビティを設定すると、そのアイコンが追加のシグナル記号で更新されます。

   パラメーターを使用してワークフローを呼び出す場合は、この領域を使用 **[!UICONTROL Parameters and values]** します。 詳しくは、[この節](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)を参照してください。

   ![](assets/external_signal_end.png)

1. ソースワークフローを保存します。

ソースワー **[!UICONTROL End]** クフローのアクティビティまたはREST API呼び出しが実行されると、宛先ワークフローはアクティビティから自動的にトリガーさ **[!UICONTROL External signal]** れます。

>[!NOTE]
>
>送信先ワークフローをトリガーするには、その前に手動で開始する必要があります。 を起動すると、がアクテ **[!UICONTROL External activity]** ィブ化され、ソースワークフローからの信号を待ちます。

## 例 ：{#example}

次の例は、一般的な使用例 **[!UICONTROL External signal]** でのアクティビティを示しています。 データのインポートは、ソースワークフローで実行されます。 インポートが完了し、データベースが更新されると、2番目のワークフローがトリガされます。 この2番目のワークフローは、インポートされたデータの集計を更新するために使用されます。

ソースワークフローは次のとおりです。

* ファイルの読 [み込みアクティビティは](../../automating/using/load-file.md) 、新しい購入データを含むファイルをアップロードします。 購入データがデ [フォルトでデータマートに存在しないので](../../developing/using/data-model-concepts.md) 、データベースはそれに応じて拡張されています。

   次に例を示します。

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* 調整ア [クティビティは](../../automating/using/reconciliation.md) 、トランザクションデータがプロファイルと製品に正しく接続されるように、インポートされたデータとデータベースの間にリンクを作成します。
* 「 [Update data](../../automating/using/update-data.md) 」アクティビティは、データベースのトランザクションリソースを受信データで挿入し、更新します。
* アクティビティ **[!UICONTROL End]** は、宛先ワークフローをトリガーします。このワークフローは、集計の更新に使用されます。

![](assets/signal_example_source1.png)

宛先ワークフローは次のとおりです。

* アクティビティ **[!UICONTROL External signal]** は、ソースワークフローが正常に終了するのを待ちます。
* Queryアクティビティ [は](../../automating/using/query.md#enriching-data) 、プロファイルをターゲット設定し、最終購入日を取得するためのコレクションセットをプロファイルに追加します。
* Updateデー [タアクティビティは](../../automating/using/update-data.md) 、追加のデータを専用のカスタムフィールドに格納します。 プロファイルリソースが拡張され、「最終購入日」フィールドが追加さ **れたことに注意** 。

![](assets/signal_example_source2.png)

