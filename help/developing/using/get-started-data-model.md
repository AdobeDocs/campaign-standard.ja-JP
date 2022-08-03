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
source-wordcount: '0'
ht-degree: 0%

---

# Campaign Standard データモデルの基本を学ぶ {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">データモデル</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">カスタムリソース</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">API の操作</a></p></td></tr>
</table>

フィールドとリソースをカスタマイズして Campaign Standard データモデルを拡張し、統合された 1 つのビューで、あらゆるデータモデルの変更を監視します。

## データモデル {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Campaign で使用されるデータは、 **事前定義済みデータモデル**. データモデルには、一連のマーケティング関連リソースの標準の SQL 構造が表示されます。配信、オーディエンス、ランディングページ、プロファイルなど 各リソースには関連フィルターが付属しており、リソース間を移動できます。

この **診断** メニューを使用すると、Campaign Standardで生成されたテクニカルオブジェクトのリストを表示できます。データスキーマ、web ページ、フィルターなど。データモデルと、それに加えられた変更を監視できます。

詳しくは、以下を参照してください。

* [データモデルの概念](../../developing/using/data-model-concepts.md)
* [データモデルのベストプラクティス](../../developing/using/data-model-best-practices.md)
* [データモデルの説明](../../developing/using/datamodel-introduction.md)
* [データモデルの変更の監視](../../developing/using/monitoring-data-model-changes.md)

## カスタムリソース {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standardでは、次のことが可能です。 **事前定義済みデータモデルのエンリッチメント** ：独自のリソース（例えば、Purchase テーブルや Product テーブルの追加）を作成したり、新しいフィールドを使用して既存のリソースを拡張したりする場合。 また、作成した新しいリソースやフィールドを使用してナビゲーションを最適化するよう、Campaign 画面を設定することもできます。

また、 **Campaign StandardREST API の拡張** を追加しました。 これにより、例えば、請求システムから生成されたプロモーションコードで顧客のプロファイルを更新できます。

詳しくは、以下を参照してください。

* [リソースの追加または拡張](../../developing/using/key-steps-to-add-a-resource.md)
* [API の拡張](../../developing/using/about-extending-the-api.md)
* [使用例：新しいフィールドを使用したプロファイルリソースの拡張](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [使用例：アプリケーションリソースへのサブスクリプションの拡張](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## API の操作 {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Campaign StandardAPI を使用すると、Adobe Campaign Standardの統合を作成し、Campaign と使用するテクノロジーのパネルを連携させて独自のエコシステムを構築できます。 [Campaign Standard REST API の概要](../../api/using/get-started-apis.md)

## その他のリソース

* [カスタムリソースのエクスポートとインポート](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Campaign から Adobe Experience Platform へのデータのエクスポート](../../integrating/using/export-campaign-data.md)
