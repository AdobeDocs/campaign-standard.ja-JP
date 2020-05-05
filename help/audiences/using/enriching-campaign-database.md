---
title: データベースの強化
description: データベースを拡張する様々な方法について説明します。
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d62c8cdac83789cfdffb7fd5e0d6c086e81300b1

---


# データベースの強化{#enriching-the-database}

Campaign Standardオファーは、マーケティングデータベースの拡張に役立つツールをいくつかご紹介します。 この節では、専用のドキュメントを参照しながら、キャンペーンにデータを挿入するために使用できる様々な方法について説明します。

## ワークフローを介したデータの読み込み {#importing-data-through-workflows}

ワークフローを使用すると、データを収集し、 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) アクティビティを使用してキャンペーンデータベースにインポートできます。

ワークフローを介してデータをインポートする場合の一般的な情報とベストプラクティスについては、 [この節で説明し](../../automating/using/importing-data.md)ます。

また、データを読み込むためのテンプレートを設定することもできます。 同じ構造を持つファイルを定期的に読み込む必要がある場合は、インポートテンプレートの使用をお勧めします。

次の2種類のテンプレートを設定できます。

* **ワークフローテンプレート**: これらは事前設定済みのワークフローで、必要に応じて一度設定すれば、データを読み込んでデータベースを更新するたびに再利用できます。

   データを読み込むためのワークフローテンプレートの例について [この節で詳しく説明します](../../automating/using/importing-data.md#example--import-workflow-template)。

* **データテンプレートの読み込み**: ワークフローテンプレートと同様、テンプレートはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されます。 設定が完了すると、 **[!UICONTROL Profile & audiences]** /メニューのシンプルな表示を使用してユーザーが使用できるようになり **[!UICONTROL Imports]** ます。

   データテンプレートの読み込みについて詳しくは、 [専用のドキュメントを参照してください](../../automating/using/importing-data-with-import-templates.md)。

## ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページとは、データを収集し、データベース内の既存の情報を作成または更新するために使用できるWebフォームです。

原則は以下の通り。

* データを収集する入力フィールド（名、姓、電子メールなど）を追加して、ランディングページを作成および設計します。
* 各入力フィールドを、データベースの対応するフィールドにマップします。
* Webサイトまたはメッセージへの直接リンクを介して、ランディングページをオンラインで利用できるようにします。

ランディングページについて詳しくは、 [専用ドキュメントを参照してください](../../channels/using/getting-started-with-landing-pages.md)。

## Microsoft Dynamics 365からのプロファイルの同期

Microsoft Dynamics 365とのCampaign Standard統合により、Microsoft Dynamics 365の連絡先データをキャンペーンデータベースに渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティングキャンペーンでターゲットを設定できます。

For more on this integration, refer to the [dedicated documentation](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!NOTE]
>
>Campaign Standard-Microsoft Dynamics 365 Connectorは現在限定可用性を備えており、ドキュメントに詳しく記載されているいくつかの制限事項に従うことに注意してください。

## API呼び出しを使用したデータの読み込み

Campaign StandardAPIを使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。

For more on how to use the APIs, refer to the [dedicated documentation](../../api/using/about-campaign-standard-apis.md).

>[!CAUTION]
>
>API呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。
