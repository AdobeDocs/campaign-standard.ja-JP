---
title: バウンスサマリ
seo-title: バウンスサマリ
description: バウンスサマリ
seo-description: バウンスのサマリレポートを使用して、送信したキャンペーンとエラーのステータスについて確認します。
page-status-flag: 常にアクティブ化されていない
uuid: 90087311-4236-4df9- ae7d-4a15c00c70ab
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: レポートのリスト
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: boundPort， main;campaignCirculationReport， main;ProgramCircationReport， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Bounce summary{#bounce-summary}

このレポートでは、配信中に発生する全体的なハードおよびソフトエラーおよびバウンスの自動処理について説明します。

![](assets/campaign_reports_bounces.png)

各テーブルは、概要番号とグラフで表されます。それぞれのビジュアライゼーション設定で詳細を表示する方法を変更できます。

**5つの配信の** リストには、最大の隔離数を持つ5つの配信が表示されます。

**バウンスの理由** テーブルには、各配信のバウンスにつながったエラーのタイプに関する使用可能なデータが含まれています。

* **[!UICONTROL User unknown]**:配信が無効な電子メールアドレスに送信されたときに生成されるエラーのタイプ。
* **[!UICONTROL Invalid domain]**:ドメインが誤っているか、存在しなくなった電子メールアドレスに配信が送信されたときに生成されるエラーのタイプ。
* **[!UICONTROL Unreachable]**:メッセージ配信文字列で発生したエラーのタイプ。例えば、SMTPリレーインシデント、ドメインの一時的な到達などがあります。
* **[!UICONTROL Account disabled]**:配信が存在しない電子メールアドレスに配信されたときに生成されるエラーの種類。
* **[!UICONTROL Mailbox full]**:受信者の受信トレイがいっぱいになったときに生成されるエラーの種類。このエラーが発生する前に、メッセージの配信を5回試みます。
* **[!UICONTROL Not connected]**:受信者の携帯電話がオフになっている場合、またはメッセージの送信時にネットワークに接続されていないときに生成されるエラーのタイプです。

   >[!NOTE]
   >
   >このタイプのエラーは、モバイルチャネルに対する配信にのみ影響します。

* **[!UICONTROL Refused]**:インターネットサービスプロバイダー（ISP）によってアドレスが拒否されたときに生成されるエラーのタイプ。例えば、セキュリティルールがスパム対策ソフトウェアによって適用されているとします。

**ドメインリパーティション** テーブルには、受信者ドメインに従って配信中に発生した全体的な問題が表示されます。
