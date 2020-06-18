---
title: ダブルオプトインプロセスの設定
description: Adobe Campaign内のランディングページを使用して重複のオプトインプロセスを設定するには、次の手順に従います。
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 1%

---


# ダブルオプトインプロセスの設定{#setting-up-a-double-opt-in-process}

## 重複オプトインについて {#about-double-opt-in}

重複オプトインメカニズムは、電子メールを送信する際のベストプラクティスです。 これは、プラットフォームを誤ったまたは無効な電子メールアドレスやスパムから保護し、スパムの可能性がある苦情を防ぎます。

原則は、訪問者の契約を確認する電子メールを送信してから、「プロファイル」としてキャンペーンのデータベースに保存することです。 訪問者がオンラインランディングページに入力し、電子メールを受信したら、確認リンクをクリックして購読を終了する必要があります。

![](assets/optin_mechanism.png)

この設定を行うには、次の操作が必要です。

1. 訪問者が登録および登録できるように、ランディングページを作成して公開します。 このランディングページはWebサイトから入手できます。 このランディングページに入力して送信した訪問者は、最終的な検証前に通信を受け取らないように、ブロックリストに格納されますが、データベースに追加されます(キャンペーンの [ブロックリスト管理を参照](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md))。
1. オプトイン電子メールを作成し、確認リンクと共に自動的に送信します。 この電子メールは、ランディングページを送信したターゲットの訪問者を示します。 これは、「オプトアウト」プロファイルをターゲットできる電子メールテンプレートに基づいています。
1. 確認ランディングページにリダイレクトします。 次の最後のランディングページは、確認ボタンを提示します。 訪問者はクリックする必要があります。 確認の際に送信されるご案内の電子メールを設計したり、新しい受信者向けの特別なオファーを電子メールに追加したりできます。

これらの手順は、すべてのAdobe Campaignーを正しく有効にするために、特定の順序でパラメーターで設定する必要があります。

## 手順1: 確認ランディングページの作成 {#step-1--create-the-confirmation-landing-page}

確認ランディングページの作成時に重複のオプトインメカニズム開始を設定するプロセス。 このページは、訪問者が登録するために確認電子メールをクリックした場合に表示されます。

このランディングページを作成および設定するには、次の操作が必要です。

1. テンプレートに基づいて [新しいランディングページ](../../channels/using/getting-started-with-landing-pages.md) を設計し **[!UICONTROL Profile acquisition (acquisition)]** ます。 ラベル「**CONFIRMATION**」を入力します。

   サー [ビスを使用する必要がある場合は](../../audiences/using/about-subscriptions.md)、 **[!UICONTROL Subscription (sub)]** テンプレートも使用できます。

1. ランディングページのプロパティを編集し、「 **[!UICONTROL Access and loading]** 」セクションでオプションの選択を解除し **[!UICONTROL Authorize unidentified visitors]**&#x200B;て「」を選択します（これは必須ではありません） **[!UICONTROL Preload visitor data]** 。

   ![](assets/optin_confirmlp_param.png)

1. 「 **[!UICONTROL Job]** >」 **[!UICONTROL Additional data]** セクションでをクリックし、次のコンテキストパス **[!UICONTROL Add an element]** を入力します。

   /context/プロファイル/ブロックリスト

   値を **falseに設定し、をクリックし****[!UICONTROL Add]**&#x200B;ます。

   ![](assets/optin_confirmlp_newelement.png)

   このコンテキストでは、電子メールを送信できるように、「ブロックリスト時」フィールドが削除されます。 最初のランディングページが確認前にこのフィールドを **** trueに設定し、未確認のプロファイルに電子メールが送信されないようにしていたことが後で確認されます。 詳しくは、 [手順3を参照してください。 獲得ランディングページを作成します](#step-3--create-the-acquisition-landing-page)。

1. ランディングページのコンテンツをカスタマイズします。 例えば、パーソナライズされたデータを表示し、確認ボタンのラベルを「ここをクリックして購読を確認」に変更できます。

   ![](assets/optin_confirmlp_design.png)

1. 確認ページのコンテンツを調整して、登録されたことを購読者に通知します。

   ![](assets/optin_confimlp_page2.png)

1. [ランディングページをテストして発行します](../../channels/using/testing-publishing-landing-page.md) 。

## 手順2: 確認電子メールの作成 {#step-2--create-the-confirmation-email}

確認ランディングページを作成したら、確認電子メールを設計できます。 この電子メールは、獲得ランディングページを検証するすべての訪問者に自動的に送信されます。 この検証はイベントと見なされ、電子メールはトランザクションメッセージで、特定のタイポロジルールにリンクされており、ターゲットのオプトアウトが可能です。

これらの要素を作成する手順を以下に示します。 この電子メールテンプレートが参照されるので、ダウンロード計測用ランディングページ自体を作成する前に、テンプレートに従う必要があります。

### イベントの作成 {#create-the-event}

確認電子メールは、イベントに反応する [トランザクションメッセージ](../../channels/using/about-transactional-messaging.md) です。 フォームの検証。 最初にテンプレートを作成し、次にイベントのトランザクションメッセージを作成する必要があります。

1. Adobe Campaignのロゴからアクセスできる **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** メニューのイベントを作成し、「**CONFIRM**」というラベルを入力します。
1. ターゲティングディメンションを選択し、 **[!UICONTROL Profile]** をクリックし **[!UICONTROL Create]**&#x200B;ます。

   ![](assets/optin_eventcreate.png)

1. セクションで、をクリック **[!UICONTROL Fields]** してデータ構造 **[!UICONTROL Create element]****[!UICONTROL email]** にを追加し、調整を有効にします。
1. セクションで、をクリック **[!UICONTROL Enrichment]** し、 **[!UICONTROL Create element]****[!UICONTROL Profile]** ターゲットリソースを選択します。 その後、必要に応じて、セクション内の **[!UICONTROL email]** フィールドまたは **[!UICONTROL Join definition]** 他の複合紐付けキーにマップできます。

   ![](assets/optin_eventcreate_join.png)

   サービスを使用する必要がある場合は、 **[!UICONTROL Service]** ターゲットリソースを追加し、フィールドにマップし **[!UICONTROL serviceName]** ます。 詳しくは、を参照してください。

1. ドロップダウンリスト **[!UICONTROL Profile]** のを **[!UICONTROL Targeting enrichment]** 選択します。
1. をクリック **[!UICONTROL Publish]** して、イベントを公開します。

イベントの準備ができました。 これで、電子メールテンプレートを設計できます。 このテンプレートには、前に作成した **CONFIRMATION** ランディングページへのリンクを含める必要があります。 詳しくは、「確認メッセージの [設計](#design-the-confirmation-message)」を参照してください。

### タイポロジの作成 {#create-the-typology-rule}

あらかじめ用意されている [類型を複製して、特定の](../../sending/using/about-typology-rules.md)類型を作成する必要があります。 タイポロジを使用すると、契約をまだ確認しておらず、まだブロックリスト中のプロファイルにメッセージを送信できます。 デフォルトでは、タイポロジによってオプトアウト(ブロックリスト時など)プロファイルが除外されます。 このタイポロジを作成するには、次の手順に従います。

1. Adobe Campaignのロゴから、/ **[!UICONTROL Administration]****[!UICONTROL Channels]** /を選択し、 **[!UICONTROL Typologies]** をクリックし **[!UICONTROL Typologies]**&#x200B;ます。
1. 既製のタイポロジの重複 **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**。
1. 重複が確認されたら、新しいタイポロジを編集し、ラベル **TYPOLOGY_プロファイルを入力します**。
1. 「ブロックリスト時の **住所** 」の規則を削除します。
1. クリック **[!UICONTROL Save]** .

このタイポロジを確認電子メールに関連付けることができるようになりました。

### 確認メッセージの設計 {#design-the-confirmation-message}

確認電子メールは、前に作成したイベントに基づくトランザクションメッセージです。 次の手順に従って、このメッセージを作成します。

1. Adobe Campaignのロゴから/を選択し、 **[!UICONTROL Marketing plans]** をクリック **[!UICONTROL Transactional messages]** し **[!UICONTROL Transactional messages]**&#x200B;ます。
1. **CONFIRM** 電子メールテンプレートを編集し、カスタマイズします。 既存のコンテンツをアップロードすることも、あらかじめ用意されているテンプレートを使用することもできます。
1. 追加 **CONFIRMATION** ランディングページへのリンクをクリックし、をクリックして変更 **[!UICONTROL Confirm]** を保存します。

   ![](assets/optin_email_selectlp.png)

1. 電子メールテンプレートのプロパティを編集します。 「 **[!UICONTROL Advanced parameters]** >」 **[!UICONTROL Preparation]** セクションで、前に作成した **TYPOLOGY_プロファイル** ・タイポロジを選択します。
1. トランザクションメッセージを保存して公開します。

## 手順3: 獲得ランディングページの作成 {#step-3--create-the-acquisition-landing-page}

最初の獲得ランディングページを作成する必要があります。 このオプトインフォームはWebサイトに公開されます。

このランディングページを作成および設定するには、次の操作が必要です。

1. テンプレートに基づいて [新しいランディングページ](../../channels/using/getting-started-with-landing-pages.md) を設計し **[!UICONTROL Profile acquisition (acquisition)]** ます。 ラベル&#39;**ACQUISITION**&#39;を入力します。
1. ランディングページのプロパティを編集します。 「 **[!UICONTROL Job]** >」 **[!UICONTROL Additional data]** セクションでをクリックし、次のコンテキストパス **[!UICONTROL Add an element]** を入力します。

   /context/プロファイル/ブロックリスト

   値を **trueに設定します**。

   ブロックリストに追加を強制し、契約を確認していない訪問者にメッセージを送信しないようにするには、このオプションが必須です。 確認ランディングページの検証では、確認後にこのフィールドが **false** に設定されます。 この点について詳しくは、 [手順1を参照してください。 確認ランディングページを作成します](#step-1--create-the-confirmation-landing-page)。

1. 「 **[!UICONTROL Job]** >」 **[!UICONTROL Specific actions]** セクションで、オプションを選択し **[!UICONTROL Start sending messages]**&#x200B;ます。
1. 関連するドロップダウンリストで、作成した **CONFIRM** トランザクションメッセージテンプレートを選択します。

   ![](assets/optin_acquisition_startoption.png)

1. ブランドや取得する必要のあるデータに応じて、ランディングページのコンテンツをカスタマイズします。 パーソナライズされたデータを表示し、確認ボタンのラベルを「 **購読を** 確認」などに変更できます。

   ![](assets/optin_acquisition_page1.png)

1. 確認ページをカスタマイズして、新しい購読者に購読の検証が必要であることを通知します。

   ![](assets/optin_acquisition_page2.png)

1. [ランディングページをテストして発行します](../../channels/using/testing-publishing-landing-page.md) 。

重複のオプトインメカニズムが設定されました。 この **[!UICONTROL ACQUISITION]** ランディングページのパブリックURLから開始して、プロシージャを実行し、最後から最後までテストできます。 このURLは、ランディングページダッシュボードに表示されます。
