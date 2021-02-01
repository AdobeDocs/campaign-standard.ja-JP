---
solution: Campaign Standard
product: campaign
title: Campaign Standard データモデルの概要
description: カスタムフィールドとリソースを用いて Campaign Standard データモデルを強化し、REST API を拡大して拡張フィールドを公開します。
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 30%

---


# Campaign Standard データモデルの概要 {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">データモデル</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">カスタムリソース</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">APIの使用</a></p></td></tr>
</table>

独自のフィールドとリソースを使用して Campaign Standard データモデルを拡張し、あらゆるデータモデルの変更を単一ビューで監視します。

## データモデル {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

キャンペーンが使用するデータは、**事前定義データモデル**&#x200B;で定義された異なるリソースを介して定義されます。 データモデルには、一連のマーケティング関連リソースの標準搭載されたSQL構造が表示されます。配信、オーディエンス、ランディングページ、プロファイル等 各リソースには関連フィルターが付属し、各リソース間を移動できます。

**診断**&#x200B;メニューを使用すると、Campaign Standardが生成する技術的なオブジェクトをリストできます。データスキーマ、Webページ、フィルターなど。データモデルおよび変更を監視できます。

詳しくは、以下を参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [データモデルのベストプラクティス](../../developing/using/data-model-best-practices.md)
* [データモデルの説明](../../developing/using/datamodel-introduction.md)
* [データモデルの変更の監視](../../developing/using/monitoring-data-model-changes.md)

## カスタムリソース {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standardでは、**定義済みのデータモデル**&#x200B;を拡張して独自のリソースを作成（例えば、購入テーブルや製品テーブルの追加）したり、既存のリソースを新しいフィールドで拡張したりできます。 また、キャンペーン画面を設定して、作成された新しいリソースやフィールドを使用してナビゲーションを最適化することもできます。

また、Campaign StandardREST APIを&#x200B;**拡張して、カスタムリソースプロファイルのAPI拡張フィールドに公開することもできます。**&#x200B;これにより、例えば、請求システムから生成されたプロモーションコードで顧客のプロファイルを更新できます。

詳しくは、以下を参照してください。

* [リソースの追加または拡張](../../developing/using/key-steps-to-add-a-resource.md)
* [APIの拡張](../../developing/using/about-extending-the-api.md)
* [使用例：新しいフィールドを使用してプロファイルリソースを拡張する](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [使用例：アプリケーションリソースへの購読の拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## APIを使用する{#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Campaign StandardAPIを使用して、Adobe Campaign Standard向けの統合を作成し、使用するテクノロジーのパネルとキャンペーンを連携させて独自のエコシステムを構築します。 [Campaign Standard REST API の概要](../../api/using/get-started-apis.md)

## その他のリソース

* [Adobe Experience Platform Data Connector について](../../developing/using/aep-about-data-connector.md)
* [カスタムリソースのエクスポートとインポート](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
