---
title: Audience Destinations サービスについて
description: Audience Destinations サービスについて詳しく説明します。
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
source-git-commit: 7ad12890a24b2c0b8730d09b7d161bff511f4c69
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 3%

---

# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations サービスは非推奨になりました。 非推奨（廃止予定）の機能は引き続き利用できますが、それ以上強化したり、サポートしたりすることはありません。 詳細[このページ内](../../rn/using/deprecated-features.md)

[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html)を活用して、大規模で複雑なデータセットに基づいて、ターゲットを絞ったオーディエンスを構築することで、顧客体験を強化します。 Adobe Experience Platformは、Adobe Analyticsを含むオンラインとオフラインのソースをまたいでプロファイル、行動、マルチエンティティデータを統合し、顧客の全体像を構築するのに役立ちます。これにより、顧客体験を効果的に管理できます。

その後、Adobe Campaign Standardは&#x200B;**Audience Destinations** サービスを使用して、マルチステップおよび/またはクロスチャネルキャンペーンプログラム用に&#x200B;**Audiences**&#x200B;と呼ばれるプロファイルのコレクションをAdobe Experience Platformから取得します。

**オーディエンス**&#x200B;は、最初に&#x200B;**セグメント**&#x200B;を構築することによって作成されます。これは、基本的に、Adobe Experience Platformから顧客プロファイル内の事実上あらゆる変数（プロファイル、イベント、マルチエンティティティデータなど）に基づく一連のルールであり、多次元ターゲットを作成します。 リアルタイム顧客プロファイルとセグメンテーションサービスに関するグローバルな概念については、次の専用ドキュメントで紹介しています。

* [ リアルタイム顧客プロファイルの概要](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)
* [ セグメント化サービスの概要](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

セグメントを作成したら、[Campaign Standard ワークフロー](../../integrating/using/aep-targeting-audiences.md)で配信のオーディエンスとしてアクティブ化できます。 さらに、Adobe Experience Platformのコンテキストデータを使用して[ パーソナライズ ](../../integrating/using/aep-personalizing-campaigns.md)し、キャンペーンに動的コンテンツを追加できます。

![](assets/do-not-localize/how-to-video.png)のハウツー動画は[このセクション ](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)でも利用できます。

これらのセクションで使用される用語：

* **プロファイル**: プロファイルは、消費者の属性を定義するために使用されるExperience Platform標準データモデルです。 プロファイルには、個人やデバイスに関連するイベントデータと属性を集約したデータを含めることもできます。

  例：「John Doeは55歳の男性です。」

* **セグメント**：属性とイベントデータの両方を使用して、データベースからプロファイルのサブセットを定義する一連のルール。

  例：「50歳以上の男性」

* **オーディエンス**: セグメントルールを満たすプロファイルのコレクション。

  例：データベース内の50歳以上のすべての男性に対応するプロファイルのリスト。
