---
title: ランディング·ページのコンテンツ·デザインについて
seo-title: ランディング·ページのコンテンツ·デザインについて
description: ランディング·ページのコンテンツ·デザインについて
seo-description: ランディング·ページのコンテンツ·エディタの特殊性について説明します。
page-status-flag: 未活性化の
uuid: 8b230690-8a63-44da-b4ed-8e9d8fd84262
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 設計
content-type: 参照
topic-tags: 編集，ランディングページの内容
discoiquuid: 212720d2-5d57-4e7a-bb72-10512050e78c
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---

# ランディング·ページのコンテンツ·デザインについて{#about-landing-page-content-design}

標準のコンテンツエディタを使用して、Adobe Campaignのランディングページのコンテンツを作成および変更します。

この項では、ランディング·ページのコンテンツ·エディタの特徴について説明します。

* [ランディング·ページ·コンテンツ·エディタ·インタフェース](../../channels/using/landing-page-content-editor-interface.md)
* [ランディングページの構造とスタイルを管理する](../../channels/using/managing-landing-page-structure-and-style.md)
* [ランディング·ページ·フォームのデータ·プロパティの変更](../../channels/using/changing-a-landing-page-form-data-properties.md)

1つ以上のマーケティング活動に共通するアクションの詳細については、次の項を参照してください。

* ランディング·ページ·コンテンツのパーソナライズの詳細は、「パーソナライズ· [フィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field) 」および「コンテ [ンツ·ブロックの追加」を参照してください](../../designing/using/personalization.md#adding-a-content-block)。
* ランディング·ページでの動的コンテンツの定義の詳細は、「ランディング·ページでの動 [的コンテンツの定義」を参照してください](../../channels/using/defining-dynamic-content-in-a-landing-page.md)。
* ランディング·ページへのリンクの挿入の詳細は、「リンクの挿入」を [参照してください](../../designing/using/links.md#inserting-a-link)。
* ランディング·ページへのイメージの挿入の詳細は、「イメージの挿入」を参 [照してくださ](../../designing/using/images.md)い。

また、コンテンツ設 [計に関する一般的なベストプラクティスも確認します](../../designing/using/overview.md#content-design-best-practices)。

>[!NOTE]
>
>Adobe Campaign Standard 19.0リリースより前にインストールしたインスタンスの場合は、従来の電子メールコンテンツエディタにアクセスできます。 インタフェース、使用原理、構成は、次のランディング·ページで説明した内容とほとんど同じです。 ただし、19.0リリース以降で廃止されたレガシーEメールコンテンツエディタでは、すべての機能が使用できないか、維持されない場合があります。 拡張機能を備えたドラッグ·アンド·ドロップ·インタフェースを使用して、電子メール·コンテンツをすばやく編集するには、電子メール·デザイナ [を使用します](../../designing/using/overview.md)。

## ランディングページのデザインのベストプラクティス {#landing-pages-best-practices-design}

* ランディング· **ページの内容を編集する場合**:

   * Adobe CampaignでHTMLページテンプレートを読み込む前に、テンプレートが開いて、さまざまなブラウザで正しく表示されていることを確認してください。
   * HTMLページにJavaScriptスクリプトが含まれている場合は、エディタの外部でエラーなしで実行する必要があります。 一般的に、メッセージの内容にスクリプトを使用して、電子メールクライアントが正しく処理されることを確認しないでください。
   * テンプレートを作成する場合は、タグに' **type'属性を追加す** ることをお勧めします。 この情報はエディタで処理され、Webアプリケーションの構成時にデータベースフィールドをフォームフィールドにリンクするのに役立ちます。
   テンプレート内のHTMLコードの例：

   ```
   <input id="email" type="email" name="email"/>
   ```

   'type'属性の公式リストは、次のアドレスで入手できます。http://www.w3schools.com/tags/att_input_type.asp [](http://www.w3schools.com/tags/att_input_type.asp)