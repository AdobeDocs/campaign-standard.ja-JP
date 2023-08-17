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

People コアサービスの統合により、テクニカルワークフロー経由でオーディエンスをAdobe Campaignに直接インポートし、データベースをエンリッチメントできます。 People コアサービスでのオーディエンスの共有について詳しくは、こちらを参照してください。 [ドキュメント](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=ja).

Adobe Campaignの People コアサービスからオーディエンス/セグメントをインポートする場合は、 **[!UICONTROL Audiences]** メニューは、IMS(Adobe IDでの認証 ) を介して接続されたユーザーのみが使用できます。

1. 次に移動： **[!UICONTROL Audiences]** メニュー。
1. アクションバーで、「 」を選択します。 **[!UICONTROL Create]** をクリックして、オーディエンスを作成する画面に移動します。
1. 新しいオーディエンスのラベルを指定します。
1. オーディエンスの設定 **[!UICONTROL Type]** から **[!UICONTROL Experience Cloud]** をクリックして、作成されるオーディエンスが People コアサービスからインポートされたオーディエンスであることを示します。
1. 次から： **[!UICONTROL Name of the shared audience]** 「 」フィールドで、インポートするオーディエンスを選択します。 インポートできるのはセグメントのみです。キーと値のペア、特徴、ルールなどの詳細データはサポートされません。

   ![](assets/aam_import_audience.png)

1. 対応する **[!UICONTROL Shared Data Source]**.

   選択したデータソースが暗号化アルゴリズムを使用するように設定されている場合は、別のオプションを使用して、次の操作を実行できます。 **[!UICONTROL Force reconciliation with a profile]**. このオプションをオンにすると、 **[!UICONTROL Channel]** データソースのフィールドが「電子メール」または「モバイル (SMS) 」に設定されていて、プロファイルデータを活用する場合は、このフィールドを使用します。

   このオプションを選択しない場合、 **[!UICONTROL Force reconciliation with a profile]** また、 **[!UICONTROL Channel]** が AMC データソースで電子メールまたはモバイル (SMS) に設定されている場合、暗号化された宣言済み ID はすべて復号化されます。 タイプのオーディエンス **ファイル** に、すべての電子メールアドレス/携帯電話番号のリストが作成/更新されます。 これにより、この統合で共有オーディエンスをインポートする際に、そのプロファイルが Campaign に存在しない場合でも、電子メールアドレスや携帯電話番号が失われることはありません。 このタイプのオーディエンスは、ワークフローを使用して手動で紐付けする必要があるので、直接使用することはできません。

1. オーディエンスの作成を確認します。

   オーディエンスはテクニカルワークフローでインポートされます。 これは、ID（「訪問者 ID」または「宣言済み ID」）をプロファイルディメンションと紐付けできたレコードで構成されます。 Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。

オーディエンスがAdobe Campaignデータベースにインポートされました。 インポートプロセスで、People コアサービスまたは Audience Manager からセグメントを直接インポートする場合は、同期に 24～36 時間かかります。同期が終了すると、Adobe Campaign で新しいオーディエンスを検索したり、使用したりできます。

>[!NOTE]
>
>Adobe AnalyticsからAdobe Campaignにオーディエンスをインポートする場合は、まず People コアサービスまたはAudience Managerでそれらのオーディエンスを共有する必要があります。 このプロセスには 12～24 時間を要し、Campaign との同期にはさらに 24～36 時間が必要です。場合により、オーディエンスの共有プロセスは最大 60 時間に及ぶことがあります。People コアサービスと Audience Manager での Adobe Analytics オーディエンスの共有について詳しくは、この[ドキュメント](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=ja)を参照してください。

## オーディエンスのエクスポート {#exporting-an-audience}

オーディエンスは、Adobe CampaignからAudience Managerまたは People コアサービスに書き出すことができます。 **[!UICONTROL Save audience]** アクティビティ。

新しいワークフローで実行でき、IMS(Adobe IDでの認証 ) で接続したユーザーのみが実行できます。

1. プログラム、キャンペーン、またはマーケティングアクティビティのリストから新しいワークフローを作成します。
1. 使用可能な様々なアクティビティを使用して、一連のプロファイルをターゲティングします。
1. ターゲティング後、 **[!UICONTROL Save audience]** 「 」アクティビティをワークフローに追加し、開きます。
1. 「**[!UICONTROL Share in Adobe Experience Cloud]**」を選択します。

   ![](assets/aam_save_audience_activity.png)

1. オーディエンスを指定するには、 **[!UICONTROL Shared audience]** フィールドに入力します。 表示されるウィンドウで、既存のオーディエンスを選択するか、新しいオーディエンスを作成するかを選択できます。

   * 既存オーディエンスを選択した場合、新規レコードだけがオーディエンスに追加されます。
   * プロファイルリストを新しいオーディエンスに書き出すには、 **[!UICONTROL Segment name]** 「 」をクリックし、 **[!UICONTROL Create]** 新しく作成されたオーディエンスを選択する前に。

   ![](assets/aam_save_audience_segment_picker.png)

   紐付けされ、交換されるために、レコードにAdobe Experience Cloud ID（「訪問者 ID」または「宣言済み ID」）が必要です。 紐付けされていないレコードは、オーディエンスのインポートおよびエクスポート時に無視されます。

1. 終了するには、画面の右上にあるチェックマークをクリックします。
1. 対応する **[!UICONTROL Shared Data Source]**.
1. 必要に応じて、 **[!UICONTROL Generate an outbound transition]** 」ボックスを使用して、書き出されたプロファイルを使用します。 紐付け可能なプロファイルのみが書き出されます。
1. アクティビティの設定を確認し、ワークフローを保存します。
1. ワークフローを開始して、オーディエンスをエクスポートします。 Adobe Campaignと People コアサービス間の同期には、数時間かかる場合があります

Adobe Campaign と People コアサービス間の同期には、24～36 時間かかります。同期が終了すると、People コアサービスで新しいオーディエンスを検索できるようになり、そのオーディエンスを他の Adobe Experience Cloud ソリューションで再利用することができます。Adobe People コアサービスで Adobe Campaign の共有オーディエンスを使用する方法について詳しくは、この[ドキュメント](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html?lang=ja)を参照してください。

**関連トピック：**

* [ワークフロー](../../automating/using/get-started-workflows.md)
* [オーディエンス](../../audiences/using/about-audiences.md)
