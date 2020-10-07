---
title: タイポロジとタイポロジルールについて
description: Adobe Campaign でのタイポロジやタイポロジルールの仕組みを説明します。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 100%

---


# タイポロジとタイポロジルールについて{#about-typology-rules}

Campaign Standard を使用すると、メッセージを&#x200B;**タイポロジ**&#x200B;にリンクして、メッセージが有効で品質の基準を満たしているかどうかを確認できます。

タイポロジとは、メッセージの分析段階で実行される一連の&#x200B;**タイポロジルール**&#x200B;です。電子メールに常に必要な特定の要素（購読解除リンクや件名行など）が含まれていることを確かめたり、ターゲットグループから特定グループ（非購読者、競合他社、非顧客など）を除外するフィルタールールを設定したりできます。

![](assets/typology_messagelink.png)

Campaign Standard には、すぐに使えるタイポロジとタイポロジルールが用意されています。必要に応じて、新しいルールを作成し、既存または新規のタイポロジに追加して、メッセージにリンクすることもできます。

タイポロジを作成してメッセージに適用する手順は次のとおりです。

1. タイポロジルールを作成します（[こちらの節](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)を参照）。
1. タイポロジを作成し、作成したルールを参照させます（[こちらの節](../../sending/using/managing-typologies.md#creating-a-typology)を参照）。
1. 作成したタイポロジを使用するように配信を設定します（[こちらの節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)を参照）。
1. メッセージの準備中、条件が満たされたプロファイルは除外されます。ログを確認して除外を監視できます。
