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
TQID: 'https://experienceleague.adobe.com/-YjlK1Op8P08sxb--BOHl8AWyciX4BqPnCPQ3lpD3Co'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
    internal-label: REST API
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%
---
# ワークフロー呼び出し時のパラメーターの定義 {#defining-the-parameters-when-calling-the-workflow}

この節では、ワークフローの呼び出し時にパラメーターを定義する方法について詳しく説明します。 API呼び出しからこの操作を実行する方法について詳しくは、[REST API ドキュメント &#x200B;](../../api/using/triggering-a-signal-activity.md)を参照してください。

パラメーターを定義する前に、次のことを確認します。

* パラメーターが&#x200B;**[!UICONTROL External Signal]** アクティビティで宣言されました。 [このページ](../../automating/using/declaring-parameters-external-signal.md)を参照してください。
* シグナル アクティビティを含むワークフローが実行中です。

**[!UICONTROL End]** アクティビティを設定するには、次の手順に従います。

1. 「**[!UICONTROL End]**」アクティビティを開き、「**[!UICONTROL External signal]**」タブを選択します。
1. 呼び出すワークフローと外部信号アクティビティを選択します。
1. **[!UICONTROL Create element]** ボタンをクリックしてパラメーターを追加し、その名前と値を入力します。

   * **[!UICONTROL Name]**: **[!UICONTROL External signal]** アクティビティで宣言された名前（[このページ &#x200B;](../../automating/using/declaring-parameters-external-signal.md)を参照）。
   * **[!UICONTROL Value]**: パラメーターに割り当てる値。 値は、[このセクション &#x200B;](../../automating/using/advanced-expression-editing.md#standard-syntax)で説明されている&#x200B;**標準構文**&#x200B;に従う必要があります。

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >すべてのパラメーターが&#x200B;**[!UICONTROL External signal]** アクティビティで宣言されていることを確認してください。 それ以外の場合は、アクティビティの実行時にエラーが発生します。

1. パラメーターを定義したら、アクティビティを確認し、ワークフローを保存します。
