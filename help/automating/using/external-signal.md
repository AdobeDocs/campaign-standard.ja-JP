---
title: 外部シグナル
description: 「外部シグナル」アクティビティは、別のワークフロー内で特定の条件が満足された場合にワークフローの実行をトリガーします。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a4fbd6b5-7cfb-44ad-bf3a-f3aabc122b77
TQID: https://experienceleague.adobe.com/-Bmy97uF0S3O3EHS8Dsx9yQt7wKNvqijOVxhtpVL1dc
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 601
ht-degree: 95%

---

# 外部シグナル{#external-signal}

## 説明 {#description}

![](assets/signal.png)

「**[!UICONTROL External signal]**」アクティビティでは、別のワークフローで特定の条件が満足されたときに、または REST API 呼び出しからワークフローをトリガーします。

## Context of use {#context-of-use}

「**[!UICONTROL External signal]**」アクティビティは、同じカスタマージャーニーの構成要素である様々なプロセスを様々なワークフローに編成する場合に使用します。 このアクティビティでは、あるワークフローを別のワークフローから起動できるので、さらに複雑なカスタマージャーニーをサポートできる一方、問題が発生した場合の監視と対応を改善することができます。

「**[!UICONTROL External signal]**」アクティビティは、あるワークフローの最初のアクティビティとして配置するように設計されています。 このアクティビティは、別のワークフローの「**[!UICONTROL End]**」アクティビティから、または REST API 呼び出しからトリガーできます（REST API 呼び出しについて詳しくは、[API のドキュメント](../../api/using/triggering-a-signal-activity.md)を参照してください）。

トリガーする際に外部パラメーターを定義し、ワークフローイベント変数で使用することができます。 外部パラメーターを指定してワークフローを呼び出す方法について詳しくは、[こちらの節](../../automating/using/calling-a-workflow-with-external-parameters.md)を参照してください。

>[!NOTE]
>
>このアクティビティは、10 分未満の間隔でトリガーすることはできません。

なお、「**[!UICONTROL External signal]**」アクティビティは、別の複数のイベントからトリガーできます。 その場合、「**[!UICONTROL External signal]**」アクティビティは、いずれか 1 つのソースワークフローまたは API 呼び出しが実行されるとすぐにトリガーされます。 すべてのソースワークフローが完了している必要はありません。

**関連トピック**

* [使用例：外部シグナル アクティビティとデータのインポート ](../../automating/using/external-signal-data-import.md)。
* [ユースケース：外部パラメーターを使用してファイルからオーディエンスを作成するワークフローの呼び出し](../../automating/using/use-case-calling-workflow.md)

## 設定 {#configuration}

外部シグナルを設定する場合は，まず宛先ワークフローに［**[!UICONTROL External signal]**］アクティビティを設定することが重要です。 設定が完了したら、このワークフローの「**[!UICONTROL External signal]**」アクティビティを使用してソースワークフローの「**[!UICONTROL End]**」アクティビティを設定できるようになります。

1. 宛先ワークフローに「**[!UICONTROL External signal]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アクティビティのラベルを編集します。 このラベルは、「**[!UICONTROL External signal]**」をトリガーするソースワークフローを設定するときに必要になります。

   パラメーターを指定してワークフローを呼び出す場合は、「**[!UICONTROL Parameters]**」エリアを使用してパラメーターを宣言します。 詳しくは、[このページ](../../automating/using/declaring-parameters-external-signal.md)を参照してください。

   ![](assets/external_signal_configuration.png)

1. アクティビティの設定を確認し、その他必要なアクティビティを追加して、ワークフローを保存します。

   >[!NOTE]
   >
   >別のワークフローから宛先ワークフローをトリガーする場合は、次の手順に進みます。 また、REST API 呼び出しから宛先ワークフローをトリガーする場合は、[API のドキュメント](../../api/using/triggering-a-signal-activity.md)を参照して詳細を確認してください。

1. ソースワークフローを開き、「**[!UICONTROL End]**」アクティビティを選択します。 使用できる「**[!UICONTROL End]**」アクティビティがない場合は、ワークフローの分岐の最終アクティビティの後に追加します。

   アクティビティによっては、デフォルトでアウトバウンドトランジションがない場合があります。 こうしたアクティビティについては、「**[!UICONTROL Properties]**」タブでアウトバウンドトランジションを追加できます。

   例えば、「**[!UICONTROL Update data]**」アクティビティの場合は、「**[!UICONTROL Transitions]**」タブに移動して、「**[!UICONTROL Add an outbound transition without the population]**」オプションをオンにします。 このオプションを使用すると、データを含んでいないトランジションを追加できるので、システムの領域を不必要に消費せずに済みます。 このオプションを使用するだけで宛先ワークフローをトリガーする追加の「**[!UICONTROL End]**」アクティビティを接続できます。

   ![](assets/external_signal_empty_transition.png)

1. 「**[!UICONTROL End]**」アクティビティの「**[!UICONTROL External signal]**」タブで、宛先ワークフローと、このワークフロー内でトリガーする「**[!UICONTROL External signal]**」アクティビティを選択します。

   別のワークフローをトリガーする「**[!UICONTROL End]**」アクティビティを設定すると、そのアイコンが追加のシグナルシンボルで更新されます。

   パラメーターを指定してワークフローを呼び出す場合は、「**[!UICONTROL Parameters and values]**」エリアを使用します。 詳しくは、[このページ](../../automating/using/defining-parameters-calling-workflow.md)を参照してください。

   ![](assets/external_signal_end.png)

1. ソースワークフローを保存します。

ソースワークフローの「**[!UICONTROL End]**」アクティビティ、または REST API 呼び出しが実行されると、「**[!UICONTROL External signal]**」アクティビティから宛先ワークフローが自動的にトリガーされます。

>[!NOTE]
>
>宛先ワークフローをトリガーするには、その前に手動で開始しておく必要があります。 開始すると、**[!UICONTROL External activity]**&#x200B;が有効になり、ソースワークフローからシグナルが送られるのを待機します。
