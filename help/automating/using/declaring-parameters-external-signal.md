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
source-wordcount: '0'
ht-degree: 0%

---


# 外部シグナルアクティビティでパラメータを宣言{#declaring-the-parameters-in-the-external-signal-activity}

パラメーターを使用してワークフローを呼び出す最初の手順は、**[!UICONTROL External signal]**&#x200B;アクティビティでワークフローを宣言することです。

1. **[!UICONTROL External signal]**&#x200B;アクティビティを開き、「**[!UICONTROL Parameters]**」タブを選択します。
1. **[!UICONTROL Create element]**&#x200B;ボタンをクリックし、各パラメーターの名前とタイプを指定します。

   >[!CAUTION]
   >
   >名前とパラメーター数が、ワークフローの呼び出し時に定義されたものと同じであることを確認します（[このページ](../../automating/using/defining-parameters-calling-workflow.md)を参照）。 また、パラメーターの型は、期待される値と一致する必要があります。

   ![](assets/extsignal_declaringparameters_1.png)

1. パラメーターが宣言されたら、ワークフローの設定を終了し、実行します。
