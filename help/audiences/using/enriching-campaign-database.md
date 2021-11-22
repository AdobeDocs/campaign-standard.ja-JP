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

Campaign Standardには、マーケティングデータベースを拡張するのに役立つツールがいくつか用意されています。 この節では、Campaign にデータを挿入するための様々な方法と、専用ドキュメントへの参照について詳しく説明します。

## ワークフローを使用したデータのインポート {#importing-data-through-workflows}

ワークフローを使用すると、データを収集し、 [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) アクティビティ。

ワークフローを通じてデータをインポートする際の一般的な情報とベストプラクティスについては、 [この節](../../automating/using/about-data-import-and-export.md).

さらに、データをインポートするテンプレートを設定できます。 同じ構造を持つファイルを定期的にインポートする必要がある場合は、インポートテンプレートを使用することをお勧めします。

次の 2 種類のテンプレートを設定できます。

* **ワークフローテンプレート**:これらは、必要に応じて一度設定できる事前設定済みのワークフローで、データのインポートとデータベースの更新をおこなうたびに再利用します。

   データをインポートするワークフローテンプレートの例について詳しくは、 [この節](../../automating/using/creating-import-workflow-templates.md).

* **データテンプレートのインポート**:ワークフローテンプレートと同様に、ワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されています。 設定が完了すると、ユーザーは、 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** メニュー

   データテンプレートのインポートについて詳しくは、 [専用ドキュメント](../../automating/using/importing-data-with-import-templates.md).

## ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページは、データを収集し、データベース内の既存の情報を作成または更新するために使用できる Web フォームです。

原則は次のとおりです。

* データ（名、姓、E メールなど）を収集するための入力フィールドを追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* Web サイト経由、またはメッセージへの直接リンクを通じて、ランディングページをオンラインで使用できるようにします。

ランディングページについて詳しくは、 [専用ドキュメント](../../channels/using/getting-started-with-landing-pages.md).

## Microsoft Dynamics 365 からのプロファイルの同期

Microsoft Dynamics 365 とのCampaign Standard統合により、Microsoft Dynamics 365 の連絡先データを Campaign データベースに渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティングキャンペーンのターゲットに設定できます。

この統合について詳しくは、 [専用ドキュメント](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Campaign Standard- Microsoft Dynamics 365 コネクタは現在、使用が制限されています。また、ドキュメントに詳しく記載されているいくつかの制限が適用されます。

## API 呼び出しを使用したデータの読み込み

Campaign StandardAPI を使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。

API の使用方法について詳しくは、 [専用ドキュメント](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>API 呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。
