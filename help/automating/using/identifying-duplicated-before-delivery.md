---
title: 配信前の重複の特定
description: 次に、メールを送信する前にターゲットの重複を除外する重複排除の例を示します。 同じプロファイルに対して同じ通信を複数回送信することを回避できます。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a09b101b-f76f-4377-9854-1fcffaad4f9a
TQID: 'https://experienceleague.adobe.com/4t0TujgM3kHTT36-Gy2lmiVQIRMy3OeChAw-Xx5MnWY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 79%
---
# 配信前の重複の特定 {#identifying-duplicates-before-a-delivery}

次に、メールを送信する前にターゲットの重複を除外する重複排除の例を示します。 同じプロファイルに対して同じ通信を複数回送信することを回避できます。

このワークフローは次の要素で構成されます。

![](assets/deduplication_example_workflow.png)

* メールのターゲットを定義できる[ クエリ ](../../automating/using/query.md)です。 このワークフローでは、18 歳から 25 歳までのプロファイルのうち、1 年以上クライアントデータベースに存在しているすべてのプロファイルがターゲットになります。

  ![](assets/deduplication_example_query.png)

* [重複排除](../../automating/using/deduplication.md) アクティビティ。前のクエリから発生した重複を識別できます。 この例では、保存されるレコードは重複ごとに 1 つだけです。 重複はメールアドレスを使用して識別されます。 つまり、ターゲティングに存在するメールアドレスごとに 1 回しかメール配信を送信できません。

  選択する重複排除方法は「**[!UICONTROL Non-empty value]**」です。 これにより、重複が識別された場合、**名前（名）**&#x200B;が含まれているレコードを優先して保持することができます。 メールコンテンツのパーソナライゼーションフィールドで名が使用されている場合に一貫性が向上する方法です。

  また、重複を保持し一覧表示するために、トランジションが追加されています。

  ![](assets/deduplication_example_dedup.png)

* 重複排除のメインのアウトバウンドトランジションの後に配置された[ メール配信](../../automating/using/email-delivery.md)。
* 重複を&#x200B;**重複** オーディエンスに保存するために、重複排除の追加移行後に配置された[ オーディエンスを保存](../../automating/using/save-audience.md) アクティビティ。 このオーディエンスを再利用して、メール配信のたびにオーディエンスのメンバーを直接除外することができます。
