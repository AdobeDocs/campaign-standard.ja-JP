---
title: 概要
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
TQID: https://experienceleague.adobe.com/Pin9vFRMMylFFKw6VSvQowwXvzAn1Ihg76e2cSoaeyw
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 186
ht-degree: 4%

---

# 概要 {#calling-a-workflow-with-external-parameters}

Campaign Standardでは、パラメーター（ターゲットとなるオーディエンス名、インポートするファイル名、メッセージコンテンツの一部など）を使用してワークフローを呼び出すことができます。 これにより、Campaignの自動処理機能を外部システムと簡単に統合できます。

CMSから直接メールを送信する場合の例を次に示します。 その場合、CMSにオーディエンスとメールコンテンツを選択するようにシステムを設定できます。 「送信」をクリックすると、これらのパラメーターを含むCampaign ワークフローが呼び出され、ワークフローでそれらを使用して、配信で使用するオーディエンスとURL コンテンツを定義できます。

パラメーターを使用してワークフローを呼び出すプロセスは次のとおりです。

1. **[!UICONTROL External signal]** アクティビティのパラメーターを宣言します。 外部信号アクティビティのパラメーターの宣言[を参照してください](../../automating/using/declaring-parameters-external-signal.md)。
1. パラメーターを定義し、ワークフロー&#x200B;**[!UICONTROL External signal]** アクティビティをトリガーするには、**[!UICONTROL End]** アクティビティまたはAPI呼び出しを設定します。 [このページ](../../automating/using/defining-parameters-calling-workflow.md)を参照してください
1. ワークフローがトリガーされると、パラメーターはワークフローのイベント変数に取り込まれ、ワークフロー内で使用できます。 [このページ](../../automating/using/customizing-workflow-external-parameters.md)を参照してください。

![](assets/extsignal_process.png)
