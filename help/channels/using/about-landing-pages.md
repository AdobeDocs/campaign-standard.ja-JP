---
title: ランディングページについて
description: Discover Campaignのランディングページとそのライフサイクル。
page-status-flag: 非活性化の
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ランディングページ
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# ランディングページについて{#about-landing-pages}

キャンペーンにはランディングページが付属しており、このページを使用してオーディエンスの情報を取得したり、サービスの購読を提供したり、データを表示したり、データベースを拡張したりできます。 ランディングページは、既存のプロファイルの取得や更新にも使用できます。

ランディングページを設定するために必要な手順の詳細については、この節を参照し [てください](../../channels/using/main-steps-to-set-up-a-landing-page.md)

**関連トピック：**

* [ランディングページチュートリアルビデオの作成](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html) （英語のみ）
* [ランディングページを使用したサービスの購読](../../audiences/using/creating-a-service.md)

## ランディングページのライフサイクル {#landing-pages-life-cycle}

ランディングページの完全なライフサイクルは次のとおりです。

1. 作成：ランディングページのコンテンツを設計および設定します。
1. テスト：テストプロファイルでのランディングページの実行をシミュレートします。
1. パブリケーション：ランディングページを公開してライブにプッシュします。
1. 有効期限または公開停止：手動で非公開にするか、ランディングページの有効期限が切れるまで待つと、使用できなくなります。

![](assets/lp_livecycle.png)

作成して発行すると、ランディングページをWebサイト経由でアクセス可能にするか、ランディングペ [ージへの直接リンクを電子メールに挿入することができます](../../designing/using/links.md#inserting-a-link)。

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
