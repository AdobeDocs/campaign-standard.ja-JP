---
title: トランザクションメッセージを設定する主な手順
description: トランザクションメッセージの概要を明らかにし、Adobe Campaign Standardでトランザクションメッセージを設定する主な手順を学びます。
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 25%

---


# トランザクションメッセージの概要 {#getting-started-with-transactional-messaging}

## 概要

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_transactional.svg" width="60px"><br><p>トランザクションメッセージの概念の <b>概要</b></p></td>
<td ><br><p>トランザクションメッセージングを使用すると、個別のメッセージや個別のメッセージを <b></b> 、顧客にリアルタイムで送信できます。</p></td>
<td>ウェルカムメッセージ、発送確認書、パスワードの変更などがあります。</td>
<td>Adobe Campaignを使用すると、この機能を、カスタムトランザクションメッセージに変換するイベントを送信する情報システムに統合できます。</td>
</tr>
</table>

トランザクションメッセージは、オプションに応じて、E メール、SMS、またはプッシュ通知で送信できます。使用許諾契約書を確認してください。

Adobe Campaignは、他の配信よりも処理トランザクションメッセージを優先します。

トランザクションメッセージは、Adobe Campaign Standard API でも利用できます。詳しくは、[該当するドキュメント](../../api/using/managing-transactional-messages.md)を参照してください。

>[!NOTE]
>
>配信品質、スループット、バウンス処理を向上させるために、すべてのトランザクションメッセージが Adobe Campaign Enhanced MTA で送信されるようになりました。この変更による影響はすべて、標準のマーケティングメッセージと同じです。詳しくは、[こちらの節](../../administration/using/configuring-email-channel.md)を参照してください。

## トランザクションメッセージの定義 {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>トランザクションメッセージとは</b></p></td>
<td><p>これは、Webサイトなどのプロバイダーから送信される個別で固有の通信です。</p></td>
<td><p>受信者が確認または確認したい重要な情報が含まれているので、特に期待されます。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>いつになる？</b></p></td>
<td><p> このメッセージには重要な情報が含まれているので、ユーザーはこの情報がリアルタイムで送信されることを期待しています。</p></td>
<td><p>したがって、トリガーされるイベントとメッセージの到着との間の遅延は非常に短くなる必要があります。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>なぜ重要なのか？</b></p></td>
<td><p>一般的に、トランザクションメッセージの開放率は高い。 そのため、注意深く設計する必要があります。</p></td>
<td><p>実際、顧客の関係を定義するので、顧客の行動に強い影響を与える可能性があります。</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><p><b>例えば？</b></p></td>
<td><p>アカウント作成後のお知らせメッセージ、注文の発送確認、請求書などが表示される場合があります。</p></td>
<td><p>また、パスワードの変更を確認するメッセージや、顧客がWebサイトを閲覧した後の通知を指定することもできます。</p></td>
</tr>
</table>

## トランザクションメッセージタイプ

Adobe Campaign では、2 つのトランザクションメッセージを使用できます。

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p><a href="../../channels/using/event-transactional-messages.md">イベントトランザクション</a><br>メッセージのターゲット設定と <b>イベント</b></p></td>
<td><p><ul><li>イベントトランザクションメッセージにはプロファイル情報が含まれません。</li><li>これらは <a href="../../sending/using/fatigue-rules.md">疲労ルールとは互換性がありません</a> (プロファイルとのエンリッチメントの場合でも)。</li><li>配信ターゲットは、イベント自体に含まれるデータによって定義されます。</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><p><a href="../../channels/using/profile-transactional-messages.md">プロファイルマーケティングデータベースからのAdobe Campaignトランザクション</a><br>メッセージターゲット <b>プロファイル</b></p></td>
<td><p>プロファイルトランザクションメッセージを使用すると、次のことができます。<ul><li>Apply marketing <a href="../../sending/using/managing-typology-rules.md">typology rules</a> or <a href="../../sending/using/fatigue-rules.md">fatigue rules</a>.</li><li>メッセージ内に購読解除リンクを含める。</li><li>グローバル配信レポートにトランザクションメッセージを追加する。</li><li>カスタマージャーニーでトランザクションメッセージを活用する。</li></ul></p></td>
</tr>
</table>

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。[トランザクションメッセージの設定](../../administration/using/configuring-transactional-messaging.md)を参照してください。

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

## トランザクションメッセージの動作原則 {#transactional-messaging-operating-principle}

Webサイトを持つ会社の例を見てみましょう。このWebサイトで顧客が商品を購入できる例を見てみましょう。

Adobe Campaign を使用すると、買い物かごに商品を追加したサイトユーザーに通知メールを送信できます。訪問者が購入せずにサイトを離れると、買い物かご放棄の E メールが自動的に送信されます。

これを配置する手順は次のとおりです。

### 手順1 -イベント設定を作成して公開する {#create-event-configuration}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_config.svg" width="60px"><br><p><b>トランザクションイベントの設定</b></p></td>
<td><br><p>「買い物かごの放棄」という名前のイベントを設定し、このイベント設定を公開します。</p></td>
<td>Webサイト開発者が使用するAPIがデプロイされ、トランザクションメッセージが自動的に作成されます。</td>
<td>この手順は、 <a href="../../administration/using/users-management.md#functional-administrators">管理権限を持つユーザーが実行する必要があります</a>。</td>
</tr>
</table>

イベントの作成と公開については、[イベントトランザクションメッセージを送信するためのイベントの設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)の節を参照してください。

### 手順2 -トランザクションメッセージを編集して公開する {#create-transactional-message}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_notification.svg" width="40px"><br><p><b>トランザクションメッセージ版</b></p></td>
<td><br><p>トランザクションメッセージを編集してパーソナライズし、テストして公開します。</p></td>
<td>トランザクションメッセージを送信する準備が整います。</td>
<td>この手順は、 <a href="../../administration/using/users-management.md#basic-users">基本アクセス権を持つ任意のマーケティングユーザーが実行できます</a>。
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### 手順3 -イベントトリガーを統合する {#integrate-event-trigger}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_api.svg" width="55px"><br><p><b>イベントトリガー統合</b></p></td>
<td><br><p>RESTトランザクションメッセージAPIを使用して、イベントをWebサイトに統合します。</p></td>
<td>イベントは、クライアントが買い物かごを放棄した場合にトリガーされます。</td>
<td>この手順は、Webサイトの開発者が実行します。
</tr>
</table>

イベントをWebサイトに統合する方法について詳しくは、 [サイト統合を参照してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

### 手順4 — メッセージ配信 {#message-delivery}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>Webサイトからの外部イベント</b></p></td>
<td><br><p>これらの手順がすべて実行されると、メッセージを配信できます。</p></td>
<td>ユーザーが買い物かごに商品を注文せずにサイトを離れるとすぐに、対応するキャンペーンイベントがトリガーされます。</td>
<td>その後、ユーザーは通知電子メールを自動的に受信します。</td>
</tr>
</table>

## 主な手順 {#key-steps}

Adobe Campaignでパーソナライズされたトランザクションメッセージを作成し管理する際の主な手順を、以下の表にまとめます。

![](assets/message-center-overview.png)

**関連トピック：**

* [メッセージを送信するための主要な手順](../../channels/using/key-steps-to-send-a-message.md)
* [通信チャネルの概要](../../channels/using/get-started-communication-channels.md)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->