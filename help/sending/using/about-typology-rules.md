---
title: タイポロジとタイポロジルールについて
description: Adobe Campaign でのタイポロジやタイポロジルールの仕組みを説明します。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
TQID: 'https://experienceleague.adobe.com/fFTJTgKfIhII-D6pefx9hqnX3a022odFZS5AAmNK1Ao'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: e5fb657f-3c0a-4fcc-9980-3589a23ab4de
    internal-label: Typology rules
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 100%
---
# タイポロジとタイポロジルールについて{#about-typology-rules}

Campaign Standard を使用すると、メッセージを&#x200B;**タイポロジ**&#x200B;にリンクして、メッセージが有効で品質の基準を満たしているかどうかを確認できます。

タイポロジとは、メッセージの分析段階で実行される一連の&#x200B;**タイポロジルール**&#x200B;です。 メールに常に必要な特定の要素（登録解除リンクや件名行など）が含まれていることを確かめたり、ターゲットグループから特定グループ（非購読者、競合他社、ロイヤルティの低い顧客など）を除外するフィルタールールを設定したりできます。

![](assets/typology_messagelink.png)

Campaign Standard には、すぐに使えるタイポロジとタイポロジルールが用意されています。 必要に応じて、新しいルールを作成し、既存または新規のタイポロジに追加して、メッセージにリンクすることもできます。

タイポロジを作成してメッセージに適用する手順は次のとおりです。

1. タイポロジルールを作成します（[こちらの節](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)を参照）。
1. タイポロジを作成し、作成したルールを参照させます（[こちらの節](../../sending/using/managing-typologies.md#creating-a-typology)を参照）。
1. 作成したタイポロジを使用するように配信を設定します（[こちらの節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)を参照）。
1. メッセージの準備中、条件が満たされたプロファイルは除外されます。 ログを確認して除外を監視できます。
