---
title: 外部信号
seo-title: 外部信号
description: 外部信号
seo-description: 外部シグナルアクティビティは、ある条件が別のワークフローで正常に満たされたときにワークフローをトリガーします。
page-status-flag: 常にアクティブ化されていない
uuid: 884b6daf- bfd9-440b-8336-004b80c76def
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行アクティビティ
discoiquuid: 911c71b5- da8b-4916- b645-13bba6d21715
context-tags: シグナル、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# External signal{#external-signal}

## 説明 {#description}

![](assets/signal.png)

The **[!UICONTROL External signal]** activity triggers a workflow when some conditions are successfully met in another workflow or from a REST API call.

## Context of use {#context-of-use}

**[!UICONTROL External signal]** アクティビティは、異なるワークフローにわたる同じ顧客の遍歴に属する異なるプロセスを整理および編成するために使用します。これにより、別のワークフローから1つのワークフローを開始し、より複雑な顧客ジャーニーをサポートして、問題の監視や対応をより効率的に行うことができます。

**[!UICONTROL External signal]** アクティビティは、ワークフローの最初のアクティビティとして配置されるように設計されています。It can be triggered from the **[!UICONTROL End]** activity of another workflow or from a REST API call (for more on this, refer to the [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) ).

トリガーされると、外部パラメーターを定義してワークフローイベント変数で使用できます。The process to call a workflow with external parameters is detailed in [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>アクティビティは、10分ごとにより頻繁にトリガーされることはありません。

**[!UICONTROL External signal]** アクティビティは複数の異なるイベントからトリガーされることがあります。In that case, the **[!UICONTROL External signal]** is triggered as soon as one of the source workflows or API call is executed. すべてのソースワークフローが完了している必要はありません。

## Configuration {#configuration}

When configuring an external signal, it is important to first configure the **[!UICONTROL External signal]** activity in the destination workflow. Once this configuration is done, the **[!UICONTROL External signal]** activity of this workflow becomes available to configure the **[!UICONTROL End]** activity of the source workflow.

1. Drag and drop an **[!UICONTROL External signal]** activity into your destination workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. アクティビティのラベルを編集します。This label is needed when configuring the source workflow that triggers the **[!UICONTROL External signal]**.

   If you want to call the workflow with parameters, use the **[!UICONTROL Parameters]** area to declare them. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. アクティビティの設定を確認し、必要な他のアクティビティを追加してワークフローを保存します。

   >[!NOTE]
   >
   >別のワークフローから宛先ワークフローをトリガーする場合は、次の手順に従います。If you want to trigger the destination workflow from a REST API call, consult the [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) to get more details.

1. Open the source workflow and select an **[!UICONTROL End]** activity. If there is no **[!UICONTROL End]** activity available, add one after the last activity of a branch of the workflow.

   一部のアクティビティでは、デフォルトでアウトバウンドトランジションがありません。From the **[!UICONTROL Properties]** tab of these activities, you can add an outbound transition.

   **[!UICONTROL Update data]** 例えば、アクティビティで、タブに **[!UICONTROL Transitions]** 移動して **[!UICONTROL Add an outbound transition without the population]** オプションをチェックします。このオプションを使用すると、データを含まないトランジションを追加したり、システム上の不要なスペースを使用したりできます。It is just used to connect the extra **[!UICONTROL End]** activity that triggers the destination workflow.

   ![](assets/external_signal_empty_transition.png)

1. In the **[!UICONTROL External signal]** tab of the **[!UICONTROL End]** activity, select the destination workflow as well as the **[!UICONTROL External signal]** activity to trigger within that workflow.

   When you set an **[!UICONTROL End]** activity to trigger another workflow, its icon is updated with an additional signal symbol.

   If you want to call the workflow with parameters, use the **[!UICONTROL Parameters and values]** area. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. ソースワークフローを保存します。

Once the **[!UICONTROL End]** activity of the source workflow or the REST API call is executed, the destination workflow is automatically triggered from the **[!UICONTROL External signal]** activity.

>[!NOTE]
>
>宛先ワークフローは、トリガーする前に手動で開始する必要があります。When started, the **[!UICONTROL External activity]** is activated and waits for the signal from the source workflow.

## Example {#example}

The following example illustrates the **[!UICONTROL External signal]** activity in a typical use case. ソースワークフローでデータインポートが実行されます。インポートが完了し、データベースが更新されると、2つ目のワークフローがトリガーされます。この2つ目のワークフローは、インポートされたデータの集計を更新するために使用します。

ソースワークフローは次のように表示されます。

* [読み込みファイル](../../automating/using/load-file.md) アクティビティは、新しい購入データを含むファイルをアップロードします。Note that the [database has been extended](../../developing/using/data-model-concepts.md) accordingly as purchase data are not present by default in the datamart.

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

* [紐付け](../../automating/using/reconciliation.md) アクティビティにより、インポートされたデータとデータベース間のリンクが作成され、トランザクションデータがプロファイルおよび製品に適切に接続されます。
* [更新データ](../../automating/using/update-data.md) アクティビティは、受信データを使用してデータベースのトランザクションリソースを挿入および更新します。
* **[!UICONTROL End]** アクティビティによって、集計の更新に使用される宛先ワークフローがトリガーされます。

![](assets/signal_example_source1.png)

宛先ワークフローは次のように表示されます。

* **[!UICONTROL External signal]** アクティビティはソースワークフローが正常に終了するまで待機します。
* [クエリー](../../automating/using/query.md#enriching-data) アクティビティは、プロファイルをターゲットにして、最終的な購入日を取得するためのコレクションセットでエンリッチメントします。
* [更新データ](../../automating/using/update-data.md) アクティビティにより、追加のデータが専用のカスタムフィールドに保存されます。Note that the profile resource has been extended to add the **Last purchase date** field.

![](assets/signal_example_source2.png)

