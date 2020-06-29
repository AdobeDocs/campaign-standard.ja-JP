---
title: 配信前の重複の識別
description: 次の例は、電子メールを送信する前にターゲットの重複を除外する重複排除 - 重複を示しています。 つまり、同じプロファイルに対して複数回通信を送信するのを避けることができます。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# 配信前の重複の識別 {#identifying-duplicates-before-a-delivery}

次の例は、電子メールを送信する前にターゲットの重複を除外する重複排除 - 重複を示しています。 つまり、同じプロファイルに対して複数回通信を送信するのを避けることができます。

ワークフローは次の要素で構成されます。

![](assets/deduplication_example_workflow.png)

* 電子メールのターゲットを定義できる [クエリ](../../automating/using/query.md) 。 このワークフローでは、18歳から25歳のプロファイルのうち、1年以上クライアントデータベースに属しているすべてのターゲットがされます。

   ![](assets/deduplication_example_query.png)

* 前の [重複排除 - 重複からの重複を識別できる](../../automating/using/deduplication.md) クエリ。 この例では、各重複に保存されるレコードは1つだけです。 重複は電子メールアドレスを使用して識別されます。 つまり、ターゲティングに存在する電子メールアドレスごとに1回だけ電子メール配信を送信できます。

   選択した重複排除 - 重複方法はで **[!UICONTROL Non-empty value]**&#x200B;す。 これにより、重複の場合に記録されるレコードの中で、 **名が指定されているレコードを優先します** 。 これにより、電子メールコンテンツのパーソナライゼーションフィールドで名が使用される場合に、一貫性が向上します。

   また、重複を保持し、リストを行うためのトランジションも追加されます。

   ![](assets/deduplication_example_dedup.png)

* 重複排除 - 重複のメインの送信トランジションの後に配置される [電子メール配信](../../automating/using/email-delivery.md) 。
* オーディエンスを [重複](../../automating/using/save-audience.md) オーディエンスに保存するために、重複排除 - 重複の追加トランジションの後に配置される「 **重複を保存** 」アクティビティ。 このオーディエンスは、各電子メール配信からそのメンバーを直接除外するために再利用できます。
