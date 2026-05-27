---
title: データベースの充実
description: データベースを充実させるさまざまな方法について説明します。
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
TQID: https://experienceleague.adobe.com/LROFX17EE6zvJRbH4P--NjtiJLwanqeudAKzwnQj0BI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 455
ht-degree: 3%

---

# データベースの充実{#enriching-the-database}

Campaign Standardには、マーケティングデータベースを成長させるためのツールが複数あります。 この節では、Campaignにデータを挿入するために使用できるさまざまな方法について詳しく説明し、専用のドキュメントを参照します。

## ワークフローによるデータのインポート {#importing-data-through-workflows}

ワークフローを使用すると、[[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) アクティビティを使用してデータを収集し、Campaign データベースにインポートできます。

ワークフローを通じてデータを読み込む際の一般的な情報とベストプラクティスについては、[この節](../../automating/using/about-data-import-and-export.md)で説明します。

さらに、データをインポートするためのテンプレートを設定できます。 同じ構造のファイルを定期的に読み込む必要がある場合は、テンプレートの読み込みを使用することをお勧めします。

次の2種類のテンプレートを設定できます。

* **ワークフローテンプレート**：これらは事前に設定されたワークフローで、必要に応じて1回設定し、データをインポートしてデータベースを更新するたびに再利用できます。

  データを読み込むワークフローテンプレートの例については、[この節](../../automating/using/creating-import-workflow-templates.md)で詳しく説明しています。

* **データテンプレートの読み込み**: ワークフローテンプレートと同様に、これらはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されています。 設定が完了すると、**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** メニューの下に表示が簡略化されたユーザーが使用できるようになります。

  データテンプレートの読み込みについて詳しくは、[専用ドキュメント ](../../automating/using/importing-data-with-import-templates.md)を参照してください。

## ランディングページからのデータ収集 {#collecting-data-from-landing-pages}

ランディングページとは、データの収集と、データベース内の既存の情報の作成または更新に使用できるweb フォームです。

原則は次のとおりです。

* データ（名、姓、電子メールなど）を収集するための入力フィールドを追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* web サイトやメッセージへの直接リンクを通じて、ランディングページをオンラインで利用できるようにします。

ランディングページについて詳しくは、[専用ドキュメント ](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

## Microsoft Dynamics 365からのプロファイルの同期

Campaign StandardとMicrosoft Dynamics 365の連携により、Microsoft Dynamics 365からCampaign データベースに連絡先データを渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティング施策のターゲットにすることができます。

この統合について詳しくは、[専用ドキュメント ](../../integrating/using/d365-acs-get-started.md)を参照してください。

>[!NOTE]
>
>Campaign Standard-Microsoft Dynamics 365 コネクタは現在、制限付きで提供されており、ドキュメントで詳しく説明されているいくつかの制限が適用されます。

## API呼び出しを介したデータのインポート

Campaign Standard APIを使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。

APIの使用方法について詳しくは、[専用ドキュメント ](../../api/using/get-started-apis.md)を参照してください。

>[!IMPORTANT]
>
>API呼び出しを介したプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。
