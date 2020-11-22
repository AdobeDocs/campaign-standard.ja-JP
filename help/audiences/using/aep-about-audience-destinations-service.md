---
solution: Campaign Standard
product: campaign
title: Audience Destinations サービスについて
description: オーディエンスの宛先サービスについての詳細。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 7%

---


# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

大規模で複雑なデータセットに基づいて高度にターゲットを絞ったオーディエンスを構築する [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) を活用することで、顧客体験を強化できます。 Adobe Experience Platformでは、Adobe Analyticsを含むオンラインおよびオフラインのソースにわたるプロファイル、行動、および複数のエンティティのデータが統合され、顧客の360度の表示を構築し、顧客体験を効果的に管理できます。

次に、Adobe Campaign Standardは、 **オーディエンス宛先** サービスを使用して、複数手順のキャンペーンプログラムやクロスチャネル用の、Adobe Experience Platformからプロファイル( **オーディエンス**)のコレクションを取得します。

**オーディエンス** は、最初に ****&#x200B;セグメントを作成することで作成されます。これは、Adobe Experience Platformから顧客プロファイル内の事実上すべての変数(プロファイル、イベント、マルチエンティティデータなど)に基づく一連のルールで、多次元ターゲットを作成します。 リアルタイムの顧客プロファイルとセグメント化サービスに関するグローバルな概念は、次の専用ドキュメントで参照できます。

* [リアルタイム顧客プロファイルの概要](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)
* [Segmentation Serviceの概要](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

セグメントを作成したら、そのセグメントを [Campaign Standardワークフローで配信のオーディエンスとしてアクティブ化できます](../../automating/using/aep-targeting-audiences.md)。 さらに、Adobe Experience Platformのコンテキストデータを使用して [個人設定を行い](../../automating/using/aep-personalizing-campaigns.md) 、動的なコンテンツをキャンペーンに追加することもできます。

ハウツービデオは [この節でもご覧いただけます](https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html)。

これらの節で使用される用語：

* **プロファイル**:プロファイルは、Experience Platformの属性を定義するために使用される消費者標準データモデルです。 また、プロファイルは、イベントデータおよび個人や機器に関連する属性の集計にもなる。

   例：「ジョン・ドウは55歳の男です」

* **セグメント**:属性とイベントデータの両方を使用して、データベースのプロファイルのサブセットを定義する一連のルール。

   例：「男性> 50歳」

* **オーディエンス**:セグメントルールを満たすプロファイルの集まり。

   例：データベース内の男性50歳を超えるすべての男性に対応するプロファイルのリスト。
