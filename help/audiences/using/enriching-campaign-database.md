---
title: データベースの機能強化
description: データベースを充実させる様々な方法について説明します。
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 2%

---

# データベースの機能強化{#enriching-the-database}

Campaign Standardには、マーケティングデータベースの拡張に役立つツールがいくつか用意されています。 この節では、Campaign へのデータの挿入に使用できる様々な方法について、専用ドキュメントを参照しながら詳しく説明します。

## ワークフローでのデータの読み込み {#importing-data-through-workflows}

ワークフローでは、[[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) アクティビティを使用してデータを収集し、Campaign データベースに読み込むことができます。

ワークフローを通じてデータをインポートする際の一般的な情報とベストプラクティスについては、[ この節 ](../../automating/using/about-data-import-and-export.md) を参照してください。

さらに、データをインポートするためのテンプレートを設定できます。 同じ構造を持つファイルを定期的にインポートする必要がある場合は、インポートテンプレートの使用がベストプラクティスです。

次の 2 種類のテンプレートを設定できます。

* **ワークフローテンプレート**：必要に応じて一度設定し、データの読み込みとデータベースの更新を行うたびに再利用できる、事前設定済みのワークフローです。

  データをインポートするワークフローテンプレートの例について詳しくは、[ この節 ](../../automating/using/creating-import-workflow-templates.md) を参照してください。

* **データテンプレートの読み込み**：ワークフローテンプレートと同様に、これらはワークフローに基づくテンプレートであり、データベースを更新するためにファイルをアップロードするために設定されます。 設定が完了すると、**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** メニューの下の簡略化されたビューでユーザーが使用できるようになります。

  データインポートテンプレートについて詳しくは、[ 専用ドキュメント ](../../automating/using/importing-data-with-import-templates.md) を参照してください。

## ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページは、データの収集や、データベース内の既存の情報の作成または更新に使用できる web フォームです。

原則は次のとおりです。

* データを収集するための入力フィールド（名、姓、メールなど）を追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* Web サイトを介して、またはメッセージへの直接リンクを介して、ランディングページをオンラインで使用できるようにします。

ランディングページについて詳しくは、[ 専用ドキュメント ](../../channels/using/getting-started-with-landing-pages.md) を参照してください。

## Microsoft Dynamics 365 からのプロファイルの同期

Microsoft Dynamics 365 とのCampaign Standard統合により、Microsoft Dynamics 365 から Campaign データベースに連絡先データを渡すことができます。
これらの連絡先は、プロファイルリストに表示され、マーケティングキャンペーンでターゲットに設定できます。

この統合について詳しくは、[ 専用ドキュメント ](../../integrating/using/d365-acs-get-started.md) を参照してください。

>[!NOTE]
>
>Campaign Standard-Microsoft Dynamics 365 コネクタは現在限定提供であり、ドキュメントで詳しく説明されているように、いくつかの制限が適用されることに注意してください。

## API 呼び出しを使用したデータの読み込み

Campaign StandardAPI を使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。

API の使用方法について詳しくは、[ 専用ドキュメント ](../../api/using/get-started-apis.md) を参照してください。

>[!IMPORTANT]
>
>API 呼び出しを使用してプロファイルの一括作成または更新を実行する前に、ライセンス契約に対応するスケールの制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。
