---
title: ドメイン別の分類
description: ドメイン別分類の標準レポートでは、顧客の各ドメインに応じた配信のパフォーマンスデータを確認できます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 513d74ae-10c0-4d41-a7d1-8ed655e1a2d1
TQID: https://experienceleague.adobe.com/25Ci4GFEJHIO3Ed2BTBF2qUmD4LKh3jwUC56K8JZgzA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 238
ht-degree: 100%

---

# ドメイン別の分類{#breakdown-by-domains}

このレポートには、メール配信のオーディエンスで表される各ドメインのパフォーマンスデータが含まれています。 キャンペーンレポートまたはプログラムレポートの場合は、パフォーマンスデータを複数のオーディエンスで使用できます。 このデータを使用して、特定のイベントに対する各ドメインの反応を分析できます。 例えば、リンク表示、ブロックリストに登録されている URL などです。

![](assets/delivery_reports_6.png)

**ブロードキャスト統計情報**&#x200B;テーブルには、各ドメインで発生する可能性のあるエラーに関する次のような利用可能なデータが含まれています。

* **処理済み / 送信済み**：送信されたメールの数。
* **配信済み**：配信されたメールの数。
* **バウンス数 + エラー数**：配信できなかったメッセージの数。
* **ハードバウンス**：永続的なエラー（メールアドレスの間違いなど）の合計数。
* **ソフトバウンス**：一時的なエラー（受信トレイが満杯など）の合計数。

2 つ目のテーブルの&#x200B;**トラッキング統計**&#x200B;には、配信に対する受信者の反応についての次のような利用可能なデータが含まれます。

* **配信済み**：正常に配信されたメールの数。
* **開封**：1 つの配信で、あるメッセージが開かれた回数。
* **クリック**：1 つの配信で、あるコンテンツがクリックされた回数。
* **購読解除済み**：購読リンクがクリックされた回数。
* **ミラーページ**：ミラーページリンクがクリックされた回数。
* **ブロックリスト登録済み**：メールをスパムまたは迷惑メールとして報告した受信者の数。 [詳細情報](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
