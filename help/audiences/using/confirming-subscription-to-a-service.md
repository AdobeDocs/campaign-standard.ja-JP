---
title: サービスの購読の確認
seo-title: サービスの購読の確認
description: サービスの購読の確認
seo-description: Adobe Campaignでサービスを購読するプロファイルの確認メッセージを設定するには、次の手順に従います。
page-status-flag: 非活性化の
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参照
topic-tags: 購読の管理
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8b85bbad7458286252a2900ce730288f6e52442e

---


# Confirming subscription to a service{#confirming-subscription-to-a-service}

## 購読確認の送信について {#sending-subscription-confirmation}

この節では、特定のサービスを購読するプロファイルに自動カスタム確認電子メールを送信する方法について説明します。

購読（または購読解除）の確認メッセージをサービスに送信する場合は、デフォルトのメッセージまたはカスタムメッセージを使用できます。 確認メッセージを選択する手順は、「サービスの作成」セクシ [ョンに記載されます](../../audiences/using/creating-a-service.md) 。

デフォルトのメッセージを使用する場合は、次の制限を満たしてコンテンツを編集できます。
* You can only personalize the message content with limited fields from the event context.
* This message will be the same for all services that use the default mode.

To send a specific confirmation email for a given service, you can create a custom message, in which you will also be able to leverage personalization fields from other resources. To do this, you must create and configure a transactional message. This message can be referenced :
* From the service itself. For more on this, see Configuring confirmation message from a service.[](../../audiences/using/confirming-subscription-to-a-service.md#configuring-confirmation-message-from-service)
* From a subscription landing page. For more on this, see Configuring confirmation message from a landing page.[](../../audiences/using/confirming-subscription-to-a-service.md#configuring-confirmation-message-from-landing-page)

## サービスからの確認メッセージの設定 {#configuring-confirmation-message-from-service}

For example, you want to automatically send a confirmation message to the visitors of your website when they subscribe to your brand newsletter.

You need to configure a transactional email and reference that message from the desired service (subscription to your brand newsletter in this case). In order to enrich the transactional message with service information, you can define a reconciliation when creating the event.

サービスから設定する場合、確認トランザクションメッセージは、各訪問者が初めてそのサービスにサブスクライブしたときにのみ送信されます。 If a profile is already subscribed, no confirmation message will be sent again to that profile.

### Step 1: Create the confirmation email {#step-1--create-the-confirmation-email-1}

確認電子メールは、ニュースレターを購読している各プロファイルに（ランディングページなどの方法を通じて）自動的に送信されます。 購読はイベントと見なされ、電子メールはサービスを購読する [各プロファイルを](../../channels/using/about-transactional-messaging.md) 、ターゲットにするトランザクションメッセージです。

確認電子メールを作成する手順を以下に示します。 トランザクションメッセージはサービス内で参照されるので、最初に作成する必要があります。

#### イベントの作成 {#create-the-event-1}

The confirmation email is a transactional message as it reacts to an event: the subscription to a service. このメッセージは、ニュースレターの購読を確認するために送信されます。

1. イベントを作成するには、// **[!UICONTROL Marketing plans]** メニュ **[!UICONTROL Transactional messages]** ーを使 **[!UICONTROL Event configuration]** 用します。このメニューはAdobe Campaignロゴからアクセスできます。
1. ラベルを入力し、ターゲットディメンションを選択して、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   設定手順は、トランザクションメッセージング [の設定の節に示し](../../administration/using/configuring-transactional-messaging.md) ます。

1. セクション **[!UICONTROL Fields]** で、調整を有効 **[!UICONTROL Create element]** にするた **[!UICONTROL publicLabel]** めに、をクリックしてデータ構造に追加します。

   ![](assets/confirmation_publicLabel-field.png)

   >[メモ]
   >
   >このフ **[!UICONTROL publicLabel]** ィールドは必須です。 イベントデータ構造に追加しない場合、Adobe Campaignはサービスとの調整を実行できません。 サービスを購読する際に、このフィールドに対応するサービスの **[!UICONTROL Service label]** IDが入力されます。

1. セクション **[!UICONTROL Enrichment]** でをクリックし、タ **[!UICONTROL Create element]** ーゲットリソース **[!UICONTROL Service]** を選択します。

   ![](assets/confirmation_enrichment-service.png)

1. この節では、リ **[!UICONTROL Join definition]** ソースのフィールドをイベ **[!UICONTROL publicLabel]** ント設 **[!UICONTROL Service]** 定のフィール **[!UICONTROL publicLabel]** ドにマッピングします。

   ![](assets/confirmation_publicLabel-join.png)

   >[メモ]
   >
   >これにより、トランザクションメッセージ内のリソースのパーソナライゼ **[!UICONTROL Service]** ーションフィールドを使用できます。

1. イベント設定を保存し、をクリックし **[!UICONTROL Publish]** てイベントを発行します。

イベントの準備が整いました。 これで、トランザクション電子メールメッセージを設計できます。

#### 確認メッセージの設計 {#design-the-confirmation-message-1}

The confirmation email is a transactional message based on the event that you just published.

1. Adobe Campaignのロゴで、/を選択し、 **[!UICONTROL Marketing plans]** をクリ **[!UICONTROL Transactional messages]** ックしま **[!UICONTROL Transactional messages]**&#x200B;す。
1. Select the transactional email corresponding to the event that you just published.

1. Click the  section and select an email template. **[!UICONTROL Content]** For more on editing a transactional message content, see Event transactional messages.[](../../channels/using/event-transactional-messages.md)
1. As you have direct access to all fields from the  resource, you can select any field from the  &gt;  &gt;  &gt; node to personalize your content.**[!UICONTROL Service]****[!UICONTROL Context]****[!UICONTROL Real-time event (rtEvent)]****[!UICONTROL Event context (ctx)]****[!UICONTROL Service]**

   ![](assets/confirmation_personalization-service.png)

   トランザクションメッセージのパーソナライズについて詳しくは、この節を [参照してくださ](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)い。

1. Preview your message using a test profile. 詳しくは、トランザクションメッセージで [のテストプロファイルの定義を参照してください](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message)。

1. をクリック **[!UICONTROL Save & close]** して、コンテンツを保存します。
1. トランザクションメッセージを公開します。 詳しくは、ト [ランザクションメッセージの公開を参照してくださ](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)い。

### 手順2:サービスの作成と設定 {#step-2--create-and-configure-the-service-1}

1. Adobe Campaignロゴを使用して、アドバ **ンスメニュー** Profiles &amp; **Audiences** /Servicesからサービスを作成します。
1. 「」セクションに移動 **[!UICONTROL Service properties]** し、「サービス」ダッシュボ ![](assets/edit_darkgrey-24px.png) ードのボタンを使用してアクセスします。
1. Fill in the **[!UICONTROL Service label]** field.

   ![](assets/confirmation_service-label.png)

   >[メモ]
   >
   >トランザクションメッセージとの調整を有効にするには、このフィールドに入力する必要があります。

1. セクションで、 **[!UICONTROL Confirmation messages]** 以下を選択しま **[!UICONTROL Custom message]**&#x200B;す。このモードを使用すると、サービスを購読しているプロファイルに対して、特定の確認メッセージを参照できます。
1. 作成したトラン **[!UICONTROL Custom subscription event configuration]** ザクションメッセージに関連付けられているを選択します。

   ![](assets/confirmation_service-confirmation-message.png)

1. Click **[!UICONTROL Confirm]** and save the service.

現在は、プロファイルがこのサービスを購読するたびに、定義したトランザクションメッセージを受信し、選択したサービスにマッピングされたパーソナライズされたフィールドを受信します。 A message will be sent only the first time the user subscribes.

## ランディングページからの確認メッセージの設定 {#configuring-confirmation-message-from-landing-page}

また、購読ランディングページのセクションのオプションを使用して、購読のランディン **[!UICONTROL Start sending messages]** グページから確認メ **[!UICONTROL Job]** ッセージを参照することもできます。

ランディングページから確認メッセージを参照する場合、プロファイルが既に登録されている場合でも、ランディングページが送信されるたびにメッセージが送信されます。

### 手順1:確認電子メールの作成 {#step-1--create-the-confirmation-email-2}

確認の電子メールは、ランディングページを通じてニュースレターを購読する各プロファイルに自動的に送信されます。 購読はイベントと見なされ、電子メールはトランザクションメッセージで [](../../channels/using/about-transactional-messaging.md) 、サービスを購読する各プロファイルをターゲットにします。

これらの要素を作成する手順を以下に示します。 トランザクションメッセージはランディングページで参照されるので、最初に作成する必要があります。

#### イベントの作成 {#create-the-event-2}

The confirmation email is a transactional message as it reacts to an event: the subscription to a service. [](../../channels/using/about-transactional-messaging.md)このメッセージは、ニュースレターの購読を確認するために送信されます。

1. イベントを作成するには、// **[!UICONTROL Marketing plans]** メニュ **[!UICONTROL Transactional messages]** ーを使 **[!UICONTROL Event configuration]** 用します。このメニューはAdobe Campaignロゴからアクセスできます。
1. ラベルを入力し、ターゲットディメンションを選択して、をクリックしま **[!UICONTROL Create]**&#x200B;す。

   設定手順は、トランザクションメッセージング [の設定の節に示し](../../administration/using/configuring-transactional-messaging.md) ます。

1. セクション **[!UICONTROL Fields]** で、調整を有効 **[!UICONTROL Create element]** にするた **[!UICONTROL serviceName]** めに、をクリックしてデータ構造に追加します。

   ![](assets/confirmation_serviceName-field.png)

   >[メモ]
   >
   >このフ **[!UICONTROL serviceName]** ィールドは必須です。 イベントデータ構造に追加しない場合、Adobe Campaignは、登録済みサービスとの調整を実行できません。

1. セクション **[!UICONTROL Enrichment]** でをクリックし、タ **[!UICONTROL Create element]** ーゲットリソース **[!UICONTROL Service]** を選択します。
1. この節では、リ **[!UICONTROL Join definition]** ソースのフィールドをイベ **[!UICONTROL serviceName]** ント設 **[!UICONTROL Service]** 定のフィール **[!UICONTROL name]** ドにマッピングします。

   ![](assets/confirmation_serviceName-join.png)

   >[メモ]
   >
   >これにより、トランザクションメッセージ内のリソースのパーソナライゼ [!UICONTROL Service] ーションフィールドを使用できます。

#### 確認メッセージの設計 {#design-the-confirmation-message-2}

トランザクションメッセージの設計手順をこの節で説明 [します](../../audiences/using/confirming-subscription-to-a-service.md#design-the-confirmation-message-1)。

### 手順2:サービスの作成と設定 {#step-2--create-and-configure-the-service-2}

1. アドバンスメニューから **[!UICONTROL Profiles & audiences]** 、Adobe Campaign **[!UICONTROL Services]** ロゴを使用して、サービスを作成します。
1. 「」セクションに移動 **[!UICONTROL Service properties]** し、「サービス」ダッシュボ ![](assets/edit_darkgrey-24px.png) ードのボタンを使用してアクセスします。
1. Fill in the **[!UICONTROL Service label]** field. このラベルは、確認メッセージと購読のランディングページに表示されます。
1. Click **[!UICONTROL Confirm]** and save the service.

### 手順3:ランディングページの作成と設定 {#step-3--create-and-configure-the-landing-page}

Webサイトに公開する購読のランディングページを作成します。

このランディングページを作成して設定するには、次の手順に従います。

1. テンプレート [に基づいて新しいランディング](../../channels/using/about-landing-pages.md) ページをデザイン **[!UICONTROL Subscription]** します。
1. ランディングページのプロパティを編集します。 「&gt;」セクシ **[!UICONTROL Job]** ョンで、オ **[!UICONTROL Specific actions]** プションを選択 **[!UICONTROL Specific service]** し、先ほど作成したサービスをドロップダウンリストから選択します。

   ![](assets/confirmation_lp-specific-service.png)

1. このオプション **[!UICONTROL Start sending message]** を選択し、作成したトランザクションメッセージをドロップダウンリストから選択します。

   ![](assets/confirmation_lp-start-sending-message.png)

1. ランディングページのコンテンツをカスタマイズします。

1. [ランディングページをテスト](../../channels/using/sharing-a-landing-page.md) 、公開します。

現在は、プロファイルがランディングページを送信してニュースレターを購読するたびに、サービスにマッピングされたパーソナライズされたフィールドで定義した確認メッセージを受け取ります。

>[NOTE]
>
>プロファイルが既に登録されている場合でも、ランディングページが送信されるたびにメッセージが送信されます。
