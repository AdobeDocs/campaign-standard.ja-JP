---
title: Audience Destinations サービスについて
description: オーディエンスの宛先サービスについての詳細。
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
source-git-commit: be7ab90583e9c6472fd2c86082e832432d0a32b9
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 4%

---


# Audience Destinations サービスについて {#about-audiences}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 アドビカスタマーケアにお問い合わせの際は、アドビカスタマーケアにご連絡ください。

大規模で複雑なデータセットに基づいて高度にターゲットを絞ったオーディエンスを構築する [Adobe Experience Platformを活用して](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) 、顧客体験を強化します。 このAdobe Experience Platformでは、アドビAnalyticsを含むオンラインおよびオフラインのソース全体のプロファイル、行動、および複数のエンティティに関するデータが統合され、顧客の360度表示を構築できるようになり、顧客体験を効果的に管理できます。

次に、Adobe Campaign Standardは、 **オーディエンス宛先** サービスを使用して、複数手順のチャネル間のキャンペーンプログラム用のAdobe Experience Platformから、 ****&#x200B;オーディエンスと呼ばれるプロファイルのコレクションを取得します。

**オーディエンス** は、最初に ****&#x200B;セグメントを作成することで作成されます。これは、Adobe Experience Platformから顧客プロファイル内の事実上すべての変数(プロファイル、イベント、マルチエンティティデータなど)に基づく一連のルールで、多次元ターゲットを作成します。 リアルタイムの顧客プロファイルとセグメント化サービスに関するグローバルな概念は、次の専用ドキュメントで参照できます。

* [リアルタイム顧客プロファイルの概要](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)
* [Segmentation Serviceの概要](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

セグメントを作成したら、そのセグメントを [Campaign Standardワークフローで配信のオーディエンスとしてアクティブ化できます](../../automating/using/aep-targeting-audiences.md)。 さらに、Adobe Experience Platformのコンテキストデータを使用して [個人設定を行ったり](../../automating/using/aep-personalizing-campaigns.md) 、キャンペーンに動的なコンテンツを追加したりできます。

ハウツービデオは [この節でもご覧いただけます](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)。

これらの節で使用される用語：

* **プロファイル**: プロファイルは、Experience Platformの属性を定義するために使用される消費者標準データモデルです。 また、プロファイルは、イベントデータおよび個人や機器に関連する属性の集計にもなる。

   例： 「ジョン・ドウは55歳の男です」

* **セグメント**: 属性とイベントデータの両方を使用して、データベースのプロファイルのサブセットを定義する一連のルール。

   例： 「男性> 50歳」

* **オーディエンス**: セグメントルールを満たすプロファイルの集まり。

   例： データベース内の男性50歳を超えるすべての男性に対応するプロファイルのリスト。
