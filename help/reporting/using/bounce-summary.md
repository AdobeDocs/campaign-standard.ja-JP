---
solution: Campaign Standard
product: campaign
title: バウンス概要
description: すぐに使用できるバウンスの概要レポートを使用して、送信されたキャンペーンの状態と発生した可能性のあるエラーを確認します。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 8%

---


# バウンス概要{#bounce-summary}

このレポートには、配信中に発生したハードエラーとソフトエラーの全般、およびバウンスの自動処理の詳細が記載されます。

![](assets/campaign_reports_bounces.png)

各表は、数値の概要とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

**Flop 5の** 繰り返しには、強制隔離数が最も多い5つの配信が表示されます。

**バウンスの理由**&#x200B;テーブルには、各配信でバウンスを引き起こしたエラーのタイプについて、使用可能なデータが含まれています。

* **[!UICONTROL User unknown]**:配信が無効な電子メールアドレスに送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**:ドメインが正しくない、または存在しなくなった電子メールアドレスに配信が送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Unreachable]**:メッセージ配信文字列で発生したエラーの種類(ドメインの一時未到達など)。
* **[!UICONTROL Account disabled]**:存在しない電子メールアドレスに配信が送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Mailbox full]**:受信者のインボックスがいっぱいの場合に生成されるエラーの種類です。このエラーが生成される前に、5回の試行でメッセージの配信が試行されます。
* **[!UICONTROL Not connected]**:受信者の携帯電話がオフの場合、またはメッセージの送信時にネットワークに接続されていない場合に生成されるエラーの種類です。

   >[!NOTE]
   >
   >この種のエラーは、モバイルチャネルの配信にのみ関係します。

* **[!UICONTROL Refused]**:インターネットサービスプロバイダー(ISP)がアドレスを拒否した場合に生成されるエラーの種類です。例えば、スパム対策ソフトウェアによってセキュリティ規則が適用された場合です。

**ドメイン再パーティション**&#x200B;テーブルには、受信者ドメインに従って配信中に発生した問題全体が表示されます。
