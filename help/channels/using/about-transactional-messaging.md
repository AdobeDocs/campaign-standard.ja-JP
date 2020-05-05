---
title: トランザクションメッセージについて
description: 送信できる様々なタイプのトランザクションメッセージと、Adobe Campaignでの使用方法を確認します。
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
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# トランザクションメッセージについて{#about-transactional-messaging}

Adobe Campaign内でパーソナライズされたトランザクションメッセージを作成し、管理できます。

トランザクションメッセージとは、ウェブサイトなどのプロバイダによってユーザに送信される個別かつ一意の通信です。

* この種のメッセージは、受信者が確認または確認を希望する情報が含まれているので、特に期待されます。 アカウント作成後のお知らせメッセージ、注文の発送確認、請求書、パスワードの変更を確認するメッセージなどが表示されます。
* これは、クライアントの関係を定義する重要なメッセージです。 ユーザーは、それがリアルタイムで送信されることを期待しています。 トリガーされるイベントとメッセージの到着間の遅延は、非常に短くする必要があります。
* 一般に、トランザクションメッセージの開放率は高い。

Adobe Campaignを使用すると、この機能を、カスタムトランザクションメッセージに変換するイベントを送信する情報システムに統合できます。

>[!NOTE]
>
>トランザクションメッセージは、オプションに応じて、電子メール、SMS、またはプッシュ通知で送信できます。 使用許諾契約書を確認してください。

Adobe Campaignでは、次の2種類のトランザクションメッセージを使用できます。

* [イベントをターゲットにしたイベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md) 。 イベント自体に含まれるデータは、配信ターゲットの定義に使用されます。
* [Adobe Campaignマーケティングデータベースのプロファイルをターゲットにするプロファイルトランザクションメッセージ](../../channels/using/profile-transactional-messages.md) 。 Adobe Campaignデータベースの情報を使用して、顧客マーケティングプロファイルに基づいたトランザクションメッセージを送信できます。

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。 トランザク [ションメッセージの設定を参照してください](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaignは、他の配信よりもトランザクションメッセージの処理を優先します。

トランザクションメッセージングは、Adobe Campaign標準APIからも利用できます。 For more on this, refer to the [dedicated documentation](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>配信品質、スループット、バウンス処理を向上させるため、すべてのトランザクションメッセージにAdobe Campaign拡張MTAが送信されるようになりました。 すべての影響は、標準のマーケティングメッセージと同じです。 For more on this, see this [section](../../administration/using/configuring-email-channel.md).

## トランザクションメッセージングの動作原則 {#transactional-messaging-operating-principle}

Webサイトを持つ会社の例を見てみましょう。このWebサイトでユーザーが商品を購入できる例を見てみましょう。

Adobe Campaignを使用すると、買い物かごに商品を追加したサイトユーザーに通知電子メールを送信できます。 訪問者の1人が購入を経由せずにサイトを離れると、買い物かごの放棄の電子メールが自動的に送信されます。

この設定を行う手順は次のとおりです。

1. 「買い物かごの放棄」という名前を付け、このイベント設定を公開するイベントを設定します。これにより、トランザクションメッセージが自動的に作成されます。 イベントの作成と公開については、「イベントを送信するためのイベントの [設定](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 」の節を参照してください。
1. トランザクションメッセージは、パーソナライズ、テスト、公開する必要があります。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. さらに、クライアントが買い物かごを放棄したときにイベントがトリガーされるようにするには、このイベントを会社のWebサイトからAdobe Campaign標準のREST APIを使用して送信する必要があります。 「 [サイトの統合](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)」を参照してください。

これらの手順がすべて実行されると、ユーザーは買い物かごに商品を注文せずにサイトを離れるとすぐに、通知電子メールを自動的に受け取ります。

## トランザクションメッセージング発行プロセス {#transactional-messaging-pub-process}

次の図は、トランザクションメッセージングの公開プロセスを示しています。

![](assets/message-center_pub-process.png)

イベントの設定手順について詳しくは、 [トランザクションメッセージの設定を参照してください](../../administration/using/configuring-transactional-messaging.md)。

## トランザクションメッセージングの制限 {#transactional-messaging-limitations}

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、管理者権限が必要です。

### デザインと公開 {#design-and-publication}

トランザクションメッセージをデザインして公開する際、実行する必要がある一部の手順を元に戻すことはできません。 次の制限事項に注意する必要があります。

* 各イベント設定で使用できるチャネルは1つだけです。 詳しくは、イベントの [作成を参照してください](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* イベントを作成した後は、チャネルを変更できません。 したがって、メッセージが正常に送信されない場合は、ワークフローを使用して別のチャネルからメッセージを送信できるメカニズムを設計する必要があります。 See [Workflow data and processes](../../automating/using/get-started-workflows.md).
* イベントの作成後にターゲティングディメンション( **[!UICONTROL Real-time event]** または **[!UICONTROL Profile]** )を変更することはできません。 詳しくは、イベントの [作成を参照してください](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* パブリケーションをロールバックすることはできませんが、イベントの公開を取り消すことはできます。 この操作により、イベントと関連するトランザクションメッセージにアクセスできなくなります。 詳しくは、イベントの [非公開を参照してください](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* イベントに関連付けることができる唯一のトランザクションメッセージは、そのイベントの公開時に自動的に作成されるメッセージです。 詳しくは、イベントの [プレビューと公開を参照してください](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

### パーソナライゼーション {#personalization}

メッセージの内容をパーソナライズする方法は、トランザクションメッセージの種類によって異なります。 具体的な内容は次のとおりです。

**イベントベースのトランザクションメッセージ**:

* パーソナライゼーション情報は、イベント自体に含まれるデータから取得されます。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* イベントトランザクションメッセージでは **購読解除リンク** ・コンテンツ・ブロックを使用できません。
* イベントベースのトランザクションメッセージングでは、受信者とメッセージコンテンツのパーソナライゼーションを定義するために、送信イベント内のデータのみを使用することが想定されています。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージの内容を拡張することができます。 詳しくは、トランザクションメッセージコンテンツの [富化を参照してください](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)。
* イベントトランザクションメッセージにはプロファイル情報が含まれないので、プロファイルとのエンリッチメントの場合でも、疲労ルールとの互換性がありません。 「 [疲労ルール](../../sending/using/fatigue-rules.md)」を参照してください。

**プロファイルベースのトランザクションメッセージ**:

* パーソナライゼーション情報は、イベントに含まれるデータ、または調整済みのプロファイルレコードから取得できます。 See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* プロファイルトランザクションメッセージでは、 **購読解除リンク** ・コンテンツ・ブロックを使用できます。 詳しくは、コンテンツブロックの [追加を参照してください](../../designing/using/personalization.md#adding-a-content-block)。
* 疲労ルールは、プロファイルトランザクションメッセージと互換性があります。 「 [疲労ルール](../../sending/using/fatigue-rules.md)」を参照してください。

製品リストは、トランザクション用の電子メールメッセージでのみ利用できます。 詳しくは、トランザクションメッセージでの製品リストの [使用を参照してください](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

### 権限とブランディング {#permissions-and-branding}

ブラン [](../../administration/using/branding.md) ド管理に関しては、トランザクションメッセージングは標準のメッセージングよりも柔軟性が低くなります。 トランザクションメッセージで使用されているすべてのブランドを **[!UICONTROL All]** 組織単位にリンクすることをお勧めします [](../../administration/using/organizational-units.md)。 詳しくは、以下の詳細を参照してください。

トランザクションメッセージを編集する際に、ブランドにリンクして、ブランド名やブランドロゴなどのパラメーターを自動的に適用できます。 トランザクションメッセージプロパティ **[!UICONTROL Default brand]** では、デフォルトでが選択されています。

![](assets/message-center_branding.png)

トランザクションメッセージで使用されるすべてのオブジェクト（ブランドを含む）は、 **[!UICONTROL Message Center]** 組織単位（つまり、組織単位または組織単位）で表示されている必要があり **[!UICONTROL Message Center]****[!UICONTROL All]** ます。

ただし、メッセージプロパティで選択したブランドが、またはとは異なる組織単位にリンクされている場合 **[!UICONTROL Message Center]** 、 **[!UICONTROL All]**&#x200B;これはエラーの原因となり、トランザクションメッセージを送信できなくなります。

したがって、トランザクションメッセージングのコンテキストでマルチブランドを使用する場合は、すべてのブランドを **[!UICONTROL Message Center]** 組織単位または **[!UICONTROL All]** 組織単位にリンクする必要があります。

### トランザクションメッセージの書き出しと読み込み {#exporting-and-importing-transactional-messages}

* トランザクションメッセージを書き出すには、パッケージの書き出しを [作成する際に、対応するイベント設定を含める必要があります](../../automating/using/managing-packages.md#creating-a-package)。
* トランザクションメッセージをパッケージから [読み込むと](../../automating/using/managing-packages.md#importing-a-package)、トランザクションメッセージリストには表示されません。 関連するトランザクションメッセージを使用可能にするには [、イベント設定を](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) 公開する必要があります。

