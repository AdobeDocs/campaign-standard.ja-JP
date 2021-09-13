---
title: Target の動的コンテンツの追加
description: Adobe Campaign配信の1つにAdobe Target動的コンテンツを追加する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 34%

---

# Target の動的コンテンツの追加{#adding-target-dynamic-content}

Adobe Target統合を使用すると、動的画像を配信に追加して、エクスペリエンスに応じてコンテンツをパーソナライズできます。

Eメールの編集中に、Adobe Targetから動的な画像を挿入できます。この画像は受信者に応じて変わります。

Adobe Campaignの画像にアクセスする前に、次のタスクをAdobe Targetで実行する必要があります。

* 1つまたは複数の[リダイレクトオファー](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=ja)を作成します。このオファーで、使用する画像のURLを指定する必要があります。
* 1 つ以上の[オーディエンス](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html)を作成します。アクティビティのターゲットをそこで定義します。
* [フォームベースのExperience Composer](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html)アクティビティを作成します。このアクティビティで、作成したリダイレクトオファーの数に応じて、ローボックスを選択し、複数のエクスペリエンスを指定する必要があります。 エクスペリエンスごとに、作成したリダイレクトオファーの1つを選択する必要があります。
* Adobe Campaignの情報を使用してセグメントを作成し、エクスペリエンスを指定します。 オファーの選択ルールで Adobe Campaign からのデータを使用するには、Adobe Target のローボックスでデータを指定する必要があります。

1. E メール配信を作成します。
1. Eメールやランディングページのコンテンツを編集する際に、画像ブロックに移動し、コンテキストメニューから「**[!UICONTROL Dynamic image from Adobe Target]**」を選択します。

   ![](assets/tar_insert_dynamic_image.png)

1. デフォルトでEメールに表示される画像を選択します。 画像URLを直接指定するか、[Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md)で共有する画像を選択できます。

   この統合では、静的画像のみをサポートします。残りのコンテンツはカスタマイズできません。

1. Adobe Target で指定したローボックス名を入力します。
1. Adobe Target の設定で Enterprise 権限を使用している場合は、対応するプロパティをこのフィールドに追加します。Target の Enterprise 権限について詳しくは、[このページ](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=ja)を参照してください。このフィールドはオプションであり、Target で Enterprise 権限を使用しない場合は必要ありません。
1. **[!UICONTROL Additional decision parameters]**&#x200B;で、Adobe Targetセグメントで定義されたフィールドとAdobe Campaignフィールドの間のマッピングを指定します。

   使用する Adobe Campaign フィールドは、rawbox で指定されている必要があります。ここでは、受信者の性別に応じて異なるエクスペリエンスを定義します。

   ![](assets/tar_additional_decisionning_parameters.png)

1. Eメールをプレビューして、異なるプロファイルを選択する際に、挿入される画像が、Adobe TargetアクティビティとAdobe Campaignで指定されたパラメーターに応じて変わるかどうかを確認します。

これで、動的画像を含む配信を送信できます。 その結果はAdobe Targetで確認できます。

**関連トピック：**

* [Adobe Target Portal](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=ja)
* [電子メールコンテンツデザインについて](../../designing/using/designing-content-in-adobe-campaign.md)
* [リアルタイムビデオでの電子メール画像のパーソナ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) ライズ
