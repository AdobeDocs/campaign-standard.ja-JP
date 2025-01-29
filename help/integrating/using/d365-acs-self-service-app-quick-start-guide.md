---
title: 統合ツールの基本を学ぶ
description: 統合ツールの基本を学ぶ
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: e73e2069-e86d-4be2-bf73-22e6dc164340
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 2%

---

# セルフサービス統合アプリの基本を学ぶ {#gs-self-service-app}

Adobe Campaign StandardとMicrosoft Dynamics 365 セルフサービス統合アプリケーションの統合により、データフローの設定、データフローが実行されているかどうかの制御、およびどの環境での実行が可能になります。 ただし、セルフサービス統合アプリケーションを使用する前に、いくつかの前提条件を満たす必要があります。

## 概念と制限 {#concepts-and-restrictions}

統合ツールを開始する前に、統合に関連する概念とガードレールを理解し、アクセス権を取得するための初期手順を実行する必要があります。

詳しくは、以下の節を参照してください。

* [Microsoft Dynamics 365 統合の概要](../../integrating/using/d365-acs-get-started.md)
* [統合のベストプラクティスと制限事項](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [この統合を実装するための主な手順を説明します](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Microsoft Dynamics 365 統合の使用](../../integrating/using/d365-acs-using-the-integration.md)

## 前提条件 {#self-service-app-prerequisites}

統合アプリがデータにアクセスできるように、Microsoft Dynamics 365 とAdobe Campaign Standardを設定する必要があります。 Dynamics 365、Adobe Campaign Standard、およびAdobe I/Oでの設定にはある程度の時間がかかりますが、設定が完了すると、セルフサービス統合アプリケーションのユーザーインターフェイスを通じて統合を制御できるようになります。

詳しくは、以下の節を参照してください。

* [Campaign 統合用のMicrosoft Dynamics 365 の設定](../../integrating/using/d365-acs-configure-d365.md)
* [Adobe I/Oの設定](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Campaign カスタムリソースとMicrosoft Dynamics 365 カスタムエンティティのマッピング](../../integrating/using/d365-acs-notices-and-recommendations.md)

## セルフサービス統合アプリを設定するための主な手順 {#self-service-app-configuration-steps}

その後、統合ツールから開始できます。 以下の手順に従います。

1. [統合アプリへのアクセス権の取得](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [使用する環境の統合アプリを設定](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [データ同期の実装](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [同期ワークフローの設定](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 統合アプリへのリンク {#self-service-app-link}

ブラウザーを開き、地域に関連付けられているコネクタを参照します。

* [ アジア太平洋 ](https://d365-acs-ap.ea.adobe.com/)
* [ ヨーロッパ、中東、アフリカ（EMEA） ](https://d365-acs-em.ea.adobe.com/)
* [ アメリカ ](https://d365-acs-am.ea.adobe.com/)

## プライバシーリクエストの確認 {#self-service-app-acknowledgement}

初めてセルフサービス UI にアクセスすると、プライバシー確認が表示されます。 続行する前に、Campaign とMicrosoft Dynamics 365 でプライバシーリクエストを個別に実行する自身の役割を理解していることを確認する必要があります。
プライバシーの責任と、プライバシーリクエストの管理方法について詳しくは、[ この節 ](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy) を参照してください。

## 認証情報の設定 {#self-service-app-credentials}

初めて UI に参照すると、次のようなヘッダーを持つページが表示されます。

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> アプリの設定がまだ行われていない場合は、Adobe Campaign StandardまたはMicrosoft Dynamics 365 に「接続できません」というアラートを受け取るのは通常です。

「ORG」と「INSTANCE」の選択内容が、設定しようとしている項目であることを確認してください。  表示されない場合は、ドロップダウンリストをクリックして、正しい組織とインスタンスを選択します。

>[!IMPORTANT]
>
> 初めてコネクタを設定する場合やこのプロセスを初めて使用する場合は **強く** 「stage」または「dev」インスタンスを選択することを推奨します。 実稼動環境でセットアップを試す前に、設定が正常に動作することを確認する必要があります。

正しい組織とインスタンスがある場合は、「ハンバーガー」メニューをクリックして、ドロップダウンメニューを表示します。 次に、ドロップダウンメニューの **[!UICONTROL Settings...]** をクリックして、Microsoft Dynamics 365 および Campaign の資格情報を入力するページにアクセスします（以下を参照）。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

**[!UICONTROL Settings]** ページで、次のセクションに入力します。

* Microsoft Dynamics 365 資格情報
* Adobe資格情報

各入力の情報の場所の詳細については、[ ここ ](../../integrating/using/d365-acs-self-service-app-settings.md) を参照してください。 完了したら、下部にある「**[!UICONTROL Save]**」ボタンをクリックします。

## 初期設定の確認 {#self-service-app-initial-config}

上記の前提条件を満たし、すべての資格情報が正しく追加されている場合は、**[!UICONTROL Workflows]** のページに移動しましょう。 統合アプリワークフローについて詳しくは、[ このページ ](../../integrating/using/d365-acs-self-service-app-workflows.md) を参照してください。

**[!UICONTROL Workflows]** ページで、**[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフローに関連付けられている鉛筆アイコンをクリックして、設定を編集します。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

**[!UICONTROL Microsoft Dynamics 365 to Campaign]** のページで、設定したテーブルマッピングのリストにアクセスできます。  デフォルトでは、標準の連絡先/プロファイルマッピングが使用されます。 その他すべてのカスタムエンティティは、個別に設定する必要があります。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

**[!UICONTROL Edit Table Mapping]** ページで、「**[!UICONTROL Mappings]**」セクションをチェックし、Microsoft Dynamics 365 のフィールドが Campaign の正しいフィールドにマッピングされていることを確認します。 他のマッピングを追加する必要がある場合は、置換やフィルターと同様に、今すぐ追加します。 [詳細情報](../../integrating/using/d365-acs-self-service-app-data-sync.md)。

新しいマッピングを追加する場合は、[ この節 ](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) を参照してください。

設定が正しければ、**[!UICONTROL Microsoft Dynamics 365 to Campaign]** ワークフローの横にある「**[!UICONTROL Play]**」ボタンをクリックして、統合とデータのフローを開始します。

>[!IMPORTANT]
>
>実稼 **環境で実行する前に** 最初にステージング環境または開発環境で実行することを強くお勧めします。 ヘッダーでステージ/開発インスタンスが選択されていることを確認してください。
>

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

実行すると、Microsoft Dynamics 365 のエントリを追加または変更し、Adobe Campaignでその変更内容を数分以内に確認することで、テストできるようになります。 このプロセスを停止する必要がある場合は、同じボタンを押して停止します。 [詳細情報](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## 統合アプリワークスペース {#self-service-app-workspace}

### アプリヘッダー {#app-header}

セルフサービスアプリ内のヘッダーを使用すると、現在表示または設定している組織やインスタンスを定義できます。

表示/編集する **ORG** と **INSTANCE** を選択します。 これらのフィールドは読み取り専用で表示されますが、マウスカーソルをその上に置くと編集可能になります。

ヘッダーの右側に 3 本の水平線が ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) まれるボタンをクリックすると、ドロップダウンメニューが表示されます。

ドロップダウンメニューのエントリは次のとおりです。

* **設定**：このオプションを選択すると、Microsoft Dynamics 365 およびAdobe Campaignの API 資格情報と、アプリケーションのその他の一般設定を指定できる画面が表示されます。

* **ドキュメント**：このオプションは、この統合固有のAdobe Campaign ドキュメントへのリンクです

* **カスタマーケア**：カスタマーケアチケットのオープンに関連するExperience Cloudドキュメントへのリンクです

* **ログアウト**：これにより、アプリケーションからログアウトし、別のユーザーとしてログインし直すことができます。

* **バージョン情報**：著作権情報など、アプリケーションに関する情報を含むダイアログが表示されます。

### 階層リンク {#app-breadcrumbs}

アプリを移動すると、一部の画面の上部にパンくずリストが表示されます。

**例：**

以下は、パンくずリストとページタイトルを表示する、**[!UICONTROL Edit Table Mapping]** 画面の例です。 この場合、**[!UICONTROL Workflows]** または **[!UICONTROL Microsoft Dynamics 365 to Campaign]** のテキストをクリックして、前の画面のいずれかに移動できます。 この場合、パンくずリストの **[!UICONTROL Edit Table Mapping]** は現在の画面なので、クリックできません。

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### 共通ボタン {#app-buttons}

次のアイコンは、セルフサービスアプリの複数のページで使用されています。

![](assets/do-not-localize/d365-to-acs-icon-add.png) - リストに新しい項目を追加します。

![](assets/do-not-localize/d365-to-acs-icon-edit.png) – 既に存在するものを編集します

![](assets/do-not-localize/d365-to-acs-icon-delete.png) – 項目リストからの項目の削除
