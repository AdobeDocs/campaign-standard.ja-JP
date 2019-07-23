---
title: Target動的コンテンツの追加
seo-title: Target動的コンテンツの追加
description: Target動的コンテンツの追加
seo-description: Adobe Targetの動的コンテンツをAdobe Campaignの配信の1つに追加する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- target
discoiquuid: 45ddf7b7-98f7-4fdd- bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eed2e3597548c97345f51fe62dd2b56af5042e87

---


# Adding Target dynamic content{#adding-target-dynamic-content}

Adobe Targetの統合では、動的な画像を配信に追加して、エクスペリエンスに応じてコンテンツをパーソナライズできます。

電子メールの編集中に、Adobe Targetから動的な画像を挿入できます。この画像は、受信者によって変更されます。

Adobe Campaignで画像にアクセスする前に、次のタスクをAdobe Targetで実行する必要があります。

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* Create one or several [audiences](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html), to define the target of your activity.
* [フォームベースのExperience Composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) アクティビティを作成します。このアクティビティでは、作成されたリダイレクトオファーの数に応じて、rawboxを選択し、いくつかのエクスペリエンスを指定できます。各エクスペリエンスについて、作成されたリダイレクトオファーの1つを選択する必要があります。
* Adobe Campaignの情報を使用してセグメントを作成し、エクスペリエンスを指定します。Adobe Campaignのデータをオファーの選択ルールで使用するには、Adobe Targetのrawboxでデータを指定する必要があります。

1. 電子メール配信を作成します。
1. When editing the content of an email or a landing page, go to an image block, then select **[!UICONTROL Dynamic image from Adobe Target]** via the contextual menu.

   ![](assets/tar_insert_dynamic_image.png)

1. 電子メールにデフォルトで表示される画像を選択します。You can directly specify the image URL or select an image shared via [Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   統合では静的画像のみがサポートされています。残りのコンテンツはカスタマイズできません。

1. Adobe Targetで指定したrawboxの名前を入力します。
1. Adobe Targetの設定でエンタープライズ権限を使用する場合は、このフィールドに対応するプロパティを追加します。Learn more about Target Enterprise permissions in [this page](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). このフィールドはオプションです。Targetでエンタープライズ権限を使用しない場合は必須ではありません。
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   使用されるAdobe Campaignフィールドは、rawboxで指定されている必要があります。ここでは、受信者の性別に応じて異なるエクスペリエンスを定義します。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 電子メールをプレビューして、異なるプロファイルを選択するときに、Adobe TargetアクティビティおよびAdobe Campaignで指定されているパラメーターに応じて画像が挿入されるかどうかを確認します。

動的な画像を含む配信を送信できるようになりました。その結果はAdobe Targetで確認できます。

**関連トピック:**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [電子メールコンテンツデザインについて](../../designing/using/about-email-content-design.md)
* [リアルタイム](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) ビデオでの電子メール画像のパーソナライズ

