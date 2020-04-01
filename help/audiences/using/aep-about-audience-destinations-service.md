---
title: Audience Destinations サービスについて
description: Destinationsサービスの詳細オーディエンスを表示します。
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
source-git-commit: e1fa546313e8d543685ef30a072ae2d97c5bf236

---


# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>オーディエンスの宛先サービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米の場合のみベータ版）。 ご利用になりたい場合は、アドビカスタマーケアにお問い合わせください。

大規模で複雑なデータセットに基づいて高度にターゲットを絞った [オーディエンスを構築するために](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) 、Adobe Experience Platformを活用することで、顧客エクスペリエンスを強化します。 Adobe Experience Platformは、Adobe Analyticsを含むオンラインおよびオフラインのソース全体のプロファイル、行動および複数エンティティのデータを統合し、顧客の360度の表示を構築し、顧客体験を効果的に管理できるようにします。

次に、Adobe Campaign Standardは、 **オーディエンスの宛先** ( **オーディエンス**)サービスを使用して、複数手順のプロファイルやチャネル間のキャンペーンプログラムを行うための、Adobe Experience Platformからと呼ばれるのコレクションを取得します。

**オーディエンス** は、最初にセグメントを作成し **ます**。これは、多次元ターゲットを作成するために、Adobe Experience Platformの顧客プロファイル内で実質的に任意の変数(プロファイル、イベント、マルチエンティティデータなど)に基づく一連のルールです。 Unified Concepts &amp; Segmentation Servicesに関するグローバルプロファイルは、次の専用ドキュメントで参照されます。

* [リアルタイム顧客プロファイルの概要](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Segmentation Serviceの概要](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

セグメントを作成したら、配信のオーディエンスとして、セグメントをアクティブ化で [きます](../../automating/using/aep-targeting-audiences.md)。 さらに、Adobe Experience Platformのコンテキストデータを使用して、個人設定を行い [](../../automating/using/aep-personalizing-campaigns.md) 、動的なコンテンツをキャンペーンに追加できます。

ハウツービデオは、この節でもご覧 [いただけます](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

以下の節で使用される用語：

* **プロファイル**:プロファイルは、コンシューマーの属性を定義するために使用されるエクスペリエンスプラットフォームの標準データモデルです。 プロファイルはまた、個人やイベントに関連する集計データや属性のデータでもよい。

   例：「ジョン・ドウは55歳の男です」

* **セグメント**:属性とデータベースデータの両方を使用して、プロファイルのサブセットを定義する一連のルールイベント。

   例：「男性50歳以上」

* **オーディエンス**:セグメントルールを満たすプロファイルのコレクション。

   例：リストプロファイル内の男性50歳を超える男性に対応するデータベース。
