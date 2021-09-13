---
title: データベースのエンリッチメント
description: データベースをエンリッチメントする様々な方法について説明します。
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 3%

---

# データベースのエンリッチメント{#enriching-the-database}

Campaign Standardは、マーケティングデータベースの拡張に役立つツールを提供します。 この節では、Campaignにデータを挿入するための様々な方法と、専用のドキュメントの参照について説明します。

## ワークフローを使用したデータのインポート {#importing-data-through-workflows}

ワークフローでは、[[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md)アクティビティを使用してデータを収集し、Campaignデータベースにインポートできます。

ワークフローを通じてデータをインポートする際の一般的な情報とベストプラクティスについては、[この節](../../automating/using/about-data-import-and-export.md)を参照してください。

さらに、データをインポートするためのテンプレートを設定することもできます。 同じ構造を持つファイルを定期的にインポートする必要がある場合は、インポートテンプレートを使用することをお勧めします。

次の2種類のテンプレートを設定できます。

* **ワークフローテンプレート**:これらは、必要に応じて一度設定し、データをインポートしてデータベースを更新するたびに再利用できる、事前設定済みのワークフローです。

   データをインポートするワークフローテンプレートの例について詳しくは、[この節](../../automating/using/creating-import-workflow-templates.md)を参照してください。

* **データテンプレートのインポート**:ワークフローテンプレートと同様に、これらはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されています。設定が完了すると、 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;メニューの下に簡略表示が表示され、ユーザーが使用できるようになります。

   データテンプレートのインポートについて詳しくは、[専用のドキュメント](../../automating/using/importing-data-with-import-templates.md)を参照してください。

## ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページとは、データを収集し、データベース内の既存の情報を作成または更新するために使用できるWebフォームです。

原則は次のとおりです。

* データ（名、姓、Eメールなど）を収集するための入力フィールドを追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* ランディングページを、Webサイト経由、またはメッセージへの直接リンクを通じてオンラインで使用できるようにします。

ランディングページについて詳しくは、[専用のドキュメント](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

## Microsoft Dynamics 365からのプロファイルの同期

Microsoft Dynamics 365とのCampaign Standard統合により、Microsoft Dynamics 365の連絡先データをCampaignデータベースに渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティングキャンペーンのターゲットに設定できます。

この統合について詳しくは、[専用のドキュメント](../../integrating/using/d365-acs-get-started.md)を参照してください。

>[!NOTE]
>
>Campaign Standard- Microsoft Dynamics 365コネクタは現在、使用が制限されています。このコネクタには、ドキュメントで詳しく説明されているいくつかの制限が適用されます。

## API呼び出しを使用したデータの読み込み

Campaign StandardAPIを使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。

APIの使用方法について詳しくは、[専用のドキュメント](../../api/using/get-started-apis.md)を参照してください。

>[!IMPORTANT]
>
>API呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。
