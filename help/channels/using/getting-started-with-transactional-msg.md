---
title: トランザクションメッセージの基本を学ぶ
description: トランザクションメッセージの概要と、Adobe Campaign Standardでトランザクションメッセージを設定するための主な手順について説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 31%

---

# トランザクションメッセージの基本を学ぶ {#getting-started-with-transactional-messaging}

## 概要 {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

トランザクションメッセージは web サイトなどのプロバイダーがリアルタイムに送信する、個々に向けたユニークなコミュニケーションです。受信者が確認したい重要な情報が含まれているので、早い送信が特に期待されます。

* **いつまでに必要か？**&#x200B;メッセージには重要な情報が含まれているので、ユーザーはリアルタイムで送信されることを求めています。そのため、イベントがトリガーされてからメッセージが届くまでの時間を、非常に短縮する必要があります。

* **なぜ重要なのか？**&#x200B;一般に、トランザクションメッセージは高い比率で開封されます。顧客との関係を定め、顧客の行動に強い影響を与える可能性があるので、慎重に設計する必要があります。

* **メッセージ例：** アカウント作成後のお知らせメッセージ、注文の発送確認メッセージ、請求書、パスワード変更確認メッセージ、顧客がWebサイトを閲覧した後の通知などが考えられます。

Adobe Campaignを使用すると、カスタムトランザクションメッセージに変換するイベントを送信する情報システムにこの機能を統合できます。

トランザクションメッセージは、オプションに応じて、Eメール、SMS、[プッシュ通知](../../channels/using/transactional-push-notifications.md)で送信できます。 ライセンス契約をご確認ください。

>[!NOTE]
>
>Adobe Campaign は、トランザクションメッセージの処理を他のどの配信よりも優先します。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

トランザクションメッセージを開始する前に、対応する[ベストプラクティスと制限事項](../../channels/using/transactional-messaging-limitations.md)を必ずお読みください。

## トランザクションメッセージの動作原理 {#transactional-messaging-operating-principle}

トランザクションメッセージの全体的なプロセスは、次のように記述できます。

![](assets/message-center-process.png)

例えば、顧客が製品を購入できる ｗeb サイトを持つ会社の例で考えてみます。

Adobe Campaign を使用すると、買い物かごに製品を追加した顧客に通知メールを送信できます。Web サイトを訪れた人が購入せずにサイトを離れると（キャンペーンイベントをトリガーする外部イベント）、買い物かごの放棄に伴うメールを自動的に送信できます（トランザクションメッセージ配信）。

これを実現する主な手順は、[この節](#key-steps)で説明します。

## トランザクションメッセージタイプ {#transactional-message-types}

Adobe Campaignでは、2種類のトランザクションメッセージを使用できます。

**イベント自体に含ま** れるイベントトランザクションメッセージターゲットデータ。次のメッセージ：
* プロファイル情報を含めないでください。そのため、購読解除リンクを含めることはできません。
* 疲労ルールとの互換性がない（プロファイルのエンリッチメントの場合でも）。
* イベント自体に含まれるデータによって配信ターゲットを定義する。

例えば、忘れたパスワードを取得したり、注文を確認したりする必要がある顧客に、イベントトランザクションメッセージを送信できます。 実際、受信者がこのタイプのコミュニケーションを購読解除することは望ましくなく、疲労ルールの一環としてこの通知をマーケティングメッセージのカウンターに追加しないでください。

**Campaignマーケティン** グデータベースのプロファイルトランザクションメッセージターゲットプロファイル。このタイプのメッセージでは、次の操作を実行できます。
* Adobe Campaignデータベースに含まれるデータを活用します。
* イベント設定に[エンリッチメント](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)を追加して、プロファイル情報を使用してメッセージをパーソナライズします。
* [マーケティングタイポロジルール](../../sending/using/managing-typology-rules.md)または[疲労ルール](../../sending/using/fatigue-rules.md)を適用します。
* メッセージ内に購読解除リンクを含める。
* グローバル配信レポートにトランザクションメッセージを追加する。
* カスタマージャーニーでトランザクションメッセージを活用する。

例えば、Webサイトで買い物かごを放棄した顧客に連絡する際に、このタイプのメッセージを使用して、顧客に購入を促すことができます。 これにより、プロファイルデータベースのすべての情報に直接アクセスし、マーケティングルールを適用して、このメッセージをグローバルカスタマージャーニーとレポートに含め、顧客の行動をより深く把握できます。

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。[イベントベースのトランザクションメッセージ](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)および[プロファイルベースのトランザクションメッセージ](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)の設定の節を参照してください。

## 主な手順 {#key-steps}

Adobe Campaignでパーソナライズされたトランザクションメッセージを作成および管理する際の主な手順を、次のスキーマにまとめます。

![](assets/message-center-overview.png)

各手順の詳細は以下のとおりです。

>[!IMPORTANT]
>
>トランザクションイベントを設定し、トランザクションメッセージにアクセスできるのは、[管理](../../administration/using/users-management.md#functional-administrators)の役割を持つユーザーのみです。

### 手順1 — イベント設定の作成と公開 {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| ユーザー | アクション | 結果 |
|--- |--- |--- |
| この手順は、[管理権限](../../administration/using/users-management.md#functional-administrators)を持つ管理者が実行する必要があります。 | 「買い物かごの放棄」という名前のイベントを設定し、このイベント設定を公開します。 | Webサイト開発者が使用するAPIがデプロイされ、トランザクションメッセージが自動的に作成されます。 |

イベントの作成と公開については、トランザクションイベントの設定[と[トランザクションイベントの公開](../../channels/using/publishing-transactional-event.md)の節で説明しています。](../../channels/using/configuring-transactional-event.md)

### 手順2 — トランザクションメッセージの編集と公開 {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| ユーザー | アクション | 結果 |
|--- |--- |--- |
| この手順は、[管理権限](../../administration/using/users-management.md#functional-administrators)を持つマーケティングユーザーが実行できます。 | トランザクションメッセージを編集およびパーソナライズし、テストして公開します。 | これで、トランザクションメッセージを送信する準備が整いました。 |

トランザクションメッセージの編集と公開について詳しくは、[トランザクションメッセージの編集](../../channels/using/editing-transactional-message.md)および[トランザクションメッセージのライフサイクル](../../channels/using/publishing-transactional-message.md)を参照してください。

### 手順3 — イベントトリガーの統合 {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| ユーザー | アクション | 結果 |
|--- |--- |--- |
| この手順は、Webサイトの開発者が実行します。 | RESTトランザクションメッセージAPIを使用して、イベントをWebサイトに統合します。 | イベントは、クライアントが買い物かごを放棄した場合にトリガーされます。 |

イベントを作成したら、このイベントのトリガーをWebサイトに統合する必要があります。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> これをおこなうには、WebサイトのWeb開発者が **Adobe Campaign Standard REST API**&#x200B;を使用する必要があります。

トランザクションメッセージの管理にCampaign REST APIを使用する方法について詳しくは、[REST APIのドキュメント](../../api/using/managing-transactional-messages.md)を参照してください。

### 手順4 — メッセージ配信 {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

これらの手順がすべて実行されたら、メッセージを配信できます。

ユーザーが買い物かごに商品を注文せずにサイトを離れると、対応するキャンペーンイベントがトリガーされます。 ユーザーは通知Eメールを自動的に受信します。

## 関連トピック

* [メッセージを送信するための主な手順](../../channels/using/key-steps-to-send-a-message.md)
* [コミュニケーションチャネルの概要](../../channels/using/get-started-communication-channels.md)
* [トランザクションプッシュ通知](../../channels/using/transactional-push-notifications.md)
* [フォローアップメッセージ](../../channels/using/follow-up-messages.md)
