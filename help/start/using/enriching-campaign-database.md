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
source-git-commit: 50991e9b376be5e706d2e8d8dcfa8c3677651281

---


# データベースの強化{#enriching-the-database}

Campaign Standardオファーは、マーケティングデータベースの拡張に役立つツールをいくつか備えています。 この節では、専用のドキュメントを参照し、キャンペーンにデータを挿入するために使用できる様々な方法について説明します。

## データの読み込みワークフロー {#importing-data-through-workflows}

ワークフローを使用すると、データを収集し、キャンペーンデータベースにインポートで [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) きます。

この節では、ワークフローを通じてデータを読み込む際の一般的な情報とベストプラクティス [を示しま](../../automating/using/importing-data.md)す。

また、データを読み込むためのテンプレートを設定することもできます。 インポートテンプレートの使用は、同じ構造のファイルを定期的に読み込む必要がある場合に最適です。

次の2種類のテンプレートを設定できます。

* **ワークフローテンプレート**:これらは、必要に応じて一度設定し、データを読み込んでデータベースを更新するたびに再利用できる事前設定ワークフローです。

   データをインポートするワークフローテンプレートの例をこの節で [詳しく説明しま](../../automating/using/importing-data.md#example--import-workflow-template)す。

* **データテンプレートの読み込み**:ワークフローテンプレートと同様に、これらはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されています。 設定が完了すると、ユーザーは/メニューの下のシンプルな表示を使用で **[!UICONTROL Profile & audiences]** きるようにな **[!UICONTROL Imports]** ります。

   データテンプレートの読み込みについて詳しくは、専用のドキュメントを参 [照してくださ](../../automating/using/importing-data-with-import-templates.md)い。

## データの収集ランディングページ {#collecting-data-from-landing-pages}

ランディングページとは、データを収集し、データベース内の既存の情報を作成または更新するために使用できるWebフォームです。

原則は以下の通り。

* データ（姓、名、電子メールなど）を収集する入力フィールドを追加して、ランディングページを作成し、デザインします。
* 各入力フィールドを、データベースの対応するフィールドにマップします。
* ランディングページをWebサイト経由で、またはメッセージへの直接リンク経由で、オンラインで使用できるようにします。

ランディングページの詳細については、専用のドキュメントを参 [照してくださ](../../channels/using/getting-started-with-landing-pages.md)い。

## Microsoft Dynamics 365からのプロファイルの同期

Microsoft Dynamics 365とのCampaign Standard統合により、Microsoft Dynamics 365の連絡先データをキャンペーンデータベースに渡すことができます。
これらの連絡先は、プロファイルリストに表示され、マーケティングキャンペーンでターゲット設定できます。

For more on this integration, refer to the [dedicated documentation](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!NOTE]
>
>Campaign Standard-Microsoft Dynamics 365コネクターは現在、利用可能な機能が限られており、ドキュメントに詳しく記載されているいくつかの制限を受ける場合があります。

## API呼び出しを使用したデータの読み込み

Campaign StandardAPIを使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。

For more on how to use the APIs, refer to the [dedicated documentation](../../api/using/about-campaign-standard-apis.md).

>[!CAUTION]
>
>API呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。
