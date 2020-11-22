---
solution: Campaign Standard
product: campaign
title: リストのカスタマイズ
description: 「Adobe Campaign Standardのリスト画面での表示をカスタマイズし、動作をカスタマイズする方法：要素の並べ替え、フィルタリング、削除または複製を行う方法について説明します。 リスト画面には、1つまたは複数の特定のリソースの要素が表示されます。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 12%

---


# プロファイルとオーディエンスの操作

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>顧客プロファイル</td>
<td>データベースの強化</td>
<td>オーディエンスの整理</td>
<td>プライバシーの管理</td>
</tr>
</table>

## 顧客プロファイル {#customer-profiles}

<img width="60px" alt="conditions" src="assets/icon_profile.svg"/>

Adobe Campaignプロファイルは、データベースに格納されているすべての連絡先を表します。 各プロファイルはデータベース内の1つのエントリに対応し、そのプロファイルがターゲット設定され、資格を持ち、個別に追跡されるために必要な情報が格納されます。 つまり、プロファイルは次のことが可能です。組織に応じた顧客、見込み客、ニュースレターを購読している個人、受信者、ユーザー、またはその他の名称。

**詳細を表示**

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [組織内のアクティブなプロファイル数へのアクセス](../../audiences/using/active-profiles.md)

## データベースの強化 {#populating-database}

<img width="60px" alt="conditions" src="assets/icon_populate.svg"/>

Campaign Standardオファーは、マーケティングデータベースの拡張に役立つツールをいくつかご紹介します。 この節では、専用のドキュメントを参照しながら、キャンペーンにデータを挿入するために使用できる様々な方法について説明します。

### ワークフローを介したデータの読み込み {#importing-data-through-workflows}

ワークフローを使用すると、データを収集し、 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) アクティビティを使用してキャンペーンデータベースにインポートできます。 ワークフローを介してデータをインポートする場合の一般的な情報とベストプラクティスについては、 [この節で説明し](../../automating/using/about-data-import-and-export.md)ます。

また、データを読み込むためのテンプレートを設定することもできます。 同じ構造を持つファイルを定期的に読み込む必要がある場合は、インポートテンプレートの使用をお勧めします。 次の2種類のテンプレートを設定できます。

* **ワークフローテンプレート**:これらは事前設定済みのワークフローで、必要に応じて一度設定すれば、データの読み込みとデータベースの更新を行うたびに再利用できます。 データを読み込むためのワークフローテンプレートの例について [この節で詳しく説明します](../../automating/using/creating-import-workflow-templates.md)。

* **データテンプレートの読み込み**:ワークフローテンプレートと同様、テンプレートはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されます。 設定が完了すると、 **[!UICONTROL Profile & audiences]** /メニューのシンプルな表示を使用してユーザーが使用できるようになり **[!UICONTROL Imports]** ます。 データテンプレートの読み込みについて詳しくは、 [専用のドキュメントを参照してください](../../automating/using/importing-data-with-import-templates.md)。

### ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページとは、データを収集し、データベース内の既存の情報を作成または更新するために使用できるWebフォームです。 原則は以下の通り。

* データを収集する入力フィールド（名、姓、電子メールなど）を追加して、ランディングページを作成および設計します。
* 各入力フィールドを、データベースの対応するフィールドにマップします。
* Webサイトまたはメッセージへの直接リンクを介して、ランディングページをオンラインで利用できるようにします。

For more on landing pages, refer to the [dedicated documentation](../../channels/using/getting-started-with-landing-pages.md).

**詳細を表示**

* xxxx
* xxxx

### Microsoft Dynamics 365からのプロファイルの同期

Microsoft Dynamics 365とのCampaign Standard統合により、Microsoft Dynamics 365の連絡先データをキャンペーンデータベースに渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティングキャンペーンでターゲットを設定できます。 For more on this integration, refer to the [dedicated documentation](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!NOTE]
>
>Campaign Standard-Microsoft Dynamics 365 Connectorは現在限定可用性を備えており、ドキュメントに詳しく記載されているいくつかの制限事項に従うことに注意してください。

**詳細を表示**

* xxxx
* xxxx

### API呼び出しを使用したデータの読み込み

Campaign StandardAPIを使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。 For more on how to use the APIs, refer to the [dedicated documentation](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>API呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

**詳細を表示**

* xxxx
* xxxx

## オーディエンスの整理 {#organizing-audiences}

<img width="60px" alt="conditions" src="assets/icon_audience.svg"/>

関連性の高い効果的なメッセージを届け、顧客の関心を効果的に向けるために、Adobe Campaignは高度な分析とターゲティング機能を統合します。

ワークフローやクエリエディタのおかげで、キャンペーン、アクティビティ、言語、環境設定、マーケティング履歴に応じて、様々なが対象とするオーディエンスを構築できます。 これにより、例えば、登録済みのプロファイルをフィルタリングしたり、無制限の数の条件でターゲットオーディエンスを作成したりできます。

**詳細を表示**

* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## プライバシーの管理 {#privacy-management}

<img width="60px" alt="conditions" src="assets/icon_privacy.svg"/>

GDPR は欧州連合（EU）にて新しく施行されるプライバシー保護法律で、データ保護要件を現代の状況に合わせて整合化することを目的としています。GDPR は、EU に居住しているデータ主体のデータを保有している Adobe Campaign の顧客に適用されます。Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザの役割など）に加えて、Data Processorとしての役割で、特定のGDPR要求に対するData Controllerとしての準備を容易にするために、この機会を利用します。

GDPRに準拠するためにAdobe Campaignが提供するツールと機能の詳細については、この [ガイドを参照してください](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy.html) 。

**詳細を表示**

* xxxx
* xxxx