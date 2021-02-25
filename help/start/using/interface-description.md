---
solution: Campaign Standard
product: campaign
title: インターフェイスの説明
description: Adobe Campaign ワークスペースのホームページ、上部バー、詳細設定メニュー、アクションバーのナビゲーションおよび使用方法について説明します。
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 05a44f5baa66df70a57da9467baf71a953aed856
workflow-type: tm+mt
source-wordcount: '1289'
ht-degree: 92%

---


# インターフェイスの説明{#interface-description}

Adobe Campaign を使用すると、様々なメニューや画面を移動してキャンペーンを管理できます。

すべての Adobe Campaign 画面は、以下の要素で構成されています。

* ナビゲーション用の上部バー
* 特定の機能と設定にアクセスするための高度なメニュー
* 特定の要素を操作する中央ゾーン
* 表示された要素内のフィルタリングや検索をおこなうための、コンテキストに応じた横置きパネル

![](assets/ux_interface_01.png)

## ホームページ {#home-page}

Campaign ホームページは、主な Adobe Campaign 機能にすばやくアクセスできるカードのセットで構成されています。表示される内容は、権限と組織に設定されているオプションによって異なります。

![](assets/overview_home_page.png)

* 「**[!UICONTROL Create an email]**」カードを選択すると、E メール作成アシスタントが表示されます。このアシスタントでは、E メールのタイプの選択、メッセージ受信者の選択、コンテンツの定義をおこなうことができます。[E メールの作成](../../channels/using/creating-an-email.md)の節を参照してください。
* 「**[!UICONTROL Create an SMS]**」カードを選択すると、SMS 作成アシスタントが表示されます。このアシスタントでは、SMS のタイプの選択、メッセージ受信者の選択、コンテンツの定義をおこなうことができます。[SMS の作成](../../channels/using/creating-an-sms-message.md)の節を参照してください。
* 「**[!UICONTROL Create a Direct mail]**」カードを選択すると、ダイレクトメール作成アシスタントが表示されます。[ダイレクトメールの作成](../../channels/using/creating-the-direct-mail.md)を参照してください。
* 「**[!UICONTROL Create a push notification]**」カードを選択すると、通知作成アシスタントが表示されます。このアシスタントではプッシュ通知のタイプの選択、メッセージ受信者の選択、コンテンツの定義をおこなうことができます。[プッシュ通知の作成](../../channels/using/preparing-and-sending-a-push-notification.md)を参照してください。
* **[!UICONTROL Create an In-App message]**&#x200B;カードを使用すると、App内作成アシスタントが表示されます。 このアシスタントでは、作成するアプリ内メッセージのタイプを選択し、そのプロパティ、オーディエンスおよびコンテンツを定義できます。 「[アプリ内メッセージの作成](../../channels/using/about-in-app-messaging.md)」の節を参照してください。
* 「**[!UICONTROL Marketing activities]**「」カードを選択すると、すべてのアクティビティ、プログラムおよびキャンペーン、特に E メール、SMS、ワークフロー、ランディングページの一覧が表示されます。ここから、名前、日付、ステータスまたはアクティビティタイプで検索して、要素をフィルタリングできます。詳しくは、[マーケティングアクティビティリスト](../../start/using/marketing-activities.md#about-marketing-activities)の節を参照してください。
* 「**[!UICONTROL Programs & campaigns]**」カードを選択すると、キャンペーンを作成、管理できるプログラムのリストに移動します。[プログラムリスト](../../start/using/programs-and-campaigns.md#about-plans--programs-and-campaigns)を参照してください。
* 「**[!UICONTROL Timeline]**」カードを使用すると、マーケティングアクティビティのインタラクティブなタイムラインに直接移動し、進行中のプログラムとそのコンテンツを参照することができます。[タイムライン](../../start/using/timeline.md)を参照してください。
* 「**[!UICONTROL Customer profiles]**」カードを選択すると、プロファイルのリストに直接移動します。ここから、リスト内の各プロファイルに関するイベントを参照できます。[プロファイルの管理](../../audiences/using/about-profiles.md)を参照してください。
* 「**[!UICONTROL Audiences]**」カードを選択すると、オーディエンスのリストに直接移動します。ここから、既存のオーディエンスにアクセスしたり、新しいオーディエンスを作成したりできます。[オーディエンスの管理](../../audiences/using/about-audiences.md)を参照してください。

## 上部バー {#top-bar}

上部バーは各画面に表示され、Adobe Campaign機能間を移動できるほか、Adobeプロファイル、通知、Adobe Experience Cloudのソリューション、およびキャンペーンに関するドキュメントにアクセスできます。

ナビゲーションは原則として次のとおりです。

* ページの左上隅にある **[!UICONTROL Adobe Campaign]** ロゴを使用すると、高度な機能と設定にアクセスできます。表示されるメニューは、プロファイルと権限に応じて異なります。

   詳細設定メニューについては、[詳細設定メニュー](#advanced-menu)の節を参照してください。

* 「**[!UICONTROL Home]**」リンクをクリックすると、Adobe Campaign ホームページが表示されます。
* 「**[!UICONTROL Marketing activities]**」、「**[!UICONTROL Programs & Campaigns]**」、「**[!UICONTROL Profiles]**」、「**[!UICONTROL Audiences]**」、「**[!UICONTROL Reports]**」の各リンクをクリックすると、これらの機能にリンクされた画面にアクセスできます。
* **ソリューション切り替えボタン**&#x200B;を使用すると、組織または別のアプリケーションに切り替えることができます。
* **[!UICONTROL Help]**&#x200B;アイコンは[](#help)の下に記述されています。
* **通知**&#x200B;アイコンには、最新のアラートまたは情報が表示されます。
* **ユーザー**&#x200B;アイコンをクリックすると、ユーザープロファイルにリンクされた情報を表示できます。**[!UICONTROL Sign out]**&#x200B;する必要がある場合は、このアイコンを使用します。

### ヘルプ {#help}

上部バーはすべての画面に表示され、Adobe Campaign 機能を操作できるほか、接続されている Adobe プロファイル、通知、その他の Adobe Experience Cloud サービスおよびソリューション、ドキュメントにアクセスできます。

ナビゲーションは原則として次のとおりです。

* ページの左上隅にある **[!UICONTROL Adobe Campaign]** ロゴを使用すると、高度な機能と設定にアクセスできます。表示されるメニューは、プロファイルと権限に応じて異なります。

   詳細設定メニューについては、[詳細設定メニュー](#advanced-menu)の節を参照してください。

* 「**[!UICONTROL Home]**」リンクをクリックすると、Adobe Campaign ホームページが表示されます。
* 「**[!UICONTROL Marketing activities]**」、「**[!UICONTROL Programs & Campaigns]**」、「**[!UICONTROL Profiles]**」、「**[!UICONTROL Audiences]**」、「**[!UICONTROL Reports]**」の各リンクをクリックすると、これらの機能にリンクされた画面にアクセスできます。
* 「**[!UICONTROL Help]**」ボタンをクリックすると、製品ドキュメントやコンテキストヘルプ、リリースノート、バージョン番号、法律上の注意事項に加え、Adobe Experience Cloud のコミュニティやカスタマーケアへのリンクにアクセスできます。

   ![](assets/ux_help.png)

* **ソリューション選択**&#x200B;アイコンをクリックすると、別の Adobe Experience Cloud ソリューションに切り替えることができます。また、プロファイル設定に切り替えることもできます。
* **通知**&#x200B;アイコンには、最新のアラートまたは情報が表示されます。
* **ユーザー**&#x200B;アイコンをクリックすると、ユーザープロファイルにリンクされた情報を表示できます。「**[!UICONTROL Sign out]**」ボタンにアクセスできます。

## 詳細設定メニュー {#advanced-menu}

詳細設定メニューは、各画面の左上隅にある **Adobe Campaign** アイコンをクリックすると表示されます。詳細設定メニューは、契約内容やユーザー権限によって異なる場合があります。

このメニューを使用すると、特定の機能や設定に移動できます。

### マーケティングプラン {#marketing-plans}

**[!UICONTROL Marketing plans]**&#x200B;アイコンをクリックすると、次の機能にアクセスできます。

* **[!UICONTROL Marketing activities]**：詳しくは、[マーケティングアクティビティリスト](../../start/using/marketing-activities.md#about-marketing-activities)の節を参照してください。
* **[!UICONTROL Programs & Campaigns]**：詳しくは、[プログラムリスト](../../start/using/programs-and-campaigns.md#about-plans--programs-and-campaigns)の節を参照してください。
* **[!UICONTROL Timeline]**：詳しくは、[タイムライン](../../start/using/timeline.md)の節を参照してください。
* **[!UICONTROL Transactional messages]**（サブメニュー&#x200B;**[!UICONTROL Deliveries]**&#x200B;および&#x200B;**[!UICONTROL Event configuration]**&#x200B;を含む）：詳しくは、[トランザクションメッセージ](../../channels/using/getting-started-with-transactional-msg.md)の節を参照してください。

### プロファイルおよびオーディエンス {#profiles-e-audiences}

**[!UICONTROL Profiles & audiences]**&#x200B;アイコンを使用すると、次の機能にアクセスできます。

* **[!UICONTROL Profiles]**：詳しくは、[プロファイルの管理](../../audiences/using/about-profiles.md)の節を参照してください。
* **[!UICONTROL Test profiles]**：詳しくは、[テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)の節を参照してください。
* **[!UICONTROL Audiences]**：詳しくは、[オーディエンスの管理](../../audiences/using/about-audiences.md)の節を参照してください。
* **[!UICONTROL Services]**&#x200B;詳しくは、[サービスの作成](../../audiences/using/creating-a-service.md)の節を参照してください。

### リソース {#resources}

**[!UICONTROL Resources]**&#x200B;アイコンを使用すると、次の機能にアクセスできます。

* **[!UICONTROL Templates]**（テンプレートタイプ別のサブメニューを含む）：詳しくは、[テンプレートの管理](../../start/using/marketing-activity-templates.md)の節を参照してください。
* **[!UICONTROL Content blocks]**：詳しくは、[コンテンツブロックの追加](../../designing/using/personalization.md#adding-a-content-block)の節を参照してください。
* **[!UICONTROL Content templates & fragments]**：詳しくは、[コンテンツテンプレート](../../designing/using/using-reusable-content.md#content-templates)の節を参照してください。

### 管理 {#administration}

**[!UICONTROL Administration]**&#x200B;アイコンを使用すると、機能管理者のみが実行できる高度な機能にアクセスできます。詳しくは、[管理](../../administration/using/get-started-campaign-administration.md)の節を参照してください。

## 中央ゾーン {#central-zone}

ユーザーインターフェイスの中央には、要素のリストやカードのセットなどを含んだ動的ゾーンがあります。既存の要素を編集したり、リソースを作成したりできます。

![](assets/ux_genericscreen.png)

中央ゾーンのコンテンツと表示形式は次のように異なる場合があります。

* **リスト**：プログラム、キャンペーン、プロファイルなどの様々な要素の一覧を示します。これらの要素は&#x200B;**[!UICONTROL Card]**&#x200B;または&#x200B;**[!UICONTROL List]**&#x200B;モードで表示できます。切り替えモードボタンを使用して、切り替えをおこないます。各要素には、インジケーターが表示されます。

   ![](assets/ux_liste.png)

   カウンターを使用すると、要素の数を把握できます。この数が 30 を超える場合は、カウンターをクリックして合計数を取得する必要があります。

* **ダッシュボード**：アクティビティにリンクされているすべてのパラメーターの概要を示します。この画面には、異なる概念を分けて個別に設定できるインタラクティブゾーンが含まれています。

   ![](assets/ux_dashboard.png)

* 要素の作成時に複数のオファーが可能な場合は、追加する要素のタイプ（キャンペーン、配信）を&#x200B;**選択画面**&#x200B;で選択できます。この選択画面は、レポートへのアクセスにも使用できます。

   ![](assets/ux_activityselection.png)

* ワークフローとクエリエディターについては、パレットを含んだ&#x200B;**ワークスペース**&#x200B;でオブジェクトをデザインできます。

   パレットから要素をワークスペースにドラッグ＆ドロップして設定します。

   ![](assets/ux_workspace.png)

## アクションバー {#action-bar}

表示された画面のタイプに応じて、画面にリンクされたアクションを含んだバーが上部に表示されます。

![](assets/actionbar.png)

このバーには、検索やフィルターなどの一般的な操作だけでなく、表示される画面に関する操作も含まれています。

* **ワークスペース**&#x200B;タイプの画面に関連するアクションについては、ワークフローの[アクションバー](../../automating/using/workflow-interface.md#action-bar)の節を参照してください。
* **ダッシュボード**&#x200B;画面に関連するアクションについて詳しくは、[メッセージダッシュボード](../../channels/using/message-dashboard.md)の節を参照してください。
* **リスト**&#x200B;タイプの画面に関するアクションについては、以下の[リストのカスタマイズ](../../start/using/customizing-lists.md)の節を参照してください。
