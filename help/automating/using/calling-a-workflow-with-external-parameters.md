---
title: 概要
description: この節では、外部パラメーターを使用してワークフローを呼び出す方法について詳しく説明します。
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---

# 概要 {#calling-a-workflow-with-external-parameters}

Campaign Standardを使用すると、パラメーター（ターゲットにするオーディエンス名、インポートするファイル名、メッセージコンテンツの一部など）を指定してワークフローを呼び出すことができます。 これにより、Campaignの自動化を外部システムと簡単に統合できます。

次の例で、CMSから直接Eメールを送信します。 その場合は、オーディエンスとEメールコンテンツをCMSに選択するようにシステムを設定できます。 「送信」をクリックすると、これらのパラメーターを使用してキャンペーンワークフローが呼び出され、ワークフロー内で使用して、配信で使用するオーディエンスとURLコンテンツを定義できます。

パラメーターを指定してワークフローを呼び出すプロセスは、次のとおりです。

1. **[!UICONTROL External signal]**&#x200B;アクティビティのパラメーターを宣言します。 [外部シグナルアクティビティでのパラメーターの宣言](../../automating/using/declaring-parameters-external-signal.md)を参照してください。
1. **[!UICONTROL End]**&#x200B;アクティビティまたはAPI呼び出しを設定して、パラメーターを定義し、ワークフロー&#x200B;**[!UICONTROL External signal]**&#x200B;アクティビティをトリガーします。 [このページ](../../automating/using/defining-parameters-calling-workflow.md)を参照
1. ワークフローがトリガーされると、パラメーターがワークフローのイベント変数に取り込まれ、ワークフロー内で使用できます。 [このページ](../../automating/using/customizing-workflow-external-parameters.md)を参照してください。

![](assets/extsignal_process.png)
