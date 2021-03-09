---
title: '統合ツールの概要 '
description: 統合ツールの概要
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 93e4310c606cb39a1071b8e20d88978839007765
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---


# セルフサービス統合アプリ{#gs-self-service-app}の概要

Microsoft Dynamics 365セルフサービス統合アプリケーションとのAdobe Campaign Standard統合により、データフローの設定、データフローの実行の有無、および環境の制御を行うことができます。 ただし、セルフサービス統合アプリケーションの使用を開始する前に、いくつかの前提条件を満たす必要があります。

## 概念と制限{#concepts-and-restrictions}

統合ツールを使用する前に、統合に関連する概念とガードレールを理解し、最初の手順を実行してアクセスする必要があります。

詳しくは、次の節を参照してください。

* [Microsoft Dynamics 365 統合の概要](../../integrating/using/d365-acs-get-started.md)
* [統合のベストプラクティスと制限事項](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [この統合を実装するための主な手順を説明します。](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Microsoft Dynamics 365 統合の使用](../../integrating/using/d365-acs-using-the-integration.md)

## 前提条件 {#self-service-app-prerequisites}

統合アプリがデータにアクセスできるように、Microsoft Dynamics 365とAdobe Campaign Standardを構成する必要があります。 これは、Dynamics 365、Adobe Campaign Standard、およびAdobe I/Oで構成するのに、しばらく時間がかかります。ただし、設定が完了すると、セルフサービス統合アプリケーションのユーザーインターフェイスを通じて統合を制御できます。

詳しくは、次の節を参照してください。

* [Campaign 統合用の Microsoft Dynamics 365 の設定](../../integrating/using/d365-acs-configure-d365.md)
* [Adobe I/O の設定](../../integrating/using/d365-acs-configure-adobe-io.md)
* [キャンペーンのカスタムリソースとMicrosoft Dynamics 365カスタムエンティティのマップ](../../integrating/using/d365-acs-notices-and-recommendations.md)

## セルフサービス統合アプリ{#self-service-app-configuration-steps}を設定するための主要な手順

その後、統合ツールと開始できます。 次の手順に従います。

1. [統合アプリへのアクセス権を取得する](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [使用する統合アプリの設定](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [データ同期の実装](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [同期ワークフローの設定](../../integrating/using/d365-acs-self-service-app-workflows.md)

## 統合アプリ{#self-service-app-link}へのリンク

ブラウザを開き、領域に関連付けられているコネクタを参照します。

* [アジア太平洋](https://d365-acs-ap.ea.adobe.com/)
* [ヨーロッパ、中東、アフリカ(EMEA)](https://d365-acs-em.ea.adobe.com/)
* [アメリカ](https://d365-acs-am.ea.adobe.com/)

## プライバシー要求の確認{#self-service-app-acknowledgement}

セルフサービスUIを初めて参照すると、プライバシーに関する確認が表示されます。 続行する前に、キャンペーンとMicrosoft Dynamics 365で個別にプライバシー要求を実行する際の役割を理解していることを確認する必要があります。
プライバシー責任の詳細とプライバシー要求の管理方法については、[このセクション](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy)を参照してください。

## 資格情報の設定{#self-service-app-credentials}

UIを初めて参照すると、次のようなヘッダーを含むページが表示されます。

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> アプリ設定がまだ構成されていない場合は、Adobe Campaign StandardまたはMicrosoft Dynamics 365に「接続できません」という警告を受け取るのが普通です。

「ORG」と「INSTANCE」が設定の予定であることを確認してください。  正しくない場合は、ドロップダウンリストをクリックし、正しい組織とインスタンスを選択します。

>[!IMPORTANT]
>
> 初めてコネクタを設定する場合、またはこのプロセスを初めて使用する場合は、**厳密に**&#x200B;使用する場合は、&quot;stage&quot;インスタンスまたは&quot;dev&quot;インスタンスを選択するよう強く求めます。 実稼動環境でセットアップを試行する前に、設定が正常に動作することを確認する必要があります。

正しい組織とインスタンスがある場合は、「ハンバーガー」メニューをクリックしてドロップダウンメニューを表示します。 次に、ドロップダウンメニューの&#x200B;**[!UICONTROL Settings...]**&#x200B;をクリックして、Microsoft Dynamics 365およびキャンペーン用の資格情報を入力したページにアクセスします（以下を参照）。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

**[!UICONTROL Settings]**&#x200B;ページで、次のセクションを設定します。

* Microsoft Dynamics 365資格情報
* Adobe資格情報

[ここ](../../integrating/using/d365-acs-self-service-app-settings.md)に移動して、各入力の情報を見つける場所に関する詳細情報を見つけます。 終了したら、下の&#x200B;**[!UICONTROL Save]**&#x200B;ボタンをクリックします。

## 初期構成{#self-service-app-initial-config}を確認

上記の前提条件が完了し、資格情報をすべて正しく追加できたと仮定して、**[!UICONTROL Workflows]**&#x200B;ページに移動します。 統合アプリのワークフローについて詳しくは、[このページ](../../integrating/using/d365-acs-self-service-app-workflows.md)を参照してください。

**[!UICONTROL Workflows]**&#x200B;ページで、**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ワークフローに関連付けられている鉛筆アイコンをクリックして、設定を編集します。

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ページで、設定したテーブルマッピングのリストにアクセスできます。  デフォルトでは、デフォルトで連絡先/プロファイルのマッピングがすぐに使用できます。 他のすべてのカスタムエンティティは、個別に設定する必要があります。

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

**[!UICONTROL Edit Table Mapping]**&#x200B;ページで&#x200B;**[!UICONTROL Mappings]**&#x200B;セクションをチェックし、Microsoft Dynamics 365のフィールドがキャンペーンの正しいフィールドにマップされていることを確認します。 他のマッピングを追加する必要がある場合は、置き換えやフィルターだけでなく、今すぐ追加してください。 [詳細情報](../../integrating/using/d365-acs-self-service-app-data-sync.md)。

新しいマッピングを追加する場合は、[この](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping)セクションを参照してください。

設定が正しくなったら、**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;ワークフローの横の&#x200B;**[!UICONTROL Play]**&#x200B;ボタンをクリックして、統合とデータの流れを開始します。

>[!IMPORTANT]
>
>**強く**&#x200B;お勧めするのは、実稼動環境で実行する前に、まずStage環境またはDevで実行することです。 ヘッダーでステージ/開発インスタンスが選択されていることを確認してください。


![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

実行後は、Microsoft Dynamics 365のエントリを追加または変更し、数分以内にAdobe Campaignの変化を観察することで、テストを実行できます。 この処理を停止する必要がある場合は、同じボタンを押すだけで停止できます。 [詳細情報](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## 統合アプリワークスペース{#self-service-app-workspace}

### アプリのヘッダー{#app-header}

セルフサービスアプリ内のヘッダーを使用すると、現在表示中の組織やインスタンス、設定中の組織やインスタンスを定義できます。

表示/編集する&#x200B;**ORG**&#x200B;と&#x200B;**INSTANCE**&#x200B;を選択します。 これらのフィールドは読み取り専用に表示されますが、マウスカーソルをフィールドの上に置くと編集可能になります。

ヘッダーの右側に3本の水平線![](assets//do-not-localize/d365-to-acs-icon-hamburger.png)が表示されたボタンをクリックすると、ドロップダウンメニューが表示されます。

ドロップダウンメニューのエントリは次のとおりです。

* **設定**:このオプションを選択すると、Microsoft Dynamics 365およびAdobe Campaign用のAPI資格情報や、その他のアプリケーションの一般設定を指定できる画面が表示されます。

* **ドキュメント**:このオプションは、この統合に固有のAdobe Campaignドキュメントへのリンクです。

* **カスタマーケア**:これは、カスタマーケアチケットの開封に関するExperience Cloudドキュメントへのリンクです

* **サインアウト**:これにより、アプリケーションからサインアウトし、別のユーザーとして再びサインインできるようになります。

* **情報**:著作権情報など、アプリケーションに関する情報を含むダイアログが表示されます。

### パンくず{#app-breadcrumbs}

アプリ内を移動すると、一部の画面の上部にパンくずリストが表示されます。

**例：**

**[!UICONTROL Edit Table Mapping]**&#x200B;画面のパンくずリストとページタイトルの例を以下に示します。 この場合、**[!UICONTROL Workflows]**&#x200B;または&#x200B;**[!UICONTROL Microsoft Dynamics 365 to Campaign]**&#x200B;のテキストをクリックすると、前の画面の1つに移動できます。 **[!UICONTROL Edit Table Mapping]** 」は、現在の画面であるため、この場合はクリックできません。

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### 共通ボタン{#app-buttons}

セルフサービスアプリの複数のページでは、次のアイコンが使用されます。

![](assets/do-not-localize/d365-to-acs-icon-add.png) -リスト追加に対する新しいアイテム。

![](assets/do-not-localize/d365-to-acs-icon-edit.png)  — 既に存在するものを編集する

![](assets/do-not-localize/d365-to-acs-icon-delete.png)  — 項目のリストから項目を削除する
