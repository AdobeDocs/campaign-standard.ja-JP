---
title: バウンス概要
description: すぐに使用できるバウンスの概要レポートを使用して、送信されたキャンペーンのステータスと発生した可能性のあるエラーについて説明します。
page-status-flag: never-activated
uuid: 90087311-4236-4df9-ae7d-4a15c00c70ab
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bee7ea0f1728da2a96c1f225b91b13a7903be660

---


# バウンス概要{#bounce-summary}

このレポートは、配信中に発生したハードエラーとソフトエラーの全体と、バウンスの自動処理の詳細を示します。

![](assets/campaign_reports_bounces.png)

各表は、概要番号とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

**Flop 5 repartitionは** 、最も多い検疫数を持つ5つの配信を示します。

「バウ **ンスの理由** 」テーブルには、各配信でバウンスを引き起こしたエラーのタイプに関して、使用可能なデータが含まれています。

* **[!UICONTROL User unknown]**:配信が無効な電子メールアドレスに送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**:ドメインが間違っているか、存在しなくなった電子メールアドレスに配信が送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Unreachable]**:メッセージ配信文字列で発生したエラーの種類（ドメインが一時的に到達不能な場合など）。
* **[!UICONTROL Account disabled]**:存在しない電子メールアドレスに配信が送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Mailbox full]**:受信者の受信トレイがいっぱいの場合に生成されるエラーの種類です。 このエラーが生成される前に、5回の試行でメッセージの配信が試行されます。
* **[!UICONTROL Not connected]**:受信者の携帯電話がオフの場合、またはメッセージの送信時にネットワークに接続されていない場合に生成されるエラーの種類です。

   >[!NOTE]
   >
   >このタイプのエラーは、モバイルチャネルへの配信にのみ関係します。

* **[!UICONTROL Refused]**:インターネットサービスプロバイダ(ISP)がアドレスを拒否した場合に生成されるエラーの種類です。 例えば、スパム対策ソフトウェアによってセキュリティルールが適用された場合などです。

「ドメイ **ンの再パーティション** 」(Domain repartition)テーブルには、受信者ドメインに従って配信中に発生した問題全体が表示されます。
