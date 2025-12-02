---
title: Audience Destinations サービスについて
description: Audience Destinations サービスの詳細について説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---

# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations サービスは非推奨（廃止予定）になりました。 廃止される機能は引き続き使用できますが、それ以上の機能強化やサポートは行われません。 詳しくは [&#x200B; このページを参照してください &#x200B;](../../rn/using/deprecated-features.md)

[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) を活用して、大きく複雑なデータセットに基づいて高度にターゲット化されたオーディエンスを構築することで、コンシューマーエクスペリエンスを強化します。 Adobe Experience Platformは、Adobe Analyticsを含むオンラインおよびオフラインのソースをまたいでプロファイル、行動、マルチエンティティのデータを統合し、顧客の 360 度のビューを作成するのに役立ち、カスタマーエクスペリエンスを効果的に管理できます。

その後、Adobe Campaign Standardは **Audience Destinations** サービスを使用して、複数手順の、またはクロスチャネルキャンペーンプログラム用のプロファイルのコレクション **Audiences** をAdobe Experience Platformから取得します。

**オーディエンス** は、最初に **セグメント** を作成することによって作成されます。セグメントとは基本的に、Adobe Experience Platformのお客様のプロファイル内にあるほぼすべての変数（プロファイル、イベント、マルチエンティティデータなど）に基づく一連のルールであり、多次元のターゲットを作成します。 リアルタイム顧客プロファイルおよびセグメント化サービスのグローバルな概念については、次の専用ドキュメントで参照します。

* [&#x200B; リアルタイム顧客プロファイルの概要 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)
* [&#x200B; セグメント化サービスの概要 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

セグメントを作成したら、[Campaign Standard workflows](../../integrating/using/aep-targeting-audiences.md) で配信のオーディエンスとしてアクティブ化できます。 さらに、Adobe Experience Platformのコンテキストデータを使用して、キャンペーンに動的コンテンツを [&#x200B; パーソナライズ &#x200B;](../../integrating/using/aep-personalizing-campaigns.md) して追加できます。

![](assets/do-not-localize/how-to-video.png) のチュートリアルビデオは、[&#x200B; この節 &#x200B;](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html) でも参照できます。

この節で使用する用語：

* **プロファイル**：プロファイルは、コンシューマーの属性を定義するために使用されるExperience Platform標準データモデルです。 プロファイルは、イベントデータと、個人やデバイスに関連する属性の集計にすることもできます。

  例：「John Doe は 55 歳の男性です」

* **セグメント**：属性とイベントデータの両方を使用して、データベースからプロファイルのサブセットを定義する一連のルール。

  例：「50 歳以上の男性」

* **オーディエンス**：セグメントルールを満たすプロファイルのコレクションです。

  例：データベース内の 50 歳以上のすべての男性に対応するプロファイルのリスト。
