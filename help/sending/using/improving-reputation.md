---
title: Adobe Campaign Standardでの評判の向上
description: 重複の電子メールアドレスと強制隔離を管理して、Adobe Campaign Standardでの評判を高める方法を学びます。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 70%

---


# 評価の向上{#improving-reputation}

受信者を疲弊させるのを避けるために、重複した E メールアドレスをターゲットから削除します。この手順は、送信レピュテーションを保護し、適切な強制隔離管理をおこなうためのものです。Adobe Campaignオファーは、これらの推奨を実装し、ISPがブロックリストに追加するリスクを回避するために必要なツールを提供します。

以下に重複および強制隔離の管理の詳細を示します。

## 重複 {#duplicates}

重複した E メールアドレスがあると、以下のような複数の結果を招く可能性があります。
* 同じメッセージが複数回送信される。Campaign がデフォルトで送信前に重複排除手順を実行しても、ターゲットが分割されている場合は、同じコンテンツを持つ異なるアクションによって同じメッセージが送信されるのを止めることはできません。
* 購読解除リクエストが履行されない。受信者がメッセージを受信後に購読解除しても、重複したプロファイルではその後のメッセージの受信が解除されません。

この状況では、オプトイン手順のサイドステップ以外に、メッセージをスパムと見なし、ISPでブロックリスト手順を開始する可能性が高くなります。

データベースに対する操作を実行する場合は、特に注意が必要です。 可能な限り重複を避けるために、以下を実施する必要があります。
* **インポートは細かく設定する必要があります。** これは、紐付けキーを選択する際に特に重要です。
* **E メールアドレスを変更する際は注意する.**&#x200B;変更された E メールアドレスも、重複の元になる可能性があります。特に、異なるドメインの 2 つのアドレスが、同じメールボックスにルーティングされる場合があります（例えば、名前を変更し、一定期間以前のドメインを維持する場合の joe.doe@amce-co.com と joe.doe@acme-rebranded.com など）。
* **自動インポート時は注意する.** リストの場合も、他のデータベースの場合も、プロファイルの管理時に考慮すべき要素です。 プロファイルを削除したり別のパーティションに移動したりすると何が起こるでしょうか。例えば、注文がおこなわれると、自動インポートによって最初のパーティションに再作成される可能性があります。
* **プロファイルは異なるフォルダーに分類する.**

同様に、異なるパーティション間での重複が正常である場合があります。例えば、サードパーティや会社の別の組織に送信する場合、同じ人物が異なる理由で受信者になるのは、理にかなっています。しかし、同じパーディション内の重複が正常であることはまれです。

## 強制隔離 {#quarantines}

Adobe Campaign では、強制隔離されたアドレスのリストを管理します。アドレスが強制隔離されている受信者は、配信分析時にデフォルトで除外され、ターゲティングされません。

Quarantine management is detailed in [this section](../../sending/using/understanding-quarantine-management.md).

例えば、受信ボックスの容量が超過している場合や、アドレスが存在しない場合などに、E メールアドレスを強制隔離できます。いずれの場合も、検疫は、 [この節で示す特定のルールに対応し](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine)ます。
