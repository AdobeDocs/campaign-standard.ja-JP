---
title: Campaign と Audience Manager または People コアサービス統合について
description: Audience ManagerとPeopleコアサービスの統合により、様々なAdobe Experience cloudソリューション内でオーディエンスやセグメントを共有できます。
page-status-flag: never-activated
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0062079addfbcd577faa1b16096f4588a05a8f78

---


# Campaign と Audience Manager または People コアサービス統合について{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaignを使用すると、様々なAdobe Experience cloudアプリケーションとオーディエンス/セグメントを交換および共有できます。 **Adobe Campaign** を **People コアサービス**（**Profiles &amp; Audiences コアサービス**&#x200B;とも呼ばれます）または Adobe Audience Manager と統合すると、次のことが可能になります。

* 様々なAdobe Experience cloudソリューションからAdobe Campaignにオーディエンス/セグメントをインポートします。 オーディエンスは、Adobe Campaignのメニュー **[!UICONTROL Audiences]** からインポートできます。
* 共有オーディエンス/セグメントとしてオーディエンスを書き出します。 これらのオーディエンスは、お使いの他の Adobe Experience Cloud ソリューションで使用できます。オーディエンスは、アクティビティを使用して、ワークフロー内のアクティビティをターゲット化した後にエクスポート **[!UICONTROL Save audience]** できます。

統合では、次の2種類のAdobe Experience Cloud IDがサポートされます。

* **訪問者ID**:このタイプのIDを使用すると、Adobe Experience cloudの訪問者をAdobe Campaignのプロファイルと紐付けることができます。
* **宣言済みID**:このタイプのIDを使用すると、任意のタイプのデータをAdobe Campaignデータベース内のプロファイルと調整できます。 この統合は、正規の宣言ID、ハッシュ化された宣言ID、暗号化された宣言IDをサポートします。

   暗号化を使用すると、暗号化アルゴリズムを指定して、宣言されたIDを使用して、データソース（PIIなど）の暗号化されたデータを共有できます。

   例えば、暗号化された電子メールアドレスやSMS番号を復号化できる機能を使用して、ユーザーのプロファイルがAdobe Campaignデータベースに存在しない場合でも、トリガーされたメッセージをユーザーに送信できます。

>[!CAUTION]
>
>交換されるデータによっては、Adobe Campaign でのオーディエンスのインポートは法規制の対象となる場合があります。

