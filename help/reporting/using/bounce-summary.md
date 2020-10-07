---
title: バウンス概要
description: すぐに使用できるバウンスの概要レポートを使用して、送信されたキャンペーンの状態と発生した可能性のあるエラーを確認します。
page-status-flag: never-activated
uuid: 90087311-4236-4df9-ae7d-4a15c00c70ab
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 8%

---


# バウンス概要{#bounce-summary}

このレポートには、配信中に発生したハードエラーとソフトエラーの全般、およびバウンスの自動処理の詳細が記載されます。

![](assets/campaign_reports_bounces.png)

各表は、数値の概要とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

**フロップ5は** 、強制隔離数が最も多い5つの配信を再パーティション化します。

「 **バウンスの理由** 」テーブルには、各配信でバウンスを引き起こしたエラーのタイプについて、使用できるデータが含まれています。

* **[!UICONTROL User unknown]**:配信が無効な電子メールアドレスに送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**:ドメインが正しくない、または存在しなくなった電子メールアドレスに配信が送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Unreachable]**:メッセージ配信文字列で発生したエラーの種類(ドメインの一時未到達など)。
* **[!UICONTROL Account disabled]**:存在しない電子メールアドレスに配信が送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Mailbox full]**:受信者のインボックスがいっぱいの場合に生成されるエラーの種類です。 このエラーが生成される前に、5回の試行でメッセージの配信が試行されます。
* **[!UICONTROL Not connected]**:受信者の携帯電話がオフの場合、またはメッセージの送信時にネットワークに接続されていない場合に生成されるエラーの種類です。

   >[!NOTE]
   >
   >この種のエラーは、モバイルチャネルの配信にのみ関係します。

* **[!UICONTROL Refused]**:インターネットサービスプロバイダー(ISP)がアドレスを拒否した場合に生成されるエラーの種類です。 例えば、スパム対策ソフトウェアによってセキュリティ規則が適用された場合です。

「 **ドメインの再パーティション化** 」(Domain repartition)テーブルには、受信者ドメインに従って配信中に発生した問題全体が表示されます。
