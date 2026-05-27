---
title: リストのカスタマイズ
description: Adobe Campaign Standardのリスト画面での表示とアクションをカスタマイズする方法（並べ替え、フィルタリング、削除または複製）について説明します。 リスト画面には、1つまたは複数の特定のリソースの要素が表示されます。
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 9%

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
<td>データベースの充実</td>
<td>オーディエンスの整理</td>
<td>プライバシー管理</td>
</tr>
</table>

## 顧客プロファイル {#customer-profiles}

<img width="60px" alt="conditions" src="assets/icon_profile.svg"/>

Adobe Campaign プロファイルは、データベースに保存されているすべての連絡先を表します。 各プロファイルは、データベース内の1つのエントリに対応します。このエントリには、そのプロファイルがターゲット設定され、クオリファイドされ、個別に追跡されるために必要な情報が含まれます。 つまり、プロファイルには、顧客、見込み顧客、ニュースレターを購読している個人、受信者、ユーザー、その他の組織の名称を指定できます。

**詳細情報**

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [組織内のアクティブなプロファイルの数へのアクセス](../../audiences/using/active-profiles.md)

## データベースの充実 {#populating-database}

<img width="60px" alt="conditions" src="assets/icon_populate.svg"/>

Campaign Standardには、マーケティングデータベースを成長させるためのツールが複数あります。 この節では、Campaignにデータを挿入するために使用できるさまざまな方法について詳しく説明し、専用のドキュメントを参照します。

### ワークフローによるデータのインポート {#importing-data-through-workflows}

ワークフローを使用すると、[**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) アクティビティを使用してデータを収集し、Campaign データベースにインポートできます。 ワークフローを通じてデータを読み込む際の一般的な情報とベストプラクティスについては、[この節](../../automating/using/about-data-import-and-export.md)で説明します。

さらに、データをインポートするためのテンプレートを設定できます。 テンプレートの読み込みを使用すると、同じ構造のファイルを定期的に読み込むことができます。 次の2種類のテンプレートを設定できます。

* **ワークフローテンプレート**：これらは事前設定済みのワークフローで、必要に応じて1回設定し、データをインポートしてデータベースを更新するたびに再利用できます。 データを読み込むワークフローテンプレートの例については、[この節](../../automating/using/creating-import-workflow-templates.md)で詳しく説明しています。

* **データテンプレートの読み込み**: ワークフローテンプレートと同様に、これらはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されています。 設定が完了すると、**[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** メニューの下に表示が簡略化されたユーザーが使用できるようになります。 データテンプレートの読み込みについて詳しくは、[専用ドキュメント ](../../automating/using/importing-data-with-import-templates.md)を参照してください。

### ランディングページからのデータ収集 {#collecting-data-from-landing-pages}

ランディングページとは、データの収集と、データベース内の既存の情報の作成または更新に使用できるweb フォームです。 原則は次のとおりです。

* データ（名、姓、電子メールなど）を収集するための入力フィールドを追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* web サイトやメッセージへの直接リンクを通じて、ランディングページをオンラインで利用できるようにします。

ランディングページについて詳しくは、[専用ドキュメント ](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

**詳細情報**

* xxxx
* xxxx

### Microsoft Dynamics 365からのプロファイルの同期

Campaign StandardとMicrosoft Dynamics 365の連携により、Microsoft Dynamics 365からCampaign データベースに連絡先データを渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティング施策のターゲットにすることができます。 この統合について詳しくは、[専用ドキュメント ](../../integrating/using/d365-acs-get-started.md)を参照してください。

>[!NOTE]
>
>Campaign Standard-Microsoft Dynamics 365 コネクタは現在、制限付きで提供されており、ドキュメントで詳しく説明されているいくつかの制限が適用されます。

**詳細情報**

* xxxx
* xxxx

### API呼び出しを介したデータのインポート

Campaign Standard APIを使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。 APIの使用方法について詳しくは、[専用ドキュメント ](../../api/using/get-started-apis.md)を参照してください。

>[!CAUTION]
>
>API呼び出しを介したプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

**詳細情報**

* xxxx
* xxxx

## オーディエンスの整理 {#organizing-audiences}

<img width="60px" alt="conditions" src="assets/icon_audience.svg"/>

Adobe Campaignには、適切かつ効果的なメッセージを配信し、顧客を効果的に惹きつけるための高度な分析およびターゲティング機能が搭載されています。

ワークフローとクエリエディターを利用すれば、情報、アクティビティ、言語、嗜好、マーケティング履歴などに応じて、さまざまな施策のターゲットとなるオーディエンスを構築できます。 これにより、例えば、購読しているプロファイルをフィルタリングしたり、無制限の条件でターゲットオーディエンスを作成したりできます。

**詳細情報**

* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## プライバシーの管理 {#privacy-management}

<img width="60px" alt="conditions" src="assets/icon_privacy.svg"/>

GDPRとは、データ保護要件を調整し、今日の状況に対応するために近代化、整備された、EU （欧州連合）の新しいプライバシー法です。 GDPR は、EU に居住しているデータ主体のデータを保有している Adobe Campaign の顧客に適用されます。 Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持の設定、ユーザーの役割など）に加えて、この機会をデータ処理者の役割で活用して、特定のGDPR要求に対するデータ管理者としての準備を容易にするための追加機能を追加します。

Adobe Campaignが提供するGDPRへの準拠に役立つツールと機能について詳しくは、[この節](../../start/using/privacy.md)を参照してください。

**詳細情報**

* xxxx
* xxxx