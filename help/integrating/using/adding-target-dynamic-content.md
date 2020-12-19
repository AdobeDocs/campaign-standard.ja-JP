---
solution: Campaign Standard
product: campaign
title: Target の動的コンテンツの追加
description: Adobe Campaign配信の1つにAdobe Targetの動的コンテンツを追加する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Target の動的コンテンツの追加{#adding-target-dynamic-content}

Adobe Targetとの統合により、配信に動的な画像を追加して、エクスペリエンスに応じてコンテンツをパーソナライズできます。

電子メールの編集中に、受信者に応じて変化する動的な画像をAdobe Targetから挿入できます。

Adobe Campaignの画像にアクセスする前に、まずAdobe Targetで次のタスクを実行する必要があります。

* 1つまたは複数の[リダイレクトオファー](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)を作成します。ここで、使用するイメージのURLを指定する必要があります。
* 1 つ以上の[オーディエンス](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html)を作成します。アクティビティのターゲットをそこで定義します。
* [フォームベースのExperience Composer](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html)アクティビティを作成します。このフォルダーでは、rawboxを選択し、作成したリダイレクトオファーの数に応じて複数のエクスペリエンスを指定する必要があります。 各エクスペリエンスに対して、作成したリダイレクトオファーの1つを選択する必要があります。
* Adobe Campaignの情報を使用してセグメントを作成し、エクスペリエンスを指定します。 オファーの選択ルールで Adobe Campaign からのデータを使用するには、Adobe Target のローボックスでデータを指定する必要があります。

1. E メール配信を作成します。
1. 電子メールまたはランディングページのコンテンツを編集する場合は、画像ブロックに移動し、コンテキストメニューから&#x200B;**[!UICONTROL Dynamic image from Adobe Target]**&#x200B;を選択します。

   ![](assets/tar_insert_dynamic_image.png)

1. デフォルトで電子メールに表示する画像を選択します。 画像URLを直接指定するか、[アセット](../../integrating/using/working-with-campaign-and-assets-core-service.md)を介して共有される画像を選択できます。

   この統合が対応するのは、静的画像だけです。コンテンツの残りの部分はカスタマイズできません。

1. Adobe Target で指定したローボックス名を入力します。
1. Adobe Target の設定で Enterprise 権限を使用している場合は、対応するプロパティをこのフィールドに追加します。Target の Enterprise 権限について詳しくは、[このページ](https://docs.adobe.com/content/help/ja-JP/target/using/administer/manage-users/enterprise/properties-overview.translate.html)を参照してください。このフィールドはオプションであり、Target で Enterprise 権限を使用しない場合は必要ありません。
1. **[!UICONTROL Additional decision parameters]**&#x200B;で、Adobe Targetセグメントで定義されたフィールドとAdobe Campaignフィールドの間のマッピングを指定します。

   使用する Adobe Campaign フィールドは、rawbox で指定されている必要があります。ここでは、受信者の性別に応じて異なるエクスペリエンスを定義します。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 別のプロファイルを選択する際に、挿入するイメージが、Adobe TargetアクティビティとAdobe Campaignで指定したパラメータに応じて変わるかどうかを電子メールにプレビューします。

これで、動的な画像を含む配信を送信できます。 その結果はAdobe Targetで見られる。

**関連トピック：**

* [Adobe Targetポータル](https://docs.adobe.com/content/help/en/target/using/integrate/campaign-and-target.html)
* [E メールコンテンツデザインについて](../../designing/using/designing-content-in-adobe-campaign.md)
* [リアルタイムビデオでの電子メール画像のパーソナライズ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) 

