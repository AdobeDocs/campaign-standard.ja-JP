---
title: リストのカスタマイズ
description: 「Adobe Campaign Standardでリスト画面の表示をカスタマイズし、操作する方法を説明します。並べ替え、フィルタリング、削除、複製などです。 指定された 1 つまたは複数のリソースの要素を画面に表示します。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 6%

---


# プロファイルとオーディエンスの使用

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="条件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="条件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="条件" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="条件" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>顧客プロファイル</td>
<td>データベースの強化</td>
<td>オーディエンスの整理</td>
<td>プライバシー管理</td>
</tr>
</table>

## 顧客プロファイル {#customer-profiles}

<img width="60px" alt="条件" src="assets/icon_profile.svg"/>

Adobe Campaign プロファイルは、データベースに保存されているすべての連絡先を表します。 各プロファイルは、データベース内の 1 つのエントリに対応します。このエントリには、そのプロファイルをターゲットにし、認定し、個別に追跡するために必要な情報が含まれています。 つまり、プロファイルには、クライアント、見込み客、ニュースレターを購読している個人、受信者、ユーザー、組織に応じたその他の宗派があります。

**詳細情報**

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [組織内のアクティブなプロファイル数へのアクセス](../../audiences/using/active-profiles.md)

## データベースの強化 {#populating-database}

<img width="60px" alt="条件" src="assets/icon_populate.svg"/>

Campaign Standardには、マーケティングデータベースの拡張に役立つツールがいくつか用意されています。 この節では、Campaign へのデータの挿入に使用できる様々な方法について、専用ドキュメントを参照しながら詳しく説明します。

### ワークフローでのデータの読み込み {#importing-data-through-workflows}

ワークフローでは、[**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) アクティビティを使用してデータを収集し、Campaign データベースに読み込むことができます。 ワークフローを通じてデータをインポートする際の一般的な情報とベストプラクティスについては、[ この節 ](../../automating/using/about-data-import-and-export.md) を参照してください。

さらに、データをインポートするためのテンプレートを設定できます。 インポートテンプレートの使用は、同じ構造を持つファイルを定期的にインポートするためのベストプラクティスです。 次の 2 種類のテンプレートを設定できます。

* **ワークフローテンプレート**：必要に応じて一度設定し、データの読み込みとデータベースの更新を行うたびに再利用できる、事前設定済みのワークフローです。 データをインポートするワークフローテンプレートの例について詳しくは、[ この節 ](../../automating/using/creating-import-workflow-templates.md) を参照してください。

* **データテンプレートの読み込み**：ワークフローテンプレートと同様に、これらはワークフローに基づくテンプレートであり、データベースを更新するためにファイルをアップロードするために設定されます。 設定が完了すると、**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** メニューの下の簡略化されたビューでユーザーが使用できるようになります。 データインポートテンプレートについて詳しくは、[ 専用ドキュメント ](../../automating/using/importing-data-with-import-templates.md) を参照してください。

### ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページは、データの収集や、データベース内の既存の情報の作成または更新に使用できる web フォームです。 原則は次のとおりです。

* データを収集するための入力フィールド（名、姓、メールなど）を追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* Web サイトを介して、またはメッセージへの直接リンクを介して、ランディングページをオンラインで使用できるようにします。

ランディングページについて詳しくは、[ 専用ドキュメント ](../../channels/using/getting-started-with-landing-pages.md) を参照してください。

**詳細情報**

* xxxx
* xxxx

### Microsoft Dynamics 365 からのプロファイルの同期

Microsoft Dynamics 365 とのCampaign Standard統合により、Microsoft Dynamics 365 から Campaign データベースに連絡先データを渡すことができます。
これらの連絡先は、プロファイルリストに表示され、マーケティングキャンペーンでターゲットに設定できます。 この統合について詳しくは、[ 専用ドキュメント ](../../integrating/using/d365-acs-get-started.md) を参照してください。

>[!NOTE]
>
>Campaign StandardとMicrosoftの Dynamics 365 コネクタは現在限定提供であり、ドキュメントで詳しく説明されているように、いくつかの制限が適用されることに注意してください。

**詳細情報**

* xxxx
* xxxx

### API 呼び出しを使用したデータの読み込み

Campaign StandardAPI を使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。 API の使用方法について詳しくは、[ 専用ドキュメント ](../../api/using/get-started-apis.md) を参照してください。

>[!CAUTION]
>
>API 呼び出しを使用してプロファイルの一括作成または更新を実行する前に、ライセンス契約に対応するスケールの制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

**詳細情報**

* xxxx
* xxxx

## オーディエンスの整理 {#organizing-audiences}

<img width="60px" alt="条件" src="assets/icon_audience.svg"/>

お客様が適切かつ効果的なメッセージを配信し、お客様を効果的に惹きつけることができるように、Adobe Campaignではアドバンス分析とターゲティング機能を統合しています。

ワークフローとクエリエディターのおかげで、オーディエンスに関する情報、そのアクティビティ、言語、環境設定、マーケティング履歴に応じて、様々なキャンペーンでターゲットにするオーディエンスを作成できます。 これにより、例えば、購読しているプロファイルをフィルタリングしたり、無制限の数の条件でターゲットオーディエンスを作成したりできます。

**詳細情報**

* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## プライバシーの管理 {#privacy-management}

<img width="60px" alt="conditions" src="assets/icon_privacy.svg"/>

GDPR は、データ保護要件を現代の状況に合わせて整合化する、欧州連合（EU）の新しいプライバシー法です。 GDPR は、EU 在住のデータ主体のデータを保持するAdobe Campaignのお客様に適用されます。 アドビは、Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）に加え、この機会にデータ処理者としての役割を担って、特定の GDPR 要求に対するデータ管理者としての準備を容易にするためのその他の機能も含めています。

GDPR に準拠するためのAdobe Campaignのツールと機能の詳細については、[ この節 ](../../start/using/privacy.md) を参照してください。

**詳細情報**

* xxxx
* xxxx