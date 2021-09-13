---
title: リストのカスタマイズ
description: 「Adobe Campaign Standardのリスト画面での表示と動作をカスタマイズする方法（要素の並べ替え、フィルタリング、削除または複製）について説明します。 リスト画面には、1つまたは複数の特定のリソースの要素が表示されます。」
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '788'
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

Adobe Campaignプロファイルは、データベースに保存されているすべての連絡先を表します。 各プロファイルは、データベース内の1つのエントリに対応し、ターゲット設定、認定および個々に追跡するプロファイルに必要な情報を含みます。 つまり、プロファイルは次のようになります。組織に応じたクライアント、見込み客、ニュースレターを購読した個人、受信者、ユーザー、またはその他の単位。

**詳細情報**

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [組織内のアクティブなプロファイルの数へのアクセス](../../audiences/using/active-profiles.md)

## データベースのエンリッチメント {#populating-database}

<img width="60px" alt="条件" src="assets/icon_populate.svg"/>

Campaign Standardは、マーケティングデータベースの拡張に役立つツールを提供します。 この節では、Campaignにデータを挿入するための様々な方法と、専用のドキュメントの参照について説明します。

### ワークフローを使用したデータのインポート {#importing-data-through-workflows}

ワークフローでは、[**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md)アクティビティを使用してデータを収集し、Campaignデータベースにインポートできます。 ワークフローを通じてデータをインポートする際の一般的な情報とベストプラクティスについては、[この節](../../automating/using/about-data-import-and-export.md)を参照してください。

さらに、データをインポートするためのテンプレートを設定することもできます。 同じ構造を持つファイルを定期的にインポートする必要がある場合は、インポートテンプレートを使用することをお勧めします。 次の2種類のテンプレートを設定できます。

* **ワークフローテンプレート**:これらは、必要に応じて一度設定し、データのインポートとデータベースの更新をおこなうたびに再利用できる、事前設定済みのワークフローです。データをインポートするワークフローテンプレートの例について詳しくは、[この節](../../automating/using/creating-import-workflow-templates.md)を参照してください。

* **データテンプレートのインポート**:ワークフローテンプレートと同様に、これらはワークフローに基づくテンプレートで、データベースを更新するためにファイルをアップロードするように設定されています。設定が完了すると、 **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**&#x200B;メニューの下に簡略表示が表示され、ユーザーが使用できるようになります。 データテンプレートのインポートについて詳しくは、[専用のドキュメント](../../automating/using/importing-data-with-import-templates.md)を参照してください。

### ランディングページからのデータの収集 {#collecting-data-from-landing-pages}

ランディングページとは、データを収集し、データベース内の既存の情報を作成または更新するために使用できるWebフォームです。 原則は次のとおりです。

* データ（名、姓、Eメールなど）を収集するための入力フィールドを追加して、ランディングページを作成およびデザインします。
* 各入力フィールドを、データベースの対応するフィールドにマッピングします。
* ランディングページを、Webサイト経由、またはメッセージへの直接リンクを通じてオンラインで使用できるようにします。

ランディングページについて詳しくは、[専用のドキュメント](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

**詳細情報**

* xxxx
* xxx

### Microsoft Dynamics 365からのプロファイルの同期

Microsoft Dynamics 365とのCampaign Standard統合により、Microsoft Dynamics 365の連絡先データをCampaignデータベースに渡すことができます。
これらの連絡先はプロファイルリストに表示され、マーケティングキャンペーンのターゲットに設定できます。 この統合について詳しくは、[専用のドキュメント](../../integrating/using/d365-acs-get-started.md)を参照してください。

>[!NOTE]
>
>Campaign Standard- Microsoft Dynamics 365コネクタは現在、使用が制限されています。このコネクタには、ドキュメントで詳しく説明されているいくつかの制限が適用されます。

**詳細情報**

* xxx
* xxx

### API呼び出しを使用したデータの読み込み

Campaign StandardAPIを使用すると、プロファイルやサービスの作成、更新、削除など、データベースを更新する操作を実行できます。 APIの使用方法について詳しくは、[専用のドキュメント](../../api/using/get-started-apis.md)を参照してください。

>[!CAUTION]
>
>API呼び出しを使用してプロファイルの一括作成または更新を実行する前に、使用許諾契約に対応するスケール制限を確認してください。 詳しくは、[このページ](https://helpx.adobe.com/jp/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers)を参照してください。

**詳細情報**

* xxx
* xxx

## オーディエンスの整理 {#organizing-audiences}

<img width="60px" alt="条件" src="assets/icon_audience.svg"/>

関連性の高い効果的なメッセージを配信し、顧客を効果的に惹きつけるために、Adobe Campaignは高度な分析とターゲティング機能を統合しています。

ワークフローとクエリエディターを使用すれば、様々なキャンペーンのターゲットとなるオーディエンスを、所有する情報、アクティビティ、言語、好み、マーケティング履歴に応じて構築できます。 これにより、例えば、購読しているプロファイルをフィルターしたり、ターゲットオーディエンスを無制限の数の条件で作成したりできます。

**詳細情報**

* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [オーディエンスの作成](../../audiences/using/creating-audiences.md)

## プライバシーの管理 {#privacy-management}

<img width="60px" alt="条件" src="assets/icon_privacy.svg"/>

GDPR は欧州連合（EU）にて新しく施行されるプライバシー保護法律で、データ保護要件を現代の状況に合わせて整合化することを目的としています。GDPR は、EU に居住しているデータ主体のデータを保有している Adobe Campaign の顧客に適用されます。Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）に加え、特定のGDPR要求に対するデータ管理者としての準備を容易にする追加機能をデータ処理者としてご利用いただけます。

Adobe CampaignがGDPRに準拠するために提供するツールと機能の詳細については、この[ガイド](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=ja)を参照してください。

**詳細情報**

* xxx
* xxx