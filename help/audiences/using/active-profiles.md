---
title: Campaign のアクティブなプロファイル
description: 顧客指標とアクティブなプロファイルにアクセスする方法を学ぶ
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: 0ae2501b5c3ecf6dc9562bb53b5354c52aff7323
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 10%

---

# アクティブなプロファイル{#active-profiles}

**[!UICONTROL Customer metrics]** レポートからアクティブなプロファイルの詳細にアクセスできます。 このレポートは、Campaign 機能管理者のみが使用できます。 このレポートにアクセスするには、[ ユーザーインターフェイス ](../../start/using/interface-description.md#advanced-menu) の左上にあるAdobe Campaign アイコンをクリックして、**[!UICONTROL Administration > Customer metrics]** を参照します。

![](assets/audience_customer_metrics.png)

このレポートは、**[!UICONTROL Billing]** テクニカルワークフローによって毎月生成され、**アクティブなプロファイル** の数を表示します。 テクニカルワークフローについて詳しくは、[ このページ ](../../administration/using/technical-workflows.md) を参照してください。

「プロファイル」は、エンドカスタマー、見込み客またはリードを表す情報のレコードです。 過去 12 か月以内に任意のチャネルを介してキャンペーン配信のターゲットとなったプロファイルは、**アクティブ** と見なされます。

各 Campaign インスタンスには、契約に従って特定数のアクティブなプロファイルがプロビジョニングされます。 購入したアクティブなプロファイルの数については、使用許諾契約書を参照してください。

![](assets/audience_active_profiles_list.png)



* 配信準備（タイポロジルールや強制隔離メカニズムなど）の際に除外されたプロファイルは考慮されません。

* トランザクションメッセージの受信者は、アクティブなプロファイルにカウントされます。

* プロファイルは、複数の配信のターゲットになっていても一度しかカウントされません。

* このレポートは情報提供だけを目的としており、請求に直接影響を与えるものではありません。

ページの下部に、ターゲティングディメンションと、それぞれのプロファイル数が表示されます。 トランザクションメッセージの受信者は、**匿名** ディメンションに関連付けられます。

>[!NOTE]
>
>管理者ユーザーは、インスタンスで使用されているアクティブなプロファイルの数をCampaign コントロールパネルから直接監視することもできます。 詳しくは、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=ja)を参照してください。
>
