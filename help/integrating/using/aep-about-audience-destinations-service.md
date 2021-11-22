---
title: Audience Destinations サービスについて
description: Audience Destinations サービスの詳細を説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations サービスは現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

顧客体験を活用する [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) 大規模で複雑なデータセットに基づいて、ターゲットを絞り込んだオーディエンスを構築する。 Adobe Experience Platformは、Adobe Analyticsを含むオンラインおよびオフラインのソースにわたるプロファイル、行動および複数エンティティのデータを統合し、顧客の 360 度のビューを構築し、顧客体験を効果的に管理できます。

Adobe Campaign Standardが **オーディエンスの宛先** プロファイルのコレクションを取得するサービス ( **オーディエンス** Adobe Experience Platformから。複数手順のキャンペーンプログラムやクロスチャネルのキャンペーンプログラムに使用します。

**オーディエンス** 最初のビルで作成 **セグメント**：基本的に、Adobe Experience Platformから顧客プロファイル内のほぼすべての変数（プロファイル、イベント、マルチエンティティデータなど）に基づいて、多次元ターゲットを作成する一連のルールです。 リアルタイム顧客プロファイルとセグメント化サービスに関するグローバルな概念は、次の専用ドキュメントで参照されています。

* [リアルタイム顧客プロファイルの概要](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [セグメント化サービスの概要](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

セグメントを作成したら、 [Campaign Standardワークフロー](../../integrating/using/aep-targeting-audiences.md). さらに、Adobe Experience Platformからのコンテキストデータを [パーソナライズ](../../integrating/using/aep-personalizing-campaigns.md) キャンペーンに動的コンテンツを追加します。

![](assets/do-not-localize/how-to-video.png) ハウツービデオは、 [この節](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

これらの節で使用される用語：

* **プロファイル**:プロファイルは、Experience Platformの属性を定義するために使用される消費者標準データモデルです。 プロファイルは、個人やデバイスに関連するイベントデータや属性の集計にすることもできます。

   例：「ジョン・ドアは 55 歳の男性です」

* **セグメント**:属性とイベントデータの両方を使用して、データベースのプロファイルのサブセットを定義する一連のルール。

   例：「男の子は 50 歳以上」

* **対象ユーザ**:セグメントルールを満たすプロファイルの集まり。

   例：データベース内のすべての男性が 50 歳を超えるに対応するプロファイルのリスト。
