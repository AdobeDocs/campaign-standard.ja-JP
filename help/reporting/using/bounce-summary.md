---
title: バウンス概要
description: すぐに使用できるバウンスの概要レポートで、送信済みキャンペーンのステータスと発生した可能性のあるエラーを確認します。
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

このレポートには、配信中に発生したハードエラーとソフトエラーの全体、およびバウンスの自動処理の詳細が記載されています ( [配信エラーの理解](../../sending/using/understanding-delivery-failures.md)) をクリックします。

![](assets/campaign_reports_bounces.png)

各テーブルは、数値の概要とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

**5 個の再区分をフロップ** に、強制隔離の数が最も多い 5 件の配信のリストを表示します。

この **バウンスの理由** テーブルには、各配信のバウンスを引き起こしたエラーのタイプに関して使用可能なデータが含まれています。

* **[!UICONTROL User unknown]**:配信が無効な E メールアドレスに送信されたときに生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**:ドメインが正しくないか存在しない E メールアドレスに配信が送信されたときに生成されるエラーのタイプ。
* **[!UICONTROL Unreachable]**:メッセージ配信文字列で発生したエラーのタイプ（一時的に到達できないドメインなど）。
* **[!UICONTROL Account disabled]**:存在しない E メールアドレスに配信が送信されたときに生成されるエラーのタイプ。
* **[!UICONTROL Mailbox full]**:受信者の受信ボックスがいっぱいになったときに生成されるエラーのタイプ。 このエラーが生成される前に、5 回メッセージの配信を試みます。
* **[!UICONTROL Not connected]**:受信者の携帯電話がオフの場合、またはメッセージの送信時にネットワークに接続されていない場合に生成されるエラーのタイプ。

   >[!NOTE]
   >
   >このタイプのエラーは、モバイルチャネルでの配信にのみ関係します。

* **[!UICONTROL Refused]**:インターネットサービスプロバイダー (ISP) がアドレスを拒否した場合に生成されるエラーのタイプ。 例えば、スパム対策ソフトウェアによってセキュリティルールが適用された場合などです。

この **ドメインの再区分** 「 」テーブルには、受信者ドメインに応じて、配信中に発生した問題の全体が表示されます。
