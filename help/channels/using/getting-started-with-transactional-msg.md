---
title: トランザクションメッセージの基本を学ぶ
description: トランザクションメッセージの概要と、Adobe Campaign Standardでトランザクションメッセージを設定するための主な手順を説明します。
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
source-git-commit: 0e486e87c94e273442de23d6eb65c99f065e5a71
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 30%

---

# トランザクションメッセージの基本を学ぶ {#getting-started-with-transactional-messaging}

トランザクションメッセージは web サイトなどのプロバイダーがリアルタイムに送信する、個々に向けたユニークなコミュニケーションです。受信者が確認したい重要な情報が含まれているので、早い送信が特に期待されます。

* **いつまでに必要か？**&#x200B;メッセージには重要な情報が含まれているので、ユーザーはリアルタイムで送信されることを求めています。そのため、イベントがトリガーされてからメッセージが届くまでの時間を、非常に短縮する必要があります。

* **なぜ重要なのか？**&#x200B;一般に、トランザクションメッセージは高い比率で開封されます。顧客との関係を定め、顧客の行動に強い影響を与える可能性があるので、慎重に設計する必要があります。

* **メッセージ例：** アカウント作成後のウェルカムメッセージ、注文の発送確認、請求書、パスワード変更の確認メッセージ、顧客が web サイトを閲覧した後の通知などがあります。

Adobe Campaignでは、この機能を情報システムと統合し、カスタムトランザクションメッセージに変換するイベントを送信できます。

トランザクションメッセージは、オプションに応じて、メール、SMS または [ プッシュ通知 ](../../channels/using/transactional-push-notifications.md) で送信できます。 使用許諾契約書を確認してください。

>[!NOTE]
>
>Adobe Campaign は、トランザクションメッセージの処理を他のどの配信よりも優先します。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

トランザクションメッセージの使用を開始する前に、対応する [ ベストプラクティスと制限事項 ](../../channels/using/transactional-messaging-limitations.md) を読んでください。

## トランザクションメッセージの動作原理 {#transactional-messaging-operating-principle}

トランザクションメッセージの全体的なプロセスは、次のように記述できます。

![](assets/message-center-process.png)

例えば、顧客が製品を購入できる ｗeb サイトを持つ会社の例で考えてみます。

Adobe Campaign を使用すると、買い物かごに製品を追加した顧客に通知メールを送信できます。Web サイトを訪れた人が購入せずにサイトを離れると（キャンペーンイベントをトリガーする外部イベント）、買い物かごの放棄に伴うメールを自動的に送信できます（トランザクションメッセージ配信）。

これを実現する主な手順は、[この節](#key-steps)で説明します。

## トランザクションメッセージタイプ {#transactional-message-types}

Adobe Campaignでは、2 種類のトランザクションメッセージを使用できます。

**イベントトランザクションメッセージ** イベント自体に含まれるターゲットデータ。 これらのメッセージ：
* プロファイル情報を含めないので、購読解除リンクを含めることはできません。
* 疲労ルールとの互換性がない（プロファイルを含むエンリッチメントの場合でも）。
* イベント自体に含まれるデータによって配信ターゲットを定義する。

例えば、パスワードを忘れた場合や注文を確認する必要があるお客様に、イベントトランザクションメッセージを送信できます。 実際、受信者にこのタイプのお知らせの登録解除を望んでいません。また、この通知は、疲労ルールの一部としてマーケティングメッセージのカウンターに追加しないでください。

**プロファイルトランザクションメッセージ** は、Campaign マーケティングデータベースからプロファイルをターゲットにします。 このタイプのメッセージを使用すると、次のことができます。
* Adobe Campaign データベースに含まれるデータを活用します。
* イベント設定に [ エンリッチメント ](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) を追加して、プロファイル情報を使用してメッセージをパーソナライズします。
* [ マーケティングタイポロジルール ](../../sending/using/managing-typology-rules.md) または [ 疲労ルール ](../../sending/using/fatigue-rules.md) を適用します。
* メッセージ内に購読解除リンクを含める。
* グローバル配信レポートにトランザクションメッセージを追加する。
* カスタマージャーニーでトランザクションメッセージを活用する。

例えば、web サイトで買い物かごを放棄した後に顧客に連絡する際に、このタイプのメッセージを使用して、購入を続行するように促すことができます。 これにより、プロファイルデータベースからのすべての情報に直接アクセスしてメッセージをより簡単にパーソナライズし、マーケティングルールを適用し、このメッセージをグローバルなカスタマージャーニーおよびレポートに含めて、顧客行動をより明確に把握できます。

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。[ イベントベースのトランザクションメッセージ ](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) および [ プロファイルベースのトランザクションメッセージ ](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) 設定の節を参照してください。

## 主な手順 {#key-steps}

パーソナライズされたトランザクションメッセージをAdobe Campaignで作成し、管理する主な手順については、以下のスキーマを参照してください。

![](assets/message-center-overview.png)

これらの各手順について、以下で詳しく説明します。

>[!IMPORTANT]
>
>トランザクションイベントを設定してトランザクションメッセージにアクセスできるのは、[ 管理 ](../../administration/using/users-management.md#functional-administrators) の役割を持つユーザーだけです。

### 手順 1 - イベント設定の作成と公開 {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">-->

| イベントの作成 | ユーザー | アクション | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_config.svg" width="60px"> | この手順は、[ 管理権限 ](../../administration/using/users-management.md#functional-administrators) を持つ管理者が実行する必要があります。 | 「買い物かごの放棄」という名前のイベントを設定し、このイベント設定を公開します。 | Web サイト開発者が使用する API がデプロイされ、トランザクションメッセージが自動的に作成されます。 |

イベントの作成と公開については、[ トランザクションイベントの設定 ](../../channels/using/configuring-transactional-event.md) および [ トランザクションイベントの公開 ](../../channels/using/publishing-transactional-event.md) を参照してください。

### 手順 2 - トランザクションメッセージを編集して公開する {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_notification.svg" width="40px">-->

| メッセージを編集 | ユーザー | アクション | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_notification.svg" width="40px"> | この手順は、（管理権限 [ を持つマーケティングユーザーが実行でき ](../../administration/using/users-management.md#functional-administrators) す。 | トランザクションメッセージを編集してパーソナライズし、テストしてから公開します。 | これで、トランザクションメッセージを送信する準備が整いました。 |

トランザクションメッセージの編集と公開について詳しくは、[ トランザクションメッセージの編集 ](../../channels/using/editing-transactional-message.md) および [ トランザクションメッセージのライフサイクル ](../../channels/using/publishing-transactional-message.md) を参照してください。

### 手順 3 - イベントトリガーの統合 {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="55px">-->

イベントを作成したら、このイベントのトリガーを web サイトに統合する必要があります。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> それには、web サイトの開発者が **Adobe Campaign Standard REST API** を使用する必要があります。

| トリガーの実装 | ユーザー | アクション | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_api.svg" width="55px"> | この手順は、web サイトの開発者が実行します。 | REST トランザクションメッセージ API を使用して、web サイトにイベントを統合します。 | クライアントが買い物かごを放棄すると、イベントがトリガーされます。 |

Campaign REST API を使用したトランザクションメッセージの管理について詳しくは、[REST API ドキュメント ](../../api/using/managing-transactional-messages.md) を参照してください。

### 手順 4 - メッセージ配信 {#message-delivery}

<!--<img src="assets/do-not-localize/icon_channels.svg" width="60px">-->

上記のすべての手順を実行したら、メッセージを配信できます。

| メッセージの配信 | ユーザー | アクション | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_channels.svg" width="60px"> | この手順は、Web サイトを訪問する顧客が実行します。 | ユーザーが買い物かごに製品を注文せずにサイトを離れると、対応するキャンペーンイベントがトリガーされます。 | ユーザーは通知メールを自動的に受け取ります。 |

## 関連トピック

* [メッセージを送信するための主な手順](../../channels/using/key-steps-to-send-a-message.md)
* [コミュニケーションチャネルの概要](../../channels/using/get-started-communication-channels.md)
* [トランザクションプッシュ通知](../../channels/using/transactional-push-notifications.md)
* [フォローアップメッセージ](../../channels/using/follow-up-messages.md)
