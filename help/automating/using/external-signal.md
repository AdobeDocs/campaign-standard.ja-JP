---
title: 外部シグナル
description: 外部シグナルアクティビティは、別のワークフローで一部の条件が満たされた場合にワークフローをトリガします。
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
source-git-commit: 16afc307df6902584624d6457954a472b11c5129
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 4%

---


# 外部シグナル{#external-signal}

## 説明 {#description}

![](assets/signal.png)

アクティビティは、別のワークフローで、またはREST API呼び出しで、一部の条件が正常に満たされた場合にワークフローをトリガーします。 **[!UICONTROL External signal]**

## 使用状況 {#context-of-use}

この **[!UICONTROL External signal]** アクティビティは、同じ顧客遍歴の一部である異なるプロセスを別々のワークフローに編成および調整するために使用します。 ワークフローを別のワークフローから開始でき、より複雑な顧客の遍歴をサポートしながら、問題が発生した場合の監視と対応を改善できます。

この **[!UICONTROL External signal]** アクティビティは、ワークフローの最初のアクティビティとして配置されるように設計されています。 別のワークフローの **[!UICONTROL End]** アクティビティまたはREST API呼び出しからトリガーされる場合があります(詳しくは、 [APIのドキュメントを参照](../../api/using/triggering-a-signal-activity.md))。

トリガーされた場合、外部パラメーターを定義し、ワークフローイベント変数で使用できます。 外部パラメーターを使用してワークフローを呼び出すプロセスについて詳し [くは、この節](../../automating/using/calling-a-workflow-with-external-parameters.md)。

>[!NOTE]
>
>アクティビティは、10分に1回より頻繁にトリガーされることはありません。

アクティビティは、複数の異なるイベントからトリガーされる場合があることに注意してください。 **[!UICONTROL External signal]** この場合、ソースワークフロー **[!UICONTROL External signal]** の1つまたはAPI呼び出しが実行されるとすぐに、がトリガーされます。 すべてのソースワークフローを終了する必要はありません。

**関連トピック**

* [使用例： 外部信号のアクティビティとデータのインポート](../../automating/using/external-signal-data-import.md)。
* [使用例： 外部パラメーターを使用してファイルからオーディエンスを作成するためのワークフローの呼び出し](../../automating/using/calling-a-workflow-with-external-parameters.md#use-case)

## 設定 {#configuration}

外部信号を設定する場合、まず、宛先ワークフローで **[!UICONTROL External signal]** アクティビティを設定することが重要です。 この設定が完了すると、このワークフローの **[!UICONTROL External signal]** アクティビティを使用して、ソースワークフローの **[!UICONTROL End]** アクティビティを設定できるようになります。

1. 目的のワークフローに **[!UICONTROL External signal]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アクティビティのラベルを編集します。 このラベルは、をトリガーするソースワークフローを設定する場合に必要で **[!UICONTROL External signal]**&#x200B;す。

   パラメーターを使用してワークフローを呼び出す場合は、 **[!UICONTROL Parameters]** 領域を使用して宣言します。 詳しくは、[この節](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)を参照してください。

   ![](assets/external_signal_configuration.png)

1. アクティビティの設定を確認し、必要なその他のアクティビティを追加して、ワークフローを保存します。

   >[!NOTE]
   >
   >別のワークフローから宛先ワークフローをトリガーする場合は、次の手順に進みます。 REST API呼び出しから宛先ワークフローをトリガーする場合は、 [APIドキュメント](../../api/using/triggering-a-signal-activity.md) を参照して詳細を確認してください。

1. ソースワークフローを開き、 **[!UICONTROL End]** アクティビティを選択します。 使用できる **[!UICONTROL End]** アクティビティがない場合は、ワークフローの最後のアクティビティの後に1つ追加します。

   一部のアクティビティには、デフォルトでアウトバウンドトランジションが設定されていません。 これらのアクティビティの **[!UICONTROL Properties]** タブから、アウトバウンドトランジションを追加できます。

   例えば、 **[!UICONTROL Update data]** アクティビティの場合は、 **[!UICONTROL Transitions]** タブに移動し、 **[!UICONTROL Add an outbound transition without the population]** オプションを選択します。 このオプションを使用すると、データを含まず、システム上の不要な領域を消費しないトランジションを追加できます。 これは、宛先ワークフローをトリガーする追加の **[!UICONTROL End]** アクティビティを接続するために使用されます。

   ![](assets/external_signal_empty_transition.png)

1. ワークフローの **[!UICONTROL External signal]** タブで、 **[!UICONTROL End]** アクティビティ内でトリガーする宛先ワークフローと **[!UICONTROL External signal]** アクティビティを選択します。

   別のワークフローをトリガーする **[!UICONTROL End]** アクティビティを設定すると、そのアイコンは追加のシグナル記号で更新されます。

   パラメーターを使用してワークフローを呼び出す場合は、 **[!UICONTROL Parameters and values]** 領域を使用します。 詳しくは、[この節](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)を参照してください。

   ![](assets/external_signal_end.png)

1. ソースワークフローを保存します。

ソースワークフローまたはREST API呼び出しの **[!UICONTROL End]** アクティビティが実行されると、宛先ワークフローは **[!UICONTROL External signal]** アクティビティから自動的にトリガーされます。

>[!NOTE]
>
>宛先ワークフローをトリガーするには、その前に手動で開始する必要があります。 を起動すると、がアクティブ化 **[!UICONTROL External activity]** され、ソースワークフローからの信号を待ちます。
