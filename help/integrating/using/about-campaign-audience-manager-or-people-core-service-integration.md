---
title: Campaign と Audience Manager または People コアサービスの統合について
description: Audience Manager/人物コアサービスの統合を使用すると、様々なAdobe Experience Cloud ソリューション内でオーディエンスやセグメントを共有できます。
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
ht-degree: 31%

---

# Campaign と Audience Manager または People コアサービスの統合について{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>交換するデータによっては、Adobe Campaignでのオーディエンスの読み込みが法的規制の対象となる場合があります。

Adobe Campaignでは、様々なAdobe Experience Cloud アプリケーションとのオーディエンス/セグメントの交換および共有が可能です。 **Adobe Campaign** を **People コアサービス**（**Profiles &amp; Audiences コアサービス**&#x200B;とも呼ばれます）または Adobe Audience Manager と統合すると、次のことが可能になります。

* 様々なAdobe Experience Cloud ソリューションからAdobe Campaignにオーディエンス/セグメントを読み込みます。 オーディエンスは、Adobe Campaignの **[!UICONTROL Audiences]** メニューから読み込むことができます。
* オーディエンスを共有オーディエンス / セグメントとして書き出します。 これらのオーディエンスは、お使いの他の Adobe Experience Cloud ソリューションで使用できます。オーディエンスは、**[!UICONTROL Save audience]** アクティビティを使用して、ワークフローのターゲティングアクティビティの後に書き出すことができます。

の統合では、次の 2 種類のAdobe Experience Cloud ID をサポートしています。

* **訪問者 ID**：このタイプの ID を使用すると、Adobe Experience Cloudの訪問者をAdobe Campaign プロファイルと紐付けできます。 Adobe IMSで接続が有効になるとすぐに、Marketing Cloud訪問者 ID サービスがアクティブになります。これはAdobe Campaignで使用される永続的な cookie に代わるものです。 これにより、訪問者を識別してプロファイルにリンクできます。
  <br> 訪問者 ID は、Adobe Campaign経由で送信されたメールでプロファイルがクリックされるとすぐに、プロファイルにリンクされます。
   * プロファイルに既に訪問者 ID がある場合、プロファイルのブラウザーデータを使用すると、Adobe Campaignを復元して、プロファイルを訪問者 ID に自動的にリンクできます。
   * 訪問者 ID が見つからない場合は、新しい ID が作成されます。 この訪問者 ID は、プロファイルトラッキングログに保存されます。

  この ID は、他の Adobe Marketing Cloud アプリケーションに同じ CNAME で認識されます。

* **宣言済み ID**：このタイプの ID を使用すると、あらゆる種類のデータをAdobe Campaign データベース内の要素と紐付けできます。 Adobe Campaignでは、事前定義された紐付けキーとして表されます。 データを交換する際、Adobe Campaign データベースの識別情報はハッシュ化されます。 これらのハッシュ化された ID は、インポートまたはエクスポートに含まれる Adobe Marketing Cloud オーディエンスのハッシュ化された ID と比較されます。
  <br> この統合では、通常の宣言済み ID、ハッシュ化された宣言済み ID および暗号化された宣言済み ID がサポートされます。

  >[!NOTE]
  >
  >宣言済み ID データソースも People コアサービス統合で使用できるようになりました。 
  >
  >People コアサービス統合を使用していて、Audience Manager 統合を追加する場合は、Adobe Audience Manager コンテキストでこの宣言済み ID データソースに移行する際に収集された ID 同期がすべて失われないように、Adobe Audience Manager コンサルタントの支援が必要です。


  暗号化を使用すると、暗号化アルゴリズムを指定することで、宣言された ID を使用して、データソース（PII など）内の暗号化されたデータを共有できます。

  例えば、暗号化されたメールアドレスや SMS 番号の復号機能を使用すると、プロファイルがAdobe Campaign データベースに存在しない場合でも、トリガーメッセージをユーザーに送信できます。

次の図は、この統合の仕組みについて詳しく説明しています。ここで、AAMはAdobe Audience Managerを、ACS はAdobe Campaign Standardを表します。

![](assets/aam_diagram.png)
