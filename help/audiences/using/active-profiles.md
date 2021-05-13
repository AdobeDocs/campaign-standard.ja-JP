---
solution: Campaign Standard
product: campaign
title: キャンペーンアクティブプロファイル
description: 顧客指標およびアクティブなプロファイルにアクセスする方法について説明します。
feature: プロファイル
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d2fcf2ca22bb5fe3632280f922dfed0972f6eb09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 12%

---

# 顧客指標 {#customer-metrics}

キャンペーン機能の管理者は、**[!UICONTROL Administration > Customer metrics]**&#x200B;から&#x200B;**[!UICONTROL Customer metrics]**&#x200B;レポートにアクセスできます。

![](assets/audience_active_profiles1.png)

このレポートには次の情報が表示されます。

* Experience CloudID
* IMS組織ID
* **アクティブなプロファイル**&#x200B;の数
* インスタンスで使用可能なターゲティングディメンションのリスト

このレポートは、テクニカルワークフロー&#x200B;**[!UICONTROL Billing]**&#x200B;によって毎月生成されます。

## アクティブなプロファイル{#active-profiles}

契約に従って、各キャンペーンインスタンスには、特定の数のアクティブなプロファイルがプロビジョニングされます。 購入したアクティブなプロファイルの数については、使用許諾契約書を参照してください。

>[!NOTE]
>
>管理者ユーザーは、インスタンスで使用されるアクティブなプロファイルの数をCampaign コントロールパネルから直接監視することもできます。 詳しくは、[コントロールパネルのドキュメント](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=ja)を参照してください。


「プロファイル」とは、エンド顧客、見込み客、またはリードを表す情報の記録です。 プロファイルが、過去12か月間に何らかのチャネルを介してキャンペーン配信によってターゲット設定された場合、**アクティブ**&#x200B;と見なされます。 配信の準備中に除外されたプロファイル(タイポロジルールや強制隔離メカニズムなどによる)は考慮されません。 プロファイルは、複数の配信のターゲットになっていても一度しかカウントされません。このレポートは情報を提供するだけで、請求に直接影響しません。

![](assets/audience_active_profiles2.png)

レポートの下部には、各ターゲティングディメンションのアクティブなプロファイルのリストが表示されます。 過去12か月間の周期中にターゲットにしたアクティブなプロファイルの数が表示されます。

* **[!UICONTROL NmsRecipient]**&#x200B;ソースには、Campaign Standardプロファイルの情報を使用して接続されたすべてのプロファイルが含まれています。

* 顧客&#x200B;**[!UICONTROL anonymous]**&#x200B;のソースは、特定のプロファイル（電子メールアドレス、電話番号）のみを使用し、キャンペーンプロファイルとは無関係にターゲットにした情報の数を表示します。
