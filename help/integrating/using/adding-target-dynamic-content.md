---
title: ターゲットの動的コンテンツの追加
seo-title: ターゲットの動的コンテンツの追加
description: ターゲットの動的コンテンツの追加
seo-description: Adobe Campaign配信の1つにAdobe Target動的コンテンツを追加する方法を説明します。
page-status-flag: 未活性化の
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 積分
content-type: 参照
topic-tags: キャンペーンとターゲットでの作業
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# ターゲットの動的コンテンツの追加{#adding-target-dynamic-content}

Adobe Targetの統合により、ダイナミックイメージを配信に追加して、経験に応じてコンテンツをカスタマイズできます。

電子メールの編集中に、Adobe targetからダイナミックイメージを挿入し、受信者に応じて変更を加えることができます。

Adobe Campaignでイメージにアクセスする前に、まずAdobe Targetで次のタスクを実行する必要があります。

* 1つまたは複数のリダ [イレクト](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)·プランを作成し、使用するイメージのURLを指定する必要があります。
* 1人または複数の対象者 [を作成し](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html)、アクティビティのターゲットを定義します。
* フォームベー [スのエクスペリエンス作曲家アクティビティを作成します](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) 。このアクティビティでは、作成したリダイレクトプランの数に応じて、ボックスを選択し、複数のエクスペリエンスを指定する必要があります。 各エクスペリエンスに対して、作成したリダイレクトサービスの1つを選択する必要があります。
* Adobe Campaignの情報を使用して、経験を指定してセグメントを作成します。 オファーの選択ルールでAdobe Campaignのデータを使用するには、Adobe targetのボックスにデータを指定する必要があります。

1. 電子メール配信を作成します。
1. 電子メールまたはランディング·ページのコンテンツを編集する場合は、イメージ·ブロックに移動し、コンテキスト·メ **[!UICONTROL Dynamic image from Adobe Target]** ニューから選択します。

   ![](assets/tar_insert_dynamic_image.png)

1. 電子メールに既定で表示されるイメージを選択します。 イメージのURLを直接指定するか、アセットを使用して共有するイメージを選択 [できます](../../integrating/using/working-with-campaign-and-assets-core-service.md)。

   統合は静的イメージのみをサポートします。 残りのコンテンツはカスタマイズできません。

1. Adobe Targetで指定したレイアウトボックスの名前を入力します。
1. Adobe Targetの設定でEnterprise権限を使用する場合は、このフィールドに対応するプロパティを追加します。 このページのターゲットエンタープライズのアクセス許可の [詳細を表示しま](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html)す。 このフィールドはオプションで、TargetでEnterprise権限を使用しない場合は必須ではありません。
1. で、Adobe Target **[!UICONTROL Additional decision parameters]**&#x200B;セグメントで定義されたフィールドとAdobe Campaignフィールドの間のマッピングを指定します。

   使用するAdobe Campaignフィールドは、ボックスに指定されている必要があります。 ここでは、受取者の性別に応じて異なる経験を定義します。

   ![](assets/tar_additional_decisionning_parameters.png)

1. 別のプロファイルを選択する際に、Adobe TargetアクティビティとAdobe Campaignで指定したパラメータに応じて、挿入されたイメージが変更されるかどうかを確認するために、電子メールをプレビューします。

これで、ダイナミックイメージを含む配信を送信できます。 その結果はAdobe Targetにあります。

**関連トピック：**

* [Adobe Targetポータル](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [電子メールコンテンツデザインについて](../../designing/using/overview.md)
* [リアルタイムビデオでの電子メールイメージのパーソナライズ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) 。

