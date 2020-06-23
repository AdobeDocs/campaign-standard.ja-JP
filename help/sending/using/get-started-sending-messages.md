---
title: テストと送信を開始する
description: メッセージをテストして送信するための様々な手順を見つけてください。
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
source-git-commit: 2df909256b910e5e26e0fdac7e150edd0603c8ab
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 10%

---


# テストと送信を開始する {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">準備とテスト</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">送信、監視、および追跡</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">配信品質のガイドライン</a></p></td></tr>
</table>

ターゲットを定義し、メッセージのコンテンツを作成したら、配信のコンテンツ、パーソナライゼーション、レンダリング、設定を準備し、テストする必要があります。 これにより、メインターゲットにメッセージを送信する前に、すべてが正しいことを確認できます。 これを行うには、プレビュー、配達確認、電子メールの件名行テスト、電子メールのレンダリングなど、複数の機能を使用できます。

マーケティングキャンペーンが実行され、異なるメッセージが送信されたら、ログを使用してメッセージを監視し、キャンペーンの成功を確認し、受信者の追跡情報を取得します。

最後に、Campaign Standardで利用可能な配信品質ガイドラインとツールを活用して、配信されるメッセージの数を改善し、マーケティングキャンペーンを成功に導きます。

## 準備とテスト {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **メッセージ作成** :ターゲット、パーソナライゼーション、およびメッセージの有効性を分析します。 この手順で検出されたエラーは、さらに進む前に修正する必要があります。

**次の様々な機能を使用して** 、メッセージのプレビューとテストを行います。 プロファイルやタグ付きプロファイルをテストする配達確認を送信し、電子メールの件名をテストし、メッセージのレンダリングがWebクライアント、Webメール、デバイスに最適に表示されるかどうかを確認します。

キャンペーンスケジュール機能を活用して、メッセージを送信するタイミングを定義します。 例えば、受信者のタイムゾーンで送信を適応させたり、送信時間を最適化したり、送信日を計算したりできます。

タイ **ポロジ** を使用して、メッセージが有効で、疲労、制御およびターゲットルールを通じて品質基準を満たしているかどうかを準備中に確認します。 例えば、電子メールに常に件名行が含まれているかどうかを確認したり、メッセージ受信者から非購読者を除外したりする場合です。

詳しくは、以下を参照してください。

* [送信の準備](../../sending/using/preparing-the-send.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [電子メールのレンダリング](../../sending/using/email-rendering.md)
* [メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)
* [タイポロジとタイポロジルールについて](../../sending/using/about-typology-rules.md)

## 送信、監視、および追跡 {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

メッセージの準備が整ったら、送信ログおよびレポートにアクセスして、配信を **監視し** 、キャンペーンの成功を測定できます。 Adobe Campaignは、配信の成功や失敗、および強制隔離管理機能を追跡するための電子メール警告システムも提供します。

**セッション** と永久的なcookieを使用して追跡受信者(クリックされたURL、ミラーページ、開かれたメッセージなど)を取得し、メッセージ情報の動作を追跡します。

最後に、プラットフォームから電子メールBCC経由で **送信された電子メールのコピーを** 保持するようにAdobe Campaignを設定できます。 特に、組織で、アウトバウンド電子メールメッセージをすべてアーカイブして準拠する必要がある場合は、この機能を有効にできます。

詳しくは、以下を参照してください。

* [送信の確認](../../sending/using/confirming-the-send.md)
* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [電子メール BCC を使用したアーカイブ](../../sending/using/archiving.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
* [配信エラーの理解](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)

## 配信品質のガイドライン {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

配信品質を使用すると、バウンスを発生させたりスパムとしてマークされたりすることなく、受信者の受信トレイに届いたキャンペーンの成功を測定できます。

Campaign Standardには、正常に配信されたメッセージの数を改善するために役立つ **** 配信品質ツールがいくつか用意されています。 配信の考慮されたレポート、送信時間の最適化、メッセージプレビュー、電子メールのレンダリング、強制隔離管理など

詳しくは、以下を参照してください。

* [配信品質について](../../sending/using/about-deliverability.md)
* [配信品質の監視](../../sending/using/monitor-deliverability.md)
* [評価の向上](../../sending/using/improving-reputation.md)
* [技術的な推奨事項](../../sending/using/technical-recommendations.md)
* [配信スループットの制御](../../reporting/using/delivery-throughput.md)

## その他のリソース

* [A/Bテスト電子メールの設計](../../channels/using/designing-an-a-b-test-email.md)
* [テストの送信、準備、電子メールの送信（ビデオ）](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/sending-test-preparing-sending-email.html)
* [電子メール配信とレポートの確認（ビデオ）](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/reviewing-personalized-email-delivery-and-reports.html)
* [電子メールの使い始めに](https://helpx.adobe.com/campaign/kb/acs-get-started-with-emails.html)
* [配信のベストプラクティス](https://helpx.adobe.com/jp/campaign/kb/delivery-best-practices.html)