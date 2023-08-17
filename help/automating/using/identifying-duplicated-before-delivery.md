---
title: 配信前の重複の特定
description: 次に、E メールを送信する前にターゲットの重複を除外する重複排除の例を示します。同じプロファイルに対して同じ通信を複数回送信することを回避できます。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: a09b101b-f76f-4377-9854-1fcffaad4f9a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---

# 配信前の重複の特定 {#identifying-duplicates-before-a-delivery}

次に、E メールを送信する前にターゲットの重複を除外する重複排除の例を示します。同じプロファイルに対して同じ通信を複数回送信することを回避できます。

このワークフローは次の要素で構成されます。

![](assets/deduplication_example_workflow.png)

* A [クエリ](../../automating/using/query.md) :E メールのターゲットを定義できます。 このワークフローでは、18 歳から 25 歳までのプロファイルのうち、1 年以上クライアントデータベースに存在しているすべてのプロファイルがターゲットになります。

  ![](assets/deduplication_example_query.png)

* A [重複排除](../../automating/using/deduplication.md) 「 」アクティビティ：先行するクエリで生成された重複を識別できます。 この例では、保存されるレコードは重複ごとに 1 つだけです。重複は E メールアドレスを使用して識別されます。つまり、ターゲティングに存在する E メールアドレスごとに 1 回しか E メール配信を送信できません。

  選択する重複排除方法は「**[!UICONTROL Non-empty value]**」です。これにより、重複が識別された場合、**名前（名）**&#x200B;が含まれているレコードを優先して保持することができます。E メールコンテンツのパーソナライゼーションフィールドで名が使用されている場合に一貫性が向上する方法です。

  また、重複を保持し一覧表示するために、トランジションが追加されています。

  ![](assets/deduplication_example_dedup.png)

* An [E メール配信](../../automating/using/email-delivery.md) は、重複排除の主なアウトバウンドトランジションの後に配置されています。
* A [オーディエンスを保存](../../automating/using/save-audience.md) 「 」アクティビティ：重複排除の追加トランジションの後に配置されています。 **重複** オーディエンス。 このオーディエンスを再利用して、E メール配信のたびにオーディエンスのメンバーを直接除外することができます。
