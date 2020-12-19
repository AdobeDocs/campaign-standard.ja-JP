---
solution: Campaign Standard
product: campaign
title: アクティブなプロファイル
description: 顧客指標に関する専用レポートにアクセスし、キャンペーンデータベースでアクティブなプロファイルを視覚化できます。
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---


# アクティブなプロファイル{#active-profiles}

Adobe Campaignは、アクティブなプロファイルの数を表示するレポートを提供します。 このレポートは情報を提供するだけで、請求に直接影響しません。 **[!UICONTROL Administration > Customer metrics]**&#x200B;の下で、管理者のみがこのレポートにアクセスできます。

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>AWSでホストし、ビルド10368のCampaign Standardを使用している場合は、インスタンスで使用されるアクティブなプロファイルの数をCampaign コントロールパネルから直接監視することもできます。 詳しくは、[コントロールパネルのドキュメント](https://docs.adobe.com/content/help/ja-JP/control-panel/using/performance-monitoring/active-profiles-monitoring.html)を参照してください。
>
>アクティブなプロファイル指標は使用可能で、**マーケティングインスタンス**&#x200B;にのみ関連します。 MID（ミッドソーシング）およびRT(Message Center/Real-time messaging)インスタンスを意味する、実行インスタンスには適用されず、使用できません。


配信の準備中に除外されたプロファイル(タイポロジルール、強制隔離、コントロール母集団)は考慮されません。 プロファイルは、複数の配信のターゲットになっていても一度しかカウントされません。レポートの下部には、各ターゲティングディメンションのアクティブなプロファイルのリストが表示されます。

このレポートは、テクニカルワークフロー&#x200B;**[!UICONTROL Billing]**&#x200B;によって毎月生成されます。 過去12か月間の周期中にターゲットにしたアクティブなプロファイルの数が含まれます。

配信の準備中に除外されたプロファイル(タイポロジルール、強制隔離)は考慮されません。 また、複数の配信がターゲットにしたプロファイルは1回だけカウントされます。

![](assets/audience_active_profiles2.png)

レポートの下部には、請求ワークフローで処理されるアクティブなプロファイルのリストが表示されます。

* **[!UICONTROL NmsRecipient]**&#x200B;ソースには、Campaign Standardプロファイルの情報を使用して連絡を受けたすべての顧客が含まれます。

* 一方、特定の情報（電子メールアドレス、電話番号）のみを使用してターゲットに設定され、キャンペーンプロファイルとは無関係の顧客は&#x200B;**[!UICONTROL anonymous]**&#x200B;のソースに属します。
