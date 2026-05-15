---
title: 外部信号アクティビティのパラメーターの宣言
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
TQID: https://experienceleague.adobe.com/au0xUZ7C8m3hiK9wbm3QBiHd9RtpZQW-AEoc-SvnhfE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 0%

---

# 外部信号アクティビティのパラメーターの宣言 {#declaring-the-parameters-in-the-external-signal-activity}

パラメーターを含むワークフローを呼び出す最初の手順は、**[!UICONTROL External signal]** アクティビティでそれらを宣言することです。

1. 「**[!UICONTROL External signal]**」アクティビティを開き、「**[!UICONTROL Parameters]**」タブを選択します。
1. 「**[!UICONTROL Create element]**」ボタンをクリックし、各パラメーターの名前とタイプを指定します。

   >[!CAUTION]
   >
   >パラメーターの名前と数が、ワークフローの呼び出し時に定義されるものと同じであることを確認します（[このページ &#x200B;](../../automating/using/defining-parameters-calling-workflow.md)を参照）。 さらに、パラメーターの型は、期待される値と一致している必要があります。

   ![](assets/extsignal_declaringparameters_1.png)

1. パラメーターを宣言したら、ワークフロー設定を完了してから実行します。
