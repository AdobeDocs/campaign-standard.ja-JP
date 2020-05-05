---
title: ランディングページを設定するための主な手順
description: ランディングページを設定する主な手順を説明します。
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0dd69cbad3e05a5a7eb36da80264e6eb6aae0e34

---


# ランディングページの概要 {#getting-started-with-landing-pages}

ランディングページを設定する際の主な手順は次のとおりです。

![](assets/lp_steps.png)

このページでは、各手順の情報と、詳細についての専用ドキュメントの参照情報を示します。

**関連トピック：**

* [ランディングページチュートリアルビデオの作成](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/landing-pages/landing-page-create-and-edit.html) （英語のみ）
* [サービスの作成](../../audiences/using/creating-a-service.md)
* [ダブルオプトインプロセスの設定](setting-up-a-double-opt-in-process.md)

## ランディングページ制限{#landing-page-limitations}

以下の節では、ランディングページの設定を開始する前に考慮する必要がある制限についてリストします。

**データの書き込みと更新**

* ランディングページは、 **[!UICONTROL Profile]** および **[!UICONTROL Subscription]** リソースにのみ制限されます。 レコードは、購読 **[!UICONTROL Profile]** や購読解除からに保存および更新でき **[!UICONTROL Service]**ます。
リソース設定の詳細については、「リソースのデータ構造の [設定](../../developing/using/configuring-the-resource-s-data-structure.md)」を参照してください。

>[!CAUTION]
>
>ランディングページは、および以外のリソースのデータを表示または更新す **[!UICONTROL Profile]** ることはできません **[!UICONTROL Subscription]**。

**プリロード**

* ランディングページは、レコードのリストを自動的に表示できません。プロファイルが既に登録しているリストサービスは表示できません。 For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* 事前入力されたフォーム（データはページと共にプリロードされる）を持つランディングページは、Adobe Campaignの電子メールからのみアクセスできます。 Webサイトページからは、このようなフォームにアクセスできません。

**紐付け**

* 調整の動作は次のとおりです。 一致が見つかると、調整プロセスが停止します。 つまり、調整は1つのプロファイルレコードに対してのみ実行でき、重複が発生した場合は複数のレコードに対しては実行できません。

例えば、次のダウンロード計測ランディングページをプロファイルに送信して、キャンペーンデータベースをプロファイルのモバイル番号に更新するとします。

![](assets/landing_page_limitation_1.png)

プロファイルの1人が新しい情報をランディングページに入力し、既にプロファイルが重複している場合は、作成日のみに基づいてプロファイルが優先されるので、一致するプロファイルが最も早い作成日に更新されます。

ここでは最古のプロファイルであるため、最初の項目のみが更新された。

![](assets/landing_page_limitation_2.png)

**ランディングページのテスト**

* ランディングページはプロファイルーでのみ機能し、テストプロファイルは機能しません。つまり、ランディングページを電子メール配達確認の一部としてテストすることはできません。

## 手順1 -ランディングページテンプレートを設定する {#configure-the-landing-page-template}

ランディングページを設定する前に、まず、必要に応じてランディングページテンプレートを設定します。 テンプレートの準備が整うと、テンプレートに基づくすべてのランディングページが、必要なパラメーターで事前設定されます。

1. 詳細設定メニューのAdobe Campaignロゴから、 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** /を選択 **[!UICONTROL Landing page templates]**&#x200B;し、使用するテンプレートを重複します。
1. テンプレートプロパティで、ランディングページに共通する必要のあるすべてのパラメーターを指定します。 次に例を示します。 ターゲティングディメンション、識別されたユーザーまたは識別されなかった訪問者のページアクセスパラメーター、訪問者による検証フォームに固有のアクション、コンテンツで使用するブランド/ロゴなど。 ランディングページのプロパティについて詳しくは、 [この節を参照してください](../../channels/using/configuring-landing-page.md)
1. 変更を保存します。

For more on landing page templates, refer to [this section](../../channels/using/getting-started-with-landing-pages.md).

![](assets/lp-steps1.png)

## 手順2 -ランディングページの作成と設定 {#create-and-configure-the-landing-page}

前の手順で定義したテンプレートから、プログラムまたはキャンペーンに新しいランディングページを作成します。

1. 目的のテンプレートに基づいてランディングページを作成します。
1. ランディングページの一般的なパラメータ（ラベル、説明など）を入力します。
1. その後、ランディングページダッシュボードにアクセスします。 必要に応じて、ランディングページのプロパティを編集します(ランディングページの [設定を参照](../../channels/using/configuring-landing-page.md))。 デフォルトでは、プロパティはランディングページテンプレートで設定されたプロパティです。
セキュリティ上の理由とプラットフォームのパフォーマンス上、有効期限はランディングページのプロパティで設定することを強くお勧めします。 完了すると、ランディングページは選択した日付に自動的に非公開になります。 For more on validity parameters, refer to [this section](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >変更は、編集中のランディングページに対してのみ有効です。 これらの変更を他のランディングページに適用する場合は、専用のテンプレートで実行し、そのテンプレートから他のランディングページを作成できます。

## 手順3 -ランディングページを設計する {#design-the-landing-page}

これで、ランディングページのコンテンツを定義できます。 デフォルトでは、ランディングページには次の3つのページが含まれており、これらはスクロールする矢印を使用してアクセスできます。 メインコンテンツページ、確認ページ、エラーページ。

![](assets/lp-steps4.png)

各ページでは、デフォルトで複数のフィールドが設定されています。 必要に応じて、プロパティとマッピングを編集できます。

また、プロファイルが確認ボタンをクリックした場合の動作を設定し、必要に応じてコンテンツ(画像、パーソナライゼーションフィールドなど)をパーソナライズすることもできます。 例えば、プロファイルの名をランディングページの確認ページに挿入して、登録していただきありがとうございます。

ランディングページデザインの詳細については、 [この節を参照してください](../../channels/using/designing-a-landing-page.md)。

## 手順4 -ランディングページをテストする {#test-the-landing-page}

ランディングページを定義したら、オンラインで利用できる場合に、その実行や動作をシミュレートできます。

![](assets/lp-steps5.png)

>[!CAUTION]
>
>ランディングページテストは、プロファイルでのみ実行でき、テストプロファイルでは実行できません。 フォームが送信されると、選択したプロファイルのデータが実際に更新されます。 実際のプロファイルを変更しないようにするには、偽の顧客プロファイルを使用します。

ランディングページの動作に満足した場合は、その画像を公開してオンラインで利用できます。

ランディングページのテスト方法の詳細については、 [この節を参照してください](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-)。

## 手順5 -ランディングページを公開する {#publish-the-landing-page}

テストが成功したら、ダッシュボードのアクションバーの **[!UICONTROL Publish]** ボタンを使用してランディングページを公開できます。 監視ブロックは、パブリケーションの進行状況とステータスを示します。

ランディングページを公開すると、オンラインでアクセスできるようになります。 公開後は、いつでも更新できます。 これを行うには、変更のたびに再公開する必要があります。 また、ランディングページを公開停止して使用できなくすることもできます。

![](assets/lp-steps6.png)

公開したランディングページは、使用できる状態になります。 その後、異なるメカニズムを導入して、データベース内の新しいプロファイルを取得したり、既存のプロファイルに関する追加情報を取得したりできます。

ランディングページの公開について詳しくは、 [この節を参照してください](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page)。
