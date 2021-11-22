---
title: キャンペーンのアクティブなプロファイル
description: 顧客指標とアクティブなプロファイルにアクセスする方法を説明します
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 14%

---

# アクティブなプロファイル{#active-profiles}

Campaign 機能管理者は、 **[!UICONTROL Customer metrics]** から報告 **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

このレポートは、毎月 **[!UICONTROL Billing]** テクニカルワークフローと、 **アクティブなプロファイル**.

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
>管理者ユーザーは、インスタンスで使用されるアクティブなプロファイルの数をCampaign コントロールパネルから直接監視することもできます。 詳しくは、[Campaign コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=ja)を参照してください。
