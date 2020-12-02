---
solution: Campaign Standard
product: campaign
title: トランザクションメッセージを設定する主な手順
description: トランザクションメッセージの概要を明らかにし、Adobe Campaign Standardでトランザクションメッセージを設定する主な手順を学びます。
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 28%

---


# トランザクションメッセージの概要 {#getting-started-with-transactional-messaging}

## 概要

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

**トランザクションメッセージング**&#x200B;の概念の紹介

トランザクションメッセージングを使用すると、個別のメッセージを顧客にリアルタイムで送信できます。

ウェルカムメッセージ、発送確認、パスワードの更新などがあります。
Adobe Campaignを使用すると、この機能を、カスタムトランザクションメッセージに変換するイベントを送信する情報システムに統合できます。

トランザクションメッセージは、オプションに応じて、E メール、SMS、またはプッシュ通知で送信できます。使用許諾契約書を確認してください。

Adobe Campaignは、他の配信よりも処理トランザクションメッセージを優先します。

トランザクションメッセージは、Adobe Campaign Standard API でも利用できます。詳しくは、[該当するドキュメント](../../api/using/managing-transactional-messages.md)を参照してください。

>[!NOTE]
>
>配信品質、スループット、バウンス処理を向上させるために、すべてのトランザクションメッセージが Adobe Campaign Enhanced MTA で送信されるようになりました。この変更による影響はすべて、標準のマーケティングメッセージと同じです。詳しくは、[こちらの節](../../administration/using/configuring-email-channel.md)を参照してください。

## トランザクションメッセージング定義{#transactional-messaging-definition}

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

<img src="assets/do-not-localize/icon_event.svg" width="60px">

イベントをターゲットとする[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)。

* イベントトランザクションメッセージにはプロファイル情報が含まれません。

* これらは[疲労ルール](../../sending/using/fatigue-rules.md)と互換性がありません(プロファイルとのエンリッチメントの場合でも)。

* 配信ターゲットは、イベント自体に含まれるデータによって定義されます。


<img src="assets/do-not-localize/icon_profile.svg" width="60px">

 Campaign マーケティングデータベースのプロファイルをターゲットとする[プロファイルトランザクションメッセージ](../../channels/using/profile-transactional-messages.md)。

プロファイルトランザクションメッセージを使用すると、次のことができます。

* [マーケティングタイポロジルール](../../sending/using/managing-typology-rules.md)または[疲労ルール](../../sending/using/fatigue-rules.md)を適用します。

* メッセージ内に購読解除リンクを含める。

* グローバル配信レポートにトランザクションメッセージを追加する。

* カスタマージャーニーでトランザクションメッセージを活用する。

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。[トランザクションメッセージの設定](../../administration/using/configuring-transactional-messaging.md)を参照してください。

>[!IMPORTANT]
>
>すべてのトランザクションメッセージにアクセスするには、**[!UICONTROL Administrators (all units)]**&#x200B;セキュリティグループに属している必要があります。

## トランザクションメッセージの動作原則 {#transactional-messaging-operating-principle}

Webサイトを持つ会社の例を見てみましょう。このWebサイトで顧客が商品を購入できる例を見てみましょう。

Adobe Campaign を使用すると、買い物かごに商品を追加したサイトユーザーに通知メールを送信できます。訪問者が購入せずにサイトを離れると、買い物かご放棄の E メールが自動的に送信されます。

これを配置する手順は次のとおりです。

### 手順1 -イベント設定を作成して公開する{#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

**トランザクションイベント設定**:

* 「買い物かごの放棄」という名前のイベントを設定し、このイベント設定を公開します。

* Webサイト開発者が使用するAPIがデプロイされ、トランザクションメッセージが自動的に作成されます。

* この手順は、[管理権限](../../administration/using/users-management.md#functional-administrators)を持つユーザーが実行する必要があります。

イベントの作成と公開については、[イベントトランザクションメッセージを送信するためのイベントの設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)の節を参照してください。

### 手順2 -トランザクションメッセージを編集して公開する{#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

**トランザクションメッセージ版**

* トランザクションメッセージを編集してパーソナライズし、テストして公開します。

* トランザクションメッセージを送信する準備が整います。

* この手順は、[標準的なユーザーアクセス権](../../administration/using/users-management.md#basic-users)を持つマーケティングユーザーが実行できます。

トランザクションメッセージの編集と公開について詳しくは、[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。

### 手順3 -イベントトリガー{#integrate-event-trigger}を統合する

<img src="assets/do-not-localize/icon_api.svg" width="55px">

**イベントトリガー統合**

* RESTトランザクションメッセージAPIを使用して、イベントをWebサイトに統合します。&lt;

* イベントは、クライアントが買い物かごを放棄した場合にトリガーされます。

* この手順は、Webサイトの開発者が実行します。

イベントのWebサイトへの統合について詳しくは、[サイトの統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)を参照してください。

### 手順4 — メッセージ配信{#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

**Webサイトからの外部イベント**

* これらの手順がすべて実行されると、メッセージを配信できます。

* ユーザーが買い物かごに商品を注文せずにサイトを離れるとすぐに、対応するキャンペーンイベントがトリガーされます。

* その後、ユーザーは通知電子メールを自動的に受信します。

## 主な手順 {#key-steps}

Adobe Campaignでパーソナライズされたトランザクションメッセージを作成し管理する際の主な手順を、以下の表にまとめます。

![](assets/message-center-overview.png)

## 関連トピック

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