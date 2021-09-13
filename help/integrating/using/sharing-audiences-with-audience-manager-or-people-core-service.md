---
title: Audience Manager または People コアサービスとのオーディエンスの共有
description: 様々なAdobe Experience Cloudソリューション内でオーディエンスをインポートまたはエクスポートする方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 29%

---

# Audience Manager または People コアサービスとのオーディエンスの共有{#sharing-audiences-with-audience-manager-or-people-core-service}

## オーディエンスのインポート {#importing-an-audience}

Peopleコアサービスの統合により、テクニカルワークフローを使用してオーディエンスをAdobe Campaignに直接インポートし、データベースをエンリッチメントできます。 Peopleコアサービスでのオーディエンスの共有について詳しくは、この[ドキュメント](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=ja)を参照してください。

Adobe CampaignのPeopleコアサービスからのオーディエンス/セグメントのインポートは、IMS(Adobe ID経由の認証)で接続したユーザーのみが&#x200B;**[!UICONTROL Audiences]**&#x200B;メニューから実行できます。

1. **[!UICONTROL Audiences]**&#x200B;メニューに移動します。
1. アクションバーで、**[!UICONTROL Create]**&#x200B;を選択してオーディエンスを作成します。
1. 新しいオーディエンスのラベルを指定します。
1. オーディエンス&#x200B;**[!UICONTROL Type]**&#x200B;を&#x200B;**[!UICONTROL Experience Cloud]**&#x200B;に設定して、作成中のオーディエンスがPeopleコアサービスからインポートされたオーディエンスであることを示します。
1. 「 **[!UICONTROL Name of the shared audience]** 」フィールドで、インポートするオーディエンスを選択します。 インポートできるのはセグメントのみです。キーと値のペア、特徴、ルールなどの詳細データはサポートされません。

   ![](assets/aam_import_audience.png)

1. 対応する&#x200B;**[!UICONTROL Shared Data Source]**&#x200B;を選択します。

   選択したデータソースが暗号化アルゴリズムを使用するように設定されている場合は、追加のオプションで&#x200B;**[!UICONTROL Force reconciliation with a profile]**&#x200B;を実行できます。 データソースの&#x200B;**[!UICONTROL Channel]**&#x200B;フィールドが「 Eメール」または「モバイル(SMS) 」に設定されていて、プロファイルデータを活用する場合は、このオプションを選択します。

   **[!UICONTROL Force reconciliation with a profile]**&#x200B;を選択せず、AMCデータソースで&#x200B;**[!UICONTROL Channel]**&#x200B;が電子メールまたはモバイル(SMS)に設定されている場合、暗号化された宣言済みIDがすべて復号化されます。 すべての電子メールアドレス/携帯電話番号のリストを含む、**ファイル**&#x200B;タイプのオーディエンスが作成/更新されます。 これにより、この統合を通じて共有オーディエンスをインポートする際に、そのプロファイルがCampaignに存在しなくても、電子メールアドレスや携帯電話番号が失われることはありません。 このタイプのオーディエンスは、ワークフローを使用して手動で紐付けする必要があるので、直接使用することはできません。

1. オーディエンスの作成を確認します。

   オーディエンスはテクニカルワークフローによってインポートされます。 これは、ID（「訪問者ID」または「宣言済みID」）をプロファイルディメンションと紐付けできたレコードで構成されます。 Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。

これで、オーディエンスがAdobe Campaignデータベースにインポートされます。 インポートプロセスで、People コアサービスまたは Audience Manager からセグメントを直接インポートする場合は、同期に 24～36 時間かかります。同期が終了すると、Adobe Campaign で新しいオーディエンスを検索したり、使用したりできます。

>[!NOTE]
>
>Adobe AnalyticsからAdobe Campaignにオーディエンスをインポートする場合は、まずPeopleコアサービスまたはAudience Managerでそれらのオーディエンスを共有する必要があります。 このプロセスには 12～24 時間を要し、Campaign との同期にはさらに 24～36 時間が必要です。場合により、オーディエンスの共有プロセスは最大 60 時間に及ぶことがあります。People コアサービスと Audience Manager での Adobe Analytics オーディエンスの共有について詳しくは、この[ドキュメント](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)を参照してください。

## オーディエンスのエクスポート {#exporting-an-audience}

ワークフローと&#x200B;**[!UICONTROL Save audience]**&#x200B;アクティビティを使用して、オーディエンスをAdobe CampaignからAudience ManagerまたはPeopleコアサービスにエクスポートできます。

新しいワークフローで実行できるのは、IMS(Adobe ID経由の認証)で接続したユーザーのみです。

1. プログラム、キャンペーン、またはマーケティングアクティビティのリストから新しいワークフローを作成します。
1. 使用可能な様々なアクティビティを使用して、一連のプロファイルをターゲット設定します。
1. ターゲティングが終わったら、**[!UICONTROL Save audience]**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップして開きます。
1. 「**[!UICONTROL Share in Adobe Experience Cloud]**」を選択します。

   ![](assets/aam_save_audience_activity.png)

1. **[!UICONTROL Shared audience]**&#x200B;フィールドを使用してオーディエンスを指定します。 開いたウィンドウで、既存のオーディエンスを選択するか、新しいオーディエンスを作成するかを選択できます。

   * 既存オーディエンスを選択した場合、新規レコードだけがオーディエンスに追加されます。
   * プロファイルリストを新しいオーディエンスにエクスポートするには、**[!UICONTROL Segment name]**&#x200B;フィールドを入力し、新しく作成したオーディエンスを選択する前に&#x200B;**[!UICONTROL Create]**&#x200B;をクリックします。

   ![](assets/aam_save_audience_segment_picker.png)

   紐付けおよび交換をおこなうには、レコードにAdobe Experience Cloud ID（「訪問者ID」または「宣言済みID」）が含まれている必要があります。 オーディエンスのインポートおよびエクスポート時に、紐付けされていないレコードは無視されます。

1. 終了するには、画面の右上にあるチェックマークをクリックします。
1. 対応する&#x200B;**[!UICONTROL Shared Data Source]**&#x200B;を選択します。
1. 必要に応じて、「 **[!UICONTROL Generate an outbound transition]** 」ボックスをオンにして、書き出されたプロファイルを使用します。 紐付け可能なプロファイルのみがエクスポートされます。
1. アクティビティの設定を確認し、ワークフローを保存します。
1. ワークフローを開始して、オーディエンスをエクスポートします。 Adobe CampaignとPeopleコアサービス間の同期には、数時間かかる場合があります

Adobe Campaign と People コアサービス間の同期には、24～36 時間かかります。同期が終了すると、People コアサービスで新しいオーディエンスを検索できるようになり、そのオーディエンスを他の Adobe Experience Cloud ソリューションで再利用することができます。Adobe People コアサービスで Adobe Campaign の共有オーディエンスを使用する方法について詳しくは、この[ドキュメント](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html?lang=ja)を参照してください。

**関連トピック：**

* [ワークフロー](../../automating/using/get-started-workflows.md)
* [Audiences](../../audiences/using/about-audiences.md)
