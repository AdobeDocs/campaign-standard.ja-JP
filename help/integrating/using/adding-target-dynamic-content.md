---
title: Target の動的コンテンツの追加
description: Adobe Campaign配信の 1 つにAdobe Targetの動的コンテンツを追加する方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 7dfbd89f-877e-4598-bfe3-d743bb31ae9e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 31%

---

# Target の動的コンテンツの追加{#adding-target-dynamic-content}

Adobe Target統合を使用すると、動的な画像を配信に追加して、エクスペリエンスに応じてコンテンツをパーソナライズできます。

メールの編集時に、Adobe Targetから動的画像を挿入できます。この画像は受信者に応じて変わります。

Adobe Campaignで画像にアクセスする前に、まずAdobe Targetで次のタスクを実行する必要があります。

* 使用する画像の URL を指定する必要がある、1 つまたは複数の [&#x200B; リダイレクトオファー &#x200B;](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=ja) を作成します。
* 1 つ以上の[オーディエンス](https://experienceleague.adobe.com/docs/target/using/audiences/create-audiences/audiences.html)を作成します。アクティビティのターゲットをそこで定義します。
* [&#x200B; フォームベースの Experience Composer](https://experienceleague.adobe.com/docs/target/using/experiences/form-experience-composer.html) アクティビティを作成し、作成するリダイレクトオファーの数に応じて、rawbox を選択して複数のエクスペリエンスを指定する必要があります。 エクスペリエンスごとに、作成されたリダイレクトオファーの 1 つを選択する必要があります。
* Adobe Campaignの情報を使用してセグメントを作成し、エクスペリエンスを指定します。 オファーの選択ルールで Adobe Campaign からのデータを使用するには、Adobe Target のローボックスでデータを指定する必要があります。

1. メール配信を作成します。
1. メールまたはランディングページのコンテンツを編集する際は、画像ブロックに移動し、コンテキストメニューから「**[!UICONTROL Dynamic image from Adobe Target]**」を選択します。

   ![](assets/tar_insert_dynamic_image.png)

1. メールにデフォルトで表示される画像を選択します。 画像の URL を直接指定するか、[Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md) で共有される画像を選択することができます。

   この統合では、静的画像のみをサポートします。残りのコンテンツはカスタマイズできません。

1. Adobe Target で指定したローボックス名を入力します。
1. Adobe Target の設定で Enterprise 権限を使用している場合は、対応するプロパティをこのフィールドに追加します。Target の Enterprise 権限について詳しくは、[このページ](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=ja)を参照してください。このフィールドはオプションであり、Target で Enterprise 権限を使用しない場合は必要ありません。
1. **[!UICONTROL Additional decision parameters]** では、Adobe Target セグメントで定義されたフィールドとAdobe Campaignのフィールドとのマッピングを指定します。

   使用する Adobe Campaign フィールドは、rawbox で指定されている必要があります。この例では、受信者の性別に応じて異なるエクスペリエンスを定義します。

   ![](assets/tar_additional_decisionning_parameters.png)

1. メールをプレビューして、異なるプロファイルを選択した場合、挿入された画像がAdobe Target アクティビティとAdobe Campaignで指定されたパラメーターに応じて変化するかどうかを確認します。

これで、動的画像を含む配信を送信できます。 結果は、Adobe Targetで確認できます。

**関連トピック：**

* [Adobe Target ポータル &#x200B;](https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=ja)
* [メールコンテンツデザインについて](../../designing/using/designing-content-in-adobe-campaign.md)
* [&#x200B; リアルタイムでのメール画像のパーソナライズ &#x200B;](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) ビデオ
