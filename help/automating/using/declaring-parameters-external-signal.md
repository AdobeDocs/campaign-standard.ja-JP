---
title: 外部パラメーターを使用したワークフローの呼び出し
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 5%

---

# 外部シグナルアクティビティでのパラメーターの宣言 {#declaring-the-parameters-in-the-external-signal-activity}

パラメーターを指定してワークフローを呼び出す最初の手順は、**[!UICONTROL External signal]**&#x200B;アクティビティで宣言することです。

1. **[!UICONTROL External signal]**&#x200B;アクティビティを開き、「**[!UICONTROL Parameters]**」タブを選択します。
1. 「**[!UICONTROL Create element]**」ボタンをクリックし、各パラメーターの名前とタイプを指定します。

   >[!CAUTION]
   >
   >パラメーターの名前と数が、ワークフローの呼び出し時に定義されたものと同じであることを確認します（[このページ](../../automating/using/defining-parameters-calling-workflow.md)を参照）。 また、パラメーターの型は、期待される値と一致する必要があります。

   ![](assets/extsignal_declaringparameters_1.png)

1. パラメーターが宣言されたら、ワークフローの設定を完了し、実行します。
