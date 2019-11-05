---
title: バウンス概要
description: すぐに使えるバウンスサマリレポートを使用して、送信されたキャンペーンのステータスと発生した可能性のあるエラーについて説明します。
page-status-flag: 非活性化の
uuid: 90087311-4236-4df9-ae7d-4a15c00c70ab
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: レポートのリスト
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: bounceReport,main;campaignCurculationReport,main;programCurculationReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# バウンス概要{#bounce-summary}

このレポートは、配信中に発生したハードエラーとソフトエラーの全体と、バウンスの自動処理の詳細を示します。

![](assets/campaign_reports_bounces.png)

各表は、概要番号とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

**Flop 5 repartitionは** 、検疫数が最も多い5つの配信を示します。

「バウ **ンスの理由** 」テーブルには、各配信でバウンスを引き起こしたエラーのタイプに関して使用できるデータが含まれています。

* **[!UICONTROL User unknown]**:配信が無効な電子メールアドレスに送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**:ドメインが間違っているか、存在しなくなった電子メールアドレスに配信が送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Unreachable]**:メッセージ配信文字列で発生したエラーのタイプ。 例えば、SMTPリレーインシデント、ドメインに一時的に到達できないなど。
* **[!UICONTROL Account disabled]**:配信が存在しなくなった電子メールアドレスに送信された場合に生成されるエラーのタイプ。
* **[!UICONTROL Mailbox full]**:受信者の受信トレイがいっぱいの場合に生成されるエラーの種類です。 このエラーが生成される前に、5回メッセージを配信しようとします。
* **[!UICONTROL Not connected]**:受信者の携帯電話がオフの場合、またはメッセージの送信時にネットワークに接続されていない場合に生成されるエラーの種類です。

   >[!NOTE]
   >
   >このタイプのエラーは、モバイルチャネルへの配信にのみ関係します。

* **[!UICONTROL Refused]**:インターネットサービスプロバイダ(ISP)がアドレスを拒否した場合に生成されるエラーの種類です。 例えば、スパム対策ソフトウェアによってセキュリティルールが適用された場合です。

「ドメイ **ンの再分割** 」テーブルには、受信者ドメインに従って、配信中に発生した問題全体が表示されます。
