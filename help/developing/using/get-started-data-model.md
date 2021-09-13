---
title: Campaign Standard データモデルの基本を学ぶ
description: カスタムフィールドとリソースを用いて Campaign Standard データモデルを強化し、REST API を拡大して拡張フィールドを公開します。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 31%

---

# Campaign Standard データモデルの基本を学ぶ {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">データモデル</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">カスタムリソース</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">APIの操作</a></p></td></tr>
</table>

フィールドとリソースをカスタマイズして Campaign Standard データモデルを拡張し、統合された 1 つのビューで、あらゆるデータモデルの変更を監視します。

## データモデル {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Campaignで使用されるデータは、**事前定義データモデル**&#x200B;で定義されている様々なリソースを通じて定義されます。 データモデルには、一連のマーケティング関連リソースの標準のSQL構造が表示されます。配信、オーディエンス、ランディングページ、プロファイルなど 各リソースには、リソース間を移動できるフィルターが関連付けられています。

**診断**&#x200B;メニューを使用すると、Campaign Standardによって生成されるテクニカルオブジェクトをリストできます。データスキーマ、webページ、フィルターなど。データモデルと、それに対する変更を監視できます。

詳しくは、以下を参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [データモデルのベストプラクティス](../../developing/using/data-model-best-practices.md)
* [データモデルの説明](../../developing/using/datamodel-introduction.md)
* [データモデルの変更の監視](../../developing/using/monitoring-data-model-changes.md)

## カスタムリソース {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standardでは、事前定義済みのデータモデル&#x200B;**をエンリッチメントして、独自のリソースを作成（例えば、PurchaseやProductテーブルの追加）したり、新しいフィールドを使用して既存のリソースを拡張したりできます。**&#x200B;また、作成した新しいリソースやフィールドを使用してナビゲーションを最適化するように、キャンペーン画面を設定することもできます。

さらに、Campaign StandardREST API **を拡張して、カスタムリソースプロファイルのAPI拡張フィールドに公開することもできます。**&#x200B;これにより、例えば、請求システムから生成されたプロモーションコードを使用して顧客のプロファイルを更新できます。

詳しくは、以下を参照してください。

* [リソースの追加または拡張](../../developing/using/key-steps-to-add-a-resource.md)
* [APIの拡張](../../developing/using/about-extending-the-api.md)
* [使用例：新しいフィールドを使用したプロファイルリソースの拡張](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [使用例：アプリケーションリソースへのサブスクリプションの拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## APIの操作 {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Campaign StandardAPIを使用して、Adobe Campaign Standardの統合を作成し、Campaignと使用するテクノロジーのパネルを連携させて独自のエコシステムを構築します。 [Campaign Standard REST API の概要](../../api/using/get-started-apis.md)

## その他のリソース

* [カスタムリソースのエクスポートとインポート](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Campaign から Adobe Experience Platform へのデータのエクスポート](../../integrating/using/export-campaign-data.md)
