---
title: テストと送信の基本を学ぶ
description: メッセージの準備、テスト、スケジュール、送信、および監視を行います。
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 17%

---

# テストと送信の基本を学ぶ {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">準備とテスト</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages"> の送信、監視、トラッキング</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">配信品質のガイドライン</a></p></td></tr>
</table>

ターゲットを定義し、メッセージのコンテンツを作成したら、配信のコンテンツ、パーソナライゼーション、レンダリングおよび設定を準備およびテストする必要があります。 これにより、メッセージをメインターゲットに送信する前に、すべてが正しいことを確認できます。 これをおこなうには、プレビュー、配達確認、Eメールの件名行テスト、Eメールのレンダリングなど、複数の機能を使用できます。

マーケティングキャンペーンが実行され、異なるメッセージが送信されたら、ログを使用してキャンペーンを監視し、キャンペーンの成功を確認し、受信者のトラッキング情報を取得します。

最後に、Campaign Standardで使用できる配信品質のガイドラインとツールを活用して、配信されるメッセージの数を改善し、マーケティングキャンペーンを成功に導きます。

![](assets/do-not-localize/how-to-video.png) [テスト用Eメールの送信、Eメール配信の準備および送信方法をビデオで確認](#video)

## 準備とテスト {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **メッセージの準備**&#x200B;は、ターゲット、パーソナライゼーションおよびメッセージの有効性を分析します。 この手順で検出されたエラーは、続行する前に修正する必要があります。

**次の様々な機能を使** 用して、メッセージをプレビューおよびテストします。配達確認を送信してプロファイルやターゲットプロファイルをテストし、eメールの件名をテストし、メッセージのレンダリングを確認して、様々なWebクライアント、Webメールおよびデバイスで最適な方法で表示されることを確認します。

キャンペーンのスケジュール機能を活用して、メッセージを送信するタイミングを定義します。 例えば、受信者のタイムゾーンに合わせて送信を調整したり、送信時間を最適化したり、送信日を計算したりできます。

**タイポロジ**&#x200B;を使用して、準備中に、メッセージが有効で、疲労、制御、ターゲット設定ルールを通じて品質の基準を満たしているかどうかを確認します。 例えば、Eメールに常に件名行が含まれていることを確認したり、メッセージ受信者から登録解除したりできます。

詳しくは、以下を参照してください。

* [送信の準備](../../sending/using/preparing-the-send.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)
* [E メールのレンダリング](../../sending/using/email-rendering.md)
* [メッセージのスケジュール設定](../../sending/using/about-scheduling-messages.md)
* [タイポロジとタイポロジルールについて](../../sending/using/about-typology-rules.md)

##  の送信、監視、トラッキング {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

メッセージの準備が整ったら、送信を確認し、**配信を監視し、キャンペーンの成功を測定するためのログとレポートにアクセスできます。** Adobe Campaignには、配信の成功または失敗、および強制隔離管理機能を追跡するEメールアラートシステムも用意されています。

**セッション** と永続的なCookieを使用してトラッキング情報（クリックされたURL、ミラーページ、開封されたメッセージなど）を取得し、メッセージ受信者の行動を追跡します。

最後に、「BCCでEメールを送信」を使用して、プラットフォームから送信されるEメール&#x200B;**のコピーを**&#x200B;保持するようにAdobe Campaignを設定できます。 特に、組織が準拠のためにすべてのアウトバウンドEメールメッセージをアーカイブする必要がある場合、この機能を有効にできます。

詳しくは、以下を参照してください。

* [送信の確認](../../sending/using/confirming-the-send.md)
* [メッセージのトラッキング](../../sending/using/tracking-messages.md)
* [E メールの BCC を使用したアーカイブ](../../sending/using/archiving.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
* [配信エラーについて](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理について](../../sending/using/understanding-quarantine-management.md)

## 配信品質のガイドライン {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

配信品質を使用すると、バウンスしたりスパムとしてマークされたりせずに、受信者の受信ボックスに到達したかに基づいて、キャンペーンの成功を測定できます。

Campaign Standardには、正常に配信されたメッセージの数を改善するのに役立つ、配信品質のツール&#x200B;**がいくつか用意されています。配信スループットレポート、送信時間の最適化、メッセージのプレビュー、Eメールのレンダリング、強制隔離の管理など**

詳しくは、以下を参照してください。

* [配信品質について](../../sending/using/about-deliverability.md)
* [配信品質の監視](../../sending/using/monitor-deliverability.md)
* [Adobe配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ja)
* [配信スループットの制御](../../reporting/using/delivery-throughput.md)

## その他のリソース

* [A/Bテスト用Eメールのデザイン](../../channels/using/designing-an-a-b-test-email.md)
* [Eメールの概要](https://helpx.adobe.com/jp/campaign/kb/acs-get-started-with-emails.html)
* [配信のベストプラクティス](../../sending/using/delivery-best-practices.md)
* [コントロール母集団の追加](../../sending/using/control-group.md)

## チュートリアルビデオ {#video}

このビデオでは、テスト用Eメールを送信し、Eメール配信を準備してCampaign Standardで送信する方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

追加のCampaign Standardハウツービデオは[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)からご覧いただけます。
