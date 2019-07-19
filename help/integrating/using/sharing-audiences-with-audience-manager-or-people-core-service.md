---
title: Audience ManagerまたはPeopleコアサービスでのオーディエンスの共有
seo-title: Audience ManagerまたはPeopleコアサービスでのオーディエンスの共有
description: Audience ManagerまたはPeopleコアサービスでのオーディエンスの共有
seo-description: 様々なAdobe Experience Cloudソリューション内でオーディエンスをインポートまたは書き出す方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: a3701e72-5846-4241- afee- d713b499a27a
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- audiences- manager- or- people- core- service
discoiquuid: 77af0772-52b5-46bc- a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Sharing audiences with Audience Manager or People core service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importing an audience {#importing-an-audience}

Peopleコアサービス統合を使用すると、データベースを強化する技術ワークフローを介して、オーディエンスを直接Adobe Campaignにインポートできます。For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

Importing audiences/segments from People core service in Adobe Campaign can be carried out from the **[!UICONTROL Audiences]** menu only by users connected via IMS (authentication via Adobe ID).

1. Go to the **[!UICONTROL Audiences]** menu.
1. In the action bar, select **[!UICONTROL Create]** to be taken to the screen to create an audience.
1. 新しいオーディエンスのラベルを指定します。
1. Set the audience **[!UICONTROL Type]** to **[!UICONTROL Experience Cloud]** to indicate that the audience being created is an audience that was imported from People core service.
1. **[!UICONTROL Name of the shared audience]** フィールドから、読み込むオーディエンスを選択します。インポートできるのはセグメントのみです。キーと値のペアを含む詳細なデータ、特徴およびルールはサポートされていません。

   ![](assets/aam_import_audience.png)

1. Select the corresponding **[!UICONTROL Shared Data Source]**.

   If the selected data source is configured to use an encryption algorithm, an additional option offers you the possibility to **[!UICONTROL Force reconciliation with a profile]**. Check this option if the **[!UICONTROL Channel]** field of the data source is set to Email or Mobile (SMS) and if you want to leverage profile data.

   If you do not select the **[!UICONTROL Force reconciliation with a profile]** and if **[!UICONTROL Channel]** is set in AMC Data source to Email or Mobile (SMS) then all the encrypted declared IDs are decrypted. An audience of type **File** with a list of all the email addresses/mobile phone numbers is created/updated. これにより、キャンペーンにそのプロファイルが存在しない場合でも、この統合によって共有オーディエンスをインポートする際に、電子メールアドレスや携帯電話番号が失われます。このタイプのオーディエンスは、ワークフローを使用して手動で調整する必要があるため、直接使用することはできません。

1. オーディエンスを作成するかどうかを確認します。

   オーディエンスは、技術ワークフローを通してインポートされます。これは、ID（「訪問者ID"または「宣言ID"）がプロファイルディメンションと調和できるレコードで構成されています。Adobe Campaignで認識されないPeopleコアサービスセグメントからのIDはインポートされません。

オーディエンスがAdobe Campaignデータベースに読み込まれるようになりました。セグメントがPeopleコアサービスまたはAudience Managerから直接インポートされると、インポートプロセスには24~36時間かかります。この期間後、Adobe Campaignで新しいオーディエンスを見つけて使用できます。

>[!NOTE]
>
>Adobe AnalyticsからAdobe Campaignにオーディエンスを読み込む場合、これらのオーディエンスをPeopleコアサービスまたはAudience Managerで共有する必要があります。このプロセスは12~24時間かかります。これは、キャンペーンとの24~36時間の同期に追加する必要があります。特定のケースでは、オーディエンス共有時間枠は最大60時間です。For more information on Adobe Analytics audience sharing in People Core service and Audience manager, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exporting an audience {#exporting-an-audience}

An audience can be exported from Adobe Campaign to Audience Manager or People core service using a workflow and the **[!UICONTROL Save audience]** activity.

これは、新しいワークフローで実行でき、IMS経由で接続したユーザーのみが実行できます（Adobe ID経由での認証）。

1. プログラム、キャンペーン、またはマーケティングアクティビティのリストから新しいワークフローを作成します。
1. 使用可能な様々なアクティビティを使用して、プロファイルのセットをターゲットにします。
1. After the targeting, drag and drop a **[!UICONTROL Save audience]** activity into the workflow, then open it.
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. **[!UICONTROL Shared audience]** フィールドを使用してオーディエンスを指定します。開くウィンドウで、既存のオーディエンスを選択するか、新しいオーディエンスを作成するかを選択できます。

   * 既存のオーディエンスを選択すると、新しいレコードのみがオーディエンスに追加されます。
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.
   ![](assets/aam_save_audience_segment_picker.png)

   紐付けおよび交換するには、レコードにAdobe Experience Cloud ID（「訪問者ID"または「宣言ID"）が必要です。オーディエンスの読み込みおよび書き出し時に、紐付けされていないレコードは無視されます。

1. 終了するには、画面右上にあるチェックマークをクリックします。
1. Select the corresponding **[!UICONTROL Shared Data Source]**.
1. If you like, check the **[!UICONTROL Generate an outbound transition]** box to use the profiles that were exported. 結合できるのは、紐付け可能なプロファイルのみです。
1. アクティビティの設定を確認し、ワークフローを保存します。
1. ワークフローを開始してオーディエンスをエクスポートします。Adobe CampaignとPeopleコアサービス間の同期には数時間かかる場合があります

Adobe CampaignとPeopleコアサービスの同期には24~36時間かかります。この期間後、Peopleコアサービスで新しいオーディエンスを見つけて、他のAdobe Experience Cloudソリューションで再利用できます。For more information on using an Adobe Campaign shared audience in Adobe People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**関連トピック:**

* [ワークフロー](../../automating/using/workflow-data-and-processes.md)
* [オーディエンス](../../audiences/using/about-audiences.md)

