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
source-wordcount: '334'
ht-degree: 22%

---

# Campaign Standard データモデルの基本を学ぶ {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">データモデル</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">カスタムリソース</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">API の操作</a></p></td></tr>
</table>

フィールドとリソースをカスタマイズしてCampaign Standardデータモデルを拡張し、統合された 1 つのビューで、あらゆるデータモデルの変更をモニタリングします。

## データモデル {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Campaign で使用するデータは、（事前定義済みのデータモデル **で定義された様々なリソースを通じて定義され** す。 データモデルには、一連のマーケティング関連リソース（配信、オーディエンス、ランディングページ、プロファイルなど）に対する標準の SQL 構造が表示されます。 各リソースにはフィルターが関連付けられているので、リソース間を移動できます。

**診断** メニューを使用すると、Campaign Standardで生成された技術的なオブジェクト（データスキーマ、web ページ、フィルターなど）を一覧表示でき、データモデルと、データモデルに加えられた変更を監視できます。

詳しくは、以下を参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [データモデルのベストプラクティス](../../developing/using/data-model-best-practices.md)
* [データモデルの説明](../../developing/using/datamodel-introduction.md)
* [データモデルの変更の監視](../../developing/using/monitoring-data-model-changes.md)

## カスタムリソース {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standardを使用すると、**事前定義済みのデータモデルをエンリッチメント** して、独自のリソースを作成（購入テーブルや商品テーブルを追加するなど）、または新しいフィールドで既存のリソースを拡張できます。 また、Campaign Screens を設定して、作成された新しいリソースとフィールドのナビゲーションを最適化することもできます。

さらに、API でカスタムリソースプロファイルの拡張フィールドを公開するために、**Campaign Standard REST API を拡張** できます。 これにより、例えば、顧客のプロファイルを請求システムから生成されたプロモーションコードで更新できます。

詳しくは、以下を参照してください。

* [リソースの追加または拡張](../../developing/using/key-steps-to-add-a-resource.md)
* [API の拡張](../../developing/using/about-extending-the-api.md)
* [ユースケース：新しいフィールドを使用したプロファイルリソースの拡張](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [ユースケース：アプリケーションリソースに対する購読の拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## API の操作 {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Campaign StandardAPI を使用すると、Campaign に使用するテクノロジーのパネルを接続することで、Adobe Campaign Standardとの統合を作成し、独自のエコシステムを構築できます。 [Campaign Standard REST API の概要](../../api/using/get-started-apis.md)

## その他のリソース

* [ カスタムリソースの書き出し/読み込み ](https://helpx.adobe.com/jp/campaign/kb/acs-get-started-with-cusres.html)
* [Campaign から Adobe Experience Platform へのデータのエクスポート](../../integrating/using/export-campaign-data.md)
