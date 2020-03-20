---
title: Campaign でのメッセージの送信について
description: テストとメッセージの送信のための異なる手順を見つけます。
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6e605f1046ddcbad9b4e6f369ea5ecf7202f3def

---


# Campaign でのメッセージの送信について{#about-sending-messages-with-campaign}

ターゲットを定義し、メッセージのコンテンツを作成したら、メインターゲットにメッセージを送信する前に、テストおよび承認する必要があります。 手順は次のとおりです。

* テストプロファイルを使用して配信をプレビューします。
* 送信のスケジュール：メッセージを送信するタイミングを定義します。
* 送信の準備：この手順を実行すると、送信するメッセージの分析と準備に移ることができます。 メッセージ作成は、ターゲット、パーソナライゼーション、およびメッセージの有効性を分析する。 この手順で検出されたエラーは、先に進む前に修正する必要があります。 メッセージの準備は、必要な回数だけ起動できます。

   >[!NOTE]
   >
   >キャンペーンから過剰なプロファイルを自動的に除外する、グローバルなチャネル間疲労ルールを設定できます。 疲労ルー [ルを参照してくださ](../../administration/using/fatigue-rules.md)い。

* 送信のテスト：この手順では、配達確認を送信してメッセージを承認できます。
* 配信のレンダリングを確認します。様々なWebクライアント、Webメール、デバイスに最適な方法でメッセージを表示する（強くお勧めします）。
* メッセージの送信：メッセージの準備が整ったら、送信を開始できます。 その後、アクセスログとレポートを使用して、メッセージ配信を監視し、キャンペーンの成功度を測定できます。 また、Adobe Campaignは、配信の成功または失敗を追跡するための電子メール警告システムも提供します。

**関連トピック**：

* [メッセージのスケジュールについて](../../sending/using/about-scheduling-messages.md)
* [送信の準備](../../sending/using/preparing-the-send.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [電子メールのレンダリング](../../sending/using/email-rendering.md)
* [エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)
* [配信品質の最適化](../../sending/using/about-deliverability.md)
