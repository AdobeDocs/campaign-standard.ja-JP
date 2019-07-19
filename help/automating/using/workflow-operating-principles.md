---
title: ワークフローの操作の原則
seo-title: ワークフローの操作の原則
description: ワークフローの操作の原則
seo-description: ワークフローの主な側面を学びます。
page-status-flag: 常にアクティブ化されていない
uuid: 85755e85-617b-4a9b- bb30-96ba8333f4f0
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: about- workflows- and- data- management
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Workflow operating principles{#workflow-operating-principles}

A workflow is a **sequence of configurable activities**. 各アクティビティには、プロセス内の特定のロールがあります。The result of each activity is forwarded to the following activity by a **transition**, represented by an arrow.

1つのアクティビティ間で交換されるデータのタイプは、次のアクティビティの設定方法に影響を与える可能性があります。例えば、電子メール配信アクティビティの前に訪問者が確立された場合、対象となる電子メールのターゲットとして機能できます。

ワークフローの実行前または実行後に、アクティビティを開いたり、編集したりすることができます。

トランジションを開いて、ワークフローの実行中または実行後に送信されたデータが正しいことを確認できます。To access the detail view of the transitions, you have to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

![](assets/workflow_overview.png)

