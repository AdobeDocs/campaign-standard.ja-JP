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
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---

# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations サービスは非推奨（廃止予定）となりました。 非推奨（廃止予定）の機能は引き続き使用できますが、それ以上の機能強化やサポートはおこなわれません。 詳細情報 [このページの](../../rn/using/deprecated-features.md)

次の機能を活用して、消費者エクスペリエンスを強化 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) 大規模で複雑なデータセットに基づいて、ターゲットを絞り込んだオーディエンスを構築する。 Adobe Experience Platformは、Adobe Analyticsを含むオンラインおよびオフラインのソースにわたるプロファイル、行動および複数エンティティのデータを統合し、顧客の 360 度のビューを構築し、顧客体験を効果的に管理できます。

Adobe Campaign Standardが **オーディエンスの宛先** プロファイルのコレクションを取得するサービス ( **オーディエンス** Adobe Experience Platformから。複数手順のキャンペーンプログラムやクロスチャネルのキャンペーンプログラムに使用します。

**オーディエンス** 最初のビルで作成 **セグメント**：基本的に、Adobe Experience Platformから顧客プロファイル内のほぼすべての変数（プロファイル、イベント、マルチエンティティデータなど）に基づいて、多次元ターゲットを作成する一連のルールです。 リアルタイム顧客プロファイルとセグメント化サービスに関するグローバルな概念は、次の専用ドキュメントで参照されています。

* [リアルタイム顧客プロファイルの概要](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)
* [セグメント化サービスの概要](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

セグメントを作成したら、そのセグメントを、 [Campaign Standardワークフロー](../../integrating/using/aep-targeting-audiences.md). さらに、Adobe Experience Platformからのコンテキストデータを [パーソナライズ](../../integrating/using/aep-personalizing-campaigns.md) キャンペーンに動的コンテンツを追加します。

![](assets/do-not-localize/how-to-video.png) ハウツービデオは、 [この節](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

これらの節で使用される用語：

* **プロファイル**：プロファイルは、Experience Platformの属性を定義するために使用される消費者標準データモデルです。 プロファイルは、個人やデバイスに関連するイベントデータや属性の集計にすることもできます。

  例：「John Doe は 55 歳の男性です。」

* **セグメント**：属性とイベントデータの両方を使用して、データベースのプロファイルのサブセットを定義する一連のルール。

  例：「男性 > 50 歳」

* **対象ユーザ**：セグメントルールを満たすプロファイルの集まりです。

  例：データベース内のすべての男性が 50 歳を超えるに対応するプロファイルのリスト。
