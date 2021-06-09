---
solution: Campaign Standard
product: campaign
title: Audience Destinations サービスについて
description: Audience Destinationsサービスの詳細を説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM統合
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 2%

---

# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html)を活用して、大規模で複雑なデータセットに基づいて、ターゲットを絞り込んだオーディエンスを構築することで、消費者エクスペリエンスを強化します。 Adobe Experience Platformは、Adobe Analyticsを含むオンラインおよびオフラインのソースにわたるプロファイル、行動および複数エンティティのデータを統合し、顧客の360度のビューを構築し、顧客体験を効果的に管理できます。

次に、Adobe Campaign Standardは、 **Audience Destinations**&#x200B;サービスを使用して、マルチステップおよびクロスチャネルのキャンペーンプログラム用に、Adobe Experience Platformから&#x200B;**Audiences**&#x200B;と呼ばれるプロファイルのコレクションを取得します。

**** オーディエンスは、最初にセグメントを作成することで作成されます ****。これは、基本的に、Adobe Experience Platformから顧客プロファイル内のほぼすべての変数（プロファイル、イベント、複数エンティティデータなど）に基づいて、多次元ターゲットを作成するルールです。リアルタイム顧客プロファイルとセグメント化サービスに関するグローバルな概念は、次の専用ドキュメントで参照されています。

* [リアルタイム顧客プロファイルの概要](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [セグメント化サービスの概要](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

セグメントを作成したら、[Campaign Standardワークフロー](../../integrating/using/aep-targeting-audiences.md)で配信のオーディエンスとしてアクティブ化できます。 さらに、Adobe Experience Platformのコンテキストデータを使用して[パーソナライズ](../../integrating/using/aep-personalizing-campaigns.md)し、キャンペーンに動的なコンテンツを追加することもできます。

![](assets/do-not-localize/how-to-video.png) ハウツービデオについては、この節でも [参照できます](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

以下の節で使用される用語：

* **プロファイル**:プロファイルは、Experience Platformの属性を定義するために使用される消費者標準データモデルです。プロファイルは、個人やデバイスに関連するイベントデータや属性の集計にすることもできます。

   例：「ジョン・ドアは55歳の男です」

* **セグメント**:属性とイベントデータの両方を使用して、データベースのプロファイルのサブセットを定義する一連のルール。

   例：「男の子は50歳以上」

* **オーディエンス**:セグメントルールを満たすプロファイルの集まり。

   例：データベース内のすべての男性が50歳を超えるに対応するプロファイルのリスト。
