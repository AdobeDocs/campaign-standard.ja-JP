---
solution: Campaign Standard
product: campaign
title: 外部パラメーターを使用したワークフローの呼び出し
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---


# ワークフロー呼び出し時のパラメーターの定義 {#defining-the-parameters-when-calling-the-workflow}

この節では、ワークフローを呼び出す際のパラメーターの定義方法について詳しく説明します。 API呼び出しからこの操作を実行する方法について詳しくは、[REST APIドキュメント](../../api/using/triggering-a-signal-activity.md)を参照してください。

パラメーターを定義する前に、次のことを確認します。

* パラメーターが&#x200B;**[!UICONTROL External Signal]**&#x200B;アクティビティーで宣言されています。 [このページ](../../automating/using/declaring-parameters-external-signal.md)を参照してください。
* シグナルアクティビティを含むワークフローが実行中です。

**[!UICONTROL End]**&#x200B;アクティビティを設定するには、次の手順に従います。

1. **[!UICONTROL End]**&#x200B;アクティビティを開き、「**[!UICONTROL External signal]**」タブを選択します。
1. 呼び出すワークフローと外部シグナルアクティビティを選択します。
1. **[!UICONTROL Create element]**&#x200B;ボタンをクリックしてパラメーターを追加し、名前と値を入力します。

   * **[!UICONTROL Name]**: **[!UICONTROL External signal]** アクティビティで宣言された名前( [このページを参照](../../automating/using/declaring-parameters-external-signal.md))。
   * **[!UICONTROL Value]**:パラメーターに割り当てる値。値は&#x200B;**標準構文**&#x200B;に従う必要があります。[この節](../../automating/using/advanced-expression-editing.md#standard-syntax)で説明します。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >すべてのパラメーターが&#x200B;**[!UICONTROL External signal]**&#x200B;アクティビティーで宣言されていることを確認してください。 それ以外の場合は、アクティビティの実行時にエラーが発生します。

1. パラメーターを定義したら、アクティビティーを確認し、ワークフローを保存します。
