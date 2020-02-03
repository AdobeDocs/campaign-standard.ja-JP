---
title: Adobe Experience Manager での E メールコンテンツの作成.
description: Adobe Experience Managerの統合により、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# Adobe Experience Manager での E メールコンテンツの作成 {#creating-email-aem}

Adobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignの電子メールで使用できます。

この使用例では、Adobe Experience Managerで電子メールコンテンツを作成する方法を示します。

## 前提条件 {#prerequisites}

前もって次の要素があることを確認してください。

* An Adobe Experience Manager **authoring** instance
* An Adobe Experience Manager **publishing** instance
* Adobe Campaignインスタンス

## 設定 {#configuration}

2 つのソリューションを同時に使用するには、相互接続を設定する必要があります。

1. Adobe Campaign を設定します。手順は次のとおりです。

   * Adobe Experience Managerタイプの外部アカウントを設定します。
   * **[!UICONTROL AEMResourceTypeFilter]**オプションを設定します。このオプションは、Adobe Experience Manager で作成された Adobe Campaign 用のコンテンツタイプを認識します。
   * 電子メールテンプレートを作成し、Adobe Experience Managerコンテンツであることを指定して、以前に作成した外部アカウントをこのテンプレートにリンクします。

1. Adobe Experience Manager を設定します。手順は次のとおりです。

   * Adobe Experience Manager のオーサーインスタンスとパブリッシュインスタンスの間でレプリケーションを設定します。
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

## Adobe Experience Manager での E メールコンテンツの作成 {#use-case}

Adobe Experience Managerで電子メールコンテンツを作成するには：

1. Adobe Campaign 向けに特別に作成されたテンプレートを使用して、E メールコンテンツを作成します。
1. In the content properties, select the **[!UICONTROL Cloud Service]**corresponding to your Adobe Campaign instance.
1. テキスト、画像、パーソナライゼーションなどを挿入して、コンテンツを編集します。
1. コンテンツを検証します。

詳しくは、[詳細ドキュメント](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html)を参照してください。

![](assets/aem_content.png)

Adobe Campaignでコンテンツを取得するには：

1. Adobe Experience Managerタイプのコンテンツテンプレートに基づいて電子メールを作成します。
1. Adobe Campaign の E メールコンテンツ定義画面を使用して、作成したコンテンツを Adobe Experience Manager にリンクします。

![](assets/aem_linked_content.png)

