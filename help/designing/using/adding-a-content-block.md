---
title: コンテンツブロックの追加
seo-title: コンテンツブロックの追加
description: コンテンツブロックの追加
seo-description: メッセージをパーソナライズするために使用できる様々な動的コンテンツブロックを用意し、カスタムコンテンツブロックの作成方法を学習します。
page-status-flag: 常にアクティブ化されていない
uuid: 08153ea0-42fb-4c0b-8d4b-9407540748d6
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: personalizing- content
discoiquuid: 3ffda143- f42a-4cf9- b43c- e53d24549025
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 84bc011b079c9f620ea672bf081e54adc023aa07

---


# Adding a content block{#adding-a-content-block}

Adobe Campaignには、事前設定済みのコンテンツブロックのリストが用意されています。これらのコンテンツブロックは動的でパーソナライズされたもので、特定のレンダリングがあります。例えば、ミラーページへの挨拶やリンクを追加できます。

>[!NOTE]
>
>The images below show how to insert a content block using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) for an email.

コンテンツブロックを追加するには:

1. Click inside a text block, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert content block]**. For more on the Email Designer interface, see [this section](../../designing/using/about-email-content-design.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. 挿入するコンテンツブロックを選択します。使用できるブロックは、コンテキスト（電子メールまたはランディングページ）によって異なります。

   ![](assets/email_content_block_2.png)

1. **[!UICONTROL Save]**&#x200B;をクリックします。

コンテンツブロックの名前はエディターに表示され、黄色でハイライト表示されます。パーソナライゼーションが生成されると、プロファイルに自動的に対応します。

![](assets/email_content_block_3.png)

あらかじめ用意されているコンテンツブロックは次のとおりです。

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Link to mirror page (MirrorPage)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**:このコンテンツブロックは **ランディングページでのみ使用**&#x200B;できます。
* **[!UICONTROL Default sender name (DefaultSenderName)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**:このコンテンツブロックは **配信でのみ使用**&#x200B;できます。
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

## Creating custom content blocks {#creating-custom-content-blocks}

メッセージまたはランディングページに挿入する新しいコンテンツブロックを定義できます。

コンテンツブロックを作成するには、次の手順に従います。

1. Click **[!UICONTROL Resources > Content blocks]** from the advanced menu to access the list of content blocks.
1. **[!UICONTROL Create]** ボタンをクリックするか、既存のコンテンツブロックを複製します。

   ![](assets/content_bloc_01.png)

1. ラベルを入力します。
1. Select the block's **[!UICONTROL Content type]**. 次の3つのオプションがあります。

   * **[!UICONTROL Shared]**:コンテンツブロックは、配信またはランディングページで使用できます。
   * **[!UICONTROL Delivery]**:コンテンツブロックは配信でのみ使用できます。
   * **[!UICONTROL Landing page]**:コンテンツブロックはランディングページでのみ使用できます。
   ![](assets/content_bloc_02.png)

1. You can select a **[!UICONTROL Targeting dimension]**. For more on this, see [About targeting dimension](../../designing/using/adding-a-content-block.md#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. You can select the **[!UICONTROL Depends on format]** option to define two different blocks: one for HTML emails, and one for emails in text format. エディター（HTMLおよびテキスト）に2つのタブが表示され、対応するコンテンツが定義されます。

   ![](assets/content_bloc_03.png)

1. Enter the content of the content block(s), and click the **[!UICONTROL Create]** button.

コンテンツブロックをメッセージまたはランディングページのコンテンツエディターで使用できるようになりました。

>[!CAUTION]
>
>When editing the content of a block, make sure there are no extra white spaces between the beginning and the end of your *if* statements. HTMLでは、空白が画面に表示され、コンテンツレイアウトに影響します。

## About targeting dimension {#about-targeting-dimension}

ターゲットディメンションを使用すると、コンテンツブロックを使用できるメッセージのタイプを定義できます。これは、メッセージに不適切なブロックを使用しないようにするためのもので、エラーにつながる可能性があります。

実際には、メッセージの編集時には、そのメッセージのターゲットディメンションと互換性のあるターゲットディメンションを持つコンテンツブロックのみを選択できます。

**[!UICONTROL Unsubscription link]** 例えば、ブロックのターゲットディメンションは **[!UICONTROL Profiles]****[!UICONTROL Profiles]** 、リソースに固有のパーソナライゼーションフィールドが含まれているためです。Therefore, you cannot use an **[!UICONTROL Unsubscription link]** block in an [event transactional message](../../channels/using/event-transactional-messages.md), because the targeting dimension of that type of message is **[!UICONTROL Real-time events]**. However, you can use the **Unsubscription link** block in a [profile transactional message](../../channels/using/profile-transactional-messages.md), because the targeting dimension of that type of message is **Profiles**. Finally, the **[!UICONTROL Link to mirror page]** block does not have a targeting dimension, so you can use it in any message.

このフィールドを空のままにすると、ターゲットディメンションが何であっても、コンテンツブロックはすべてのメッセージと互換性があります。ターゲットディメンションを設定した場合、そのブロックは同じターゲットディメンションを持つメッセージとのみ互換性があります。

For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
