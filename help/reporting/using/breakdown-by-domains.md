---
title: ドメイン別の分類
description: 標準のドメイン別分類レポートでは、顧客の各ドメインに応じた配信のパフォーマンスデータについて学習します。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 513d74ae-10c0-4d41-a7d1-8ed655e1a2d1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# ドメイン別の分類{#breakdown-by-domains}

このレポートには、Eメール配信のオーディエンスに表示された各ドメインのパフォーマンスデータが含まれます。 キャンペーンまたはプログラムレポートの場合、パフォーマンスデータは複数のオーディエンスで使用できます。 このデータを使用すると、特定のイベントに対する各ドメインの動作を分析できます。 例えば、リンクの表示、ブロックリストURL（上など）

![](assets/delivery_reports_6.png)

テーブル&#x200B;**Broadcast statistics**&#x200B;には、次のような各ドメインで発生する可能性のあるエラーに対して使用可能なデータが含まれます。

* **処理済み/送信済み**:送信された電子メールの数。
* **配信済み**:配信された電子メールの数。
* **バウンス+エラー**:配信できなかったメッセージの数。
* **ハードバウンス**:誤った電子メールアドレスなどの永続的なエラーの合計数です。
* **ソフトバウンス**:完全なインボックスなどの一時的なエラーの合計数です。

2つ目のテーブル（**トラッキング統計**）には、次のような、配信に対する受信者の反応度に使用可能なデータが含まれます。

* **配信済み**:配信された電子メールの数
* ****&#x200B;を開きます。配信でメッセージが開封された回数。
* ****&#x200B;をクリックします。配信でコンテンツがクリックされた回数。
* **購読解除**:購読リンクのクリック数。
* **ミラーページ**:ミラーページリンクでのクリック数。
* **時**:Eメールをスパムまたは迷惑メールとして宣言した受信者の数です。[詳細情報](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
