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
source-git-commit: e6c43770755e59bf2a2d49540a052ac0bd2a2438

---


# Campaign でのメッセージの送信について{#about-sending-messages-with-campaign}

ターゲットを定義し、メッセージのコンテンツを作成したら、コンテンツのテストと承認、パーソナライゼーション、レンダリング、設定を行い、すべてが正しいことを確認してから、メインターゲットにメッセージを送信する必要があります。

これを行うためのベストプラクティスは次のとおりです。

* 送信の準備：この手順を実行すると、送信するメッセージの分析と準備に移ることができます。 メッセージ作成は、ターゲット、パーソナライゼーション、及びメッセージの有効性を分析する。 この手順で検出されたエラーは、先に進む前に修正する必要があります。 メッセージの準備は、必要な回数だけ起動できます。 For more on message preparation, refer to [this section](../../sending/using/preparing-the-send.md).

   >[!NOTE]
   >
   >訪問者から過剰訪問のプロファイルを自動的に除外する、チャネル間の疲労ルールをグローバルに設定できます。 疲労ルー [ルを参照してくださ](../../sending/using/fatigue-rules.md)い。

* プレビューメッセージをテストプロファイル。 For more on previewing messages, refer to [this section](../../sending/using/previewing-messages.md).
* 配達確認を送信してメッセージをテストします。 For more on proofs, refer to [this  section](../../sending/using/sending-proofs.md).
* メッセージのレンダリングを確認します。様々なWebクライアント、Webメール、デバイスに最適な方法でメッセージが表示されるようにします。 電子メールのレンダリングについて詳し [くは、この節](../../sending/using/email-rendering.md)。

その後、次の操作を実行できます。

* 送信のスケジュール：メッセージを送信するタイミングを定義できます。 例えば、送信を受信者のタイムゾーンに合わせて調整したり、送信時刻を最適化したり、送信日を計算したりできます。 詳しくは、[この節](../../sending/using/about-scheduling-messages.md)を参照してください。
* メッセージの送信：メッセージの準備が整ったら、送信側の開始を作成できます。 その後、アクセスログとレポートを使用して、メッセージ配信を監視し、成功度を測定できます。 Adobe Campaignは、電子メール通知システムも提供し、配信の成功や失敗を追跡します。 Learn more in [this page](../../sending/using/confirming-the-send.md).

## 関連トピック

| 役に立つページ | その他のリソース |
|---|---|
| [配信品質の最適化](../../sending/using/about-deliverability.md) | [疲労管理](../../sending/using/fatigue-rules.md) |
| [配信の監視](../../audiences/using/creating-profiles.md) | [A/Bテスト電子メールの設計](../../channels/using/designing-an-a-b-test-email.md) |
| [エラー発生時の通知の受信](../../sending/using/receiving-alerts-when-failures-happen.md) | [配信の監視](../../sending/using/monitoring-a-delivery.md) |
| [コントロール母集団の作成](../../automating/using/workflow-control-group.md) | [エラー発生時の通知の受信](../../sending/using/receiving-alerts-when-failures-happen.md) |
| [配信スループットの制御](../../reporting/using/delivery-throughput.md) | [配信の監視](../../sending/using/monitoring-a-delivery.md) |