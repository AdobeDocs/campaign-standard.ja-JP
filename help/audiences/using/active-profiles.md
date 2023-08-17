---
title: キャンペーンのアクティブなプロファイル
description: 顧客指標とアクティブなプロファイルにアクセスする方法を説明します
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: 0ae2501b5c3ecf6dc9562bb53b5354c52aff7323
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 12%

---

# アクティブなプロファイル{#active-profiles}

アクティブなプロファイルの詳細には、 **[!UICONTROL Customer metrics]** レポート。 このレポートは、Campaign 機能管理者のみが使用できます。 このレポートにアクセスするには、 [ユーザーインターフェイス](../../start/using/interface-description.md#advanced-menu)をクリックし、 **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

このレポートは、毎月 **[!UICONTROL Billing]** テクニカルワークフローと、 **アクティブなプロファイル**. テクニカルワークフローの詳細については、 [このページ](../../administration/using/technical-workflows.md).

「プロファイル」とは、エンド顧客、見込み客、またはリードを表す情報の記録です。 プロファイルは考慮されます **アクティブ** 過去 12 ヶ月以内に任意のチャネルを介して Campaign 配信のターゲットにされている場合。

各 Campaign インスタンスには、契約に従って特定数のアクティブなプロファイルがプロビジョニングされます。 購入したアクティブなプロファイルの数については、使用許諾契約を参照してください。

![](assets/audience_active_profiles_list.png)



* （タイポロジルールや強制隔離メカニズムなどによって）配信の準備中に除外されたプロファイルは、考慮されません。

* トランザクションメッセージの受信者は、アクティブなプロファイルにカウントされます。

* プロファイルは、複数の配信のターゲットになっていても一度しかカウントされません。

* このレポートは情報提供のみで、請求に直接影響しません。

ページの下部に、ターゲティングディメンションと、それぞれのプロファイル数が表示されます。 トランザクションメッセージの受信者は、 **匿名** ディメンション。

>[!NOTE]
>
>管理者ユーザーは、インスタンスで使用されるアクティブなプロファイルの数をCampaign コントロールパネルから直接監視することもできます。 詳しくは、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=ja)を参照してください。
>
