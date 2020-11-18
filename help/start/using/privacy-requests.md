---
title: プライバシーリクエスト
description: Adobe Campaign Standardでプライバシー要求を管理する方法を学びます。
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 06b886989243405df04b4abef46994afd980f6d8
workflow-type: tm+mt
source-wordcount: '1711'
ht-degree: 20%

---


# Managing Privacy requests {#privacy-requests}

For a general presentation on Privacy Management, refer to [this section](../../start/using/privacy-management.md).

この情報は、GDPR、CCPA、PDPA、LGPD に適用されます。これらの規制について詳しくは、[こちら](../../start/using/privacy-management.md#privacy-management-regulations)を参照してください。

The opt-out for the Sale of Personal Information, which is specific to CCPA, is explained in [this section](#sale-of-personal-information-ccpa).

>[!IMPORTANT]
>
>19.4 以降、アクセス要求および削除要求に対する Campaign API およびインターフェイスの使用は廃止されます。GDPR、CCPA、PDPA、またはLGPDのアクセスと削除のリクエストに対しては、 [プライバシーコアサービス](#create-privacy-request) の統合方法を使用する必要があります。

## About Privacy requests {#about-privacy-requests}

プライバシーの準備を容易にするために、Adobe Campaignではアクセスおよび削除の要求を処理できます。 この節では、 **アクセス権** と「忘れ去られる **権利** 」（削除要求）について説明 [します](../../start/using/privacy-management.md#right-access-forgotten)。

これらの要求を実行するには、 **プライバシーコアサービス** 統合を使用する必要があります。 プライバシーコアサービスからすべてのExperience Cloudソリューションにプッシュされたプライバシー要求は、専用のワークフローを介してキャンペーンによって自動的に処理されます。

### 前提条件 {#prerequesites}

Adobe Campaignオファーデータコントローラーツールを使用して、Adobe Campaignに保存されたデータに対するプライバシー要求を作成し、処理します。 ただし、データ主体とのやり取り（電子メール、カスタマーサポート、Web ポータル）はデータ管理者がおこなう必要があります。

また、要求者であるデータ主体の身元の確認、および要求者に返されるデータがデータ主体に関するものであることの確認は、データ管理者がおこないます。

>[!NOTE]
>
>個人データおよびデータを管理する様々なエンティティ（データ管理者、データ処理者、データ主体）について詳しくは、[個人データとペルソナ](../../start/using/privacy.md#personal-data)を参照してください。

### 名前空間 {#namesspaces}

プライバシーリクエストを作成する前に、使用する名前空間を定義する必要があります。 名前空間は、Adobe Campaign データベースでデータ主体を識別するために使用するキーです。標準では、次の2つの名前空間を使用できます。電子メールと携帯電話。 別の名前空間(例えば、プロファイルのカスタムフィールド)が必要な場合は、次の手順に従います。

Also refer to this [tutorial](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/namespaces-for-privacy-requests.html?lang=en#privacy) on how to create a namespace.

>[!NOTE]
>
>複数の名前空間を使用する場合は、名前空間ごとに1つのプライバシーリクエストを作成する必要があります。

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Namespaces]**.

   ![](assets/privacy-namespaces.png)

1. 名前空間のリストで、をクリックし **[!UICONTROL Create]**&#x200B;ます。

   ![](assets/privacy-namespace-create.png)

1. aと入力し **[!UICONTROL Label]**&#x200B;ます。

   ![](assets/privacy-namespace-label.png)

1. 既存のIDサービス名前空間を使用する場合は、を選択し、 **[!UICONTROL Map from Identity Namespace Service]****[!UICONTROL Identity Service Namespaces]** リストから名前空間を選択します。

   ![](assets/privacy-map-from-namespace.png)

   で新しい名前空間を作成し、キャンペーンでマッピングする場合 **[!UICONTROL Identity Service]** は、を選択し **[!UICONTROL Create new]** て **[!UICONTROL Identity namespace name]** フィールドに名前を入力します。

   ![](assets/privacy-create-new-namespace.png)

   ID名前空間について詳しくは、 [Experience Platformドキュメントを参照してください](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=en) 。

1. ID サービスの 1 つの名前空間が Campaign の 1 つの名前空間にマッピングされます。Campaign での名前空間の紐付け方法を指定する必要があります。

   ターゲットマッピング(**[!UICONTROL Recipients]**&#x200B;または **[!UICONTROL Real-time event]****[!UICONTROL Subscriptions to an application]**)を選択します。 複数のターゲットマッピングを使用する場合は、ターゲットマッピングごとに1つの名前空間を作成する必要があります。

   ![](assets/privacy-namespace-target-mapping.png)

1. を選択し **[!UICONTROL Reconciliation key]**&#x200B;ます。 これは、Adobe Campaignデータベース内のData Subjectを識別するために使用されるフィールドです。

   ![](assets/privacy-namespace-reconciliation-key.png)

1. 「**[!UICONTROL Create]**」をクリックします。新しい名前空間に基づいてプライバシーリクエストを作成できるようになりました。 複数の名前空間を使用する場合は、名前空間ごとに1つのプライバシーリクエストを作成する必要があります。

### Creating a Privacy request {#create-privacy-request}

>[!IMPORTANT]
>
>The **Privacy Core Service** integration is the method you should use for all Access and Delete requests.
>
>19.4 以降、アクセス要求および削除要求に対する Campaign API およびインターフェイスの使用は廃止されます。GDPR、CCPA、PDPA、LGPDのアクセスおよび削除のリクエストに対して、コア・Privacy Serviceを使用します。

プライバシーコアサービスの統合により、単一のJSON API呼び出しを使用して、複数のソリューションのコンテキストでプライバシーリクエストを自動化できます。 プライバシーコアサービスからすべてのExperience Cloudソリューションにプッシュされたプライバシー要求は、専用のワークフローを介してキャンペーンによって自動的に処理されます。

Refer to the [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) documentation to learn how to create Privacy requests from the Privacy Core Service.

各プライバシーコアサービスジョブは、使用されている名前空間数(1人の名前空間に対応する1件の要求)に基づいて、キャンペーン内で複数のプライバシー要求に分割されます。 また、1つのジョブを複数のインスタンスで実行できます。 したがって、1つのジョブに対して複数のファイルが作成されます。 例えば、リクエストに2つの名前空間があり、3つのインスタンスで実行されている場合、合計6つのファイルが送信されます。 名前空間およびインスタンスごとに1つのファイル

ファイル名のパターンは次のとおりです。 `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**：Campaign インスタンス名
* **NamespaceId**:使用する名前空間のIDサービス名前空間ID
* **紐付けキー**:エンコードされた紐付けキー

### 資源のリスト {#list-of-resources}

When performing a Delete or Access Privacy request, Adobe Campaign searches all the Data Subject&#39;s data based on the **Reconciliation** value in all the resources that have a link to the profiles resource (own type).

以下に、プライバシーリクエストの実行時に考慮される標準のリソースのリストを示します。

* プロファイル(受信者)
* プロファイル配信ログ(broadLogRcp)
* プロファイルトラッキングログ(trackingLogRcp)
* 配信ログ(アプリケーションへの購読)(broadLogAppSubRcp)
* トラッキングログ(アプリケーションへの購読)(trackingLogAppSubRcp)
* アプリケーションへの購読(appSubscriptionRcp)
* プロファイルの購読履歴(subHistoRcp)
* プロファイル購読(subscriptionRcp)
* 訪問者（visitor）

プロファイルリソース（独自のタイプ）へのリンクを持つカスタムリソースを作成した場合は、作成したカスタムリソースも考慮されます。 例えば、トランザクションリソースにリンクされたトランザクションプロファイルとトランザクションリソースにリンクされたトランザクション詳細リソースがある場合、その両方が考慮されます。

また、カスタムリソースの修正方法に関する[このチュートリアル](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/custom-resources-for-privacy-requests.html?lang=en#privacy)も参照してください。

これを機能させるには、カスタムリソースで次の **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** オプションを選択する必要があります。

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**.

1. プロファイルリソース（独自のタイプ）へのリンクを持つカスタムリソースを選択します。

1. セクションをクリックし **[!UICONTROL Links]** ます。

1. リンクごとに、鉛筆アイコン(**[!UICONTROL Edit properties]**)をクリックします。

1. In the **[!UICONTROL Behavior if deleted/duplicated]** section, select the **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** option.

   ![](assets/privacy-cus-resource-option.png)

### プライバシー要求のステータス {#privacy-request-statuses}

プライバシーリクエストの様々なステータスを次に示します。

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**:実行中の場合、ワークフローはまだ要求を処理していません。
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**:ワークフローは、リクエストを処理しています。
* **[!UICONTROL Delete pending]**:削除するすべての受信者データがワークフローによって識別されました。
* **[!UICONTROL Delete in progress]**:ワークフローは削除を処理しています。
   <!--**[!UICONTROL Delete Confirmation Pending]** (Delete request in 2-steps process mode): the workflow has processed the Access request. Manual confirmation is requested to perform the deletion. The button is available for 15 days.-->
* **[!UICONTROL Complete]**:要求の処理がエラーなく完了しました。
* **[!UICONTROL Error]**:ワークフローでエラーが発生しました。 理由は、 **[!UICONTROL Request status]** 列の「プライバシーリクエスト」のリストに表示されます。 例えば、Data Subjectの値に一致する受信者データがデータベース内に見つからないこ **[!UICONTROL Error data not found]****[!UICONTROL Reconciliation value]** とを意味します。

### 2ステップのプロセスの無効化 {#disabling-two-step-process}

Core Privacy Service は、2 段階プロセスをサポートしていません。

>[!IMPORTANT]
>
>Core Privacy Service 統合を使用してプライバシーリクエストを管理する前に、Campaign Standard インターフェイスから削除要求の 2 段階プロセスを無効にする必要があります。

このオプションを無効にしないと、Privacy Core Service で管理されるすべての削除要求は保留状態のままとなり、完了しません。

デフォルトでは、2ステップのプロセスがアクティブ化されます。

このモードを変更するには、をクリックし **[!UICONTROL Edit properties]**、 **[!UICONTROL Privacy Requests]** 画面の右上隅にあるを選択して、 **[!UICONTROL Activate the 2-step process]** オプションの選択を解除します。

![](assets/privacy-disable-2-step-process.png)

## 個人情報の販売のオプトアウト（CCPA）{#sale-of-personal-information-ccpa}

The **California Consumer Privacy Act** (CCPA) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

アクセス要求および削除要求の設定および使用方法は、GDPR と CCPA で共通です。ここでは、CCPAに固有の個人データ販売のオプトアウトについて説明します。

In addition to the [Consent management](../../start/using/privacy-management.md#consent-management) tools provided by Adobe Campaign, you have the possibility to track whether a consumer has opted-out for the Sale of Personal Information.

消費者は、自分の個人情報を第三者に売り渡すことを自分のシステムを通じて許可しないと判断する。 Adobe Campaignでは、この情報を保存して追跡できます。

>[!NOTE]
>
>オプトアウトを利用して、キャンペーンインターフェイスおよびAPIを介した個人情報の販売を行うことができます。 プライバシーコアサービスを通じて使用することはできません。

>[!IMPORTANT]
>
>データサブジェクトのリクエストを受け取り、CCPAのリクエスト日を追跡するのは、データコントローラーとしてのお客様の責任です。 テクノロジープロバイダーとして、オプトアウトの方法を提供するだけです。 データコントローラーとしての役割について詳しくは、「 [個人データと個人」を参照してください](../../start/using/privacy.md#personal-data)。

### カスタムテーブルの前提条件 {#ccpa-prerequisite}

Starting 19.4, the **[!UICONTROL CCPA Opt-Out]** field is provided out-of-the-box in the Campaign interface and API. By default, the field is available for the standard **[!UICONTROL Profile]** resource.

カスタムプロファイルリソースを使用する場合は、リソースを拡張し、フィールドを追加する必要があります。We recommend that you use a different name than the out-of-the-box field, for example:  **[!UICONTROL Opt-Out for CCPA]** (optoutccpa). 新しいフィールドが作成されると、Campaign API によって自動的にサポートされます。

For more detailed information on how to extend the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

>[!NOTE]
>
>リソースの変更は慎重に行う必要がある操作です。この操作は、エキスパートユーザーのみが実行する必要があります。

1. 移動 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**. カスタムプロファイルリソースをクリックします。 For more on extending a resource, see [this section](../../developing/using/creating-or-extending-the-resource.md).

   ![](assets/privacy-ccpa-extend-cus.png)

1. または **[!UICONTROL Add field]** をクリック **[!UICONTROL Create Element]**&#x200B;し、ラベルとIDを追加して、 **[!UICONTROL Boolean]** タイプを選択します。 For the name, use **Opt-Out for CCPA**. IDには、次を使用します。 **optOutCcpa**.

   ![](assets/privacy-ccpa-extend-field.png)

1. タブの下で、フィールド **[!UICONTROL Screen definition]** を追加してを選択し **[!UICONTROL Detail screen configuration]****[!UICONTROL Input field]**&#x200B;ます。 これにより、プロファイルリストと詳細でフィールドを使用できるようになります。  For more on configuring the screen definition, see [this section](../../developing/using/configuring-the-screen-definition.md).

   ![](assets/privacy-ccpa-extend-screen.png)

1. / **[!UICONTROL Administration]** >に移動し、パブリケーションを準備し **[!UICONTROL Development]****[!UICONTROL Publishing]**&#x200B;て変更を公開します。 For more on publishing a resource, see [this section](../../developing/using/updating-the-database-structure.md).

   ![](assets/privacy-ccpa-extend-pub.png)

1. フィールドがプロファイルの詳細に表示されていることを確認します。 詳しくは、[この節](#usage)を参照してください。

### 使用状況 {#usage}

フィールドの値を入力し、データ販売に関するCCPAのガイドラインとルールに従うのは、データコントローラーの責任です。

値はいくつかの方法で入力できます。

* 受信者の詳細を編集してキャンペーンのインターフェイスを使用する（以下を参照）
* Using the Campaign Privacy API (see the [API documentation](../../api/using/managing-ccpa-opt-out.md))
* データインポートワークフローの使用

その後、オプトアウトしたプロファイルの個人情報を第三者に販売しないようにする必要があります。

1. キャンペーンのインターフェイスで、プロファイルを編集してオプトアウトステータスを変更します。

   ![](assets/privacy-ccpa-profile-opt-out.png)

1. When the value of the field is **[!UICONTROL True]**, the information is displayed on the profile&#39;s details.

   ![](assets/privacy-ccpa-profile-opt-out-true.png)

1. 「プロファイル」リストを設定して、オープアウト列を表示できます。 リストの設定方法については、 [この節を参照してください](../../start/using/customizing-lists.md)。

   ![](assets/privacy-ccpa-profile-configure-list.png)

1. 列をクリックすると、オプトアウト情報に従って受信者を並べ替えることができます。

   ![](assets/privacy-ccpa-profile-sorting.png)
