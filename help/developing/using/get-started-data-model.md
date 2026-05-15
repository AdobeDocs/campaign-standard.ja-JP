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
TQID: https://experienceleague.adobe.com/LHlfIZ24iApQfr6dL-x-nQViltSetibBgt1slLDsRi4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 348
ht-degree: 24%

---

# Campaign Standard データモデルの基本を学ぶ {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">データモデル</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">カスタムリソース</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">APIの操作</a></p></td></tr>
</table>

独自のフィールドとリソースを使用してCampaign Standard data modelを拡張し、あらゆるデータモデルの変更を単一のビューでモニタリングします。

## データモデル {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Campaignで使用されるデータは、**事前定義済みデータモデル**&#x200B;で定義された様々なリソースを通じて定義されます。 データモデルには、配信、オーディエンス、ランディングページ、プロファイルなど、マーケティングに関連する一連のリソースの、すぐに使用できるSQL構造が表示されます。各リソースには関連するフィルターが用意されており、リソースを移動できます。

「**診断**」メニューでは、Campaign Standardで生成されたテクニカルオブジェクト（データスキーマ、web ページ、フィルターなど）を一覧表示して、データモデルとその変更をモニターできます。

詳しくは、以下を参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [データモデルのベストプラクティス](../../developing/using/data-model-best-practices.md)
* [データモデルの説明](../../developing/using/datamodel-introduction.md)
* [データモデルの変更の監視](../../developing/using/monitoring-data-model-changes.md)

## カスタムリソース {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standardでは、定義済みデータモデル **をエンリッチメントして、独自のリソースを作成したり（購入テーブルや商品テーブルの追加など）、既存のリソースを新しいフィールドで拡張したりできます。**&#x200B;また、キャンペーン画面を設定して、作成された新しいリソースとフィールドのナビゲーションを最適化することもできます。

さらに、カスタムリソースプロファイルのAPI拡張フィールドで公開するために、**Campaign Standard REST APIを拡張**&#x200B;できます。 これにより、例えば、請求システムから生成されたプロモーションコードを使用して、顧客プロファイルを更新できます。

詳しくは、以下を参照してください。

* [リソースの追加または拡張](../../developing/using/key-steps-to-add-a-resource.md)
* [APIの拡張](../../developing/using/about-extending-the-api.md)
* [ユースケース：新しいフィールドを使用したプロファイルリソースの拡張](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [ユースケース：アプリケーションリソースへのサブスクリプションの拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## APIの操作 {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Campaign Standard APIを使用すれば、Adobe Campaign Standard向けの統合を構築し、使用するテクノロジーパネルにAdobe Campaignをインターフェイスして独自のエコシステムを構築できます。 [Campaign Standard REST API の概要](../../api/using/get-started-apis.md)

## その他のリソース

* [カスタムリソースのエクスポートとインポート](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Campaign から Adobe Experience Platform へのデータのエクスポート](../../integrating/using/export-campaign-data.md)
