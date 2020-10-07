---
title: アクティブなプロファイル
description: 顧客指標に関する専用レポートにアクセスし、キャンペーンデータベースでアクティブなプロファイルを視覚化できます。
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---


# アクティブなプロファイル{#active-profiles}

Adobe Campaignは、アクティブなプロファイルの数を表示するレポートを提供します。 このレポートは情報を提供するだけで、請求に直接影響しません。 このレポートにアクセスできるのは、管理者のみです。 **[!UICONTROL Administration > Customer metrics]**

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>AWSでホストし、ビルド10368のCampaign Standardを使用している場合は、インスタンスで使用されるアクティブなプロファイルの数をCampaign コントロールパネルから直接監視することもできます。 詳しくは、[コントロールパネルのドキュメント](https://docs.adobe.com/content/help/ja-JP/control-panel/using/performance-monitoring/active-profiles-monitoring.html)を参照してください。
>
>Note that Active profiles metric is available and relevant for **Marketing instances** only. MID（ミッドソーシング）およびRT(Message Center/Real-time messaging)インスタンスを意味する、実行インスタンスには適用されず、使用できません。


配信の準備中に除外されたプロファイル(タイポロジルール、強制隔離、コントロール母集団)は考慮されません。 プロファイルは、複数の配信のターゲットになっていても一度しかカウントされません。レポートの下部には、各ターゲティングディメンションのアクティブなプロファイルのリストが表示されます。

このレポートは、 **[!UICONTROL Billing]** 技術的なワークフローによって毎月生成されます。 過去12か月間の周期中にターゲットにしたアクティブなプロファイルの数が含まれます。

配信の準備中に除外されたプロファイル(タイポロジルール、強制隔離)は考慮されません。 また、複数の配信がターゲットにしたプロファイルは1回だけカウントされます。

![](assets/audience_active_profiles2.png)

レポートの下部には、請求ワークフローで処理されるアクティブなプロファイルのリストが表示されます。

* この **[!UICONTROL NmsRecipient]** ソースには、Campaign Standardプロファイルの情報を使用して連絡を受けたすべての顧客が含まれます。

* 一方、特定の情報（電子メールアドレス、電話番号）のみを使用してターゲットを設定した顧客は、キャンペーンプロファイルとは無関係に、その **[!UICONTROL anonymous]** ソースに属します。
