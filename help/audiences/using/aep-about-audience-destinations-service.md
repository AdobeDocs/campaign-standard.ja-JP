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
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# Audience Destinationsサービスについて {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

Audience Destinationsサー **ビスを使用すると** 、大規模で複雑なデータセットに基づいてターゲットを絞ったオーディエンスを構築し、他のAdobe Experience cloudソリューションとほぼリアルタイムにこれらのセグメントを共有できます。

[Adobe Experience Platformは](https://www.adobe.io/apis/experienceplatform/home.html) 、プロファイル、行動、マルチエンティティのデータを統合して、顧客に関する360のビューを構築し、顧客体験を効果的に管理できるようにします。

Campaign Standardでは、Adobe Experience Platformを使用して、オーディエンスと呼ばれる一連のプロファイルを識別で **きます**。 セグメントは、Adobe Experience Platformから生成さ **れるプロファイル属性やイベントデータを含むルールである**、セグメントを作成することで作成されます。 Unified Profile &amp; Segmentation Servicesに関するグローバル概念は、これらの専用ドキュメントで [参照できます](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)。

オーディエンスが作成されると、 [Campaign Standardのワークフローで配信用にアクティブ化できます](../../automating/using/aep-targeting-audiences.md)。 また、必要に応じて、Adobe Experience Platformのコンテキストデータを使用して、動的なコ [ンテンツを](../../automating/using/aep-personalizing-campaigns.md) パーソナライズし、キャンペーンに追加することもできます。

デモビデオはこのページでもご [覧いただけます](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/leveraging-aep-audiences-overview.html)

以下の節で使用する用語：

* **プロファイル**:プロファイルは、コンシューマーの属性を定義するために使用されるエクスペリエンスプラットフォームの標準データモデルです。 また、プロファイルは、個人やデバイスに関連するイベントデータと属性の集合でも構いません。

   例：「ジョン・ドウは55歳の男です」

* **セグメント**:属性とイベントデータの両方を使用して、データベースからプロファイルのサブセットを定義する一連のルール。

   例：「男性50歳以上」

* **オーディエンス**:セグメントルールを満たすプロファイルの集まり。

   例：データベース内の50歳以上の男性に対応するプロファイルのリストです。
