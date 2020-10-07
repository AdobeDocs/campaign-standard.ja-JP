---
title: 配信前の重複の特定
description: 次に、E メールを送信する前にターゲットの重複を除外する重複排除の例を示します。同じプロファイルに対して同じ通信を複数回送信することを回避できます。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---


# 配信前の重複の特定 {#identifying-duplicates-before-a-delivery}

次に、E メールを送信する前にターゲットの重複を除外する重複排除の例を示します。同じプロファイルに対して同じ通信を複数回送信することを回避できます。

このワークフローは次の要素で構成されます。

![](assets/deduplication_example_workflow.png)

* A [Query](../../automating/using/query.md) which allows you to define the target of the email. このワークフローでは、18 歳から 25 歳までのプロファイルのうち、1 年以上クライアントデータベースに存在しているすべてのプロファイルがターゲットになります。

   ![](assets/deduplication_example_query.png)

* A [Deduplication](../../automating/using/deduplication.md) activity, which allows you to identify the duplicates that come from the preceding query. この例では、保存されるレコードは重複ごとに 1 つだけです。重複は E メールアドレスを使用して識別されます。つまり、ターゲティングに存在する E メールアドレスごとに 1 回しか E メール配信を送信できません。

   選択する重複排除方法は「**[!UICONTROL Non-empty value]**」です。これにより、重複が識別された場合、**名前（名）**&#x200B;が含まれているレコードを優先して保持することができます。E メールコンテンツのパーソナライゼーションフィールドで名が使用されている場合に一貫性が向上する方法です。

   また、重複を保持し一覧表示するために、トランジションが追加されています。

   ![](assets/deduplication_example_dedup.png)

* An [Email delivery](../../automating/using/email-delivery.md) placed after the main outbound transition of the deduplication.
* A [Save audience](../../automating/using/save-audience.md) activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. このオーディエンスを再利用して、E メール配信のたびにオーディエンスのメンバーを直接除外することができます。
