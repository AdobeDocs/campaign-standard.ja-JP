---
title: Campaign アクティブなプロファイル
description: 顧客指標とアクティブなプロファイルにアクセスする方法について説明します
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
TQID: 'https://experienceleague.adobe.com/XKRIP6jfP3ROPWTN4moJKsBLQcRqmR3gSWZ-hi5P8I4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 13%
---
# アクティブなプロファイル{#active-profiles}

アクティブなプロファイルの詳細には、**[!UICONTROL Customer metrics]** レポートからアクセスできます。 このレポートは、Campaignの機能管理者のみが利用できます。 このレポートにアクセスするには、[ ユーザーインターフェイス ](../../start/using/interface-description.md#advanced-menu)の左上にあるAdobe Campaign アイコンをクリックし、**[!UICONTROL Administration > Customer metrics]**&#x200B;を参照します。

![](assets/audience_customer_metrics.png)

このレポートは、毎月&#x200B;**[!UICONTROL Billing]**&#x200B;のテクニカルワークフローによって生成され、**アクティブなプロファイル**&#x200B;の数が表示されます。 技術的なワークフローについて詳しくは、[このページ ](../../administration/using/technical-workflows.md)を参照してください。

「プロファイル」とは、最終顧客、見込み顧客、リードを表す情報の記録です。 任意のチャネルを介して過去12か月以内にキャンペーン配信によってターゲット設定されたプロファイルは、**アクティブ**&#x200B;とみなされます。

契約に従って、各Campaign インスタンスには特定の数のアクティブなプロファイルがプロビジョニングされます。 購入したアクティブなプロファイルの数については、使用許諾契約を参照してください。

![](assets/audience_active_profiles_list.png)



* 配信の準備中に除外されたプロファイル（タイポロジルールや強制隔離メカニズムなど）は考慮されません。

* トランザクションメッセージの受信者は、アクティブなプロファイルにカウントされます。

* プロファイルは、複数の配信のターゲットになっていても一度しかカウントされません。

* このレポートは情報提供に過ぎず、請求に直接影響を与えません。

ページの下部には、ターゲティングディメンションと、各ターゲティングディメンションのプロファイル数が表示されます。 トランザクションメッセージの受信者は、**匿名** ディメンションに関連付けられます。

>[!NOTE]
>
>管理者ユーザーは、インスタンスで使用されているアクティブなプロファイルの数をCampaign コントロールパネルから直接監視することもできます。 詳しくは、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=ja)を参照してください。
>
