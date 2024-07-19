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
ht-degree: 4%

---

# 概要 {#calling-a-workflow-with-external-parameters}

Campaign Standardを使用すると、パラメーター（ターゲットにするオーディエンス名、読み込むファイル名、メッセージコンテンツの一部など）を使用してワークフローを呼び出すことができます。 これにより、Campaign の自動化を外部システムと簡単に統合できます。

次の例では、CMS から直接メールを送信します。 その場合は、オーディエンスとメールコンテンツを CMS に選択するようにシステムを設定できます。 「送信」をクリックすると、これらのパラメーターを含むキャンペーンワークフローが呼び出され、それらをワークフローで使用して、配信で使用するオーディエンスおよび URL コンテンツを定義できるようになります。

パラメーターを使用してワークフローを呼び出すプロセスは次のとおりです。

1. **[!UICONTROL External signal]** アクティビティでパラメーターを宣言します。 [ 外部シグナルアクティビティでのパラメーターの宣言 ](../../automating/using/declaring-parameters-external-signal.md) を参照してください。
1. **[!UICONTROL End]** アクティビティまたは API 呼び出しを設定して、パラメーターを定義し、ワークフロー **[!UICONTROL External signal]** アクティビティをトリガーします。 [このページ](../../automating/using/defining-parameters-calling-workflow.md)を参照してください
1. ワークフローがトリガーされると、パラメーターがワークフローのイベント変数に取り込まれ、ワークフロー内で使用できるようになります。 [このページ](../../automating/using/customizing-workflow-external-parameters.md)を参照してください。

![](assets/extsignal_process.png)
