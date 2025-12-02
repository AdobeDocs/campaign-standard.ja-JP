---
title: 外部シグナルアクティビティでのパラメーターの宣言
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# 外部シグナルアクティビティでのパラメーターの宣言 {#declaring-the-parameters-in-the-external-signal-activity}

パラメーターを使用してワークフローを呼び出す最初の手順は、**[!UICONTROL External signal]** アクティビティでパラメーターを宣言することです。

1. **[!UICONTROL External signal]** アクティビティを開き、「**[!UICONTROL Parameters]**」タブを選択します。
1. **[!UICONTROL Create element]** ボタンをクリックし、各パラメーターの名前とタイプを指定します。

   >[!CAUTION]
   >
   >名前とパラメーター数が、ワークフローを呼び出す際に定義した名前と数と同じであることを確認します（[&#x200B; このページ &#x200B;](../../automating/using/defining-parameters-calling-workflow.md) を参照）。 さらに、パラメーターのタイプは、期待される値と一致する必要があります。

   ![](assets/extsignal_declaringparameters_1.png)

1. パラメーターを宣言したら、ワークフロー設定を完了してから実行します。
