---
title: ドメイン別の分類
description: 標準のドメイン別分類レポートでは、顧客の各ドメインに応じた配信のパフォーマンスデータを確認できます。
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

このレポートには、メール配信のオーディエンスで表された各ドメインのパフォーマンスデータが含まれています。 キャンペーンレポートまたはプログラムレポートの場合は、パフォーマンスデータを複数のオーディエンスで使用できます。 このデータを使用すると、特定のイベントに対する各ドメインの反応を分析できます。 例えば、リンク表示、ブロックリスト上の URL などです。

![](assets/delivery_reports_6.png)

表 **ブロードキャスト統計** には、各ドメインで発生する可能性のあるエラーに関する使用可能なデータが含まれます。次に例を示します。

* **処理済み/送信済み**：送信されたメールの数。
* **配信済み**：配信されたメールの数。
* **バウンス + エラー**：配信できなかったメッセージの数。
* **ハードバウンス**：永続的なエラー（メールアドレスの間違いなど）の合計数。
* **ソフトバウンス数**：一時的なエラー（インボックスが満杯など）の合計数。

2 つ目の表 **トラッキング統計** には、配信に対する受信者の反応に使用できるデータが含まれます。例えば、次のようなデータです。

* **配信済み**：配信されたメールの数
* **開封**：配信でメッセージが開かれた回数。
* **クリック**：配信でコンテンツがクリックされた回数。
* **購読解除済み**：購読リンクのクリック数。
* **ミラーページ**：ミラーページリンクのクリック数。
* **ブロックリスト上**: メールをスパムまたはジャンクとして宣言した受信者の数。 [詳細情報](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
