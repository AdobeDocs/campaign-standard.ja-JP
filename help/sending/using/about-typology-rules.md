---
title: タイポロジとタイポロジルール
description: タイポロジとタイポロジルールの機能をAdobe Campaign。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 396084934a41d103eecd6fe141c700c118000f75

---


# タイポロジとタイポロジルール{#about-typology-rules}

Campaign Standardを使用すると、メッセージをタイポロジ **ーにリンクし**、メッセージが有効で品質基準を満たしているかどうかを確認できます。

タイポロジとは、メッ **セージ**&#x200B;タイポロジルール段階で実行される一連の分析です。 電子メールに特定のターゲット(購読解除リンクや件名行など)を常に含めるか、フィルタリングルールを使用して、対象の要素(非購読者、競合他社、非忠誠度顧客など)からグループを除外できます。

![](assets/typology_messagelink.png)

すぐに使用できるタイポロジとタイポロジルールは、Campaign Standardで利用できます。 必要に応じて、新しいルールを作成し、既存または新しいタイポロジに追加して、メッセージにリンクすることもできます。

メッセージにタイポロジを作成し、適用する手順は次のとおりです。

1. タイポロジルールを作成します( [この節を参照](../../sending/using/managing-typology-rules.md#creating-a-typology-rule))。
1. Create a typology and reference the rules you created into it (see [this section](../../sending/using/managing-typologies.md#creating-a-typology)).
1. 作成した配信を使用するようにタイポロジを設定します( [この節を参照](../../sending/using/managing-typologies.md#applying-typologies-to-messages))。
1. メッセージの準備中、プロファイルは条件が満たされると除外されます。 ログを確認して除外を監視することができます。
