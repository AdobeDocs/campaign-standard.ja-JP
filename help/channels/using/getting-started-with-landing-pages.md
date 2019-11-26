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
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# ランディングページの概要 {#getting-started-with-landing-pages}

## ランディングページについて {#about-landing-pages}

キャンペーンにはランディングページが付属しており、このページを使用してオーディエンスの情報を取得したり、サービスの購読を提供したり、データを表示したり、データベースを拡張したりできます。 ランディングページは、既存のプロファイルの取得や更新にも使用できます。

ランディングページを使用して、二重オプトインメカニズムを設定し、間違った電子メールアドレスや無効な電子メールアドレス、スパンボットからプラットフォームを保護することもできます。 For more on this, refer to the [dedicated use case](../../channels/using/setting-up-a-double-opt-in-process.md).

ランディングページを設定する際の主な手順は次のとおりです。

![](assets/lp_steps.png)

このページでは、これらの各手順に関する情報と、詳細についての専用ドキュメントへの参照を示します。

**関連トピック：**

* [ランディングページチュートリアルビデオの作成](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html) （英語のみ）
* [サービスの作成](../../audiences/using/creating-a-service.md)
* [ダブルオプトインプロセスの設定](setting-up-a-double-opt-in-process.md)

## ランディングページの制限{#landing-page-limitations}

以下の節では、ランディングページの設定を開始する前に考慮する必要がある制限事項を示します。

**データの書き込みと更新**

* ランディングページは、およびリソ **[!UICONTROL Profile]** ースに **[!UICONTROL Subscription]** のみ制限されます。 レコードは、の購読/購読解除から **[!UICONTROL Profile]** 保存および更新できます **[!UICONTROL Service]**。
リソース設定の詳細については、「リソースの [データ構造の設定」を参照してください](../../developing/using/configuring-the-resource-s-data-structure.md)。

>[!CAUTION]
>
>ランディングページは、および以外のリソースのデータを表示または更新すること **[!UICONTROL Profile]** はできま **[!UICONTROL Subscription]**&#x200B;せん。

**プリロード**

* ランディングページでは、レコードのリストを自動的に表示することはできません。既に登録されているプロファイルのサービスをリストすることはできません。 For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* 事前入力されたフォーム（データはページと共にプリロードされる）を含むランディングページには、Adobe Campaign電子メールからのみアクセスできます。 Webサイトページからこのようなフォームにアクセスすることはできません。

**紐付け**

* 調整の動作は次のとおりです。一致が見つかると、調整プロセスが停止します。 つまり、重複するレコードが存在する場合は、調整は1つのプロファイルレコードでのみ実行でき、複数のレコードでは実行できません。

例えば、次の獲得ランディングページをプロファイルに送信して、Campaignデータベースをプロファイルのモバイル番号で更新するとします。

![](assets/landing_page_limitation_1.png)

プロファイルの1つが新しい情報でランディングページに入力し、既に重複したプロファイルを持つ場合、作成日のみに基づいてプロファイルが優先されるので、作成日が最も古いプロファイルが更新されます。

最も古いエントリであったため、最初のプロファイルのみが更新されました。

![](assets/landing_page_limitation_2.png)

**ランディングページのテスト**

* ランディングページはプロファイルでのみ機能し、テストプロファイルでは機能しません。つまり、電子メールの校正の一部としてランディングページをテストすることはできません。

## 手順1 — ランディングページテンプレートを設定する {#configure-the-landing-page-template}

ランディングページを設定する前に、最初の手順は、ニーズに対応したランディングページテンプレートを設定することです。 テンプレートの準備が整うと、それに基づくすべてのランディングページが、必要なパラメーターで事前設定されます。

1. 詳細メニューのAdobe Campaignロゴで、 **[!UICONTROL Resources]** / **[!UICONTROL Templates]** /を選択 **[!UICONTROL Landing page templates]**&#x200B;し、使用するテンプレートを複製します。
1. テンプレートプロパティで、ランディングページに共通する必要のあるすべてのパラメーターを指定します。 例：ターゲットディメンション、識別された訪問者または識別されなかった訪問者のページアクセスパラメーター、訪問者によるフォーム検証に固有のアクション、コンテンツで使用するブランド/ロゴなど。 ランディングページのプロパティの詳細については、この節を参照 [してください](../../channels/using/configuring-landing-page.md)
1. 変更を保存します。

For more on landing page templates, refer to [this section](../../channels/using/getting-started-with-landing-pages.md).

![](assets/lp-steps1.png)

## 手順2 — ランディングページを作成し、設定する {#create-and-configure-the-landing-page}

前の手順で定義したテンプレートから、プログラムまたはキャンペーンに新しいランディングページを作成します。

1. 目的のテンプレートに基づいてランディングページを作成します。
1. ランディングページの一般的なパラメータ（ラベル、説明など）を入力します。
1. その後、ランディングページのダッシュボードにアクセスします。 必要に応じて、ランディングページのプロパティを編集します(「ラ [ンディングページの設定](../../channels/using/configuring-landing-page.md)」を参照)。 デフォルトでは、プロパティはランディングページテンプレートで設定されたプロパティです。
セキュリティ上の理由とプラットフォームパフォーマンス上の理由から、ランディングページのプロパティに有効期限を設定することを強くお勧めします。 完了すると、ランディングページは選択した日付に自動的に非公開になります。 For more on validity parameters, refer to [this section](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >変更は、編集中のランディングページに対してのみ有効です。 これらの変更を他のランディングページに適用する場合は、専用のテンプレートで実行し、そのテンプレートから他のランディングページを作成できます。

## 手順3 — ランディングページの設計 {#design-the-landing-page}

これで、ランディングページのコンテンツを定義できます。 デフォルトでは、ランディングページには、スクロール矢印を使用してアクセスできる3つのページが含まれています。メインコンテンツページ、確認ページおよびエラーページ。

![](assets/lp-steps4.png)

各ページには、デフォルトで複数のフィールドが設定されています。 必要に応じて、プロパティとマッピングを編集できます。

また、プロファイルが確認ボタンをクリックした場合の動作を設定し、必要に応じてコンテンツをパーソナライズする（画像、パーソナライゼーションフィールドなど）こともできます。 例えば、プロファイルの名をランディングページの確認ページに挿入し、登録に対する感謝の意を表すことができます。

ランディングページのデザインについて詳しくは、この節を参 [照してくださ](../../channels/using/designing-a-landing-page.md)い。

## 手順4 — ランディングページをテストする {#test-the-landing-page}

ランディングページを定義したら、オンラインで利用できる場合の実行方法や動作をシミュレートできます。

![](assets/lp-steps5.png)

>[!CAUTION]
>
>ランディングページのテストは、プロファイルでのみ実行でき、テストプロファイルでは実行できません。 フォームの送信中に、選択したプロファイルのデータが実際に更新されます。 実際のプロファイルの変更を避けるには、偽の顧客プロファイルを使用します。

ランディングページの動作に満足した場合は、ランディングページを公開してオンラインで利用できるようにします。

ランディングページのテスト方法の詳細については、この節を参照 [してください](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-)。

## ランディングページの公開手順 {#publish-the-landing-page}

テストが正常に完了したら、ダッシュボードのアクションバーのボタンを使用してラ **[!UICONTROL Publish]** ンディングページを公開できます。 監視ブロックは、パブリケーションの進行状況とステータスを示します。

ランディングページを公開すると、オンラインでアクセスできるようになります。 公開後は、いつでも更新できます。これを行うには、各変更後に再公開する必要があります。 また、ランディングページをいつでも非公開にして、使用できなくすることもできます。

![](assets/lp-steps6.png)

公開したランディングページを使用する準備が整います。 その後、様々なメカニズムを導入して、データベース内の新しいプロファイルを取得したり、既存のプロファイルに関する追加情報を取得したりできます。

ランディングページの投稿の詳細については、この節を参 [照してください](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page)。
