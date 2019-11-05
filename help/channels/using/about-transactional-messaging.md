---
title: トランザクションメッセージについて
description: 送信できる様々なタイプのトランザクションメッセージと、Adobe Campaignでの使用方法を確認します。
page-status-flag: 非活性化の
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: トランザクションメッセージング
discoiquuid: 71a4d5d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# トランザクションメッセージについて{#about-transactional-messaging}

Adobe Campaignで、パーソナライズされたトランザクションメッセージを作成し、管理できます。

トランザクションメッセージとは、Webサイトなどのプロバイダーによってユーザーに送信される個々の一意の通信です。

* このタイプのメッセージは、受信者が確認または確認する情報が含まれているので、特に期待されます。 例えば、アカウントを作成した後のお知らせメッセージや、注文が発送されたことの確認、請求書、パスワードの変更を確認するメッセージなどが表示されます。
* これは、クライアントの関係を定義する重要なメッセージです。ユーザーは、これがリアルタイムで送信されることを期待しています。 トリガーされるイベントと到着するメッセージの間の遅延は、非常に短くする必要があります。
* 一般に、トランザクションメッセージのオープン率は高くなります。

Adobe Campaignを使用すると、この機能を、カスタムトランザクションメッセージに変換するイベントを送信する情報システムに統合できます。

>[!NOTE]
>
>トランザクションメッセージは、オプションに応じて、電子メール、SMS、またはプッシュ通知で送信できます。 使用許諾契約書を確認してください。

Adobe Campaignでは、次の2種類のトランザクションメッセージを使用できます。

* [イベントをターゲットとする](../../channels/using/event-transactional-messages.md) 、イベントトランザクションメッセージ。 イベント自体に含まれるデータは、配信ターゲットの定義に使用されます。
* [Adobe Campaignマーケティングデータベースから](../../channels/using/profile-transactional-messages.md) 、プロファイルをターゲットとするプロファイルトランザクションメッセージ。 Adobe Campaignデータベースの情報を使用して、顧客マーケティングプロファイルに基づくトランザクションメッセージを送信できます。

メッセージタイプは、トランザクションメッセージに変換されるイベントを設定する際に定義されます。 トランザクショ [ンメッセージングの設定を参照](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaignは、他の配信よりもトランザクションメッセージの処理を優先します。

トランザクションメッセージングは、Adobe Campaign Standard APIからも利用できます。 For more on this, refer to the [dedicated documentation](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## トランザクションメッセージングの動作原則 {#transactional-messaging-operating-principle}

Webサイトを持つ会社の例を見てみましょう。このWebサイトでは、ユーザーが製品を購入できます。

Adobe Campaignでは、製品を買い物かごに追加したサイトユーザーに通知電子メールを送信できます。訪問者の1人が購入を経験せずにサイトを離れると、買い物かごの中断の電子メールが自動的に送信されます。

これを配置する手順は次のとおりです。

1. 「買い物かごの放棄」という名前を付け、このイベント設定を公開するイベントを設定し、トランザクションメッセージを自動的に作成します。 イベントの作成と発行は、「イベントトランザクションメッセージを送 [信するためのイベントの設定」の節に示され](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 、
1. トランザクションメッセージは、パーソナライズし、テストして、公開する必要があります。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. さらに、クライアントが買い物かごを放棄したときにイベントがトリガーされるには、このイベントをAdobe Campaign Standard REST APIを使用して会社のWebサイトから送信する必要があります。 サイトの統 [合を参照してください](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

これらの手順がすべて実行されると、ユーザーは買い物かごに商品を注文せずにサイトを離れると、自動的に通知電子メールを受け取ります。

## トランザクションメッセージング発行プロセス {#transactional-messaging-pub-process}

以下の表に、トランザクションメッセージングの発行プロセスを示します。

![](assets/message-center_pub-process.png)

イベントの設定手順について詳しくは、トランザクションメッセージ [の設定を参照してくださ](../../administration/using/configuring-transactional-messaging.md)い。

## トランザクションメッセージングの制限 {#transactional-messaging-limitations}

>[!NOTE]
>
>トランザクションメッセージにアクセスするには、管理権限が必要です。

### デザインと出版 {#design-and-publication}

トランザクションメッセージをデザインして公開する際に、実行する必要がある手順の一部を元に戻すことはできません。 次の制限事項に注意する必要があります。

* 各イベント設定には1つのチャネルのみを使用できます。 イベント [の作成を参照してください](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* イベントが作成されると、チャネルを変更できなくなります。 したがって、メッセージが正常に送信されない場合は、ワークフローを使用して別のチャネルからメッセージを送信できるメカニズムを設計する必要があります。 See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* イベントの作成後にターゲットディメンシ **[!UICONTROL Real-time event]** ョン(ま **[!UICONTROL Profile]** たは)を変更することはできません。 イベント [の作成を参照してください](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* パブリケーションをロールバックすることはできませんが、イベントの公開を取り消すことはできます。この操作により、イベントと関連するトランザクションメッセージにアクセスできなくなります。 イベント [の非公開を参照してください](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)。
* イベントに関連付けることができる唯一のトランザクションメッセージは、イベントの発行時に自動的に作成されるメッセージです。 詳しくは、イ [ベントのプレビューと公開を参照してくださ](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)い。

### パーソナライゼーション {#personalization}

メッセージコンテンツをパーソナライズする方法は、トランザクションメッセージのタイプによって異なります。 具体的な内容は次のとおりです。

**イベント・ベースのトランザクション・メッセージ**:

* パーソナライゼーション情報は、イベント自体に含まれるデータから取得されます。 See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* イベントトランザクションメ **ッセージでは** 、購読解除リンクコンテンツブロックを使用できません。
* イベントベースのトランザクションメッセージングは、送信されたイベント内のデータのみを使用して、受信者とメッセージコンテンツのパーソナライゼーションを定義する必要があります。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージのコンテンツを強化できます。 詳しくは、ト [ランザクションメッセージコンテンツの強化を参照してくださ](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)い。
* イベントトランザクションメッセージにはプロファイル情報が含まれないので、プロファイルを含むエンリッチメントの場合でも、疲労ルールとの互換性はありません。 疲労ル [ールを参照](../../administration/using/fatigue-rules.md)。

**プロファイルベースのトランザクションメッセージ**:

* パーソナライゼーション情報は、イベントに含まれるデータまたは調整済みプロファイルレコードから取得できます。 See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* プロファイルトランザクシ **ョンメッセージで** 、購読解除リンクコンテンツブロックを使用できます。 詳しくは、コ [ンテンツブロックの追加を参照してくださ](../../designing/using/personalization.md#adding-a-content-block)い。
* 疲労ルールは、プロファイルトランザクションメッセージと互換性があります。 疲労ル [ールを参照](../../administration/using/fatigue-rules.md)。

製品リストは、トランザクション電子メールメッセージでのみ使用できます。 詳しくは、 [トランザクションメッセージでの製品リストの使用を参照してくださ](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)い。

### 権限とブランド {#permissions-and-branding}

ブランド管理に関しては、トランザ [クション](../../administration/using/branding.md) ・メッセージングは標準のメッセージングよりも柔軟性が低くなります。 アドビでは、トランザクションメッセージで使用されるすべてのブランドを組織単位にリンクす **[!UICONTROL All]** るこ [とを推奨しま](../../administration/using/organizational-units.md)す。 詳しくは、以下の詳細な説明を参照してください。

トランザクションメッセージを編集する際に、そのメッセージをブランドにリンクして、ブランド名やブランドロゴなどのパラメーターを自動的に適用できます。 トランザクシ **[!UICONTROL Default brand]** ョンメッセージのプロパティでは、デフォルトでこのオプションが選択されます。

![](assets/message-center_branding.png)

トランザクションメッセージで使用されるすべてのオブジェクト（ブランドを含む）は、組織単位で表示する必要があります。つまり、こ **[!UICONTROL Message Center]** れらのオブジェクトは、組織単位または組織単位で表 **[!UICONTROL Message Center]** 示する必 **[!UICONTROL All]** 要があります。

ただし、メッセージプロパティで選択したブランドが、またはと異なる組織単位にリンクされている場合は、エラーが発生し、トランザクションメッセージを送信できなくなります **[!UICONTROL Message Center]****[!UICONTROL All]**。

したがって、トランザクションメッセージングのコンテキストでマルチブランドを使用する場合は、すべてのブランドを組織単位または組織単位 **[!UICONTROL Message Center]** にリンクする必要が **[!UICONTROL All]** あります。

### トランザクションメッセージの書き出しと読み込み {#exporting-and-importing-transactional-messages}

* トランザクションメッセージを書き出すには、パッケージの書き出しを作成する際に、対応するイベン [ト設定を含める必要があります](../../automating/using/managing-packages.md#creating-a-package)。
* トランザクションメッセージは、パッ [ケージを介して読み込まれると](../../automating/using/managing-packages.md#importing-a-package)、トランザクションメッセージリストに表示されません。 関連するトランザクシ [ョンメッセージを使用可能にするには](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) 、イベント設定を発行する必要があります。

