---
title: テストと送信の基本を学ぶ
description: メッセージの準備、テスト、スケジュール、送信、および監視を行います。
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 12%

---

# テストと送信の基本を学ぶ {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">準備とテスト</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">送信、監視、トラッキング</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">配信品質のガイドライン</a></p></td></tr>
</table>

ターゲットを定義し、メッセージのコンテンツを作成したら、配信のコンテンツ、パーソナライゼーション、レンダリングおよび設定を準備してテストする必要があります。 これにより、メッセージをメインターゲットに送信する前に、すべてが正しいことを確認できます。 これを行うには、プレビュー、配達確認、メールの件名のテスト、メールのレンダリングなど、複数の機能を使用できます。

マーケティングキャンペーンが実行され、様々なメッセージが送信されたら、ログを使用してそれらを監視し、キャンペーンが成功したことを確認し、受信者のトラッキング情報を取得します。

最後に、Campaign Standardで使用可能な配信品質のガイドラインとツールを活用して、配信されるメッセージの数を増やし、マーケティングキャンペーンを確実に成功させます。

![](assets/do-not-localize/how-to-video.png) [&#x200B; テストメールの送信方法、メール配信の準備および送信方法をビデオで確認 &#x200B;](#video)

## 準備とテスト {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **メッセージの準備** は、メッセージのターゲット、パーソナライゼーションおよび有効性を分析します。 この手順で検出されたエラーは、先に進む前に修正する必要があります。

**プレビューとテスト** 様々な機能を使用してメッセージを表示します。テストプロファイルやターゲット設定されたプロファイルに配達確認を送信したり、メールの件名をテストしたり、メッセージのレンダリングを確認したりして、様々な web クライアント、web メール、デバイスで最適な方法で表示されることを確認します。

Campaign のスケジュール機能を活用して、メッセージを送信するタイミングを定義します。 例えば、受信者のタイムゾーンでの送信の調整、送信時間の最適化、送信日の計算などを行うことができます。

**タイポロジ** を使用すると、準備中に、疲労、制御、ターゲティングルールを通じて、メッセージが有効で、品質基準を満たしているかどうかを確認できます。 例えば、メールに常に件名が含まれていることを確認したり、メッセージ受信者から購読者を除外したりする場合です。

詳しくは、以下を参照してください。

* [送信の準備](../../sending/using/preparing-the-send.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [メールのレンダリング](../../sending/using/email-rendering.md)
* [メッセージのスケジュール設定](../../sending/using/about-scheduling-messages.md)
* [タイポロジとタイポロジルールについて](../../sending/using/about-typology-rules.md)

## 送信、監視、トラッキング {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

メッセージの準備が整ったら、送信を確認し、ログとレポートにアクセスして **配信を監視** キャンペーンの成功を測定できます。 Adobe Campaignには、配信の成功または失敗を追跡するためのメールアラートシステムや、強制隔離管理機能も用意されています。

セッション Cookie と永続 Cookie を使用してトラッキング情報 **クリックされた URL、ミラーページ、開かれたメッセージなど）を取得することで、メッセージ受信者の** 行動をトラッキングします。

最後に、「BCC で E メールを送信」を使用して、プラットフォームから送信される **メールのコピーを保持** するように、Adobe Campaignを設定できます。 特に、組織がコンプライアンスのためにすべての送信メールメッセージをアーカイブする必要がある場合は、この機能を有効にできます。

詳しくは、以下を参照してください。

* [送信の確認](../../sending/using/confirming-the-send.md)
* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [メールの BCC を使用したアーカイブ](../../sending/using/archiving.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
* [配信エラーについて](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理について](../../sending/using/understanding-quarantine-management.md)

## 配信品質のガイドライン {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

配信品質は、バウンスしたりスパムと見なされたりすることなく、受信者のインボックスに到達するキャンペーンの成否を測定する手法です。

Campaign Standardでは、正常に配信されたメッセージ数を増やすのに役立つ **配信品質ツール** がいくつか用意されています（配信スループットレポート、送信時間の最適化、メッセージのプレビュー、メールのレンダリング、強制隔離管理など）。

詳しくは、以下を参照してください。

* [配信品質について](../../sending/using/about-deliverability.md)
* [配信品質の監視](../../sending/using/monitor-deliverability.md)
* [Adobe配信品質のベストプラクティスガイド &#x200B;](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ja)
* [配信スループットの制御](../../reporting/using/delivery-throughput.md)

## その他のリソース

* [A/B テストメールのデザイン](../../channels/using/designing-an-a-b-test-email.md)
* [メッセージの概要](../../channels/using/key-steps-to-send-a-message.md)
* [配信のベストプラクティス](../../sending/using/delivery-best-practices.md)
* [コントロール母集団の追加](../../sending/using/control-group.md)

## チュートリアルビデオ {#video}

このビデオでは、テストメールを送信し、Campaign Standardでメール配信を準備して送信する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/328368?captions=jpn)

その他のCampaign Standardチュートリアルビデオについては、[&#x200B; こちら &#x200B;](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja) を参照してください。
