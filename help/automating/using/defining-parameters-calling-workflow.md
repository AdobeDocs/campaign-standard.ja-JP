---
title: 外部パラメーターを使用したワークフローの呼び出し
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3cb37426410eeb8be04c9c75afa4505894b15140
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 8%

---


# ワークフロー呼び出し時のパラメーターの定義 {#defining-the-parameters-when-calling-the-workflow}

この節では、ワークフローを呼び出す際のパラメーターの定義方法について詳しく説明します。 API呼び出しからこの操作を実行する方法について詳しくは、 [REST APIのドキュメントを参照してください](../../api/using/triggering-a-signal-activity.md)。

パラメーターを定義する前に、次のことを確認します。

* パラメーターが **[!UICONTROL External Signal]** アクティビティで宣言されています。 [](../../automating/using/declaring-parameters-external-signal.md) を参照してください。
* シグナルアクティビティを含むワークフローが実行中です。

アクティビティを設定するには、次の手順に従い **[!UICONTROL End]** ます。

1. アクティビティを開き、 **[!UICONTROL End]** タブを選択し **[!UICONTROL External signal]** ます。
1. 呼び出すワークフローと外部シグナルアクティビティを選択します。
1. ボタンをクリックし **[!UICONTROL Create element]** てパラメーターを追加し、名前と値を入力します。

   * **[!UICONTROL Name]**: **[!UICONTROL External signal]** アクティビティで宣言された名前(を参照 [](../../automating/using/declaring-parameters-external-signal.md))。
   * **[!UICONTROL Value]**:パラメーターに割り当てる値。 この値は、 **標準構文**( [この節で説明)に従う必要があります](../../automating/using/advanced-expression-editing.md#standard-syntax)。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. それ以外の場合は、アクティビティの実行時にエラーが発生します。

1. パラメーターを定義したら、アクティビティーを確認し、ワークフローを保存します。
