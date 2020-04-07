---
title: セグメント化とターゲティング
description: 「プロファイル、ターゲット、オーディエンスの作成についてキャンペーン:オーディエンスの作成、連絡先のインポート、Experience Cloudソリューションとのオーディエンスの共有、マーケティングの疲れの回避を行います。」
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# セグメント化とターゲティング{#segmentation-and-targeting}

## プロファイル {#profiles}

Adobe Campaignの柔軟なデータモデルを使用して、顧客プロファイルデータを強化し、新しい属性や表を追加します。 次に、これらの顧客プロファイルを使用して、より正確なセグメント化、パーソナライゼーション、レポートを行います。

Adobe Campaignプロファイルは、データベースに保存されているすべての連絡先を表します。 各プロファイルは、データベース内の1つのエントリに対応し、ターゲット設定、修飾、個々の追跡を行うプロファイルに必要な情報が格納されます。 つまり、次のようなプロファイルが可能です。組織に応じて、顧客、見込み客、ニュースレター、受信者、ユーザー、またはその他の名称を購読している個人。

顧客プロファイル機能は、すべての顧客データを1か所に統合します。

![](assets/mkt_hist_view.png)

Adobe Campaignは、プロファイル獲得の様々なメカニズムを提案する。ランディングページ、手動または自動のインポートメカニズムを介して [](../../channels/using/getting-started-with-landing-pages.md)、Adobe Campaignインターフェイスでの直接入力、 [キャンペーンAPIを介したバルク作成を介したデータのオンラインでの収集を行い](../../automating/using/about-data-import-and-export.md)[](../../audiences/using/creating-profiles.md)[](../../api/using/about-campaign-standard-apis.md)ます。

**関連トピック：**

* 様々なタイプのプロファイルについては、「 [プロファイル](../../audiences/using/about-profiles.md) 」の節を参照してください。
* このセクションで、組織内 **のアクティブ** プロファイルの数にア [クセスします](../../audiences/using/active-profiles.md)。
* ワークフローターゲット機能を使用して、データをカスタマイズし、計算、集計、重複除外、結合などの複雑なデータ管理タスクを処理する方法につ [いて説明します。](../../automating/using/about-targeting-activities.md)

## オーディエンス {#audiences}

関連性の高い効果的なメッセージを配信し、顧客を効果的に惹きつけるために、Adobe Campaignは高度な分析とターゲット機能を統合します。 ワークフローとクエリエディターのおかげで、様々なキャンペーンが提供するオーディエンスを作成できます。その情報は、ユーザーが提供する情報、アクティビティ、言語、好み、マーケティング履歴に応じて異なります。 これにより、例えば、登録済みのプロファイルをフィルターしたり、無制限の数の条件でターゲットオーディエンスを作成したりできます。

オーディエンスはこのペ [ージに表示され](../../audiences/using/about-audiences.md) 、詳細は「 [オーディエンス](../../audiences/using/creating-audiences.md) 」の節で説明します。

**関連トピック：**

* 多言語のプッシュ通知または多言語の電子メールを送信して、複数の地域の多言語オーディエンスに到達 [する方法について](../../channels/using/creating-a-multilingual-push-notification.md) 、説明し [ています。](../../channels/using/creating-a-multilingual-email.md)
* オーディエンスを構築するための [クエリ](../../audiences/using/creating-audiences.md#creating-query-audiences) の作成方法
* ワークフローで [リストオーディエンス](../../audiences/using/creating-audiences.md#creating-list-audiences) を作成する方法
* ワークフロー内のフ [ァイルからオーディエンスを読み込む方法](../../audiences/using/creating-audiences.md#creating-file-audiences) 、または
* Experience Cloudソリューションで [オーディエンス](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) を共有する方法を説明します。

## General Data Protection Regulation {#general-data-protection-regulation}

GDPR は欧州連合（EU）にて新しく施行されるプライバシー保護法律で、データ保護要件を現代の状況に合わせて整合化することを目的としています。GDPR は、EU に居住しているデータ主体のデータを保有している Adobe Campaign の顧客に適用されます。Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザの役割など）に加え、Data Processorとしてこの機会を利用して、特定のGDPR要求に対するData Controllerとしての準備を容易にします。

GDPRに準拠するた [めに](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) 、Adobe Campaignが提供するツールと機能の詳細については、このガイドを参照してください。

## 疲労管理 {#fatigue-management}

疲労ルールを使用すると、マーケティング担当者は、過剰に要請されたチャネルをキャンペーンから自動的に除外する、グローバルなクロスビジネスルールを設定できます。

疲労ルールを実装するには、プロファイルごとの最大メッセージ数を定義し、ルールを適用する期間を選択します。 配信の準備中、プロファイルは、既に送信されている配信の数に応じて、該当する場合はメッセージから除外されます。

**関連トピック：**

* 一連のサンプルを使 [用して疲労ルール](../../sending/using/fatigue-rules.md#examples) を設計する方法を学びます。
* 作成方法を学びま [す](../../sending/using/about-typology-rules.md)
* フィルタ [ールールを使用し](../../sending/using/filtering-rules.md) 、メッセージのオーディエンスを絞り込む
