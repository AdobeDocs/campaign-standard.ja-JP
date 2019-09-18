---
title: トランザクションメッセージングについて
seo-title: トランザクションメッセージングについて
description: トランザクションメッセージングについて
seo-description: 送信できるさまざまな種類のトランザクションメッセージと、Adobe Campaignでの使用方法を確認します。
page-status-flag: 未活性化の
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: チャンネル
content-type: 参照
topic-tags: トランザクション·メッセージング
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# トランザクションメッセージングについて{#about-transactional-messaging}

Adobe Campaignで、個人用のトランザクションメッセージを作成および管理できます。

トランザクションメッセージとは、Webサイトなどのプロバイダがユーザに送信する個別の一意の通信です。

* この種類のメッセージは、受信者が確認または確認する情報を含むので、特に期待されます。 たとえば、アカウントを作成した後のウェルカムメッセージ、または注文が出荷されたことを確認するメッセージ、請求書、またはパスワードの変更を確認するメッセージなどです。
* クライアントの関係を定義する重要なメッセージです。ユーザは、リアルタイムで送信されることを想定しています。 トリガーされるイベントとメッセージの受信間の遅延は、非常に短くする必要があります。
* トランザクション·メッセージのオープン·レートは一般に高い。

Adobe Campaignでは、この機能を、カスタムトランザクションメッセージに変換されるイベントを送信する情報システムと統合できます。

>[!NOTE]
>
>トランザクションメッセージは、オプションに応じて、電子メール、SMS、またはプッシュ通知で送信できます。 使用許諾契約を確認してください。

Adobe Campaignでは、次の2種類のトランザクションメッセージを使用できます。

* [イベントを対象とした](../../channels/using/event-transactional-messages.md) 、イベントトランザクションメッセージ。 イベント自体に含まれるデータは、配信ターゲットの定義に使用されます。
* [Adobe Campaignのマーケティング](../../channels/using/profile-transactional-messages.md) ·データベースのプロファイルを対象としたトランザクション·メッセージのプロファイル Adobe Campaignデータベースの情報を使用して、顧客のマーケティングプロファイルに基づいてトランザクションメッセージを送信できます。

メッセージ·タイプは、トランザクション·メッセージに変換されるイベントを構成する際に定義されます。 「トランザクシ [ョン·メッセージ構成」を参照](../../administration/using/configuring-transactional-messaging.md)。

>[!NOTE]
>
>Adobe Campaignは、トランザクションメッセージの処理を他の配信よりも優先します。

トランザクションメッセージングは、Adobe Campaign Standard APIからも利用できます。 詳細については、専用のマニュアルを参照し [てください](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging)。

## トランザクションメッセージングの動作原則 {#transactional-messaging-operating-principle}

Webサイトを持つ企業の例を見てみましょう。このWebサイトでは、ユーザーが製品を購入できます。

Adobe Campaignを使用すると、カートに製品を追加したサイトユーザに通知電子メールを送信できます。購入を経ずに退場すると、カート廃棄メールが自動的に送信されます。

これを配置する手順は次のとおりです。

1. 「Cart Abbonding」という名前のイベントを構成し、このイベント構成を公開します。このイベント構成は、トランザクションメッセージを自動的に作成します。 イベントの作成と公開は、「イベントトランザクショ [ンメッセージを送信するイベントの構成](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) 」のセクションで行います。
1. トランザクション·メッセージは、パーソナライズされ、テストされ、公開される必要があります。 「イベント·ト [ランザクション·メッセージ](../../channels/using/event-transactional-messages.md)」を参照。
1. さらに、クライアントがカートを破棄したときにイベントがトリガーされるように、このイベントはAdobe Campaign Standard REST APIを使用して会社のWebサイトから送信する必要があります。 「サイト [の統合」を参照](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)。

これらの手順がすべて実行されると、ユーザーがカート内の製品を注文せずにサイトを離れると、自動的に通知Eメールが送信されます。

## トランザクションメッセージングの制限 {#transactional-messaging-limitations}

### デザインと出版 {#design-and-publication}

トランザクション·メッセージを設計および公開する際に、実行する必要のある手順の一部を元に戻すことはできません。 次の制限に注意する必要があります。

* 各イベント構成に使用できるチャネルは1つだけです。 「イベ [ントの作成」を参照](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* イベントが作成された後は、チャンネルを変更できません。 したがって、メッセージが正常に送信されない場合は、ワークフローを使用して別のチャネルから送信できるメカニズムを設計する必要があります。 「ワークフ [ロー·データとプロセス」を参照](../../automating/using/workflow-data-and-processes.md)。
* イベントの作成後にターゲットディメンシ **[!UICONTROL Real-time event]** ョン(ま **[!UICONTROL Profile]** たは)を変更することはできません。 「イベ [ントの作成」を参照](../../administration/using/configuring-transactional-messaging.md#creating-an-event)。
* パブリケーションをロールバックすることはできませんが、イベントの公開を取り消すことができます。この操作を行うと、イベントと関連するトランザクションメッセージにアクセスできなくなります。 「イベント [の公開の取り消し」を参照してくださ](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event)い。
* イベントに関連付けられるトランザクションメッセージは、そのイベントの発行時に自動的に作成されるメッセージだけです。 「イベント [のプレビューと公開」を参照してください](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)。

### 個人用設定 {#personalization}

メッセージ·コンテンツをパーソナライズする方法は、トランザクション·メッセージのタイプによって異なります。 次に、特定の内容を示します。

**イベント·ベースのトランザクション·メッセージ**:

* 個人情報は、イベント自体に含まれるデータから取得されます。 「イベント·ト [ランザクション·メッセージ](../../channels/using/event-transactional-messages.md)」を参照。
* イベントトランザクショ **ンメッセージでは** 、[サブスクリプション解除]リンクコンテンツブロックは使用できません。
* イベント·ベースのトランザクション·メッセージングでは、送信イベント内のデータのみを使用して、受信者とメッセージ·コンテンツのパーソナライズを定義します。 ただし、Adobe Campaignデータベースの情報を使用して、トランザクションメッセージの内容を強化できます。 「トランザク [ション·メッセージの内容の強化」を参照してくださ](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)い。
* イベント·トランザクション·メッセージにはプロファイル情報が含まれないため、プロファイルとの拡張の場合でも、疲労ルールとの互換性はありません。 疲労ル [ールを参照](../../administration/using/fatigue-rules.md)。

**プロファイル·ベースのトランザクション·メッセージ**:

* 個人用設定情報は、イベントに含まれるデータまたは調整済みプロファイルレコードから取得できます。 「トランザクシ [ョン·メッセージのプロファイル](../../channels/using/profile-transactional-messages.md)」を参照。
* プロファイル·トランザクショ **ン·メッセージで** 、「≪サブスクリプション解除|Unsubscription|Eas≫」リンク·コンテンツ·ブロックを使用できます。 「コンテンツ [ブロックの追加」を参照してくださ](../../designing/using/personalization.md#adding-a-content-block)い。
* 疲労ルールは、プロファイルトランザクションメッセージと互換性があります。 疲労ル [ールを参照](../../administration/using/fatigue-rules.md)。

製品一覧は、トランザクションの電子メールメッセージでのみ使用できます。 トランザク [ション·メッセージでの製品リストの使用を参照](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)。

### 権限とブランド化 {#permissions-and-branding}

ブランド管理に関しては [](../../administration/using/branding.md) 、トランザクションメッセージングは標準メッセージングよりも柔軟性が低くなります。 トランザクションメッセージで使用されるすべてのブランドを組織単位にリンクするこ **[!UICONTROL All]** とをお勧めします。 詳細については、以下の詳細な説明を参照してください。

トランザクションメッセージを編集する際に、そのメッセージをブランドにリンクして、ブランド名やブランドロゴなどのパラメータを自動的に適用できます。 トランザク **[!UICONTROL Default brand]** ションメッセージのプロパティでは、が既定で選択されています。

![](assets/message-center_branding.png)

トランザクションメッセージにアクセスするには、組織単位( **[!UICONTROL Message Center agents]** organizational unit)にリンクされた(mcExec)セキュリティグループに属している必要が **[!UICONTROL Message Center]** あ [ります](../../administration/using/organizational-units.md)。 したがって、トランザクションメッセージで使用されるすべてのオブジェクト（ブランド化を含む）は、組織単位(OU)から参照できる必要があります。つまり、これらのオブジェクトは、または組織単位(OU)に **[!UICONTROL Message Center]** 含まれる必要が **[!UICONTROL Message Center]****[!UICONTROL All]** あります。

ただし、メッセージのプロパティで選択したブランドが、またはとは異なる組織単位にリンクされている場合は、エラーが発生し、トランザクションメッセージを送信できなくなります。 **[!UICONTROL Message Center]****[!UICONTROL All]**

したがって、トランザクションメッセージングのコンテキストでマルチブランドを使用する場合は、すべてのブランドを組織単位または組織単位 **[!UICONTROL Message Center]** にリンクする必要が **[!UICONTROL All]** あります。

### トランザクション·メッセージのエクスポートとインポート {#exporting-and-importing-transactional-messages}

* トランザクションメッセージをエクスポートするには、パッケージのエクスポートを作成する際に、対応するイベ [ント構成を含める必要がありま](../../automating/using/managing-packages.md#creating-a-package)す。
* トランザクション·メッセージは、パッ [ケージを介してインポートされ](../../automating/using/managing-packages.md#importing-a-package)、トランザクション·メッセージ·リストには表示されません。 関連するトランザクシ [ョンメッセージを使用可能にするには](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) 、イベント構成を公開する必要があります。

