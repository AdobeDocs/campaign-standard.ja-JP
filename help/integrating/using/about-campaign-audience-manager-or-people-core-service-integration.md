---
title: Campaign と Audience Manager または People コアサービスの統合について
description: Audience Manager/人物コアサービスの統合により、オーディエンスやセグメントを様々なAdobe Experience Cloudソリューション内で共有できます。
page-status-flag: never-activated
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 27%

---


# Campaign と Audience Manager または People コアサービスの統合について{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>交換されるデータに応じて、Adobe Campaignでのオーディエンスのインポートに関しては法的な制限が適用される場合があります。

Adobe Campaignを使用すると、オーディエンス/セグメントを別のAdobe Experience Cloudアプリケーションと交換および共有できます。 **Adobe Campaign** を **People コアサービス**（**Profiles &amp; Audiences コアサービス**&#x200B;とも呼ばれます）または Adobe Audience Manager と統合すると、次のことが可能になります。

* 様々なAdobe Experience CloudソリューションからAdobe Campaignにオーディエンス/セグメントをインポートする。 オーディエンスは、Adobe Campaignの **[!UICONTROL Audiences]** メニューから読み込むことができます。
* オーディエンスを共有オーディエンス/セグメントとして書き出す。 これらのオーディエンスは、お使いの他の Adobe Experience Cloud ソリューションで使用できます。オーディエンスは、ワークフローでアクティビティをターゲット設定した後に、 **[!UICONTROL Save audience]** アクティビティを使用して書き出すことができます。

統合では、2種類のAdobe Experience CloudIDがサポートされます。

* **訪問者ID**:このタイプのIDを使用すると、Adobe Experience Cloud訪問者をAdobe Campaignプロファイルと調整できます。 AdobeIMSを介した接続が有効になるとすぐに、Marketing Cloud訪問者IDサービスがアクティブ化され、Adobe Campaignで使用される永続的なcookieが置き換えられます。 これにより、訪問者を識別してプロファイルにリンクできます。
   <br>訪問者IDは、プロファイルがAdobe Campaign経由で送信された電子メール内でクリックするとすぐにプロファイルにリンクされます。
   * プロファイルに既に訪問者IDが割り当てられている場合、プロファイルのブラウザデータを使用して、Adobe Campaignがプロファイルを回復し、自動的に訪問者IDにリンクすることができます。
   * 訪問者 ID がない場合、新しい ID が作成されます。この訪問者IDは、プロファイルトラッキングログに格納されます。

   この ID は、他の Adobe Marketing Cloud アプリケーションに同じ CNAME で認識されます。

* **宣言済みID**:この種のIDを使用すると、任意の種類のデータをAdobe Campaignデータベースの要素と紐付けできます。 Adobe Campaign では、事前定義された紐付けキーとして示されます。データを交換する場合、Adobe Campaign データベースの識別子はハッシュ化されます。これらのハッシュ化された ID は、インポートまたはエクスポートに含まれる Adobe Marketing Cloud オーディエンスのハッシュ化された ID と比較されます。
   <br>この統合では、正規の宣言ID、ハッシュ化された宣言ID、暗号化された宣言IDをサポートします。

   >[!CAUTION]
   >
   >宣言済みIDはAdobe Audience Managerでのみ機能します。 宣言済みIDがないと機能しません。

   暗号化を使用すると、暗号化アルゴリズムを指定して、宣言済みIDを使用して、データソース（PIIなど）の暗号化されたデータを共有できます。

   例えば、暗号化された電子メールアドレスやSMS番号を復号化できる機能を備えたユーザーは、プロファイルがAdobe Campaignデータベースに存在しない場合でも、トリガーされたメッセージをユーザーに送信できます。

次の図は、この統合の仕組みについて詳しく説明しています。ここで、AAMはAdobe Audience Manageret ACSはAdobe Campaign Standardを表します。

![](assets/aam_diagram.png)