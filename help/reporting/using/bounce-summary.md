---
title: バウンス概要
description: 標準のバウンス概要レポートで、送信済みキャンペーンのステータスと、発生した可能性のあるエラーについて説明します。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# バウンス概要{#bounce-summary}

このレポートは、配信中に発生した全体的なハードエラーとソフトエラーおよびバウンスの自動処理について詳しく説明します（[ 配信エラーについて ](../../sending/using/understanding-delivery-failures.md) を参照）。

![](assets/campaign_reports_bounces.png)

各テーブルは、概要番号とグラフで表されます。 それぞれのビジュアライゼーション設定で、詳細の表示方法を変更できます。

**フロップ 5 の再パーティション** には、強制隔離数が最も多い 5 つの配信が一覧表示されます。

**バウンスの理由** テーブルには、各配信でバウンスを発生させたエラーの種類に関する利用可能なデータが含まれています。

* **[!UICONTROL User unknown]**：配信が無効なメールアドレスに送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**: ドメインが正しくないか、存在しないメールアドレスに配信が送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Unreachable]**: ドメインに一時的に到達できないなど、メッセージ配信文字列で発生したエラーのタイプ。
* **[!UICONTROL Account disabled]**：配信が存在しないメールアドレスに送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Mailbox full]**：受信者のインボックスがいっぱいであるときに生成されるエラーのタイプ。 このエラーが生成される前に、メッセージを配信する試みは 5 回あります。
* **[!UICONTROL Not connected]**：受信者の携帯電話がオフになっているか、メッセージの送信時にネットワークに接続されていない場合に生成されるエラーのタイプ。

  >[!NOTE]
  >
  >このタイプのエラーは、モバイルチャネルでの配信にのみ関係します。

* **[!UICONTROL Refused]**: アドレスがインターネットサービスプロバイダー（ISP）によって拒否された場合に生成されるエラーのタイプ。 例えば、スパム対策ソフトウェアによってセキュリティルールが適用された場合などです。

**ドメインの再パーティション** テーブルには、受信者ドメインに応じた、配信中に発生した全体的な問題が表示されます。
