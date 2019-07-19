---
title: セグメント化とターゲティング
seo-title: セグメント化とターゲティング
description: セグメント化とターゲティング
seo-description: 「キャンペーンでのプロファイル、ターゲット設定およびオーディエンスの作成についてオーディエンスを構築し、連絡先をインポートすることで、Experience Cloudソリューションでオーディエンスを共有し、マーケティングの疲労を回避できます」。
page-status-flag: 常にアクティブ化されていない
uuid: 71f53808-0309-49f6- a4ee-3446eac9758a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: 参照
topic-tags: about- adobe- campaign
discoiquuid: d8c8a318-9433-4par- b378- fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Segmentation and targeting{#segmentation-and-targeting}

## Profiles {#profiles}

Adobe Campaignの柔軟なデータモデルを使用して、顧客プロファイルデータを強化し、新しい属性やテーブルを追加します。次に、より正確なセグメント化、パーソナライゼーションおよびレポートに、これらの顧客プロファイルを使用します。

Adobe Campaignプロファイルは、データベースに保存されているすべての連絡先を表します。各プロファイルは、データベース内の1つのエントリに対応します。このエントリには、ターゲット設定、修飾および個別に追跡するために必要な情報が含まれます。つまり、プロファイルは次のようになります。顧客、見込み客、ニュースレター、受信者、ユーザー、その他組織によって決まるその他の分母。

顧客プロファイル機能により、顧客データはすべて1か所に統合されます。

![](assets/mkt_hist_view.png)

Adobe Campaign proposes various mechanisms for profile acquisition: collecting data online via [landing pages](../../channels/using/about-landing-pages.md), manual or [automated import mechanisms](../../automating/using/about-data-import-and-export.md), [direct input](../../audiences/using/creating-profiles.md) in the Adobe Campaign interface, bulk creation through [Campaign APIs](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

**関連トピック:**

* [プロファイル](../../audiences/using/about-profiles.md) セクションの様々なタイプのプロファイルについて説明します。
* Access the number of **Active Profiles** in your organization in [this section](../../audiences/using/active-profiles.md).
* Learn how to customize your data, handle complex data management tasks, such as calculations, aggregates, de-dupes, and merges, using [workflow targeting capabilities](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

関連性の高い効果的なメッセージを提供し、顧客を効果的に惹きつけるために、Adobe Campaignは高度な分析とターゲティング機能を統合します。ワークフローおよびクエリエディターにより、キャンペーンによってターゲット設定されるオーディエンス、そのアクティビティ、言語、環境設定、マーケティング履歴に応じて、様々なキャンペーンによってターゲット設定されるオーディエンスを構築できます。これにより、サブスクライブされたプロファイルをフィルターしたり、無制限にターゲットオーディエンスを作成したりできます。

Audiences are presented [in this page](../../audiences/using/about-audiences.md) and detailed in the [Audiences](../../audiences/using/creating-audiences.md) section.

**関連トピック:**

* [多言語プッシュ通知](../../channels/using/creating-a-multilingual-push-notification.md) または [多言語電子メール送信によって複数の地域にわたる多言語オーディエンスに到達する方法について説明します](../../channels/using/creating-a-multilingual-email.md)
* Learn how to [create queries](../../audiences/using/creating-audiences.md#creating-query-audiences) to build audiences
* Learn how to [create list audiences](../../audiences/using/creating-audiences.md#creating-list-audiences) in a workflow
* Learn how to [import an audience from a file](../../audiences/using/creating-audiences.md#creating-file-audiences) in a workflow
* Learn how to [share audiences](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) with Experience Cloud solutions

## General Data Protection Regulation {#general-data-protection-regulation}

GGPRは、データ保護要件を調和し、最新化する欧州連合（EU）新しいプライバシー法です。GGPRは、EUに存在するデータ項目のデータを保持するAdobe Campaignのお客様に適用されます。Adobe Campaignで既に使用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割を含む）に加えて、データプロセッサーとしてこのロールを利用して、特定のGGPRリクエストのデータコントローラーとしての準備を容易にすることができます。

Refer to this [guide](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) to learn more about the tools and functionalities that Adobe Campaign provides to help you become GDPR compliant.

## Fatigue management {#fatigue-management}

疲労ルールを使用すると、マーケティング担当者はグローバルなクロスチャネルビジネスルールを設定して、キャンペーンからのプロシークプロファイルを自動的に除外することができます。

疲労ルールを実装するには、プロファイルごとのメッセージの最大数を定義し、ルールを適用する期間を選択します。配信準備中は、既に送信されているメッセージの数に応じて、配信からプロファイルが除外されます。

**関連トピック:**

* Learn how to [design fatigue rules](../../administration/using/fatigue-rules.md#examples) through a set of samples
* Learn how to create [typology rules](../../administration/using/about-typology-rules.md)
* [フィルタールール](../../administration/using/filtering-rules.md) を使用したメッセージのオーディエンスの絞り込み
