---
title: 外部パラメーターを使用したワークフローの呼び出し
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---

# ワークフロー呼び出し時のパラメーターの定義 {#defining-the-parameters-when-calling-the-workflow}

この節では、ワークフローを呼び出す際にパラメーターを定義する方法について詳しく説明します。 API呼び出しからこの操作を実行する方法について詳しくは、[REST APIのドキュメント](../../api/using/triggering-a-signal-activity.md)を参照してください。

パラメーターを定義する前に、次の点を確認します。

* パラメーターが&#x200B;**[!UICONTROL External Signal]**&#x200B;アクティビティで宣言されている。 [このページ](../../automating/using/declaring-parameters-external-signal.md)を参照してください。
* シグナルアクティビティを含むワークフローが実行中です。

**[!UICONTROL End]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL End]**&#x200B;アクティビティを開き、「**[!UICONTROL External signal]**」タブを選択します。
1. 呼び出すワークフローと外部シグナルアクティビティを選択します。
1. 「**[!UICONTROL Create element]**」ボタンをクリックしてパラメーターを追加し、名前と値を入力します。

   * **[!UICONTROL Name]**:アクティビティで宣言された **[!UICONTROL External signal]** 名前(このペ [ージを参照](../../automating/using/declaring-parameters-external-signal.md))。
   * **[!UICONTROL Value]**:パラメーターに割り当てる値。値は、**この節](../../automating/using/advanced-expression-editing.md#standard-syntax)で説明する[標準構文**&#x200B;に従う必要があります。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >**[!UICONTROL External signal]**&#x200B;アクティビティですべてのパラメーターが宣言されていることを確認します。 それ以外の場合は、アクティビティの実行時にエラーが発生します。

1. パラメーターを定義したら、アクティビティを確認し、ワークフローを保存します。
