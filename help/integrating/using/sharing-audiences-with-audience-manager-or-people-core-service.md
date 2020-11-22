---
solution: Campaign Standard
product: campaign
title: Audience Manager または People コアサービスのオーディエンスを共有
description: 様々なAdobe Experience Cloudソリューション内でのオーディエンスの読み込みまたは書き出し方法を説明します。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 29%

---


# Audience Manager または People コアサービスのオーディエンスを共有{#sharing-audiences-with-audience-manager-or-people-core-service}

## オーディエンスのインポート {#importing-an-audience}

Peopleコアサービスの統合により、技術的なワークフローを介してオーディエンスをAdobe Campaignに直接インポートし、データベースを拡張できます。 For more information on audience sharing in People core service, refer to this [documentation](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-publish.translate.html).

Adobe CampaignのPeopleコアサービスからオーディエンス/セグメントを読み込むことは、IMS(Adobe ID経由の認証)を使用して接続しているユーザーのみが **[!UICONTROL Audiences]** メニューから実行できます。

1. Go to the **[!UICONTROL Audiences]** menu.
1. アクションバーで、オーディエンスを作成す **[!UICONTROL Create]** る画面に移動することを選択します。
1. 新しいオーディエンスのラベルを指定します。
1. オーディエンス **[!UICONTROL Type]****[!UICONTROL Experience Cloud]** をに設定し、作成するオーディエンスがPeopleコアサービスから読み込まれたオーディエンスであることを示します。
1. フィールドから、読み込むオーディエンスを選択し **[!UICONTROL Name of the shared audience]** ます。 インポートできるのはセグメントのみです。キーと値のペア、特徴、ルールなどの詳細データはサポートされません。

   ![](assets/aam_import_audience.png)

1. 対応するを選択し **[!UICONTROL Shared Data Source]**&#x200B;ます。

   選択したデータソースで暗号化アルゴリズムを使用するように設定されている場合は、他のオファーも使用でき **[!UICONTROL Force reconciliation with a profile]**&#x200B;ます。 データソースの **[!UICONTROL Channel]** フィールドが電子メールまたはモバイル(SMS)に設定されていて、プロファイルデータを活用する場合は、このオプションを選択します。

   を選択しない場合 **[!UICONTROL Force reconciliation with a profile]** 、およびがAMCデータソースで電子メールまたはモバイル(SMS)に設定さ **[!UICONTROL Channel]** れている場合は、暗号化された宣言済みIDがすべて復号化されます。 すべての電子メールアドレス/携帯電話番号のリストを持つ **File** （ファイル）タイプのオーディエンスが作成/更新されます。 これにより、この統合を通じて共有オーディエンスを読み込む際に、そのプロファイルがキャンペーンに存在しない場合でも、電子メールアドレスや携帯電話番号が失われることはありません。 この種のオーディエンスは、ワークフローを使用して手動で調整する必要があるので、直接使用することはできません。

1. 確認してオーディエンスを作成します。

   次に、オーディエンスを技術的なワークフローを介してインポートします。 これは、ID(「訪問者ID」または「宣言済みID」)をプロファイルディメンションと調整できたレコードで構成されます。 Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。

これで、オーディエンスがAdobe Campaignデータベースにインポートされました。 インポートプロセスで、People コアサービスまたは Audience Manager からセグメントを直接インポートする場合は、同期に 24～36 時間かかります。同期が終了すると、Adobe Campaign で新しいオーディエンスを検索したり、使用したりできます。

>[!NOTE]
>
>Adobe AnalyticsからAdobe Campaignにオーディエンスを読み込む場合、これらのオーディエンスは、まずPeopleコアサービスまたはAudience Managerで共有する必要があります。 このプロセスには 12～24 時間を要し、Campaign との同期にはさらに 24～36 時間が必要です。場合により、オーディエンスの共有プロセスは最大 60 時間に及ぶことがあります。People コアサービスと Audience Manager での Adobe Analytics オーディエンスの共有について詳しくは、この[ドキュメント](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-publish.translate.html)を参照してください。

## オーディエンスのエクスポート {#exporting-an-audience}

ワークフローと **[!UICONTROL Save audience]** アクティビティを使用して、オーディエンスをAdobe CampaignからAudience Managerにエクスポートしたり、Peopleコアサービスにエクスポートしたりできます。

新しいワークフローで実行でき、IMS(Adobe ID経由の認証)を介して接続されたユーザーのみが実行できます。

1. プログラム、キャンペーン、またはマーケティングアクティビティのリストから新しいワークフローを作成します。
1. 様々なアクティビティを使用して、一連のプロファイルをターゲットします。
1. ターゲット設定の後、ワークフローに **[!UICONTROL Save audience]** アクティビティをドラッグ&amp;ドロップしてから開きます。
1. 「**[!UICONTROL Share in Adobe Experience Cloud]**」を選択します。

   ![](assets/aam_save_audience_activity.png)

1. フィールドを使用してオーディエンスを指定し **[!UICONTROL Shared audience]** ます。 開いたウィンドウで、既存のオーディエンスを選択するか、新しいオーディエンスを作成するかを選択できます。

   * 既存オーディエンスを選択した場合、新規レコードだけがオーディエンスに追加されます。
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.

   ![](assets/aam_save_audience_segment_picker.png)

   調整して交換するには、レコードにAdobe Experience CloudID(「訪問者ID」または「宣言済みID」)が含まれている必要があります。 オーディエンスの読み込みおよび書き出し時に、非調整レコードは無視されます。

1. 終了するには、画面の右上にあるチェックマークをクリックします。
1. 対応するを選択し **[!UICONTROL Shared Data Source]**&#x200B;ます。
1. 必要に応じて、書き出されたプロファイルを使用する **[!UICONTROL Generate an outbound transition]** ボックスをオンにします。 調整可能なプロファイルのみがエクスポートされます。
1. アクティビティの設定を確認し、ワークフローを保存します。
1. オーディエンスを書き出すためのワークフローを開始します。 Adobe CampaignとPeopleコアサービス間の同期には数時間かかる場合があります

Adobe Campaign と People コアサービス間の同期には、24～36 時間かかります。同期が終了すると、People コアサービスで新しいオーディエンスを検索できるようになり、そのオーディエンスを他の Adobe Experience Cloud ソリューションで再利用することができます。Adobe People コアサービスで Adobe Campaign の共有オーディエンスを使用する方法について詳しくは、この[ドキュメント](https://docs.adobe.com/content/help/ja-JP/core-services/interface/audiences/t-audience-create.html)を参照してください。

**関連トピック：**

* [ワークフロー](../../automating/using/get-started-workflows.md)
* [オーディエンス](../../audiences/using/about-audiences.md)

