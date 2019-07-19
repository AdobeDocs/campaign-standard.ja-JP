---
title: コンテンツデザインのベストプラクティス
seo-title: コンテンツデザインのベストプラクティス
description: コンテンツデザインのベストプラクティス
seo-description: これらのガイドラインについては、エディターの最適な操作を確認してください。
page-status-flag: 常にアクティブ化されていない
uuid: ad74f49d-999f-4140-89b0- d1ead8642d89
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: デザイン
content-type: 参照
topic-tags: about- content- design
discoiquuid: d33f5f14- a4e3-4327- bd16- eb3135a32076
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Content design best practices{#content-design-best-practices}

エディターの最適な操作を確実に行うには、次のガイドラインを観察することをお勧めします。

* SCSSスタイルシートはサポートされていません。HTMLコンテンツを含むZIPファイルを読み込む場合は、通常のCSSを使用します。
* When editing **email content**:

   メッセージを送信する前にプレビューしてください。Adobe Campaignでは、リトマスを使用して電子メールのレンダリングをテストできます。For more on this, see [Email rendering](../../sending/using/email-rendering.md).

* **ランディングページのコンテンツを編集する場合**:

   * Adobe CampaignでHTMLページテンプレートを読み込む前に、テンプレートが開き、様々なブラウザーで正しく表示されていることを確認してください。
   * HTMLページにJavaScriptスクリプトが含まれている場合、エディター以外でエラーなく実行する必要があります。一般に、メッセージコンテンツでスクリプトを使用しないでください。これは、電子メールクライアントで正しく処理されていることを確認するために使用します。
   * When building a template, we recommend adding a **'type'** attribute to  tags. この情報はエディターによって処理され、Webアプリケーションの設定時にデータベースフィールドをフォームフィールドにリンクさせるのに役立ちます。

      テンプレート内のHTMLコードの例:

      ```
      <input id="email" type="email" name="email"/>
      ```

      The official list of 'type' attributes is available at the following address: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)

More design and general best practices regarding messages are presented in the following Adobe Campaign step-by-step guide: [Delivery best practices with Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).
