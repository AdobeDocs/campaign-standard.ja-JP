---
solution: Campaign Standard
product: campaign
title: トランザクションメッセージを設定する主な手順
description: トランザクションメッセージの概要を明らかにし、Adobe Campaign Standardでトランザクションメッセージを設定する主な手順を学びます。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: c276c468627208b584a0342414cdbe382e349f50
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 8%

---


# トランザクションメッセージの概要 {#getting-started-with-transactional-messaging}

## 概要 {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

トランザクションメッセージとは、ウェブサイトなどのプロバイダによってリアルタイムに送信される、個別で一意な通信です。 受信者が確認または確認したい重要な情報が含まれているので、特に期待されます。

* **いつになる？** このメッセージには重要な情報が含まれているので、ユーザーはこの情報がリアルタイムで送信されることを期待しています。したがって、トリガーされるイベントとメッセージの到着との間の遅延は非常に短くなる必要があります。

* **なぜ重要なのか？** 一般的に、トランザクションメッセージの開放率は高い。したがって、顧客の関係を定義する際に顧客の行動に強い影響を与える可能性があるので、入念に設計する必要があります。

* **例えば？** アカウント作成後のお知らせメッセージ、注文が発行されたことの確認、請求書、パスワードの変更を確認するメッセージ、または顧客がWebサイトを閲覧した後の通知などが考えられます。

Adobe Campaignを使用すると、この機能を、カスタムトランザクションメッセージに変換するイベントを送信する情報システムに統合できます。

トランザクションメッセージは、電子メール、SMS、または[プッシュ通知](../../channels/using/transactional-push-notifications.md)で送信できます。どちらを送信するかは、オプションに応じて異なります。 使用許諾契約書を確認してください。

>[!NOTE]
>
>Adobe Campaignは、他の配信よりも処理トランザクションメッセージを優先します。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

<!--All transactional messages are now sent with the Adobe Campaign Enhanced MTA for improved deliverability, throughput, and bounce handling. All impacts are the same as for standard marketing messages. For more on this, see [this section](../../administration/using/configuring-email-channel.md).-->

トランザクションメッセージングを開始する前に、対応する[ベストプラクティスと制限事項](../../channels/using/transactional-messaging-limitations.md)を必ずお読みください。

## トランザクションメッセージの動作原則 {#transactional-messaging-operating-principle}

トランザクションメッセージングプロセス全体は、次のように記述できます。

![](assets/message-center-process.png)

例えば、顧客が商品を購入できるWebサイトの会社を考えてみましょう。

Adobe Campaignを使用すると、買い物かごに商品を追加した顧客に通知電子メールを送信できます。 訪問者の1人が購入を経由せずにWebサイトを離れると(キャンペーンのイベントをトリガーする外部イベント)、買い物かごの中断の電子メールが自動的に訪問者(トランザクションメッセージの配信)に送信されます。

これを配置する主な手順は、[このセクション](#key-steps)で詳しく説明します。

## トランザクションメッセージタイプ{#transactional-message-types}

Adobe Campaignでは、2種類のトランザクションメッセージを使用できます。

**イベント自体に含まれるイベントトランザクション** メッセージターゲットデータ。次のメッセージ：
* プロファイル情報を含めないでください。したがって、購読解除リンクを含めることはできません。
* 疲労ルールとの互換性がありません(プロファイルとのエンリッチメントの場合でも)。
* 配信ターゲットは、イベント自体に含まれるデータによって定義されます。

パスワードを忘れた顧客にイベントトランザクションメッセージを送信したり、注文を確認したりする場合などが考えられます。 実際、この種の通信を受信者が登録解除するのを望まないので、この通知をマーケティングメッセージのカウンターに追加しないでください。

**キャンペーンマーケティングデータベースのプロファイルトランザクション** メッセージターゲットプロファイル。この種のメッセージでは、次のことができます。
* Adobe Campaignデータベースに含まれるデータを活用します。
* イベント設定に[プロファイル](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)を追加して、エンリッチメント情報を使用してメッセージをパーソナライズします。
* [マーケティングタイポロジルール](../../sending/using/managing-typology-rules.md)または[疲労ルール](../../sending/using/fatigue-rules.md)を適用します。
* メッセージ内に購読解除リンクを含める。
* グローバル配信レポートにトランザクションメッセージを追加する。
* カスタマージャーニーでトランザクションメッセージを活用する。

例えば、Webサイトで買い物かごを放棄した顧客に連絡する際に、このタイプのメッセージを使用して、顧客に購入を促すことができます。 これにより、プロファイルデータベースのすべての情報に直接アクセスしてメッセージをパーソナライズし、マーケティングルールを適用し、グローバルな顧客の遍歴とレポートにこのメッセージを含めて、顧客の行動をより簡単に表示できます。

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。[イベントベースのトランザクションメッセージ](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)と[プロファイルベースのトランザクションメッセージ](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)の設定の節を参照してください。

## 主な手順 {#key-steps}

Adobe Campaignでパーソナライズされたトランザクションメッセージを作成し管理する際の主な手順を、以下のスキーマにまとめます。

![](assets/message-center-overview.png)

各手順の詳細は以下のとおりです。

>[!IMPORTANT]
>
>[管理](../../administration/using/users-management.md#functional-administrators)ロールを持つユーザーのみが、トランザクションイベントとアクセストランザクションメッセージを設定できます。

### 手順1 -イベント設定を作成して公開する{#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| ユーザー | アクション | 結果 |
|--- |--- |--- |
| この手順は、[管理権限](../../administration/using/users-management.md#functional-administrators)を持つ管理者が実行する必要があります。 | 「買い物かごの放棄」という名前のイベントを設定し、このイベント設定を公開します。 | Webサイト開発者が使用するAPIがデプロイされ、トランザクションメッセージが自動的に作成されます。 |

イベントの作成と公開については、「[トランザクションイベントの設定](../../channels/using/configuring-transactional-event.md)」および「[トランザクションイベントの公開](../../channels/using/publishing-transactional-event.md)」の節を参照してください。

### 手順2 -トランザクションメッセージを編集して公開する{#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| ユーザー | アクション | 結果 |
|--- |--- |--- |
| この手順は、[管理権限](../../administration/using/users-management.md#functional-administrators)を持つマーケティングユーザーが実行できます。 | トランザクションメッセージを編集してパーソナライズし、テストして公開します。 | トランザクションメッセージを送信する準備が整います。 |

トランザクションメッセージの編集と公開について詳しくは、「[トランザクションメッセージの編集](../../channels/using/editing-transactional-message.md)」および「[トランザクションメッセージのライフサイクル](../../channels/using/publishing-transactional-message.md)」を参照してください。

### 手順3 -イベントトリガー{#integrate-event-trigger}を統合する

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| ユーザー | アクション | 結果 |
|--- |--- |--- |
| この手順は、Webサイトの開発者が実行します。 | RESTトランザクションメッセージAPIを使用して、イベントをWebサイトに統合します。 | イベントは、クライアントが買い物かごを放棄した場合にトリガーされます。 |

イベントを作成したら、このイベントのトリガーをWebサイトに組み込む必要があります。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> これを行うには、WebサイトのWeb開発者が **Adobe Campaign StandardREST APIを使用する必要があります**。

キャンペーンREST APIを使用したトランザクションメッセージ管理について詳しくは、[REST APIドキュメント](../../api/using/managing-transactional-messages.md)を参照してください。

### 手順4 — メッセージ配信{#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

これらの手順がすべて実行されると、メッセージを配信できます。

ユーザーが買い物かごに商品を注文せずにサイトを離れるとすぐに、対応するキャンペーンイベントがトリガーされます。 ユーザーは、通知電子メールを自動的に受信します。

## 関連トピック

* [メッセージを送信するための主要な手順](../../channels/using/key-steps-to-send-a-message.md)
* [通信チャネルの概要](../../channels/using/get-started-communication-channels.md)
* [トランザクションプッシュ通知](../../channels/using/transactional-push-notifications.md)
* [フォローアップメッセージ](../../channels/using/follow-up-messages.md)
