---
title: リストのカスタマイズ
description: 「Adobe Campaign Standardのリスト画面での表示をカスタマイズし、操作する方法（要素の並べ替え、フィルタリング、削除または複製）について説明します。 リスト画面には、指定した 1 つまたは複数のリソースの表示要素が表示されます。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 6%

---


# プロファイルとオーディエンスの操作

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
<td>データベースのエンリッチメント</td>
<td>オーディエンスを整理</td>
<td>プライバシー管理</td>
</tr>
</table>

## 顧客プロファイル {#customer-profiles}

<img width="60px" alt="条件" src="assets/icon_profile.svg"/>

Adobe Campaignプロファイルは、データベースに保存されているすべての連絡先を表します。 各プロファイルは、データベース内の 1 つのエントリに対応し、そのエントリには、ターゲット設定、選定および個別に追跡するために必要な情報が含まれます。 つまり、プロファイルには、クライアント、見込み客、ニュースレターを購読した個人、受信者、ユーザー、または組織に応じたその他の単位が含まれます。

**詳細情報**

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [組織内のアクティブなプロファイル数へのアクセス](../../audiences/using/active-profiles.md)

## データベースのエンリッチメント {#populating-database}

<img width="60px" alt="条件" src="assets/icon_populate.svg"/>

Campaign Standardには、マーケティングデータベースを拡張するのに役立つツールがいくつか用意されています。 この節では、Campaign にデータを挿入するための様々な方法と、専用ドキュメントへの参照について詳しく説明します。

### ワークフローを使用したデータのインポート {#importing-data-through-workflows}

ワークフローを使用すると、データを収集し、 [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) アクティビティ。 ワークフローを通じてデータをインポートする際の一般的な情報とベストプラクティスについては、 [この節](../../automating/using/about-data-import-and-export.md).

さらに、データをインポートするテンプレートを設定できます。 インポートテンプレートを使用することは、同じ構造を持つファイルを定期的にインポートする場合のベストプラクティスです。 次の 2 種類のテンプレートを設定できます。

* **ワークフローテンプレート**：事前設定済みのワークフローで、必要に応じて 1 回設定し、データのインポートとデータベースの更新のたびに再利用できます。 データをインポートするワークフローテンプレートの例について詳しくは、 [この節](../../automating/using/creating-import-workflow-templates.md).

* **データテンプレートのインポート**：ワークフローテンプレートと同様、これらはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されています。 設定が完了すると、ユーザーは、 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** メニュー。 データテンプレートのインポートについて詳しくは、 [専用ドキュメント](../../automating/using/importing-data-with-import-templates.md).

### ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページは、データを収集し、データベース内の既存の情報を作成または更新するために使用できる Web フォームです。 原則は次のとおりです。

* データ（名、姓、E メールなど）を収集するための入力フィールドを追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* Web サイト経由、またはメッセージへの直接リンクを通じて、ランディングページをオンラインで使用できるようにします。

ランディングページについて詳しくは、 [専用ドキュメント](../../channels/using/getting-started-with-landing-pages.md).

**詳細情報**

* xxxx
* xxxx

### Microsoft Dynamics 365 からのプロファイルの同期

Microsoft Dynamics 365 とのCampaign Standard統合により、Microsoft Dynamics 365 の連絡先データを Campaign データベースに渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティングキャンペーンのターゲットに設定できます。 この統合について詳しくは、 [専用ドキュメント](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Campaign Standard- Microsoft Dynamics 365 コネクタは現在、使用が制限されています。また、ドキュメントに詳しく記載されているいくつかの制限が適用されます。

**詳細情報**

* xxxx
* xxxx

### API 呼び出しを使用したデータの読み込み

Campaign StandardAPI を使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。 API の使用方法について詳しくは、 [専用ドキュメント](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>API 呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

**詳細情報**

* xxxx
* xxxx

## オーディエンスの整理 {#organizing-audiences}

<img width="60px" alt="条件" src="assets/icon_audience.svg"/>

関連性の高い効果的なメッセージを配信し、顧客を効果的に惹きつけるために、Adobe Campaignは高度な分析およびターゲティング機能を統合しました。

ワークフローとクエリエディターを使用すると、様々なキャンペーンのターゲットになるオーディエンスを、それぞれのキャンペーンに含まれる情報、アクティビティ、言語、好み、マーケティング履歴に応じて構築できます。 これにより、例えば、購読しているプロファイルをフィルターしたり、無制限数の条件に基づいてターゲットオーディエンスを作成したりできます。

**詳細情報**

* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## プライバシーの管理 {#privacy-management}

<img width="60px" alt="conditions" src="assets/icon_privacy.svg"/>

GDPR は欧州連合 (EU) の新しいプライバシー法で、データ保護要件を現代の状況に合わせて整合化させることを目的としています。 GDPR は、EU に居住しているデータ主体のデータを保有しているAdobe Campaignのお客様に適用されます。 Adobe Campaignでは既にプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）を提供していますが、この機会にデータ処理者としての役割で、特定の GDPR 要求に対するデータ管理者としての準備を進めます。

参照： [この節](../../start/using/privacy.md) を参照して、GDPR に準拠するためのAdobe Campaignのツールと機能に関する詳細情報を確認してください。

**詳細情報**

* xxxx
* xxxx