---
title: トランザクションメッセージについて
description: 送信できる様々なタイプのトランザクションメッセージと、Adobe Campaign での使用方法について説明します。
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---


# トランザクションメッセージについて{#about-transactional-messaging}

Adobe Campaign では、パーソナライズされたトランザクションメッセージを作成し、管理できます。

トランザクションメッセージとは、Web サイトなどのプロバイダーによってユーザーに送信される個別かつ一意のコミュニケーション形態です。

* このメッセージは、受信者が確認を希望する情報が含まれているので、顧客の期待に即した内容を提供するのに役立ちます。一例には、アカウント作成後のお知らせメッセージ、注文の発送確認メッセージ、請求書、パスワード変更確認メッセージなどがあります。
* これは、クライアントとの関係を決定付ける重要なメッセージで、ユーザーはリアルタイムのメッセージ受信を求めています。イベントをトリガーしてからとメッセージが到着するまでの遅延を最小限に留める必要があります。
* 一般に、トランザクションメッセージの開封率は高いです。

Adobe Campaign を使用すると、カスタムトランザクションメッセージに変換するためのイベントを送信する情報システムにこの機能を統合できます。

>[!NOTE]
>
>トランザクションメッセージは、オプションに応じて、E メール、SMS、またはプッシュ通知で送信できます。使用許諾契約書を確認してください。

Adobe Campaign では、2 つのトランザクションメッセージを使用できます。

* イベントをターゲットとする[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)。イベント自体に含まれるデータを使用して、配信ターゲットを定義します。
* Adobe Campaign マーケティングデータベースのプロファイルをターゲットとする[プロファイルトランザクションメッセージ](../../channels/using/profile-transactional-messages.md)。Adobe Campaign データベースの情報を使用して、顧客マーケティングプロファイルに基づいたトランザクションメッセージを送信できます。

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。[トランザクションメッセージの設定](../../administration/using/configuring-transactional-messaging.md)を参照してください。

>[!NOTE]
>
>Adobe Campaign は、トランザクションメッセージの処理を他のどの配信よりも優先します。

トランザクションメッセージは、Adobe Campaign Standard API でも利用できます。詳しくは、[該当するドキュメント](../../api/using/managing-transactional-messages.md)を参照してください。

>[!NOTE]
>
>配信品質、スループット、バウンス処理を向上させるために、すべてのトランザクションメッセージが Adobe Campaign Enhanced MTA で送信されるようになりました。この変更による影響はすべて、標準のマーケティングメッセージと同じです。詳しくは、[こちらの節](../../administration/using/configuring-email-channel.md)を参照してください。

## トランザクションメッセージの動作原則 {#transactional-messaging-operating-principle}

商品販売用の Web サイトを運営する会社の例を見てみましょう。

Adobe Campaign を使用すると、買い物かごに商品を追加したサイトユーザーに通知メールを送信できます。訪問者が購入せずにサイトを離れると、買い物かご放棄の E メールが自動的に送信されます。

これをおこなうには、次の手順に従います。

1. 「買い物かごの放棄」という名前のイベントを設定します。このイベントを公開すると、トランザクションメッセージが自動的に作成されます。イベントの作成と公開については、[イベントトランザクションメッセージを送信するためのイベントの設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)の節を参照してください。
1. トランザクションメッセージは、パーソナライゼーションとテストをおこない、公開する必要があります。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。
1. さらに、クライアントが買い物かごを放棄したときにイベントがトリガーされるようにするには、このイベントを会社の Web サイトから Adobe Campaign Standard REST API を使用して送信する必要があります。[サイトの統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)を参照してください。

これらの手順がすべて実行されると、買い物かごの商品を注文せずにサイトを離れたユーザーに対して、自動的に通知メールが即座に送信されます。

## トランザクションメッセージの公開プロセス {#transactional-messaging-pub-process}

次の図は、トランザクションメッセージの公開プロセスを示しています。

![](assets/message-center_pub-process.png)

イベントの設定手順について詳しくは、[トランザクションメッセージの設定](../../administration/using/configuring-transactional-messaging.md)を参照してください。

## トランザクションメッセージの制限 {#transactional-messaging-limitations}

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、管理者権限が必要です。

### デザインと公開 {#design-and-publication}

トランザクションメッセージをデザインして公開する際、実行する必要がある手順の一部は元に戻すことができません。次の制限事項に留意してください。

* 各イベント設定で使用できるチャネルは 1 つだけです。詳しくは、[イベントの作成](../../administration/using/configuring-transactional-messaging.md#creating-an-event)を参照してください。
* イベントを作成した後は、チャネルを変更できません。したがって、メッセージが正常に送信されない場合は、ワークフローを使用して別のチャネルからメッセージを送信できるメカニズムを設計する必要があります。[ワークフローのデータとプロセス](../../automating/using/get-started-workflows.md).
* イベントの作成後にターゲティングディメンション（**[!UICONTROL Real-time event]** または **[!UICONTROL Profile]**）を変更することはできません。詳しくは、[イベントの作成](../../administration/using/configuring-transactional-messaging.md#creating-an-event)を参照してください。
* 公開をロールバックすることはできませんが、イベントを非公開にすることは可能です。この操作により、イベントとそれに関連するトランザクションメッセージにアクセスできなくなります。詳しくは、[イベントの非公開](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)を参照してください。
* イベントに関連付けることができる唯一のトランザクションメッセージは、そのイベントの公開時に自動的に作成されるメッセージです。詳しくは、[イベントのプレビューと公開](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)を参照してください。

### パーソナライゼーション {#personalization}

メッセージの内容をパーソナライズする方法は、トランザクションメッセージの種類によって異なります。具体的な内容は次のとおりです。

**イベントベースのトランザクションメッセージ**

* パーソナライゼーションに関する情報は、イベント自体に含まれるデータから取得されます。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。
* イベントトランザクションメッセージでは、**購読解除リンク**&#x200B;コンテンツブロックを使用できません。
* イベントベースのトランザクションメッセージでは、受信者とメッセージコンテンツのパーソナライゼーションを定義するために、送信イベント内のデータのみを使用することが想定されています。ただし、Adobe Campaign データベースの情報を使用して、トランザクションメッセージの内容をエンリッチメントすることができます。詳しくは、[トランザクションメッセージコンテンツのエンリッチメント](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)を参照してください。
* イベントトランザクションメッセージにはプロファイル情報が含まれないので、プロファイルのエンリッチメントの場合でも、疲労ルールとの互換性はありません。[疲労ルール](../../sending/using/fatigue-rules.md)を参照してください。

**プロファイルベースのトランザクションメッセージ**

* パーソナライゼーションに関する情報は、イベントに含まれるデータ、または紐付け済みのプロファイルレコードから取得できます。[プロファイルトランザクションメッセージ](../../channels/using/profile-transactional-messages.md)を参照してください。
* プロファイルトランザクションメッセージでは、**Unsubscription link** コンテンツブロックを使用できます。[コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)を参照してください。
* 疲労ルールは、プロファイルトランザクションメッセージと互換性があります。[疲労ルール](../../sending/using/fatigue-rules.md)を参照してください。

製品リストは、トランザクション用の E メールメッセージでのみ利用できます。詳しくは、[トランザクションメッセージでの製品リストの使用](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)を参照してください。

### 権限とブランディング {#permissions-and-branding}

[ブランディング](../../administration/using/branding.md)管理の場合、トランザクションメッセージは標準のメッセージよりも柔軟性が低くなります。トランザクションメッセージで使用されるすべてのブランドを&#x200B;**[!UICONTROL All]**[&#x200B;組織単位](../../administration/using/organizational-units.md)にリンクすることをお勧めします。詳しくは、以下の詳細を参照してください。

トランザクションメッセージを編集する際に、ブランドにリンクして、ブランド名やブランドロゴなどのパラメーターを自動的に適用できます。トランザクションメッセージプロパティでは、デフォルトで **[!UICONTROL Default brand]** が選択されています。

![](assets/message-center_branding.png)

トランザクションメッセージで使用されるすべてのオブジェクト（ブランドを含む）は **[!UICONTROL Message Center]** 組織単位で表示されている必要があります。つまり、これらのオブジェクトは **[!UICONTROL Message Center]** 組織単位または **[!UICONTROL All]** 組織単位に属する必要があります。

ただし、メッセージプロパティで選択したブランドが、**[!UICONTROL Message Center]** または **[!UICONTROL All]** とは異なる組織単位にリンクされている場合、これはエラーの原因となり、トランザクションメッセージを送信できなくなります。

したがって、トランザクションメッセージのコンテキストでマルチブランディングを使用する場合は、すべてのブランドを **[!UICONTROL Message Center]** 組織単位または **[!UICONTROL All]** 組織単位にリンクする必要があります。

### トランザクションメッセージのエクスポートとインポート {#exporting-and-importing-transactional-messages}

* トランザクションメッセージをエクスポートするには、[パッケージのエクスポートを作成](../../automating/using/managing-packages.md#creating-a-package)する際に、対応するイベント設定を含める必要があります。
* トランザクションメッセージが[パッケージからインポートされる](../../automating/using/managing-packages.md#importing-a-package)と、トランザクションメッセージリストには表示されなくなります。関連するトランザクションメッセージを使用可能にするには、イベント設定を[公開](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)する必要があります。

