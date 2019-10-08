---
title: セグメント化とターゲット化
seo-title: セグメント化とターゲット化
description: セグメント化とターゲット化
seo-description: 「Campaignでのプロファイル、ターゲット設定、オーディエンスの作成について説明します。オーディエンスを作成し、連絡先をインポートして、Experience cloudソリューションとオーディエンスを共有し、マーケティングの疲れを避けます。」
page-status-flag: 非活性化の
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開始
content-type: 参照
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# セグメント化とターゲット化{#segmentation-and-targeting}

## プロファイル {#profiles}

Adobe Campaignの柔軟なデータモデルを使用して、顧客プロファイルデータを強化し、新しい属性や表を追加します。 その後、これらの顧客プロファイルを使用して、より正確なセグメント化、パーソナライゼーション、およびレポートを実現します。

Adobe Campaignプロファイルは、データベースに保存されているすべての連絡先を表します。 各プロファイルは、ターゲット設定、修飾、個別追跡を行うために必要な情報を含む、データベース内の1つのエントリに対応します。 つまり、プロファイルは次のようになります。組織に応じて、顧客、見込み客、ニュースレターを購読している個人、受信者、ユーザー、またはその他の宗派。

顧客プロファイル機能は、すべての顧客データを1か所に統合します。

![](assets/mkt_hist_view.png)

Adobe Campaignでは、プロファイルの取得に関して様々なメカニズムを提案しています。ランディングページ、手動または自動インポートメカニズムを使用し [て](../../channels/using/about-landing-pages.md)、データをオンラインで収集する [(Adobe Campaignインターフェイスでの直接入力、](../../automating/using/about-data-import-and-export.md)[](../../audiences/using/creating-profiles.md)[](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)Adobe Campaign APIを使用したバルク作成)。

**関連トピック：**

* 「プロファイル」セクションで、様々なタイプのプロファイルにつ [いて](../../audiences/using/about-profiles.md) 、説明します。
* このセクションで、組織 **内のアクティブな** Profilesの数にア [クセスします](../../audiences/using/active-profiles.md)。
* ワークフローターゲット機能を使用して、データをカスタマイズし、計算、集計、重複除外、結合などの複雑なデータ管理タスクを処理する方 [法を説明します](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

関連性の高い効果的なメッセージを配信し、顧客を惹きつけるために、Adobe Campaignは高度な分析とターゲティング機能を統合します。 ワークフローとクエリエディターのおかげで、様々なキャンペーンの対象となるオーディエンスを、そのキャンペーンに関する情報、アクティビティ、言語、好み、マーケティング履歴に基づいて作成できます。 これにより、例えば、購読済みのプロファイルをフィルターしたり、無制限の数の条件でターゲットオーディエンスを作成したりできます。

オーディエンスはこのペ [ージに表示され](../../audiences/using/about-audiences.md) 、「オーディエンス」セクションに詳 [細が表示されます](../../audiences/using/creating-audiences.md) 。

**関連トピック：**

* 多言語のプッシュ通知または多言語電子メールを送信して、複数の地域の多言語オーディエ [ンスに到達する方法](../../channels/using/creating-a-multilingual-push-notification.md) を [説明します。](../../channels/using/creating-a-multilingual-email.md)
* クエリを作成してオーデ [ィエンスを構築する](../../audiences/using/creating-audiences.md#creating-query-audiences) 方法を説明します。
* ワークフローでリス [トオーディエンス](../../audiences/using/creating-audiences.md#creating-list-audiences) を作成する方法
* ワークフロー内のフ [ァイルからオーディエンスを読み込む](../../audiences/using/creating-audiences.md#creating-file-audiences) 方法について説明します。
* Experience cloudソリューションでオー [ディエンスを](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) 共有する方法を説明します。

## General Data Protection Regulation {#general-data-protection-regulation}

GDPR は欧州連合（EU）にて新しく施行されるプライバシー保護法律で、データ保護要件を現代の状況に合わせて整合化することを目的としています。GDPR は、EU に居住しているデータ主体のデータを保有している Adobe Campaign の顧客に適用されます。アドビは、Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）に加え、追加の機能を含め、特定のGDPRリクエストに対するData Controllerとしての準備を促進するため、この機会をデータプロセッサーとして取り上げます。

GDPRに準拠するた [めに](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) Adobe Campaignが提供するツールと機能の詳細については、このガイドを参照してください。

## 疲労管理 {#fatigue-management}

疲労ルールを使用すると、マーケティング担当者は、過剰に要請されたプロファイルをキャンペーンから自動的に除外するグローバルなチャネル間ビジネスルールを設定できます。

疲労ルールを実装するには、プロファイルごとに最大メッセージ数を定義し、ルールを適用する期間を選択します。 配信の準備中、既に送信されているメッセージの数に応じて、該当する場合は配信からプロファイルが除外されます。

**関連トピック：**

* 一連のサンプルを使 [用して疲労ルール](../../administration/using/fatigue-rules.md#examples) を設計する方法を説明します。
* タイポロジルールの作成 [方法を説明します](../../administration/using/about-typology-rules.md)
* フィルタ [ールールを使用し](../../administration/using/filtering-rules.md) 、メッセージのオーディエンスを絞り込む
