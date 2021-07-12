---
solution: Campaign Standard
product: campaign
title: キャンペーンのアクティブなプロファイル
description: 顧客指標とアクティブなプロファイルにアクセスする方法を説明します
feature: プロファイル
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 14%

---

# アクティブなプロファイル{#active-profiles}

Campaign機能の管理者は、**[!UICONTROL Administration > Customer metrics]**&#x200B;から&#x200B;**[!UICONTROL Customer metrics]**&#x200B;レポートにアクセスできます。

![](assets/audience_customer_metrics.png)

このレポートは、毎月&#x200B;**[!UICONTROL Billing]**&#x200B;テクニカルワークフローによって生成され、**アクティブなプロファイル**&#x200B;の数が表示されます。

「プロファイル」とは、エンド顧客、見込み客、リードを表す情報の記録です。 過去12ヶ月以内に任意のチャネルを介してキャンペーン配信のターゲットにされたプロファイルは、**アクティブ**&#x200B;と見なされます。

契約に従って、各Campaignインスタンスには、特定の数のアクティブなプロファイルがプロビジョニングされます。 購入したアクティブなプロファイルの数については、使用許諾契約を参照してください。

![](assets/audience_active_profiles_list.png)



* （タイポロジルールや強制隔離メカニズムなどによって）配信の準備中に除外されたプロファイルは、考慮されません。

* トランザクションメッセージの受信者は、アクティブなプロファイルにカウントされます。

* プロファイルは、複数の配信のターゲットになっていても一度しかカウントされません。

* このレポートは情報提供のみで、請求に直接的な影響はありません。

ページの下部に、ターゲティングディメンションが各プロファイルの数と共に表示されます。 トランザクションメッセージの受信者は、**匿名**&#x200B;ディメンションに関連付けられます。

>[!NOTE]
>
>管理者ユーザーは、インスタンスで使用されるアクティブなプロファイルの数を、Campaign コントロールパネルから直接監視することもできます。 詳しくは、[Campaign コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=ja)を参照してください。

