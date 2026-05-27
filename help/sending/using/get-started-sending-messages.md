---
title: テストと送信の基本を学ぶ
description: メッセージの準備、テスト、スケジュール、送信、および監視を行います。
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
TQID: https://experienceleague.adobe.com/0dYFLX0zAqDIz27Y-ekkp9a9rHE9zdjOjioh5gBwaAA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 15%

---

# テストと送信の基本を学ぶ {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">準備とテスト</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">送信、監視、追跡</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">配信品質のガイドライン</a></p></td></tr>
</table>

ターゲットを定義し、メッセージのコンテンツを作成したら、配信のコンテンツ、パーソナライゼーション、レンダリング、設定を準備してテストする必要があります。 これにより、メインターゲットにメッセージを送信する前に、すべてが正しいことを確認できます。 プレビュー、プルーフ、電子メールの件名テスト、電子メールのレンダリングなど、さまざまな機能を利用できます。

マーケティングキャンペーンが実行され、さまざまなメッセージが送信されたら、ログを使用してキャンペーンの成功を確認し、受信者の追跡情報を取得して監視します。

さらに、Campaign Standardで利用できる配信品質のガイドラインとツールを活用して、配信されるメッセージ数を増やし、マーケティング施策を成功に導くことができます。

![](assets/do-not-localize/how-to-video.png) [&#x200B; テストメールの送信方法、準備およびメール配信の送信方法をビデオで確認](#video)

## 準備とテスト {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **メッセージ準備**&#x200B;は、ターゲット、パーソナライゼーション、メッセージの有効性を分析します。 このステップ中に検出されたエラーは、さらに進める前に修正する必要があります。

**様々な機能を使用してメッセージをプレビューおよびテスト**&#x200B;します。プルーフを送信して、プロファイルまたはターゲット設定されたプロファイルをテストし、電子メールの件名をテストし、メッセージのレンダリングを確認して、様々なweb クライアント、web メール、デバイスで最適な方法で表示されるようにします。

キャンペーンのスケジュール機能を活用して、メッセージがいつ送信されるかを定義します。 例えば、受信者のタイムゾーンで送信を調整したり、送信時間を最適化したり、送信日を計算したりできます。

メッセージが有効かどうか、および疲労、制御、およびターゲティングルールを通じて品質基準を満たしているかどうかを準備中に確認するには、**タイポロジ**&#x200B;を使用します。 例えば、電子メールに件名が常に含まれていることを確認したり、購読解除をメッセージ受信者から除外したりします。

詳しくは、以下を参照してください。

* [送信の準備](../../sending/using/preparing-the-send.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [メールのレンダリング](../../sending/using/email-rendering.md)
* [メッセージのスケジュール設定](../../sending/using/about-scheduling-messages.md)
* [タイポロジとタイポロジルールについて](../../sending/using/about-typology-rules.md)

## 送信、監視、追跡 {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

メッセージの準備が整ったら、送信ログとアクセスログおよびレポートを確認して、**配信を監視**&#x200B;し、キャンペーンの成功を測定できます。 Adobe Campaignには、配信の成功と失敗を追跡するメールアラートシステムや、強制隔離の管理機能も備わっています。

**セッションと永続的なCookieを使用してトラッキング情報（クリックされたURL、ミラーページ、開かれたメッセージなど）を取得し、メッセージ受信者の動作**&#x200B;を追跡します。

最後に、Adobe Campaignを設定して、**メール BCCを通じてプラットフォームから送信されたメールのコピー**&#x200B;を保持できます。 特に、コンプライアンスのために送信メールのメッセージをすべてアーカイブする必要がある場合は、この機能を有効にできます。

詳しくは、以下を参照してください。

* [送信の確認](../../sending/using/confirming-the-send.md)
* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [メールの BCC を使用したアーカイブ](../../sending/using/archiving.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
* [配信エラーについて](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理について](../../sending/using/understanding-quarantine-management.md)

## 配信品質のガイドライン {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

配信品質により、受信者にバウンスしたり、迷惑メールとしてマークされたりすることなく、キャンペーンの成果を測定することができます。

Campaign Standardには、正常に配信されたメッセージの数を増やすのに役立つ&#x200B;**配信品質ツール**&#x200B;がいくつか用意されています。配信スループットレポート、送信時間の最適化、メッセージのプレビュー、メールのレンダリング、強制隔離の管理など、メッセージの配信数を増やすことができます。

詳しくは、以下を参照してください。

* [配信品質について](../../sending/using/about-deliverability.md)
* [配信品質の監視](../../sending/using/monitor-deliverability.md)
* [Adobe配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ja)
* [配信スループットの制御](../../reporting/using/delivery-throughput.md)

## その他のリソース

* [A/B テストメールのデザイン](../../channels/using/designing-an-a-b-test-email.md)
* [メッセージの基本を学ぶ](../../channels/using/key-steps-to-send-a-message.md)
* [配信のベストプラクティス](../../sending/using/delivery-best-practices.md)
* [コントロール母集団の追加](../../sending/using/control-group.md)

## チュートリアルビデオ {#video}

このビデオでは、Campaign Standardでテストメールを送信し、準備してからメール配信を送信する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/328368?captions=jpn)

その他のCampaign Standardのハウツー動画は[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)でご覧いただけます。
