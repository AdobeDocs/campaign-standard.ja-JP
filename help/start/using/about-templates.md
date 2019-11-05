---
title: テンプレートについて
description: 「Adobe Campaignテンプレートを使用すると、必要に応じて次のパラメーターを事前設定できます。テンプレートには、マーケティング活動の完全な設定または一部の設定を含めることができ、技術的でないエンドユーザー向けのAdobe Campaignの使用を簡素化できます。」
page-status-flag: 非活性化の
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開始
content-type: 参照
topic-tags: 管理テンプレート
discoiquuid: 95218ebe-5430-42a2-b900-1dadbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# テンプレートについて{#about-templates}

## マーケティング活動テンプレート {#marketing-activity-templates}

新しいマーケティングアクティビティを作成すると、ウィザードの最初の画面で、タイプまたはテンプレートを選択するよう求められます。 テンプレートを使用すると、ニーズに応じて特定のパラメーターを事前設定できます。 テンプレートには、マーケティングアクティビティの完全な設定または部分的な設定を含めることができます。 テンプレート管理は、機能管理者が実行します。

エンドユーザーのインターフェイスがシンプルになりました。 新しいマーケティングアクティビティを作成する場合は、使用するテンプレートを選択するだけで済みます。 技術的な構成について心配する必要はありません。 これは、テンプレートの機能管理者によって事前に設定されています。

例えば、電子メールテンプレートの場合、HTMLコンテンツ、オーディエンス、および配信のその他のパラメーターに事前入力できます。スケジュール、テストプロファイル、配信の一般的なプロパティ、高度なパラメーターなど これにより、新しいアクティビティを作成する際の時間を節約できます。

![](assets/template_1.png)

マーケティングアクティビティのタイプごとに、あらかじめ用意されている1つまたは複数のテンプレートを最小限の設定で使用できます。 これらの標準テンプレートは変更または削除できません。

テンプレートは、次のマーケティング活動で使用できます。

* プログラム
* キャンペーン
* E メール配信
* SMS配信
* プッシュ通知
* ランディングページ
* ワークフロー
* サービス
* インポート
* トランザクションメッセージ

これらのテンプレートは、/画面で **[!UICONTROL Resources]** 管理さ **[!UICONTROL Templates]** れます。

>[!NOTE]
>
>ブランド設定は、電子メールまたはランディングページテンプレートで事前設定できます。 For more information, refer to the [Branding](../../administration/using/branding.md) section.

## コンテンツテンプレート {#content-templates}

HTMLコンテンツテンプレートは、詳細メニューの/ **[!UICONTROL Resources]** 画面か **[!UICONTROL Content templates & fragments]** らアクセ [スできます](../../start/using/interface-description.md#advanced-menu)。 ここから、ランディングページのコンテンツテンプレート、電子メールコンテンツテンプレートおよびフラグメントを管理できます。

![](assets/content_templates_list.png)

そのまま使用できるコンテンツテンプレートは読み取り専用です。 いずれかのテンプレートを編集するには、まず目的のテンプレートを複製する必要があります。

新しいテンプレートまたはフラグメントを作成し、独自のコンテンツを定義できます。 詳しくは、「コンテンツテンプレートの作 [成」および「コンテンツ](#creating-a-content-template) フラグメ [ントの作成」を参照してください](../../designing/using/using-reusable-content.md#creating-a-content-fragment)。

電子メールデザイナーでコンテンツを編集する場合は、コンテンツをフラグメントまたはテンプレートとして保存して、コンテンツテンプレートを作成することもできます。 詳しくは、「コンテンツをテンプレートとし [て保存」および「コンテンツをフ](#saving-content-as-template) ラグメ [ントとして保存」を参照してくださ](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)い。

### 標準搭載の電子メールコンテンツテンプレート {#email-content-templates}

電子メールデザイナーのホームページのタブで提供さ **[!UICONTROL Templates]** れるHTMLコンテ [ンツを管理できます](../../designing/using/overview.md) 。

標準搭載の電子メールコンテンツテンプレートには、モバイルに最適化された18種類のレイアウトと、Behanceのアーティストがデザインしたクラス最高の4つのレスポンシブテンプレートが含まれています。 これらは、お客様のお知らせメッセージ、ニュースレター、リエンゲージメント電子メールなど、最新の使用に対応しています。 ブランドのコンテンツを使用して簡単にカスタマイズでき、一から電子メールをデザインするプロセスを簡単に実行できます。

![](assets/content_templates.png)

**関連トピック：**

* このビデオでは、コンテンツテンプレートをパーソナラ [イズする方法を説明しま](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html)す。
* コンテンツの編集について詳しくは、電子メールコンテンツデザ [インについてを参照してくださ](../../designing/using/overview.md)い。

### Creating a content template {#creating-a-content-template}

独自のコンテンツテンプレートを作成して、必要な回数だけ使用できます。

次の例は、電子メールコンテンツテンプレートの作成方法を示しています。

1. /に移動し、 **[!UICONTROL Resources]** をク **[!UICONTROL Content templates & fragments]** リックしま **[!UICONTROL Create]**&#x200B;す。
1. 電子メールラベルをクリックして、電子メー **[!UICONTROL Properties]** ルデザイナーのタブにアクセスします。
1. 認識可能なラベルを指定し、次のパラメーターを選択して、電子メールでこのテンプレートを使用できるようにします。

   * ドロッ **[!UICONTROL Shared]** プダウン **[!UICONTROL Delivery]** リストから **[!UICONTROL Content type]** またはを選択します。
   * ドロッ **[!UICONTROL Template]** プダウンリスト **[!UICONTROL HTML type]** から選択します。
   ![](assets/email_designer_create-template.png)

1. 必要に応じて、テンプレートのサムネールとして使用する画像を設定できます。 テンプレートプロパティの **[!UICONTROL Thumbnail]** タブから選択します。

   ![](assets/email_designer_create-template_thumbnail.png)

   このサムネールは、電子メールデザイナ **[!UICONTROL Templates]** ーのホームページの [タブに表示されます](../../designing/using/overview.md) 。

1. タブを閉じ **[!UICONTROL Properties]** て、メインのワークスペースに戻ります。
1. 必要に応じてカスタマイズ可能な構造コンポーネントとコンテンツコンポーネントを追加します。
   >[!NOTE]
   >
   > コンテンツテンプレート内にパーソナライゼーションフィールドや条件付きコンテンツを挿入することはできません。
1. 編集が完了したら、テンプレートを保存します。

このテンプレートは、電子メールデザイナーで作成された任意の電子メールで使用できるようになりました。 電子メールデザイナ **[!UICONTROL Templates]** ーのホームページ [のタブから](../../designing/using/overview.md) 選択します。

![](assets/content_template_new.png)

### コンテンツをテンプレートとして保存中 {#saving-content-as-template}

電子メールデザイナーで電子メールを編集する場合は、その電子メールの内容をテンプレートとして直接保存できます。

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. 電子メール **[!UICONTROL Save as template]** デザイナのメインツールバーから選択します。

   ![](assets/email_designer_save-as-template.png)

1. 必要に応じてラベルと説明を追加し、をクリックしま **[!UICONTROL Save]**&#x200B;す。

   ![](assets/email_designer_save-as-template_creation.png)

1. 作成したテンプレートを探すには、/に移動し **[!UICONTROL Resources]** ます **[!UICONTROL Content templates & fragments]**。

1. 新しいテンプレートを使用するには、電子メールデザイナ **[!UICONTROL Templates]** ーのホームページの [タブから](../../designing/using/overview.md) 、テンプレートを選択します。

   ![](assets/content_template_new.png)

