---
title: Target 動的コンテンツの追加
description: Adobe targetの動的コンテンツをAdobe Campaignの配信の1つに追加する方法について説明します。
page-status-flag: 非活性化の
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとターゲットの連携
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Target 動的コンテンツの追加{#adding-target-dynamic-content}

Adobe targetの統合により、動的な画像を配信に追加して、エクスペリエンスに応じてコンテンツをパーソナライズできます。

電子メールの編集時に、Adobe targetから動的な画像を挿入し、受信者に応じて変更されます。

Adobe Campaignの画像にアクセスする前に、Adobe targetで次のタスクを実行する必要があります。

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* 1 つ以上の[オーディエンス](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html)を作成します。アクティビティのターゲットをそこで定義します。
* Create a [Form-based experience composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. 各エクスペリエンスに対して、作成したリダイレクトオファーの1つを選択する必要があります。
* Adobe Campaignの情報を使用して、エクスペリエンスを指定してセグメントを作成します。 オファーの選択ルールで Adobe Campaign からのデータを使用するには、Adobe Target のローボックスでデータを指定する必要があります。

1. E メール配信を作成します。
1. 電子メールまたはランディングページのコンテンツを編集する場合は、画像ブロックに移動し、コンテキストメニ **[!UICONTROL Dynamic image from Adobe Target]** ューを使用して選択します。

   ![](assets/tar_insert_dynamic_image.png)

1. デフォルトで電子メールに表示する画像を選択します。 画像URLを直接指定するか、アセットを介して共有する画像を選択で [きます](../../integrating/using/working-with-campaign-and-assets-core-service.md)。

   この統合が対応するのは、静的画像だけです。残りのコンテンツはカスタマイズできません。

1. Adobe Target で指定したローボックス名を入力します。
1. Adobe Target の設定で Enterprise 権限を使用している場合は、対応するプロパティをこのフィールドに追加します。Target の Enterprise 権限について詳しくは、[このページ](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html)を参照してください。このフィールドはオプションであり、Target で Enterprise 権限を使用しない場合は必要ありません。
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   使用される Adobe Campaign フィールドは、ローボックスで指定されている必要があります。ここでは、受信者の性別に応じて異なるエクスペリエンスを定義します。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 電子メールをプレビューして、異なるプロファイルを選択する場合に、Adobe targetアクティビティとAdobe Campaignで指定されたパラメーターに応じて挿入された画像が変化するかどうかを確認します。

これで、動的な画像を含む配信を送信できます。 その結果はAdobe targetで確認できます。

**関連トピック：**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [電子メールコンテンツデザインについて](../../designing/using/overview.md)
* [リアルタイムビデオでの電子メール画像のパーソナライズ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) （英語のみ）

