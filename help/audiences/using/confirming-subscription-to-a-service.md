---
title: サービスのサブスクリプションを確認
description: Adobe Campaign 内のサービスを購読しているプロファイルに対して確認メッセージを設定するには、次の手順に従います。
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 100%

---


# サービスのサブスクリプションを確認{#confirming-subscription-to-a-service}

## サブスクリプションの確認の送信について {#sending-subscription-confirmation}

この節では、特定のサービスを購読しているプロファイルに、自動カスタム確認 E メールを送信する方法について説明します。

購読（または購読解除）の確認メッセージをサービスに送信する場合は、デフォルトのメッセージまたはカスタムメッセージを使用できます。確認メッセージを選択する手順は、[サービスの作成](../../audiences/using/creating-a-service.md)の節で説明しています。

デフォルトのメッセージを使用する場合は、その内容を編集できますが、次の制限事項があります。
* メッセージの内容をパーソナライズできるのは、イベントコンテキストからの限られたフィールドのみです。
* このメッセージは、デフォルトモードを使用するすべてのサービスで同じになります。

特定のサービスに対して特定の確認 E メールを送信するには、カスタムメッセージを作成し、その中で他のリソースのパーソナライゼーションフィールドを活用することもできます。これをおこなうには、トランザクションメッセージを作成して設定する必要があります。このメッセージは次の場所から参照できます。
* サービス自体。この詳細については、[サービスからの確認メッセージの設定](#configuring-confirmation-message-from-service)を参照してください。
* サブスクリプションランディングページ。この詳細については、[ランディングページからの確認メッセージの設定](#configuring-confirmation-message-from-landing-page)を参照してください。

## サービスからの確認メッセージの設定 {#configuring-confirmation-message-from-service}

例えば、Web サイトの訪問者がブランドニュースレターを購読する際に、確認メッセージを自動的に送信する場合などです。

トランザクション E メールを設定し、目的のサービス（この例ではブランドニュースレターのサブスクリプション）からそのメッセージを参照する必要があります。トランザクションメッセージにサービス情報を組み込むため、イベントの作成時に紐付けを定義できます。

サービスから設定する場合、確認トランザクションメッセージは、各訪問者が初めてそのサービスを購読したときにのみ送信されます。プロファイルが既に購読されている場合、そのプロファイルに確認メッセージは再送信されません。

### 手順 1：確認 E メールの作成 {#step-1--create-the-confirmation-email-1}

ニュースレターを（ランディングページなどの方法で）購読した各プロファイルに、確認の E メールが自動的に送信されます。このサブスクリプションはイベントと見なされます。また、この E メールはサービスを購読した各プロファイルを対象とする[トランザクションメッセージ](../../channels/using/getting-started-with-transactional-msg.md)です。

確認 E メールを作成する手順を以下に示します。トランザクションメッセージはサービスで参照されるので、最初に作成する必要があります。

#### イベントの作成 {#create-the-event-1}

確認 E メールは、イベント（サービスのサブスクリプション）に反応するトランザクションメッセージです。このメッセージは、ニュースレターのサブスクリプションを確認するために送信されます。

1. イベントを作成するには、Adobe Campaign のロゴから **[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Event configuration]** メニューにアクセスします。
1. ラベルを入力し、ターゲティングディメンションを選択して「**[!UICONTROL Create]**」をクリックします。

   設定手順については、[トランザクションメッセージの設定](../../administration/using/configuring-transactional-messaging.md)の節を参照してください。

1. 「**[!UICONTROL Fields]**」セクションで、紐付けを有効にするために、「**[!UICONTROL Create element]**」をクリックして **[!UICONTROL publicLabel]** をデータ構造に追加します。

   ![](assets/confirmation_publicLabel-field.png)

   >[!NOTE]
   >
   >「**[!UICONTROL publicLabel]**」フィールドは必須です。これをイベントデータ構造に追加しないと、Adobe Campaign ではサービスとの紐付けを実行できません。サービスを購読する際、このフィールドには対応するサービスの **[!UICONTROL Service label]** が入力されます。

1. 「**[!UICONTROL Enrichment]**」セクションで、「**[!UICONTROL Create element]**」をクリックし、「**[!UICONTROL Service]**」ターゲットリソースを選択します。

   ![](assets/confirmation_enrichment-service.png)

1. 「**[!UICONTROL Join definition]**」セクションでは、**[!UICONTROL Service]** リソースの「**[!UICONTROL publicLabel]**」フィールドを、イベント設定の「**[!UICONTROL publicLabel]**」フィールドにマップします。

   ![](assets/confirmation_publicLabel-join.png)

   >[!NOTE]
   >
   >これにより、トランザクションメッセージ内の **[!UICONTROL Service]** リソースのパーソナライゼーションフィールドを使用できるようになります。

1. イベント設定を保存し、「**[!UICONTROL Publish]**」をクリックしてイベントを公開します。

イベントの準備ができました。これで、トランザクション E メールメッセージを設計できます。

#### 確認メッセージのデザイン {#design-the-confirmation-message-1}

確認 E メールは、先ほど公開したイベントに基づくトランザクションメッセージです。

1. Adobe Campaign のロゴから **[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]** を選択し、「**[!UICONTROL Transactional messages]**」をクリックします。
1. 先ほど公開したイベントに対応するトランザクション E メールを選択します。

1. 「**[!UICONTROL Content]**」セクションをクリックし、E メールテンプレートを選択します。トランザクションメッセージコンテンツの編集について詳しくは、[イベントトランザクションメッセージ](../../channels/using/event-transactional-messages.md)を参照してください。
1. **[!UICONTROL Service]** リソースのすべてのフィールドに直接アクセスできるので、**[!UICONTROL Context]**／**[!UICONTROL Real-time event (rtEvent)]**／**[!UICONTROL Event context (ctx)]**／「**[!UICONTROL Service]**」ノードから任意のフィールドを選択して、コンンツをパーソナライズできます。

   ![](assets/confirmation_personalization-service.png)

   トランザクションメッセージのパーソナライズについて詳しくは、[この節](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)を参照してください。

1. テストプロファイルを使用してプレビューします。詳しくは、[トランザクションメッセージでのテストプロファイルの定義](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message)を参照してください。

1. 「**[!UICONTROL Save & close]**」をクリックして、コンテンツを保存します。
1. トランザクションメッセージを公開します。[トランザクションメッセージの公開](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)を参照してください。

### 手順 2：サービスの作成と設定 {#step-2--create-and-configure-the-service-1}

1. Adobe Campaign のロゴから、詳細メニューの **Profiles &amp; audiences**／**Services** にアクセスしてサービスを作成します。
1. サービスダッシュボードの ![](assets/edit_darkgrey-24px.png) ボタンから、「**[!UICONTROL Service properties]**」セクションに移動します。
1. 「**[!UICONTROL Service label]**」フィールドに値を入力します。

   ![](assets/confirmation_service-label.png)

   >[!NOTE]
   >
   >トランザクションメッセージとの紐付けを有効にするには、このフィールドに入力する必要があります。

1. 「**[!UICONTROL Confirmation messages]**」セクションで「**[!UICONTROL Custom message]**」を選択します。このモードを使用すると、サービスに登録しているプロファイルに対する専用の確認メッセージを参照できます。
1. 作成したトランザクションメッセージに関連付けられている **[!UICONTROL Custom subscription event configuration]** を選択します。

   ![](assets/confirmation_service-confirmation-message.png)

1. 「**[!UICONTROL Confirm]**」をクリックしてサービスを保存します。

プロファイルがこのサービスを購読するたびに、定義したトランザクションメッセージを受け取ります。このメッセージでは、パーソナライズされたフィールドが選択したサービスにマッピングされています。

>[!NOTE]
>
>ユーザーが初めて購読するときにのみメッセージが送信されます。

## ランディングページからの確認メッセージの設定 {#configuring-confirmation-message-from-landing-page}

ランディングページの「**[!UICONTROL Job]**」セクションの「**[!UICONTROL Start sending messages]**」オプションを使用して、サブスクリプションランディングページから確認メッセージを参照することもできます。

ランディングページから確認メッセージを参照する場合、ランディングページが送信されるたびに（プロファイルが既に購読されている場合でも）メッセージが送信されます。

### 手順 1：確認 E メールの作成 {#step-1--create-the-confirmation-email-2}

ニュースレターにランディングページから購読した各プロファイルに、確認 E メールが自動的に送信されます。このサブスクリプションはイベントと見なされます。また、この E メールはサービスを購読した各プロファイルを対象とする[トランザクションメッセージ](../../channels/using/getting-started-with-transactional-msg.md)です。

これらの要素を作成する手順を以下に示します。トランザクションメッセージはランディングページで参照されるので、最初に作成する必要があります。

#### イベントの作成 {#create-the-event-2}

確認 E メールは、イベント（サービスのサブスクリプション）に反応する[トランザクションメッセージ](../../channels/using/getting-started-with-transactional-msg.md)です。このメッセージは、ニュースレターのサブスクリプションを確認するために送信されます。

1. イベントを作成するには、Adobe Campaign のロゴから **[!UICONTROL Marketing plans]**／**[!UICONTROL Transactional messages]**／**[!UICONTROL Event configuration]** メニューにアクセスします。
1. ラベルを入力し、ターゲティングディメンションを選択して「**[!UICONTROL Create]**」をクリックします。

   設定手順については、[トランザクションメッセージの設定](../../administration/using/configuring-transactional-messaging.md)の節を参照してください。

1. 「**[!UICONTROL Fields]**」セクションで、紐付けを有効にするために、「**[!UICONTROL Create element]**」をクリックして **[!UICONTROL serviceName]** をデータ構造に追加します。

   ![](assets/confirmation_serviceName-field.png)

   >[!NOTE]
   >
   >「**[!UICONTROL serviceName]**」フィールドは必須です。これをイベントデータ構造に追加しないと、Adobe Campaign では購読されたサービスとの紐付けを実行できません。

1. 「**[!UICONTROL Enrichment]**」セクションで、「**[!UICONTROL Create element]**」をクリックし、「**[!UICONTROL Service]**」ターゲットリソースを選択します。
1. 「**[!UICONTROL Join definition]**」セクションでは、**[!UICONTROL Service]** リソースの「**[!UICONTROL serviceName]**」フィールドを、イベント設定の「**[!UICONTROL name]**」フィールドにマップします。

   ![](assets/confirmation_serviceName-join.png)

   >[!NOTE]
   >
   >これにより、トランザクションメッセージ内の [!UICONTROL Service] リソースのパーソナライゼーションフィールドを使用できるようになります。

#### 確認メッセージのデザイン {#design-the-confirmation-message-2}

トランザクションメッセージを設計する手順は、[この節](#design-the-confirmation-message-1)で説明しています。

### 手順 2：サービスの作成と設定 {#step-2--create-and-configure-the-service-2}

1. Adobe Campaign のロゴから、詳細メニューの **[!UICONTROL Profiles & audiences]**／**[!UICONTROL Services]** にアクセスして、サービスを作成します。
1. サービスダッシュボードの ![](assets/edit_darkgrey-24px.png) ボタンから、「**[!UICONTROL Service properties]**」セクションに移動します。
1. 「**[!UICONTROL Service label]**」フィールドに値を入力します。このラベルは、確認メッセージとサブスクリプションランディングページに表示されます。
1. 「**[!UICONTROL Confirm]**」をクリックしてサービスを保存します。

### 手順 3：ランディングページの作成と設定 {#step-3--create-and-configure-the-landing-page}

Web サイトに公開するサブスクリプションランディングページを作成します。

このランディングページを作成および設定するには、次の手順に従います。

1. [新しいランディングページ](../../channels/using/getting-started-with-landing-pages.md)を「**[!UICONTROL Subscription]**」テンプレートに基づいてデザインします。
1. ランディングページのプロパティを編集します。**[!UICONTROL Job]**／「**[!UICONTROL Specific actions]**」セクションで、「**[!UICONTROL Specific service]**」オプションを選択し、作成したサービスをドロップダウンリストから選択します。

   ![](assets/confirmation_lp-specific-service.png)

1. 「**[!UICONTROL Start sending message]**」オプションを選択し、作成したトランザクションメッセージをドロップダウンリストから選択します。

   ![](assets/confirmation_lp-start-sending-message.png)

1. ランディングページのコンテンツをカスタマイズします。

1. ランディングページを[テストして公開](../../channels/using/testing-publishing-landing-page.md)します。

プロファイルがランディングページを送信してニュースレターを購読するたびに、定義したトランザクションメッセージを受け取ります。このメッセージでは、パーソナライズされたフィールドがサービスにマッピングされています。

>[!NOTE]
>
>ランディングページが送信されるたびに（プロファイルが既に購読されている場合でも）メッセージが送信されます。
