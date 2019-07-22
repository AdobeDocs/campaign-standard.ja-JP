---
title: ランディングページの制限
seo-title: ランディングページの制限
description: ランディングページの制限
seo-description: Discoverキャンペーンのランディングページとそのライフサイクル。
page-status-flag: 常にアクティブ化されていない
uuid: b316bf47-7d98-46fa- ab4f-67ff50de8095
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ランディングページ
discoiquuid: ca8d1698-6e8a-4f5a- b017-74a152e14286
context-tags: landingPage， wizard;landingPage， overview;landingPage， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5dbb89eca363f252d0c69126878d4f79320e0f19

---


# Landing page limitations{#landing-page-limitations}

**データの書き込みと更新**

* Landing pages are limited to **[!UICONTROL Profile]** and **[!UICONTROL Subscription]** resources only. Record can be saved and updated from **[!UICONTROL Profile]** and a subscription/unsubscription to a **[!UICONTROL Service]**.
To learn more on resources configuration, see [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!CAUTION]
>
>A landing page cannot display or update data from any other resource than **[!UICONTROL Profile]** and **[!UICONTROL Subscription]**.

**プリロード**

* ランディングページにはレコードのリストを自動的に表示できないので、既に登録されているサービスをリストすることはできません。For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* 事前入力済みのフォームを含むランディングページ（データがページにプリロードされた場合）は、Adobe Campaign電子メールからのみアクセスできます。Webサイトページからこのようなフォームにアクセスすることはできません。

**紐付け**

* 紐付け動作は次のとおりです。一致が見つかったら、紐付けプロセスが停止します。つまり、紐付けは1つのプロファイルレコードでのみ実行でき、重複がある場合は複数のレコードでは実行できません。

例えば、次の獲得ランディングページをプロファイルに送信してプロファイルのモバイル番号をキャンペーンデータベースに更新するとします。

![](assets/landing_page_limitation_1.png)

プロファイルの1つが新しい情報でランディングページに入力され、既に重複したプロファイルがある場合、プロファイルの作成日のみに応じてプロファイルが優先化されるので、一致するプロファイルは更新されます。

ここでは、最初のプロファイルのみが最も古いエントリのために更新されました。

![](assets/landing_page_limitation_2.png)

**ランディングページのテスト**

* ランディングページはプロファイルでのみ機能し、プロファイルをテストしません。つまり、ランディングページは電子メールの配達確認の一部としてテストできません。
