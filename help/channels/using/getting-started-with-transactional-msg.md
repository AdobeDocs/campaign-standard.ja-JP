---
title: トランザクションメッセージの基本を学ぶ
description: トランザクションメッセージの概要と、Adobe Campaign Standardでトランザクションメッセージを設定する主な手順について説明します。
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

* **メッセージ例：** アカウント作成後のお知らせメッセージ、注文の発送確認メッセージ、請求書、パスワード変更確認メッセージ、顧客が Web サイトを閲覧した後の通知などが考えられます。

Adobe Campaignを使用すると、カスタムトランザクションメッセージに変換するイベントを送信する情報システムにこの機能を統合できます。

トランザクションメッセージは、E メール、SMS または [プッシュ通知](../../channels/using/transactional-push-notifications.md)（オプションに応じて） 使用許諾契約書を確認してください。

>[!NOTE]
>
>Adobe Campaign は、トランザクションメッセージの処理を他のどの配信よりも優先します。

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

トランザクションメッセージを開始する前に、対応する [ベストプラクティスと制限事項](../../channels/using/transactional-messaging-limitations.md).

## トランザクションメッセージの動作原理 {#transactional-messaging-operating-principle}

トランザクションメッセージの全体的なプロセスは、次のように記述できます。

![](assets/message-center-process.png)

例えば、顧客が製品を購入できる ｗeb サイトを持つ会社の例で考えてみます。

Adobe Campaign を使用すると、買い物かごに製品を追加した顧客に通知メールを送信できます。Web サイトを訪れた人が購入せずにサイトを離れると（キャンペーンイベントをトリガーする外部イベント）、買い物かごの放棄に伴うメールを自動的に送信できます（トランザクションメッセージ配信）。

これを実現する主な手順は、[この節](#key-steps)で説明します。

## トランザクションメッセージタイプ {#transactional-message-types}

Adobe Campaignでは、2 種類のトランザクションメッセージを使用できます。

**イベントトランザクションメッセージ** イベント自体に含まれるターゲットデータ。 次のメッセージ：
* プロファイル情報を含めないでください。そのため、購読解除リンクを含めることはできません。
* 疲労ルールとの互換性はありません（プロファイルとのエンリッチメントの場合も含む）。
* イベント自体に含まれるデータによって配信ターゲットを定義してもらう。

忘れたパスワードなどを取得する必要がある顧客や、注文を確認するために、イベントトランザクションメッセージを送信する場合があります。 実際、受信者がこのタイプのコミュニケーションを購読解除したくない場合に、疲労ルールの一環としてこの通知をマーケティングメッセージのカウンターに追加しないようにする必要があります。

**プロファイルトランザクションメッセージ** Campaign マーケティングデータベースからプロファイルをターゲット設定します。 このタイプのメッセージでは、次の操作を実行できます。
* Adobe Campaignデータベースに含まれるデータを活用します。
* プロファイル情報を使用してメッセージをパーソナライズするには、 [強化](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) をイベント設定に追加します。
* 適用 [マーケティングタイポロジルール](../../sending/using/managing-typology-rules.md) または [疲労ルール](../../sending/using/fatigue-rules.md).
* メッセージ内に購読解除リンクを含める。
* グローバル配信レポートにトランザクションメッセージを追加する。
* カスタマージャーニーでトランザクションメッセージを活用する。

例えば、Web サイトで買い物かごを放棄した後に顧客に連絡する場合に、このタイプのメッセージを使用して、顧客に購入を促すことができます。 これにより、プロファイルデータベースのすべての情報に直接アクセスし、マーケティングルールを適用して、このメッセージをグローバルカスタマージャーニーとレポートに含め、顧客の行動をより簡単に把握できます。

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。詳しくは、 [イベントベースのトランザクションメッセージ](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) および [プロファイルベースのトランザクションメッセージ](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) 設定セクション。

## 主な手順 {#key-steps}

Adobe Campaignでパーソナライズされたトランザクションメッセージを作成および管理する際の主な手順を、次のスキーマにまとめます。

![](assets/message-center-overview.png)

これらの各手順の詳細は、以下で説明します。

>[!IMPORTANT]
>
>次の条件を満たすユーザーのみ： [管理](../../administration/using/users-management.md#functional-administrators) の役割では、トランザクションイベントを設定し、トランザクションメッセージにアクセスできます。

### 手順 1 — イベント設定の作成と公開 {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">-->

| イベントの作成 | ユーザー | アクション | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_config.svg" width="60px"> | この手順は、管理者が保留中の状態で実行する必要があります [管理権限](../../administration/using/users-management.md#functional-administrators). | 「買い物かごの放棄」という名前のイベントを設定し、このイベント設定を公開します。 | Web サイト開発者が使用する API がデプロイされ、トランザクションメッセージが自動的に作成されます。 |

イベントの作成と公開について詳しくは、 [トランザクションイベントの設定](../../channels/using/configuring-transactional-event.md) および [トランザクションイベントの公開](../../channels/using/publishing-transactional-event.md) セクション。

### 手順 2 — トランザクションメッセージを編集して公開する {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_notification.svg" width="40px">-->

| メッセージを編集 | ユーザー | アクション | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_notification.svg" width="40px"> | この手順は、 [管理権限](../../administration/using/users-management.md#functional-administrators). | トランザクションメッセージを編集およびパーソナライズし、テストして公開します。 | これで、トランザクションメッセージを送信する準備が整います。 |

トランザクションメッセージの編集と公開について詳しくは、 [トランザクションメッセージの編集](../../channels/using/editing-transactional-message.md) および [トランザクションメッセージのライフサイクル](../../channels/using/publishing-transactional-message.md).

### 手順 3 — イベントトリガーの統合 {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="55px">-->

イベントを作成したら、このイベントの発生原因を Web サイトに統合する必要があります。<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> これをおこなうには、Web サイトの Web デベロッパーが **Adobe Campaign Standard REST API**.

| トリガー | ユーザー | アクション | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_api.svg" width="55px"> | この手順は、Web サイトの開発者が実行します。 | REST トランザクションメッセージ API を使用して、イベントを Web サイトに統合します。 | イベントは、クライアントが買い物かごを放棄したときにトリガーされます。 |

トランザクションメッセージの管理に Campaign REST API を使用する方法について詳しくは、 [REST API ドキュメント](../../api/using/managing-transactional-messages.md).

### 手順 4 — メッセージ配信 {#message-delivery}

<!--<img src="assets/do-not-localize/icon_channels.svg" width="60px">-->

上記の手順をすべて実行したら、メッセージを配信できます。

| メッセージを配信 | ユーザー | アクション | 結果 |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_channels.svg" width="60px"> | この手順は、Web サイトを訪問した顧客が実行します。 | ユーザーが買い物かごで製品を注文せずにサイトを離れると、対応する Campaign イベントがトリガーされます。 | ユーザーは通知 E メールを自動的に受信します。 |

## 関連トピック

* [メッセージを送信するための主な手順](../../channels/using/key-steps-to-send-a-message.md)
* [コミュニケーションチャネルの概要](../../channels/using/get-started-communication-channels.md)
* [トランザクションプッシュ通知](../../channels/using/transactional-push-notifications.md)
* [フォローアップメッセージ](../../channels/using/follow-up-messages.md)
