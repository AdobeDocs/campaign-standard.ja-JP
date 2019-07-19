---
title: Campaign- Audience ManagerまたはPeopleコアサービス統合について
seo-title: Campaign- Audience ManagerまたはPeopleコアサービス統合について
description: Campaign- Audience ManagerまたはPeopleコアサービス統合について
seo-description: Audience Manager/Peopleコアサービスの統合により、様々なAdobe Experience Cloudソリューション内でオーディエンスやセグメントを共有できます。
page-status-flag: 常にアクティブ化されていない
uuid: 39e3c78e- ccd-4823- afe9- abc7f8aef034
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- audiences- manager- or- people- core- service
discoiquuid: bf718329- f181-46f7-80a2- b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About Campaign-Audience Manager or People core service integration{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaignを使用すると、様々なAdobe Experience Cloudアプリケーションでオーディエンスやセグメントを交換および共有できます。**Adobe Campaign** と **Peopleコアサービス** （Profiles&amp; Audiencesコアサービスと **も呼ばれる**）またはAdobe Audience Managerとの統合により、次のことができます。

* 異なるAdobe Experience CloudソリューションからAdobe Campaignにオーディエンス/セグメントをインポートします。Audiences can be imported from the **[!UICONTROL Audiences]** menu in Adobe Campaign.
* オーディエンスを共有オーディエンス/セグメントとしてエクスポートします。これらのオーディエンスは、使用する様々なAdobe Experience Cloudソリューションで使用できます。**[!UICONTROL Save audience]** アクティビティを使用して、ワークフローのターゲットアクティビティの後にオーディエンスをエクスポートできます。

統合では、2種類のAdobe Experience Cloud IDをサポートしています。

* **訪問者ID**:このタイプのIDを使用すると、Adobe Experience Cloud訪問者をAdobe Campaignプロファイルと調和させることができます。
* **宣言済みID**:このタイプのIDを使用すると、Adobe Campaignデータベースのプロファイルに任意の種類のデータを調整できます。この統合では、正規宣言されたID、ハッシュ化されたID、暗号化されたID IDがサポートされます。

   暗号化では、暗号化アルゴリズムを指定して、宣言されたIDを使用してデータソース（PIIなど）で暗号化されたデータを共有できます。

   例えば、暗号化された電子メールアドレスまたはSMS番号を復号化する機能では、Adobe Campaignデータベースにプロファイルが存在しない場合でも、トリガーされたメッセージをユーザーに送信できます。

>[!CAUTION]
>
>交換されたデータに応じて、Adobe Campaignでのオーディエンスのインポートには法的制限が適用される可能性があります

