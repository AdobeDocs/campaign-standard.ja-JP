---
title: リストのカスタマイズ
description: 「Adobe Campaign Standardのリスト画面での表示をカスタマイズし、操作する方法（要素の並べ替え、フィルタリング、削除または複製）について説明します。 リスト画面には、1 つまたは複数の特定のリソースの要素が表示されます。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 12%

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
<td>オーディエンスの整理</td>
<td>プライバシー管理</td>
</tr>
</table>

## 顧客プロファイル {#customer-profiles}

<img width="60px" alt="条件" src="assets/icon_profile.svg"/>

Adobe Campaignプロファイルは、データベースに保存されているすべての連絡先を表します。 各プロファイルは、データベース内の 1 つのエントリに対応し、ターゲット設定、認定および個別に追跡するために必要な情報が含まれます。 つまり、プロファイルは次のようになります。組織に応じて、クライアント、見込み客、ニュースレターを購読した個人、受信者、ユーザー、またはその他の単位。

**詳細情報**

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [組織内のアクティブなプロファイル数へのアクセス](../../audiences/using/active-profiles.md)

## データベースのエンリッチメント {#populating-database}

<img width="60px" alt="条件" src="assets/icon_populate.svg"/>

Campaign Standardには、マーケティングデータベースの拡張に役立つツールがいくつか用意されています。 この節では、Campaign にデータを挿入するための様々な方法と、専用ドキュメントの参照について説明します。

### ワークフローを使用したデータのインポート {#importing-data-through-workflows}

ワークフローを使用すると、[**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) アクティビティを使用してデータを収集し、Campaign データベースにインポートできます。 ワークフローを通じてデータをインポートする際の一般的な情報とベストプラクティスについては、[ この節 ](../../automating/using/about-data-import-and-export.md) を参照してください。

また、データをインポートするテンプレートを設定することもできます。 インポートテンプレートを使用することは、同じ構造を持つファイルを定期的にインポートすることをお勧めします。 次の 2 種類のテンプレートを設定できます。

* **ワークフローテンプレート**:これらは事前設定済みのワークフローで、必要に応じて一度設定し、データのインポートとデータベースの更新をおこなうたびに再利用できます。データをインポートするワークフローテンプレートの例について詳しくは、[ この節 ](../../automating/using/creating-import-workflow-templates.md) を参照してください。

* **データテンプレートのインポート**:ワークフローテンプレートと同様に、ワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されています。設定が完了すると、 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** メニューの下に簡略表示が表示され、ユーザーが利用できるようになります。 データテンプレートのインポートについて詳しくは、[ 専用のドキュメント ](../../automating/using/importing-data-with-import-templates.md) を参照してください。

### ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページとは、データを収集し、データベース内の既存の情報を作成または更新するために使用できる Web フォームです。 原則は次のとおりです。

* データ（名、姓、E メールなど）を収集するための入力フィールドを追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* Web サイト経由またはメッセージへの直接リンクを通じて、ランディングページをオンラインで使用できるようにします。

ランディングページについて詳しくは、[ 専用のドキュメント ](../../channels/using/getting-started-with-landing-pages.md) を参照してください。

**詳細情報**

* xxxx
* xxx

### Microsoft Dynamics 365 からのプロファイルの同期

Campaign Standardと Microsoft Dynamics 365 の統合により、Microsoft Dynamics 365 の連絡先データを Campaign データベースに渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティングキャンペーンのターゲットにすることができます。 この統合について詳しくは、[ 専用のドキュメント ](../../integrating/using/d365-acs-get-started.md) を参照してください。

>[!NOTE]
>
>現在、Campaign Standard- Microsoft Dynamics 365 コネクタは使用が制限されています。このコネクタには、ドキュメントに詳しく記載されているいくつかの制限が適用されます。

**詳細情報**

* xxx
* xxx

### API 呼び出しを使用したデータの読み込み

Campaign StandardAPI を使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。 API の使用方法について詳しくは、[ 専用のドキュメント ](../../api/using/get-started-apis.md) を参照してください。

>[!CAUTION]
>
>API 呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

**詳細情報**

* xxx
* xxx

## オーディエンスの整理 {#organizing-audiences}

<img width="60px" alt="条件" src="assets/icon_audience.svg"/>

関連性の高い効果的なメッセージを配信し、顧客を効果的に惹きつけるために、Adobe Campaignは高度な分析とターゲティング機能を統合しています。

ワークフローとクエリエディターを使用すれば、様々なキャンペーンのターゲットとなるオーディエンスを、自分が持っている情報、アクティビティ、言語、好み、マーケティング履歴に応じて作成できます。 これにより、例えば、購読したプロファイルをフィルターしたり、ターゲットオーディエンスを無制限数の条件で作成したりできます。

**詳細情報**

* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## プライバシーの管理 {#privacy-management}

<img width="60px" alt="条件" src="assets/icon_privacy.svg"/>

GDPR は欧州連合（EU）にて新しく施行されるプライバシー保護法律で、データ保護要件を現代の状況に合わせて整合化することを目的としています。GDPR は、EU に居住しているデータ主体のデータを保有している Adobe Campaign の顧客に適用されます。アドビは、Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）に加え、データ処理者としての役割で、特定の GDPR 要求に対するデータ管理者としての準備を容易にする機能を追加します。

Adobe Campaignが GDPR に準拠する際に役立つツールと機能の詳細については、この [ ガイド ](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=ja) を参照してください。

**詳細情報**

* xxx
* xxx