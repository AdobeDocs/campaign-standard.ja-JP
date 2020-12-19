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

Peopleコアサービスの統合により、技術的なワークフローを介してオーディエンスをAdobe Campaignに直接インポートし、データベースを拡張できます。 Peopleコアサービスでのオーディエンス共有の詳細については、この[ドキュメント](https://docs.adobe.com/content/help/ja-JP/analytics/components/segmentation/segmentation-workflow/seg-publish.translate.html)を参照してください。

Adobe CampaignのPeopleコアサービスからのオーディエンス/セグメントの読み込みは、IMS(Adobe ID経由の認証)を介して接続されたユーザーのみが&#x200B;**[!UICONTROL Audiences]**&#x200B;メニューから実行できます。

1. **[!UICONTROL Audiences]**&#x200B;メニューに移動します。
1. アクションバーで、**[!UICONTROL Create]**&#x200B;を選択して画面に移動し、オーディエンスを作成します。
1. 新しいオーディエンスのラベルを指定します。
1. オーディエンス&#x200B;**[!UICONTROL Type]**&#x200B;を&#x200B;**[!UICONTROL Experience Cloud]**&#x200B;に設定し、作成中のオーディエンスがPeopleコアサービスからインポートされたオーディエンスであることを示します。
1. **[!UICONTROL Name of the shared audience]**&#x200B;フィールドから、読み込むオーディエンスを選択します。 インポートできるのはセグメントのみです。キーと値のペア、特徴、ルールなどの詳細データはサポートされません。

   ![](assets/aam_import_audience.png)

1. 対応する&#x200B;**[!UICONTROL Shared Data Source]**&#x200B;を選択します。

   選択したデータソースで暗号化アルゴリズムを使用するように設定されている場合は、**[!UICONTROL Force reconciliation with a profile]**&#x200B;に対する追加のオファーが表示されます。 データソースの&#x200B;**[!UICONTROL Channel]**&#x200B;フィールドが電子メールまたはモバイル(SMS)に設定されていて、プロファイルデータを活用したい場合は、このオプションを選択します。

   **[!UICONTROL Force reconciliation with a profile]**&#x200B;を選択せず、AMCデータソースで&#x200B;**[!UICONTROL Channel]**&#x200B;が電子メールまたはモバイル(SMS)に設定されている場合は、暗号化された宣言済みIDがすべて復号化されます。 タイプ&#x200B;**ファイル**&#x200B;のオーディエンスを、すべての電子メールアドレス/携帯電話番号のリストと共に作成/更新します。 これにより、この統合を通じて共有オーディエンスを読み込む際に、そのプロファイルがキャンペーンに存在しない場合でも、電子メールアドレスや携帯電話番号が失われることはありません。 この種のオーディエンスは、ワークフローを使用して手動で調整する必要があるので、直接使用することはできません。

1. 確認してオーディエンスを作成します。

   次に、オーディエンスを技術的なワークフローを介してインポートします。 これは、ID(「訪問者ID」または「宣言済みID」)をプロファイルディメンションと調整できたレコードで構成されます。 Adobe Campaign によって認識されない People コアサービスセグメントからの ID はインポートされません。

これで、オーディエンスがAdobe Campaignデータベースにインポートされました。 インポートプロセスで、People コアサービスまたは Audience Manager からセグメントを直接インポートする場合は、同期に 24～36 時間かかります。同期が終了すると、Adobe Campaign で新しいオーディエンスを検索したり、使用したりできます。

>[!NOTE]
>
>Adobe AnalyticsからAdobe Campaignにオーディエンスを読み込む場合、これらのオーディエンスは、まずPeopleコアサービスまたはAudience Managerで共有する必要があります。 このプロセスには 12～24 時間を要し、Campaign との同期にはさらに 24～36 時間が必要です。場合により、オーディエンスの共有プロセスは最大 60 時間に及ぶことがあります。People コアサービスと Audience Manager での Adobe Analytics オーディエンスの共有について詳しくは、この[ドキュメント](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html)を参照してください。

## オーディエンスのエクスポート {#exporting-an-audience}

オーディエンスは、ワークフローと&#x200B;**[!UICONTROL Save audience]**&#x200B;アクティビティを使用して、Adobe CampaignからAudience Managerにエクスポートしたり、Peopleコアサービスにエクスポートしたりできます。

新しいワークフローで実行でき、IMS(Adobe ID経由の認証)を介して接続されたユーザーのみが実行できます。

1. プログラム、キャンペーン、またはマーケティングアクティビティのリストから新しいワークフローを作成します。
1. 様々なアクティビティを使用して、一連のプロファイルをターゲットします。
1. ターゲット設定の後、**[!UICONTROL Save audience]**&#x200B;アクティビティをワークフローにドラッグ&amp;ドロップし、開きます。
1. 「**[!UICONTROL Share in Adobe Experience Cloud]**」を選択します。

   ![](assets/aam_save_audience_activity.png)

1. **[!UICONTROL Shared audience]**&#x200B;フィールドを使用してオーディエンスを指定します。 開いたウィンドウで、既存のオーディエンスを選択するか、新しいオーディエンスを作成するかを選択できます。

   * 既存オーディエンスを選択した場合、新規レコードだけがオーディエンスに追加されます。
   * プロファイルリストを新しいオーディエンスにエクスポートするには、**[!UICONTROL Segment name]**&#x200B;フィールドに入力し、**[!UICONTROL Create]**&#x200B;をクリックしてから、新しく作成したオーディエンスを選択します。

   ![](assets/aam_save_audience_segment_picker.png)

   調整して交換するには、レコードにAdobe Experience CloudID(「訪問者ID」または「宣言済みID」)が含まれている必要があります。 オーディエンスの読み込みおよび書き出し時に、非調整レコードは無視されます。

1. 終了するには、画面の右上にあるチェックマークをクリックします。
1. 対応する&#x200B;**[!UICONTROL Shared Data Source]**&#x200B;を選択します。
1. 必要に応じて、**[!UICONTROL Generate an outbound transition]**&#x200B;ボックスをオンにして、書き出されたプロファイルを使用します。 調整可能なプロファイルのみがエクスポートされます。
1. アクティビティの設定を確認し、ワークフローを保存します。
1. オーディエンスを書き出すためのワークフローを開始します。 Adobe CampaignとPeopleコアサービス間の同期には数時間かかる場合があります

Adobe Campaign と People コアサービス間の同期には、24～36 時間かかります。同期が終了すると、People コアサービスで新しいオーディエンスを検索できるようになり、そのオーディエンスを他の Adobe Experience Cloud ソリューションで再利用することができます。Adobe People コアサービスで Adobe Campaign の共有オーディエンスを使用する方法について詳しくは、この[ドキュメント](https://docs.adobe.com/content/help/ja-JP/core-services/interface/audiences/t-audience-create.html)を参照してください。

**関連トピック：**

* [ワークフロー](../../automating/using/get-started-workflows.md)
* [オーディエンス](../../audiences/using/about-audiences.md)

