---
title: ランディングページを設定するための主な手順
description: ランディングページを設定するための主な手順について説明します
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
source-git-commit: c300f50ce83d67be7c8a16f857eb46fb1ce89166
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 99%

---


# ランディングページの概要 {#getting-started-with-landing-pages}

ランディングページを設定するための主な手順は次のとおりです。

![](assets/lp_steps.png)

このページでは、各手順の情報と、詳細情報を参照できる関連ドキュメントを紹介します。

**関連トピック：**

* [ランディングページチュートリアルビデオの作成](https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/communication-channels/landing-pages/landing-page-create-and-edit.translate.html)
* [サービスの作成](../../audiences/using/creating-a-service.md)
* [ダブルオプトインプロセスの設定](setting-up-a-double-opt-in-process.md)

## ランディングページの制限{#landing-page-limitations}

以下の節では、ランディングページの設定を開始する前に考慮する必要がある制限について説明します。

**データの書き込みと更新**

* ランディングページは、**[!UICONTROL Profile]** リソースおよび **[!UICONTROL Subscription]** リソースのみに制限されています。レコードは **[!UICONTROL Profile]** から保存および更新でき、**[!UICONTROL Service]** の購読および購読解除が可能です。
リソース設定について詳しくは、[リソースのデータ構造の設定](../../developing/using/configuring-the-resource-s-data-structure.md)を参照してください。

>[!CAUTION]
>
>ランディングページは、**[!UICONTROL Profile]** および **[!UICONTROL Subscription]** 以外のリソースのデータを表示または更新することはできません。

**プリロード**

* ランディングページは、レコードのリストを自動的に表示できません。また、プロファイルが既に購読しているサービスのリストを表示できません。サービスについて詳しくは、[このページ](../../audiences/using/creating-a-service.md)を参照してください。

* 事前入力されたフォーム（データはページと共にプリロードされる）を持つランディングページは、Adobe Campaign の E メールからのみアクセスできます。Web サイトページからは、このようなフォームにアクセスできません。

**紐付け**

* 紐付け機能について説明します。一致が見つかると、紐付けプロセスは停止します。つまり、紐付けは 1 つのプロファイルレコードに対してのみ実行でき、重複が発生した場合は複数のレコードに対して紐付けを実行できません。

例えば、次の獲得ランディングページをプロファイルに送信して、Campaign データベースをプロファイルの携帯電話番号で更新するとします。

![](assets/landing_page_limitation_1.png)

プロファイルのいずれかがランディングページに新しい情報を入力したものの、既に重複するプロファイルが存在する場合、プロファイルは作成日のみに基づいて優先順位付けされるので、作成日が早いプロファイルが更新されます。

ここでは、作成日が最も古い最初のプロファイルのみが更新されました。

![](assets/landing_page_limitation_2.png)

**ランディングページのテスト**

* ランディングページはプロファイルでのみ機能し、テストプロファイルでは機能しません。つまり、ランディングページを E メール配達確認の一部としてテストすることはできません。

## 手順 1 - ランディングページテンプレートの設定 {#configure-the-landing-page-template}

ランディングページを設定する前に、必要に応じてランディングページテンプレートを設定します。テンプレートの設定が完了すると、テンプレートに基づくすべてのランディングページが、任意のパラメーターで事前設定されます。

1. 詳細設定メニューの Adobe Campaign ロゴから、**[!UICONTROL Resources]**／**[!UICONTROL Templates]**／**[!UICONTROL Landing page templates]** を選択し、使用するテンプレートを複製します。
1. テンプレートプロパティで、ランディングページに共通する必要のあるすべてのパラメーターを指定します。例：ターゲティングディメンション、識別された訪問者または識別されなかった訪問者のページアクセスパラメーター、訪問者によるフォーム検証に固有のアクション、コンテンツで使用するブランドやロゴなど。ランディングページのプロパティについて詳しくは、[この節](../../channels/using/configuring-landing-page.md)を参照してください。
1. 変更を保存します。

ランディングページテンプレートについて詳しくは、[この節](../../channels/using/getting-started-with-landing-pages.md)を参照してください。

![](assets/lp-steps1.png)

## 手順 2 - ランディングページの作成と設定 {#create-and-configure-the-landing-page}

前の手順で定義したテンプレートを使用して、プログラムまたはキャンペーンに新しいランディングページを作成します。

1. 適切なテンプレートに基づいてランディングページを作成します。
1. ランディングページの一般的なパラメーター（ラベル、説明など）を入力します。
1. ランディングページダッシュボードにアクセスします。必要に応じて、ランディングページのプロパティを編集します（[ランディングページの設定](../../channels/using/configuring-landing-page.md)を参照）。デフォルトでは、プロパティはランディングページテンプレートで設定されたプロパティです。
セキュリティ上の理由とプラットフォームのパフォーマンス上の理由により、ランディングページのプロパティで有効期限を設定することを強くお勧めします。有効期限を設定すると、ランディングページは選択した日付に自動的に非公開になります。有効期限パラメーターについて詳しくは、[この節](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters)を参照してください。

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >変更は、編集中のランディングページに対してのみ有効です。これらの変更を他のランディングページに適用する場合は、該当するテンプレートを変更し、そのテンプレートから他のランディングページを作成できます。

## 手順 3 - ランディングページのデザイン {#design-the-landing-page}

ランディングページのコンテンツを定義できます。デフォルトでは、ランディングページには、メインコンテンツページ、確認ページ、エラーページの 3 つのページが含まれており、スクロールする矢印を使用してアクセスできます。

![](assets/lp-steps4.png)

各ページでは、デフォルトで複数のフィールドが設定されています。必要に応じて、プロパティとマッピングを編集できます。

また、プロファイルが確認ボタンをクリックした場合の動作を設定し、必要に応じてコンテンツ（画像、パーソナライゼーションフィールドなど）をパーソナライズすることもできます。例えば、プロファイルの名をランディングページの確認ページに挿入して、登録の御礼メッセージを表示できます。

ランディングページのデザインについて詳しくは、[この節](../../channels/using/designing-a-landing-page.md)を参照してください。

## 手順 4 - ランディングページのテスト {#test-the-landing-page}

ランディングページを定義したら、オンライン上での稼働状況や動作をシミュレートできます。

![](assets/lp-steps5.png)

>[!CAUTION]
>
>ランディングページのテストはプロファイルでのみ実行でき、テストプロファイルでは実行できません。フォームが送信されると、選択したプロファイルのデータが実際に更新されます。実際のプロファイルを変更しないようにするには、架空の顧客プロファイルを使用します。

ランディングページの動作が正常であることを確認したら、公開してオンラインで利用できるようにします。

ランディングページのテスト方法について詳しくは、[この節](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-)を参照してください。

## 手順 5 - ランディングページの公開 {#publish-the-landing-page}

テストが成功したら、ダッシュボードのアクションバーの「**[!UICONTROL Publish]**」ボタンを使用してランディングページを公開できます。監視ブロックは、公開の進行状況とステータスを示します。

ランディングページを公開すると、オンラインでアクセスできるようになります。ランディングページは、公開後にいつでも更新できます。更新するたびに再公開が必要です。また、ランディングページはいつでも非公開にすることができます。非公開にすると、オンラインで利用できなくなります。

![](assets/lp-steps6.png)

ランディングページを公開すると、オンラインで利用できる状態になります。その後、異なるメカニズムを導入して、データベース内の新しいプロファイルを取得したり、既存のプロファイルに関する追加情報を取得できます。

ランディングページの公開について詳しくは、[この節](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page)を参照してください。
