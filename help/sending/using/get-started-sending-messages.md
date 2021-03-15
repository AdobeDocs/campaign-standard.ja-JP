---
solution: Campaign Standard
product: campaign
title: テストと送信の概要
description: メッセージの準備、テスト、スケジュール、送信、および監視を行います。
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 15%

---


# テストと送信の概要 {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">準備とテスト</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">送信、監視、および追跡</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">配信品質のガイドライン</a></p></td></tr>
</table>

ターゲットを定義し、メッセージのコンテンツを作成したら、配信のコンテンツ、パーソナライゼーション、レンダリング、設定を準備し、テストする必要があります。 これにより、メインターゲットにメッセージを送信する前に、すべてが正しいことを確認できます。 これを行うには、プレビュー、配達確認、電子メールの件名行テスト、電子メールのレンダリングなど、複数の機能を使用できます。

マーケティングキャンペーンが実行され、異なるメッセージが送信されたら、ログを使用してメッセージを監視し、キャンペーンの成功を確認し、受信者の追跡情報を取得します。

最後に、Campaign Standardで利用可能な配信品質ガイドラインとツールを活用して、配信されるメッセージの数を改善し、マーケティングキャンペーンを成功に導きます。

![](assets/do-not-localize/how-to-video.png) [ビデオでのテスト用電子メールの送信、電子メール配信の準備および送信方法の確認](#video)

## {#prepare-test-send}の準備とテスト

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **メッセージ準備**&#x200B;は、メッセージのターゲット、パーソナライゼーション、有効性を分析します。 この手順で検出されたエラーは、さらに進む前に修正する必要があります。

**様々な機能を使用したプレビューと** テスト：プロファイルやタグ付きプロファイルをテストする配達確認を送信し、電子メールの件名をテストし、メッセージのレンダリングがWebクライアント、Webメール、デバイスに最適に表示されるかどうかを確認します。

キャンペーンスケジュール機能を活用して、メッセージを送信するタイミングを定義します。 例えば、受信者のタイムゾーンで送信を適応させたり、送信時間を最適化したり、送信日を計算したりできます。

**タイポロジ**&#x200B;を使用して、メッセージが有効で、疲労、制御、ターゲティングのルールによって品質基準を満たしているかどうかを準備中に確認します。 例えば、電子メールに常に件名行が含まれているかどうかを確認したり、メッセージ受信者から非購読者を除外したりする場合です。

詳しくは、以下を参照してください。

* [送信の準備](../../sending/using/preparing-the-send.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [E メールのレンダリング](../../sending/using/email-rendering.md)
* [メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)
* [タイポロジとタイポロジルールについて](../../sending/using/about-typology-rules.md)

## 送信、監視、および追跡{#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

メッセージの準備が整ったら、**配信**&#x200B;を監視し、キャンペーンの成功を測定するために、送信ログとレポートにアクセスするかどうかを確認できます。 Adobe Campaignは、配信の成功や失敗、および強制隔離管理機能を追跡するための電子メール警告システムも提供します。

**セッションと永久的なcookieを使用して追跡受信者(クリックされたURL、ミラーページ、開かれたメッセージなど)を取得し、メッセージ情報の** 動作を追跡します。

最後に、EメールBCCを通じてプラットフォームから送信された電子メール&#x200B;**のコピーを**&#x200B;保持するようにAdobe Campaignを設定できます。 特に、組織で、アウトバウンド電子メールメッセージをすべてアーカイブして準拠する必要がある場合は、この機能を有効にできます。

詳しくは、以下を参照してください。

* [送信の確認](../../sending/using/confirming-the-send.md)
* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [E メール BCC を使用したアーカイブ](../../sending/using/archiving.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
* [配信エラーの理解](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)

## 配信品質のガイドライン{#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

配信品質を使用すると、バウンスを発生させたりスパムとしてマークされたりすることなく、受信者の受信トレイに届いたキャンペーンの成功を測定できます。

Campaign Standardは、配信に成功したメッセージの数を改善するための&#x200B;**配信品質ツール**&#x200B;をいくつか提供しています。配信の考慮されたレポート、送信時間の最適化、メッセージプレビュー、電子メールのレンダリング、強制隔離管理など

詳しくは、以下を参照してください。

* [配信品質について](../../sending/using/about-deliverability.md)
* [配信品質の監視](../../sending/using/monitor-deliverability.md)
* [評価の向上](../../sending/using/improving-reputation.md)
* [技術的な推奨事項](../../sending/using/technical-recommendations.md)
* [配信スループットの制御](../../reporting/using/delivery-throughput.md)

## その他のリソース

* [A/Bテスト電子メールの設計](../../channels/using/designing-an-a-b-test-email.md)
* [電子メールの使い始めに](https://helpx.adobe.com/jp/campaign/kb/acs-get-started-with-emails.html)
* [配信のベストプラクティス](../../sending/using/delivery-best-practices.md)
* [コントロール母集団の追加](../../sending/using/control-group.md)

## チュートリアルビデオ {#video}

このビデオでは、テスト用の電子メールを送信し、Campaign Standardで電子メール配信を準備して送信する方法を示します。

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)で参照できます。
