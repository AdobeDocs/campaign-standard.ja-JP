---
title: Audience Destinationsサービスについて
description: Audience Destinationsサービスについて詳しく説明します。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e9d4239182a7ebdec61e85fece6ec49dca8f665a

---


# Audience Destinationsサービスについて {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

Adobe Experience Platform [](https://www.adobe.io/apis/experienceplatform/home.html) (AEP)を活用して、大規模で複雑なデータセットに基づいて、ターゲットを絞ったオーディエンスを構築することで、ユーザーエクスペリエンスを強化します。 Adobe Experience Platformは、Adobe Analyticsを含むオンラインおよびオフラインのソースにわたるプロファイル、行動およびマルチエンティティのデータを統合し、顧客の360ビューを構築して、顧客体験を効果的に管理できるようにします。

その後、Adobe Campaign Standardは **Audience Destinations** サービスを使用して、複数手順のキャンペーンプログラムやクロスチャネルキャンペーンプログラムの **Audiences**（オーディエンス）と呼ばれるプロファイルのコレクションをAEPから取得します。

**オーディエンス******&#x200B;は、AEPから顧客プロファイル内の事実上すべての変数（プロファイル、イベント、マルチエンティティデータなど）に基づいた一連のルールである、最初にセグメントを作成して、多次元ターゲットを作成します。 Unified Profile &amp; Segmentation Servicesに関するグローバル概念は、これらの専用ドキュメントで [参照できます](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)。

セグメントが作成されると、 [Campaign Standardワークフローで配信のオーディエンスとしてアクティブ化できます](../../automating/using/aep-targeting-audiences.md)。 また、必要に応じて、Adobe Experience Platformのコンテキストデータを使用して、動的なコ [ンテンツを](../../automating/using/aep-personalizing-campaigns.md) パーソナライズし、キャンペーンに追加することもできます。

デモビデオはこの節でもご [覧いただけます](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

以下の節で使用する用語：

* **プロファイル**:プロファイルは、コンシューマーの属性を定義するために使用されるエクスペリエンスプラットフォームの標準データモデルです。 また、プロファイルは、個人やデバイスに関連するイベントデータと属性の集合でも構いません。

   例：「ジョン・ドウは55歳の男です」

* **セグメント**:属性とイベントデータの両方を使用して、データベースからプロファイルのサブセットを定義する一連のルール。

   例：「男性50歳以上」

* **オーディエンス**:セグメントルールを満たすプロファイルの集まり。

   例：データベース内の50歳以上の男性に対応するプロファイルのリストです。
