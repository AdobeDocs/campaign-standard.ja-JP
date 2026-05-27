---
title: バウンス概要
description: 標準のバウンス概要レポートでは、送信済みキャンペーンのステータスと、発生した可能性のあるエラーについて確認できます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
TQID: https://experienceleague.adobe.com/ggB-q-6kJyPF4GgJJzJGtsOqg6-7MeBhEfiGVY0M7sQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 282
ht-degree: 47%

---

# バウンス概要{#bounce-summary}

このレポートでは、配信中に発生した全体的なハードエラーとソフトエラー、およびバウンスの自動処理について詳しく説明します（[配信エラーについて](../../sending/using/understanding-delivery-failures.md)を参照）。

![](assets/campaign_reports_bounces.png)

各テーブルは、概要の数値とグラフで表されています。 それぞれのビジュアライゼーション設定で、詳細の表示方法を変更できます。

**フロップ 5 の再区分**&#x200B;には、強制隔離数が最も多い 5 つの配信が一覧表示されます。

**バウンスの理由**&#x200B;テーブルには、各配信でバウンスの原因となったエラーの種類に関する利用可能なデータが含まれています。

* **[!UICONTROL User unknown]**：配信が無効な電子メールアドレスに送信されたときに生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**: ドメインが間違っているか、もはや存在しないメールアドレスに配信を送信したときに生成されるエラーの種類です。
* **[!UICONTROL Unreachable]**: メッセージ配信文字列で発生したエラーの種類（ドメインに一時的に到達できないなど）。
* **[!UICONTROL Account disabled]**：配信が存在しない電子メールアドレスに送信されたときに生成されるエラーの種類。
* **[!UICONTROL Mailbox full]**：受信者の受信トレイがいっぱいになったときに生成されるエラーの種類。 このエラーが生成されるまで、メッセージを配信する試みは 5 回あります。
* **[!UICONTROL Not connected]**：受信者の携帯電話がオフの場合、またはメッセージの送信時にネットワークに接続されていない場合に生成されるエラーの種類です。

  >[!NOTE]
  >
  >この種のエラーは、モバイルチャネルでの配信のみに該当します。

* **[!UICONTROL Refused]**: アドレスがインターネット サービス プロバイダー（ISP）によって拒否されたときに生成されるエラーの種類です。 例えば、スパム対策ソフトウェアによってセキュリティルールが適用された場合などです。

**ドメインの再区分**&#x200B;テーブルには、受信者ドメインに応じた、配信中に発生した全体的な問題が表示されます。
