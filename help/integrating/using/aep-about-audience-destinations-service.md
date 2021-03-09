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
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 7%

---


# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

[Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html)を活用して、大規模で複雑なデータセットに基づいて、ターゲットを絞り込んだオーディエンスを構築することで、コンシューマーエクスペリエンスを強化します。 Adobe Experience Platformでは、Adobe Analyticsを含むオンラインおよびオフラインのソースにわたるプロファイル、行動、および複数のエンティティのデータが統合され、顧客の360度の表示を構築し、顧客体験を効果的に管理できます。

次に、Adobe Campaign Standardは、**オーディエンス宛先**&#x200B;サービスを使用して、Adobe Experience Platformから&#x200B;**オーディエンス**&#x200B;と呼ばれるプロファイルのコレクションを取得し、マルチステップおよび/またはチャネル間のキャンペーンプログラムを行います。

**オーディエンス** は、最初の作成 **セグメント**(Adobe Experience Platformから顧客プロファイル内の事実上すべての変数(プロファイル、イベント、マルチエンティティデータなど)に基づく一連のルール)によって作成され、多次元ターゲットが作成されます。リアルタイムの顧客プロファイルとセグメント化サービスに関するグローバルな概念は、次の専用ドキュメントで参照できます。

* [リアルタイム顧客プロファイルの概要](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Segmentation Serviceの概要](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

セグメントを作成したら、[Campaign Standardワークフロー](../../integrating/using/aep-targeting-audiences.md)で配信のオーディエンスとしてアクティブ化できます。 さらに、Adobe Experience Platformのコンテキストデータを[パーソナライズ](../../integrating/using/aep-personalizing-campaigns.md)に利用し、動的なコンテンツをキャンペーンに追加することもできます。

![](assets/do-not-localize/how-to-video.png) ハウツービデオは [この節でもご覧いただけます](https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html)。

これらの節で使用される用語：

* **プロファイル**:プロファイルは、Experience Platformの属性を定義するために使用される消費者標準データモデルです。また、プロファイルは、イベントデータおよび個人や機器に関連する属性の集計にもなる。

   例：「ジョン・ドウは55歳の男です」

* **セグメント**:属性とイベントデータの両方を使用して、データベースのプロファイルのサブセットを定義する一連のルール。

   例：「男性> 50歳」

* **オーディエンス**:セグメントルールを満たすプロファイルの集まり。

   例：データベース内の男性50歳を超えるすべての男性に対応するプロファイルのリスト。
