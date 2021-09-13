---
title: Campaign と Audience Manager または People コアサービスの統合について
description: Audience Manager/Peopleコアサービスの統合により、様々なAdobe Experience Cloudソリューション内でオーディエンスやセグメントを共有できます。
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 38%

---

# Campaign と Audience Manager または People コアサービスの統合について{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>交換するデータに応じて、Adobe Campaignでのオーディエンスのインポートは法的制限の対象となる場合があります。

Adobe Campaignでは、様々なAdobe Experience Cloudアプリケーションとオーディエンス/セグメントを交換し、共有できます。 **Adobe Campaign** を **People コアサービス**（**Profiles &amp; Audiences コアサービス**&#x200B;とも呼ばれます）または Adobe Audience Manager と統合すると、次のことが可能になります。

* 別のAdobe Experience CloudソリューションからAdobe Campaignにオーディエンス/セグメントをインポートします。 オーディエンスは、Adobe Campaignの&#x200B;**[!UICONTROL Audiences]**&#x200B;メニューからインポートできます。
* オーディエンスを共有オーディエンス/セグメントとしてエクスポートする。 これらのオーディエンスは、お使いの他の Adobe Experience Cloud ソリューションで使用できます。オーディエンスは、ワークフロー内のアクティビティのターゲティング後に、**[!UICONTROL Save audience]**&#x200B;アクティビティを使用してエクスポートできます。

統合では、次の2種類のAdobe Experience Cloud IDをサポートしています。

* **訪問者ID**:このタイプのIDを使用すると、Adobe Experience Cloudの訪問者をAdobe Campaignのプロファイルと紐付けできます。Adobe IMSを介した接続が有効になるとすぐに、Marketing Cloud訪問者IDサービスがアクティブ化され、Adobe Campaignが使用する永続的なcookieが置き換えられます。 これにより、訪問者を識別し、その訪問者をプロファイルにリンクできます。
   <br>訪問者IDは、Adobe Campaignを介して送信された電子メールをプロファイルがクリックするとすぐに、プロファイルにリンクされます。
   * プロファイルに既に訪問者IDがある場合、プロファイルのブラウザーデータを使用すると、Adobe Campaignがプロファイルを復元し、自動的に訪問者IDにリンクできます。
   * 訪問者 ID がない場合、新しい ID が作成されます。この訪問者IDは、プロファイルトラッキングログに保存されます。

   この ID は、他の Adobe Marketing Cloud アプリケーションに同じ CNAME で認識されます。

* **宣言済みID**:このタイプのIDを使用すると、任意のタイプのデータをAdobe Campaignデータベースから取得した要素に紐付けできます。Adobe Campaign では、事前定義された紐付けキーとして示されます。データを交換する場合、Adobe Campaign データベースの識別子はハッシュ化されます。これらのハッシュ化された ID は、インポートまたはエクスポートに含まれる Adobe Marketing Cloud オーディエンスのハッシュ化された ID と比較されます。
   <br>この統合では、通常の宣言済みID、ハッシュ化された宣言済みID、暗号化された宣言済みIDをサポートします。

   >[!NOTE]
   >
   >宣言済み ID データソースも People コアサービス統合で使用できるようになりました。 
   >
   >People コアサービス統合を使用していて、Audience Manager 統合を追加する場合は、Adobe Audience Manager コンテキストでこの宣言済み ID データソースに移行する際に収集された ID 同期がすべて失われないように、Adobe Audience Manager コンサルタントの支援が必要です。


   暗号化を使用すると、暗号化アルゴリズムを指定することで、宣言済みIDを使用してデータソース（PIIなど）で暗号化されたデータを共有できます。

   例えば、暗号化されたEメールアドレスやSMS番号を復号化する機能を使用して、ユーザーのプロファイルがAdobe Campaignデータベースに存在しない場合でも、トリガーされたメッセージをユーザーに送信できます。

次の図は、この統合の仕組みについて詳しく説明しています。ここで、AAMはAdobe Audience Managerを表し、ACSはAdobe Campaign Standardを表します。

![](assets/aam_diagram.png)
