---
title: Audience Manager または People コアサービスのオーディエンスを共有
description: 様々なAdobe Experience cloudソリューション内でオーディエンスを読み込むまたは書き出す方法について説明します。
page-status-flag: 非活性化の
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとオーディエンスの管理者または人々のコアサービスの利用
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Audience Manager または People コアサービスのオーディエンスを共有{#sharing-audiences-with-audience-manager-or-people-core-service}

## オーディエンスのインポート {#importing-an-audience}

Peopleコアサービスの統合により、技術的なワークフローを介してAdobe Campaignにオーディエンスを直接インポートし、データベースを強化できます。 For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

Adobe CampaignのPeopleコアサービスからのオーディエンス/セグメントのインポートは、IMS（Adobe IDによる認証）を介して接続され **[!UICONTROL Audiences]** たユーザーのみがメニューから実行できます。

1. メニューに移動 **[!UICONTROL Audiences]** します。
1. アクションバーで、オーディエ **[!UICONTROL Create]** ンスを作成する画面に移動するよう選択します。
1. 新しいオーディエンスのラベルを指定します。
1. オーディエンスを **[!UICONTROL Type]** 設定して、 **[!UICONTROL Experience Cloud]** 作成するオーディエンスがPeopleコアサービスから読み込まれたオーディエンスであることを示します。
1. フィールドか **[!UICONTROL Name of the shared audience]** ら、読み込むオーディエンスを選択します。 インポートできるのはセグメントのみです。キーと値のペア、特徴、ルールなどの詳細データはサポートされません。

   ![](assets/aam_import_audience.png)

1. 対応するを選択しま **[!UICONTROL Shared Data Source]**&#x200B;す。

   選択したデータソースが暗号化アルゴリズムを使用するように設定されている場合は、追加のオプションを使用して暗号化を行うことができま **[!UICONTROL Force reconciliation with a profile]**&#x200B;す。 データソースのフィールドが電子メ **[!UICONTROL Channel]** ールまたはモバイル(SMS)に設定されていて、プロファイルデータを利用する場合は、このオプションを選択します。

   を選択せず、AMCデータソースで電 **[!UICONTROL Force reconciliation with a profile]** 子メールま **[!UICONTROL Channel]** たはモバイル(SMS)に設定した場合は、暗号化された宣言済みIDがすべて復号化されます。 すべての電子メールア **ドレス** /携帯電話番号のリストを持つファイルタイプのオーディエンスが作成/更新されます。 これにより、この統合を通じて共有オーディエンスをインポートする際に、そのプロファイルがCampaignに存在しない場合でも、電子メールアドレスや携帯電話番号が失われることはありません。 このタイプのオーディエンスは、ワークフローを使用して手動で調整する必要があるので、直接使用することはできません。

1. オーディエンスの作成を確認します。

   オーディエンスは、次に技術的なワークフローを介してインポートされます。 これは、ID（「訪問者ID」または「宣言済みID」）をプロファイルディメンションと調整できたレコードで構成されます。 Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。

これで、オーディエンスがAdobe Campaignデータベースにインポートされました。 インポートプロセスで、People コアサービスまたは Audience Manager からセグメントを直接インポートする場合は、同期に 24～36 時間かかります。同期が終了すると、Adobe Campaign で新しいオーディエンスを検索したり、使用したりできます。

>[!NOTE]
>
>Adobe AnalyticsからAdobe Campaignにオーディエンスをインポートする場合は、まずPeopleコアサービスまたはAudience Managerでオーディエンスを共有する必要があります。 このプロセスには 12～24 時間を要し、Campaign との同期にはさらに 24～36 時間が必要です。場合により、オーディエンスの共有プロセスは最大 60 時間に及ぶことがあります。People コアサービスと Audience Manager での Adobe Analytics オーディエンスの共有について詳しくは、この[ドキュメント](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html)を参照してください。

## オーディエンスのエクスポート {#exporting-an-audience}

オーディエンスは、ワークフローとアクティビティを使用して、Adobe CampaignからAudience ManagerまたはPeopleコアサービスにエクスポートで **[!UICONTROL Save audience]** きます。

新しいワークフローで実行でき、IMS（Adobe IDによる認証）を介して接続されたユーザーのみが実行できます。

1. プログラム、キャンペーンまたはマーケティングアクティビティのリストから新しいワークフローを作成します。
1. 利用可能な様々なアクティビティを使用して、一連のプロファイルをターゲット設定します。
1. ターゲット設定後、アクティビティをワークフ **[!UICONTROL Save audience]** ローにドラッグ&amp;ドロップして開きます。
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. フィールドを使用してオーディエンスを指 **[!UICONTROL Shared audience]** 定します。 開いたウィンドウで、既存のオーディエンスを選択するか、新しいオーディエンスを作成するかを選択できます。

   * 既存オーディエンスを選択した場合、新規レコードだけがオーディエンスに追加されます。
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.
   ![](assets/aam_save_audience_segment_picker.png)

   調整して交換するには、レコードにAdobe Experience Cloud ID（「訪問者ID」または「宣言済みID」）が含まれている必要があります。 オーディエンスのインポートおよびエクスポート時に、非調整レコードは無視されます。

1. 終了するには、画面の右上にあるチェックマークをクリックします。
1. 対応するを選択しま **[!UICONTROL Shared Data Source]**&#x200B;す。
1. 必要に応じて、書き出されたプロ **[!UICONTROL Generate an outbound transition]** ファイルを使用するチェックボックスをオンにします。 調整可能なプロファイルのみがエクスポートされます。
1. アクティビティの設定を確認し、ワークフローを保存します。
1. ワークフローを開始して、オーディエンスを書き出します。 Adobe CampaignとPeopleコアサービス間の同期には数時間かかる場合があります

Adobe Campaign と People コアサービス間の同期には、24～36 時間かかります。同期が終了すると、People コアサービスで新しいオーディエンスを検索できるようになり、そのオーディエンスを他の Adobe Experience Cloud ソリューションで再利用することができます。Adobe People コアサービスで Adobe Campaign の共有オーディエンスを使用する方法について詳しくは、この[ドキュメント](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html)を参照してください。

**関連トピック：**

* [ワークフロー](../../automating/using/workflow-data-and-processes.md)
* [オーディエンス](../../audiences/using/about-audiences.md)

