---
title: ドメイン別の分類
description: 標準のドメイン別分類レポートでは、顧客のドメインごとに、配信のパフォーマンスデータを確認できます。
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

このレポートには、各ドメインのパフォーマンスデータが含まれます。このデータは、E メール配信のオーディエンスで表されます。 キャンペーンまたはプログラムレポートの場合、パフォーマンスデータは複数のオーディエンスで使用できます。 このデータを使用すると、特定のイベントに対する各ドメインの動作を分析できます。 例えば、リンクの表示、ブロックリスト上の URL など。

![](assets/delivery_reports_6.png)

テーブル **ブロードキャスト統計** には、次のような各ドメインで発生した可能性のあるエラーの使用可能なデータが含まれます。

* **処理済み/送信済み**:送信された電子メールの数。
* **配信済み**:配信された電子メールの数。
* **バウンス数+エラー数**:配信できなかったメッセージの数。
* **ハードバウンス**:誤った E メールアドレスなどの永続的なエラーの合計数。
* **ソフトバウンス**:一時的なエラーの合計数（メールボックス容量超過など）。

二番目の表は **トラッキング統計**&#x200B;には、次のような、配信に対する受信者の反応に使用可能なデータが含まれます。

* **配信済み**:配信された E メールの数
* **開く**:配信でメッセージが開かれた回数。
* **クリック**:配信でコンテンツがクリックされた回数。
* **配信停止済み**:購読リンクのクリック数。
* **ミラーページ**:ミラーページリンクのクリック数。
* **時**:E メールをスパムまたは迷惑メールとして宣言した受信者の数です。 [詳細情報](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
