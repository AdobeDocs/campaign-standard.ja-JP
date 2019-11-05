---
title: ワークフローの運用原則
description: ワークフローの主な側面について説明します。
page-status-flag: 非活性化の
uuid: 85755e85-617b-4a9b-bb30-96ba8333f4f0
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: about-workflows-and-data-management
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ワークフローの運用原則{#workflow-operating-principles}

ワークフローとは、設定可能 **なアクティビティのシーケンスで**&#x200B;す。 各アクティビティは、プロセス内で特定の役割を持ちます。 各アクティビティの結果は、矢印で表される遷移によって ****、次のアクティビティに転送されます。

あるアクティビティと別のアクティビティとの間で交換されるデータのタイプは、次のアクティビティの設定方法に影響を与える可能性があります。 例えば、電子メール配信アクティビティの前に訪問者が設定されている場合、その訪問者は該当する電子メールのターゲットとして機能します。

ワークフローの実行前または実行後に、アクティビティを開いてパラメーターを確認または編集できます。

ワークフローの実行中または実行後に、トランジションを開いて、送信されたデータが正しいかどうかを確認できます。 トランジションの詳細ビューにアクセスするには、ワークフロープロパティのセク **[!UICONTROL Keep interim results]** ションのオプションを **[!UICONTROL Execution]** オンにする必要があります。

![](assets/workflow_overview.png)

