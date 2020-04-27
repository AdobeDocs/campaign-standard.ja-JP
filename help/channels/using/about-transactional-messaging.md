---
title: トランザクションメッセージについて
description: 送信できる様々なタイプのトランザクションメッセージと、それらの使用方法を見つけ出します。Adobe Campaign。
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
translation-type: tm+mt
source-git-commit: f0f7441f06b51f9bd2d5a1b3c26f031d4eb1e4c1

---


# トランザクションメッセージについて{#about-transactional-messaging}

パーソナライズされたトランザクションメッセージを作成および管理できます。

トランザクションメッセージとは、Webサイトなどのプロバイダによってユーザに送信される個々の一意の通信です。

* このタイプのメッセージは、確認または確認を必要とする情報が含まれているので、受信者に特に期待されます。 アカウントの作成後のお知らせメッセージや、注文が発送されたことを確認するメッセージ、請求書、パスワードの変更を確認するメッセージなどが表示されます。
* これは、クライアントの関係を定義する重要なメッセージです。ユーザーは、これがリアルタイムで送信されることを期待しています。 トリガーされるイベントとメッセージの到着間の遅延は、非常に短くする必要があります。
* トランザクションメッセージの開放率は一般に高い。

Adobe Campaignを使用すると、この機能を情報システムに統合し、カスタムイベントに変換する情報を送信できます。

>[!NOTE]
>
>トランザクションメッセージは、オプションに応じて、電子メール、SMS、またはプッシュ通知で送信できます。 使用許諾契約書を確認してください。

次の2種類のトランザクションメッセージをAdobe Campaignで使用できます。

* [イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md) :イベント データ自体に含まれるイベントは、データターゲットの定義に使用されます。
* [プロファイルトランザクションメッセージ](../../channels/using/profile-transactional-messages.md) :プロファイルマーケティングデータベースのAdobe Campaignをターゲットにします。 顧客マーケティングAdobe Campaignに基づいてトランザクションメッセージを送信する際に、データベースの情報を使用できます。

メッセージタイプは、メッセージに変換されるイベントを設定する際に定義されます。トランザクションメッセージ トランザクショ [ンメッセージの設定を参照](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaignは、他のトランザクションメッセージよりも処理を優先します。

トランザクションメッセージングは、Adobe Campaign標準APIからも利用できます。 For more on this, refer to the [dedicated documentation](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>すべてのトランザクションメッセージは、配信品質、スループット、バウンス処理を向上させるために、Adobe Campaign拡張MTAと共に送信されるようになりました。 すべての影響は、標準のマーケティングメッセージと同じです。 For more on this, see this [section](../../administration/using/configuring-email-channel.md).

## トランザクションメッセージングの動作原則 {#transactional-messaging-operating-principle}

Webサイトを持つ会社の例を見てみましょう。このWebサイトでは、ユーザーが製品を購入できます。

Adobe Campaignを使用すると、買い物かごに製品を追加したサイトユーザーに通知電子メールを送信できます。訪問者の1人が購入を経由せずにサイトを離れると、買い物かごの放棄の電子メールが自動的に送信されます。

これを配置する手順は、次のとおりです。

1. 「買い物かごの放棄」という名前のイベントを設定し、このイベント設定を公開すると、自動的にトランザクションメッセージが作成されます。 イベントの作成と公開は、「イベントを送信す [るためのイベントの設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 」で行います。
1. このトランザクションメッセージは、パーソナライズ、テスト、公開が必要です。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. さらに、クライアントが買い物かごを放棄したときにイベントがトリガーされるようにするには、このイベントを会社のWebサイトからAdobe Campaign標準のREST APIを使用して送信する必要があります。 サイトの統 [合を参照してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

これらの手順がすべて完了すると、ユーザーは買い物かごに商品を注文せずにサイトを離れるとすぐに、通知電子メールを自動的に受信します。

## トランザクションメッセージング発行プロセス {#transactional-messaging-pub-process}

次の表に、トランザクションメッセージングの発行プロセスを示します。

![](assets/message-center_pub-process.png)

イベントの設定手順について詳しくは、トランザクションメッセ [ージの設定を参照してくださ](../../administration/using/configuring-transactional-messaging.md)い。

## トランザクションメッセージングの制限 {#transactional-messaging-limitations}

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、管理権限が必要です。

### デザインと出版 {#design-and-publication}

トランザクションメッセージをデザインし、公開する際に、実行する必要のある手順の一部を元に戻すことはできません。 次の制限事項に注意する必要があります。

* 各チャネル設定で使用できるイベントは1つだけです。 詳しくは、 [イベントの作成](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* 一旦イベントが作成されると、変更はできません。チャネル したがって、メッセージが正常に送信されない場合は、ワークフローを使用して別のチャネルから送信できるメカニズムを設計する必要があります。 See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* ターゲティングディメンションの作成後に、イベント(ま **[!UICONTROL Real-time event]** たは **[!UICONTROL Profile]** )を変更することはできません。 詳しくは、 [イベントの作成](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* パブリケーションをロールバックすることはできませんが、次の方法で公開を取り消すことができます。イベント:この操作により、イベントと関連するトランザクションメッセージにアクセスできなくなります。 詳しくは、 [非公開とイベント](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* トランザクションメッセージに関連付けることができる唯一のイベントは、メッセージの公開時に自動的に作成されるイベントです。 詳しくは、プ [レビューと公開イベントを参照してくださ](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)い。

### パーソナライゼーション {#personalization}

メッセージの内容をパーソナライズする方法は、メッセージの種類によって異なります。トランザクションメッセージ 具体的な内容は以下のとおりです。

**イベントベースのトランザクションメッセージ**:

* パーソナライゼーション情報は、データ自体に含まれるイベントから取得されます。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* リンクコンテンツブ **ロックは** 、購読解除トランザクションメッセージでは使用できません。
* イベントベースのトランザクションメッセージングは、送信イベント内のデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義する必要があります。 ただし、データベースの情報を使用して、トランザクションメッセージの内容をAdobe Campaignできます。 詳しくは、 [トランザクションメッセージコンテンツの強化](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* イベントトランザクションメッセージにはプロファイル情報が含まれないので、エンリッチメントの場合でも、疲労ルールとの互換性はありません。 疲労ルー [ルを参照してくださ](../../sending/using/fatigue-rules.md)い。

**プロファイルベースのトランザクションメッセージ**:

* パーソナライゼーション情報は、イベントに含まれるデータまたは調整済みのプロファイルレコードから取得できます。 See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* リンクコンテンツブ **ロックは** 、購読解除トランザクションメッセージで使用できます。 詳しくは、コ [ンテンツブロックの追加を参照してくださ](../../designing/using/personalization.md#adding-a-content-block)い。
* 疲労ルールは、疲労ルールとプロファイルトランザクションメッセージに対応します。 疲労ルー [ルを参照してくださ](../../sending/using/fatigue-rules.md)い。

製品リストは、トランザクション電子メールメッセージでのみ利用できます。 詳しくは、 [トランザクションメッセージでの製品リストの使用を参照](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

### 権限とブランディング {#permissions-and-branding}

ブランド管理に関しては、トランザク [ション](../../administration/using/branding.md) ・メッセージングは標準のメッセージングよりも柔軟性が低くなります。 アドビでは、組織単位にトランザクションメッセージで使用されているすべてのブランドをリン **[!UICONTROL All]** クするこ [とを推奨しま](../../administration/using/organizational-units.md)す。 詳しくは、以下の詳細な説明を参照してください。

トランザクションメッセージの編集時に、ブランドにリンクして、ブランド名やブランドロゴなどの一部のパラメーターを自動的に適用できます。 デフォル **[!UICONTROL Default brand]** トでは、このオプションはトランザクションメッセージプロパティで選択されます。

![](assets/message-center_branding.png)

トランザクションメッセージで使用されるすべてのオブジェクト（ブランドを含む）は、組織単位(つまり、 **[!UICONTROL Message Center]** 組織単位または組織単位)に表示されている必要 **[!UICONTROL Message Center]** があ **[!UICONTROL All]** ります。

ただし、メッセージのプロパティで選択したブランドが、またはとは異なる組織単位にリンクされている場合、 **[!UICONTROL Message Center]****[!UICONTROL All]**&#x200B;これはエラーの原因となり、トランザクションメッセージを送信できなくなります。

したがって、トランザクションメッセージングのコンテキストでマルチブランドを使用する場合は、すべてのブランドを組織単位または組織単位 **[!UICONTROL Message Center]** にリンクする必要が **[!UICONTROL All]** あります。

### 書き出しと読み込みトランザクションメッセージ {#exporting-and-importing-transactional-messages}

* トランザクションメッセージを書き出すには、パッケージの書き出しを作成する際に、対応するイベント設定 [を含める必要があります](../../automating/using/managing-packages.md#creating-a-package)。
* トランザクションメッセージをパッケ [ージから読み込むと](../../automating/using/managing-packages.md#importing-a-package)、トランザクションメッセージリストには表示されません。 関連する [イベント](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) を使用可能にするには、トランザクションメッセージ設定を公開する必要があります。

