---
title: Target の動的コンテンツの追加
description: Adobe Campaign配信の1つにAdobe Targetの動的コンテンツを追加する方法を説明します。
page-status-flag: never-activated
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 29%

---


# Target の動的コンテンツの追加{#adding-target-dynamic-content}

Adobe Targetとの統合により、配信に動的な画像を追加して、エクスペリエンスに応じてコンテンツをパーソナライズできます。

電子メールの編集中に、受信者に応じて変化する動的な画像をAdobe Targetから挿入できます。

Adobe Campaignの画像にアクセスする前に、まずAdobe Targetで次のタスクを実行する必要があります。

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* 1 つ以上の[オーディエンス](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html)を作成します。アクティビティのターゲットをそこで定義します。
* Create a [Form-based experience composer](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. 各エクスペリエンスに対して、作成したリダイレクトオファーの1つを選択する必要があります。
* Adobe Campaignの情報を使用してセグメントを作成し、エクスペリエンスを指定します。 オファーの選択ルールで Adobe Campaign からのデータを使用するには、Adobe Target のローボックスでデータを指定する必要があります。

1. E メール配信を作成します。
1. 電子メールまたはランディングページのコンテンツを編集する場合は、画像ブロックに移動し、コンテキストメニュー **[!UICONTROL Dynamic image from Adobe Target]** から選択します。

   ![](assets/tar_insert_dynamic_image.png)

1. デフォルトで電子メールに表示する画像を選択します。 画像URLを直接指定するか、ア [セットを介して共有される画像を選択できます](../../integrating/using/working-with-campaign-and-assets-core-service.md)。

   この統合が対応するのは、静的画像だけです。コンテンツの残りの部分はカスタマイズできません。

1. Adobe Target で指定したローボックス名を入力します。
1. Adobe Target の設定で Enterprise 権限を使用している場合は、対応するプロパティをこのフィールドに追加します。Target の Enterprise 権限について詳しくは、[このページ](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/properties-overview.html)を参照してください。このフィールドはオプションであり、Target で Enterprise 権限を使用しない場合は必要ありません。
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   使用する Adobe Campaign フィールドは、rawbox で指定されている必要があります。ここでは、受信者の性別に応じて異なるエクスペリエンスを定義します。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 別のプロファイルを選択する際に、挿入するイメージが、Adobe TargetアクティビティとAdobe Campaignで指定したパラメータに応じて変わるかどうかを電子メールにプレビューします。

これで、動的な画像を含む配信を送信できます。 その結果はAdobe Targetで見られる。

**関連トピック：**

* [Adobe Targetポータル](https://docs.adobe.com/content/help/ja-JP/target/using/integrate/campaign-and-target.html)
* [E メールコンテンツデザインについて](../../designing/using/designing-content-in-adobe-campaign.md)
* [リアルタイムビデオでの電子メール画像のパーソナライズ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) （英語のみ）

