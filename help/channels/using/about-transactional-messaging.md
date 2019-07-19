---
title: トランザクションメッセージングについて
seo-title: トランザクションメッセージングについて
description: トランザクションメッセージングについて
seo-description: 送信できるトランザクションメッセージのタイプと、Adobe Campaignでの使用方法を確認します。
page-status-flag: 常にアクティブ化されていない
uuid: 8470e9e2- ee17-456f-9e4c-460e69c78a2c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: トランザクションメッセージング
discoiquuid: 71a4d5d5- fe2a-4ce5- b22b- a4736f7add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d93c2600299a8d2ec3672b3d82222f423878034c

---


# About transactional messaging{#about-transactional-messaging}

Adobe Campaignでは、パーソナライズされたトランザクションメッセージを作成して管理できます。

トランザクションメッセージとは、Webサイトなどのプロバイダーによってユーザーに送信される個人および一意のコミュニケーションです。

* 受信者が確認または確認する情報が含まれているので、このタイプのメッセージは特に期待されます。例えば、アカウントを作成した後のお知らせメッセージや、請求書、請求書、パスワードの変更を確認するメッセージなどの確認メッセージを作成できます。
* クライアントの関係を定義する重要なメッセージです。ユーザーは、リアルタイムで送信されることを期待しています。トリガーされるイベントと到着したメッセージの間の遅延は非常に短くする必要があります。
* トランザクションメッセージには一般的に高オープン率があります。

Adobe Campaignでは、この機能を情報システムに統合して、カスタムトランザクションメッセージに変換するイベントを送信することができます。

>[!NOTE]
>
>トランザクションメッセージは、オプションに応じて電子メール、SMSまたはプッシュ通知で送信できます。使用許諾契約書を確認してください。

Adobe Campaignでは、次の2種類のトランザクションメッセージを使用できます。

* [イベントをターゲット化するイベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md) 。イベント自体に含まれるデータは、配信ターゲットを定義するために使用されます。
* [Adobe Campaignマーケティングデータベースからのプロファイルトランザクションメッセージ](../../channels/using/profile-transactional-messages.md) のターゲットプロファイル。Adobe Campaignデータベースの情報を使用して、顧客のマーケティングプロファイルに基づいてトランザクションメッセージを送信できます。

メッセージタイプは、トランザクションメッセージに変換されるイベントの設定時に定義されます。[トランザクションメッセージング設定](../../administration/using/configuring-transactional-messaging.md)を参照してください。

>[!NOTE]
>
>Adobe Campaignでは、トランザクションメッセージの処理を他の任意の配信で優先できます。

トランザクションメッセージングは、Adobe Campaign Standard APIからも利用できます。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Transactional messaging operating principle {#transactional-messaging-operating-principle}

WebサイトとこのWebサイトのユーザが製品を購入できる会社の例を見てみましょう。

Adobe Campaignでは、買い物かごに製品を追加したサイトユーザーに通知電子メールを送信できます。そのうちの1人が、購入を待たずにサイトを離れると、買い物かごの放棄電子メールが自動的に送信されます。

これを配置する手順は次のとおりです。

1. 「買い物かごの放棄」という名前のイベントを設定し、このイベント設定を発行して、トランザクションメッセージを自動的に作成します。Creating and publishing an event are presented in the [Configuring an event to send an event transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.
1. トランザクションメッセージは、パーソナライズ、テスト、発行する必要があります。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。
1. さらに、クライアントが買い物かごを放棄したときにイベントをトリガーするために、このイベントはAdobe Campaign Standard REST APIを使用して会社のWebサイトから送信する必要があります。See [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

これらの手順がすべて実行されると、ユーザが買い物かごの製品を注文せずにサイトを離れると、自動的に通知電子メールが届きます。

## Transactional messaging limitations {#transactional-messaging-limitations}

### Design and publication {#design-and-publication}

トランザクションメッセージをデザインして発行するときに、実行する必要のある手順の一部を元に戻すことはできません。以下の制限事項に注意してください。

* 各イベント設定に使用できるチャネルは1つだけです。See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* イベントが作成されると、チャネルを変更することはできません。したがって、メッセージが正常に送信されない場合は、ワークフローを使用して別のチャネルから送信できるメカニズムを設計する必要があります。[ワークフローデータとプロセス](../../automating/using/workflow-data-and-processes.md)を参照してください。
* You cannot change the targeting dimension ( **[!UICONTROL Real-time event]** or **[!UICONTROL Profile]** ) after the event is created. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* パブリケーションのロールバックはできませんが、イベントの公開を取り消すことができます。この操作により、イベントと関連するトランザクションメッセージはアクセスできません。See [Unpublishing an event](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* イベントに関連付けることのできるトランザクションメッセージは、イベントの発行時に自動的に作成されるメッセージです。See [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalization {#personalization}

メッセージコンテンツをパーソナライズする方法は、トランザクションメッセージの種類によって異なります。特異性は以下のとおりです。

**イベントベースのトランザクションメッセージ**:

* パーソナライゼーション情報は、イベント自体に含まれるデータから取得されます。[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。
* You cannot use **Unsubscription link** content blocks in an event transactional message.
* イベントベースのトランザクションメッセージでは、送信イベント内のデータのみを使用して受信者およびメッセージコンテンツのパーソナライゼーションを定義します。ただし、Adobe Campaignデータベースの情報を使用してトランザクションメッセージのコンテンツを充実させることができます。See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* イベントトランザクションメッセージにはプロファイル情報が含まれていないため、プロファイルを使用した補強の場合でも、疲労ルールとは互換性がありません。[疲労ルール](../../administration/using/fatigue-rules.md)を参照してください。

**プロファイルベースのトランザクションメッセージ**:

* パーソナライゼーション情報は、イベントに含まれるデータまたは調整されたプロファイルレコードから取得できます。See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* You can use **Unsubscription link** content blocks in a profile transactional message. See [Adding a content block](../../designing/using/adding-a-content-block.md).
* 疲労ルールは、プロファイルトランザクションメッセージと互換性があります。[疲労ルール](../../administration/using/fatigue-rules.md)を参照してください。

製品リストは、トランザクション電子メールメッセージでのみ使用できます。See [Using product listings in a transactional message](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissions and branding {#permissions-and-branding}

[ブランディング](../../administration/using/branding.md) 管理にアクセスすると、トランザクションメッセージは標準的なメッセージングよりも柔軟性を低下させます。Adobe recommends linking all brands used in transactional messages to the **[!UICONTROL All]** organizational unit. これについて詳しくは、以下の詳細を参照してください。

トランザクションメッセージを編集する際、ブランド名やブランドロゴなどの一部のパラメーターを自動的に適用するようにブランドにリンクできます。**[!UICONTROL Default brand]** トランザクションメッセージのプロパティでは、デフォルトで選択されています。

![](assets/message-center_branding.png)

To access the transactional messages, you must be part of the **[!UICONTROL Message Center agents]** (mcExec) security group, which is linked to the **[!UICONTROL Message Center]** [organizational unit](../../administration/using/organizational-units.md). Therefore, all objects (including branding) used in a transactional message must be visible from the **[!UICONTROL Message Center]** organizational unit, meaning that these objects must be in the **[!UICONTROL Message Center]** or **[!UICONTROL All]** organizational units.

However, if the brand selected in the message properties is linked to an organizational unit which is different from **[!UICONTROL Message Center]** or **[!UICONTROL All]**, this will cause an error and you will not be able to send the transactional message.

Therefore, if you want to use multi-branding in the context of transactional messaging, you should link all brands either to the **[!UICONTROL Message Center]** organizational unit or to the **[!UICONTROL All]** organizational unit.

### Exporting and importing transactional messages {#exporting-and-importing-transactional-messages}

* To export a transactional message, you need to include the corresponding event configuration when [creating the package export](../../automating/using/managing-packages.md#creating-a-package).
* Once the transactional message is [imported through a package](../../automating/using/managing-packages.md#importing-a-package), it is not displayed in the transactional message list. You need to [publish](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) the event configuration in order to make the associated transactional message available.

