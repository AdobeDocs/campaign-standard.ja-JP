---
solution: Campaign Standard
product: campaign
title: データベースの強化
description: データベースを拡張する様々な方法について説明します。
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---


# データベースの強化{#enriching-the-database}

Campaign Standardオファーは、マーケティングデータベースの拡張に役立つツールをいくつかご紹介します。 この節では、専用のドキュメントを参照しながら、キャンペーンにデータを挿入するために使用できる様々な方法について説明します。

## ワークフロー{#importing-data-through-workflows}を介したデータのインポート

ワークフローを使用すると、データを収集し、[[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md)アクティビティを使用してキャンペーンデータベースにインポートできます。

ワークフローを介してデータをインポートする場合の一般的な情報とベストプラクティスについては、[このセクション](../../automating/using/about-data-import-and-export.md)を参照してください。

また、データを読み込むためのテンプレートを設定することもできます。 同じ構造を持つファイルを定期的に読み込む必要がある場合は、インポートテンプレートの使用をお勧めします。

次の2種類のテンプレートを設定できます。

* **ワークフローテンプレート**:これらは事前設定済みのワークフローで、必要に応じて一度設定すれば、データを読み込んでデータベースを更新するたびに再利用できます。

   データをインポートするワークフローテンプレートの例については、[このセクション](../../automating/using/creating-import-workflow-templates.md)を参照してください。

* **データテンプレートの読み込み**:ワークフローテンプレートと同様、テンプレートはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されます。設定が完了すると、**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;メニューの下のシンプルな表示でユーザーが使用できるようになります。

   データテンプレートの読み込みについて詳しくは、[専用ドキュメント](../../automating/using/importing-data-with-import-templates.md)を参照してください。

## ランディングページ{#collecting-data-from-landing-pages}からデータを収集中

ランディングページとは、データを収集し、データベース内の既存の情報を作成または更新するために使用できるWebフォームです。

原則は以下の通り。

* データを収集する入力フィールド（名、姓、電子メールなど）を追加して、ランディングページを作成および設計します。
* 各入力フィールドを、データベースの対応するフィールドにマップします。
* Webサイトまたはメッセージへの直接リンクを介して、ランディングページをオンラインで利用できるようにします。

ランディングページについて詳しくは、[専用ドキュメント](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

## Microsoft Dynamics 365からのプロファイルの同期

Microsoft Dynamics 365とのCampaign Standard統合により、Microsoft Dynamics 365の連絡先データをキャンペーンデータベースに渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティングキャンペーンでターゲットを設定できます。

この統合の詳細については、[専用ドキュメント](../../integrating/using/d365-acs-get-started.md)を参照してください。

>[!NOTE]
>
>Campaign Standard-Microsoft Dynamics 365 Connectorは現在限定可用性を備えており、ドキュメントに詳しく記載されているいくつかの制限事項に従うことに注意してください。

## API呼び出しを使用したデータの読み込み

Campaign StandardAPIを使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。

APIの使用方法について詳しくは、[専用ドキュメント](../../api/using/get-started-apis.md)を参照してください。

>[!IMPORTANT]
>
>API呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[こちらのページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。
