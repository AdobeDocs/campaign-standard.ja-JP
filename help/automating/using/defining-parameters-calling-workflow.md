---
title: ワークフロー呼び出し時のパラメーターの定義
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# ワークフロー呼び出し時のパラメーターの定義 {#defining-the-parameters-when-calling-the-workflow}

この節では、ワークフローを呼び出す際にパラメーターを定義する方法について詳しく説明します。 API 呼び出しからこの操作を実行する方法について詳しくは、[REST API ドキュメント ](../../api/using/triggering-a-signal-activity.md) を参照してください。

パラメーターを定義する前に、以下を確認します。

* パラメーターは、**[!UICONTROL External Signal]** アクティビティで宣言されています。 [このページ](../../automating/using/declaring-parameters-external-signal.md)を参照してください。
* シグナルアクティビティを含むワークフローが実行中です。

**[!UICONTROL End]** アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL End]** アクティビティを開き、「**[!UICONTROL External signal]**」タブを選択します。
1. 呼び出すワークフローと外部シグナルアクティビティを選択します。
1. 「**[!UICONTROL Create element]**」ボタンをクリックしてパラメーターを追加し、その名前と値を入力します。

   * **[!UICONTROL Name]**:**[!UICONTROL External signal]** アクティビティで宣言された名前（[ このページ ](../../automating/using/declaring-parameters-external-signal.md) を参照）。
   * **[!UICONTROL Value]**: パラメーターに割り当てる値。 値は、**この節** で説明されている [ 標準構文 ](../../automating/using/advanced-expression-editing.md#standard-syntax) に従う必要があります。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >**[!UICONTROL External signal]** アクティビティですべてのパラメーターが宣言されていることを確認します。 それ以外の場合は、アクティビティの実行時にエラーが発生します。

1. パラメーターを定義したら、アクティビティを確認し、ワークフローを保存します。
