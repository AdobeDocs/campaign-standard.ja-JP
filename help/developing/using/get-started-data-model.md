---
title: Campaign Standard データモデルの概要
description: Campaign Standardデータモデルをカスタムフィールドとリソースと共に拡張し、REST APIを拡張して拡張フィールドを公開します。
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4ae70ca95cb282a694c41361d859b19385db5673
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 16%

---


# Campaign Standard データモデルの概要 {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">データモデル</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">カスタムリソース</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">APIの使用</a></p></td></tr>
</table>

独自のフィールドとリソースを使用してCampaign Standardデータモデルを拡張し、すべてのデータモデルの変更を1つの表示に監視します。

## データモデル {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

キャンペーンが使用するデータは、 **事前定義されたデータモデルで定義された異なるリソースを通じて定義され**&#x200B;ます。 データモデルには、一連のマーケティング関連リソースの標準搭載されたSQL構造が表示されます。配信、オーディエンス、ランディングページ、プロファイル等 各リソースには関連するフィルターが付属し、各リソース間を移動できます。

[ **診断** ]メニューを使用すると、Campaign Standardによって生成される技術的なオブジェクトをリストできます。データスキーマ、Webページ、フィルターなど。データモデルおよび変更を監視できます。

詳しくは、以下を参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [データモデルのベストプラクティス](../../developing/using/data-model-best-practices.md)
* [データモデルの説明](../../developing/using/datamodel-introduction.md)
* [データモデルの変更の監視](../../developing/using/monitoring-data-model-changes.md)

## カスタムリソース {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standardを使用すると、事前定義されたデータモデルを **** 拡張して、独自のリソースを作成（購入テーブルや製品テーブルの追加など）したり、既存のリソースを新しいフィールドで拡張したりできます。 また、キャンペーン画面を設定して、作成された新しいリソースやフィールドを使用してナビゲーションを最適化することもできます。

また、Campaign StandardREST APIを **拡張して** 、カスタムリソースプロファイルのAPI拡張フィールドに公開できます。 これにより、例えば、請求システムから生成されたプロモーションコードで顧客のプロファイルを更新できます。

詳しくは、以下を参照してください。

* [リソースの追加または拡張](../../developing/using/key-steps-to-add-a-resource.md)
* [APIの拡張](../../developing/using/about-extending-the-api.md)
* [使用例：新しいフィールドを使用してプロファイルリソースを拡張する](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [使用例：アプリケーションリソースへの購読の拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## APIの使用 {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Campaign StandardAPIを使用して、Adobe Campaign Standard向けの統合を作成し、使用するテクノロジーのパネルとキャンペーンを連携させて独自のエコシステムを構築します。 [Campaign StandardREST APIの概要](../../api/using/get-started-apis.md)

## その他のリソース

* [Adobe Experience Platform Data Connector について](../../developing/using/aep-about-data-connector.md)
* [カスタムリソースの作成（ビデオ）](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [カスタムリソースのエクスポートとインポート](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
