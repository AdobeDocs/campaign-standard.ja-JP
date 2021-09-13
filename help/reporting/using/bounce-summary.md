---
title: バウンス概要
description: すぐに使用できるバウンスの概要レポートで、送信したキャンペーンのステータスと発生した可能性のあるエラーを確認します。
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
source-wordcount: '277'
ht-degree: 1%

---

# バウンス概要{#bounce-summary}

このレポートには、配信中に発生したハードエラーとソフトエラーの全体と、バウンスの自動処理の詳細が表示されます（[配信エラーの理解](../../sending/using/understanding-delivery-failures.md)を参照）。

![](assets/campaign_reports_bounces.png)

各テーブルは、概要の数値とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

**Flop 5の再分** 割は、強制隔離の数が最も多い5つの配信をリストします。

**バウンス理由**&#x200B;テーブルには、各配信でバウンスが発生したエラーのタイプで使用可能なデータが含まれます。

* **[!UICONTROL User unknown]**:配信が無効なEメールアドレスに送信されたときに生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**:ドメインが正しくないか存在しないEメールアドレスに配信が送信されたときに生成されるエラーのタイプ。
* **[!UICONTROL Unreachable]**:一時的に到達できないドメインなど、メッセージ配信文字列で発生したエラーのタイプ。
* **[!UICONTROL Account disabled]**:存在しないEメールアドレスに配信を送信したときに生成されるエラーのタイプ。
* **[!UICONTROL Mailbox full]**:受信者の受信ボックスがいっぱいになったときに生成されるエラーのタイプ。このエラーが生成される前に、メッセージの配信は5回試行されます。
* **[!UICONTROL Not connected]**:受信者の携帯電話の電源が切れた場合、またはメッセージの送信時にネットワークに接続されていない場合に生成されるエラーのタイプ。

   >[!NOTE]
   >
   >このタイプのエラーは、モバイルチャネルでの配信のみに関係します。

* **[!UICONTROL Refused]**:インターネットサービスプロバイダー(ISP)がアドレスを拒否した場合に生成されるエラーのタイプ。例えば、スパム対策ソフトウェアによってセキュリティルールが適用された場合などです。

**ドメインの再パーティション**&#x200B;テーブルには、受信者のドメインに従って、配信中に発生した全体的な問題が表示されます。
