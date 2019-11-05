---
title: Experience Manager との統合
description: Adobe Experience Managerの統合により、AEMで直接コンテンツを作成し、後でAdobe Campaignで使用できます。
page-status-flag: 非活性化の
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: キャンペーンとエクスペリエンスの管理職との連携
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Experience Manager との統合{#integrating-with-experience-manager}

Adobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成されたコンテンツをAdobe Campaignの電子メールで使用できます。

したがって、Adobe Experience Managerのコンテンツ編集機能と、Adobe Campaignの配信およびデータ管理機能を最大限に活用できます。

>[!NOTE]
>
>Adobe Experience Managerから読み込んだコンテンツに対してはA/Bテストを実行できません。

Adobe Campaign Standardは、Adobe Experience Manager 6.1、6.2、6.3および6.4と互換性があります。以下の節では、実行できるアクションの概要を示します。 詳しくは、設定と統合の使用に関する節 [を参](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html) 照してください [](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) 。

## 前提条件 {#prerequisites}

前もって次の要素があることを確認してください。

* An Adobe Experience Manager **authoring** instance
* An Adobe Experience Manager **publishing** instance
* Adobe Campaignインスタンス

## 使用例 {#use-case}

Adobe Experience Managerで電子メールコンテンツを作成するには：

1. Adobe Campaign 向けに特別に作成されたテンプレートを使用して、E メールコンテンツを作成します。
1. In the content properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.
1. テキスト、画像、パーソナライゼーションなどを挿入して、コンテンツを編集します。
1. コンテンツを検証します。

詳しくは、[詳細ドキュメント](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html)を参照してください。

![](assets/aem_content.png)

Adobe Campaignでコンテンツを取得するには：

1. Adobe Experience Managerタイプのコンテンツテンプレートに基づいて電子メールを作成します。
1. Adobe Campaign の E メールコンテンツ定義画面を使用して、作成したコンテンツを Adobe Experience Manager にリンクします。

![](assets/aem_linked_content.png)

## 設定 {#configuration}

2 つのソリューションを同時に使用するには、相互接続を設定する必要があります。

1. Adobe Campaign を設定します。手順は次のとおりです。

   * Adobe Experience Managerタイプの外部アカウントを設定します。
   * **AEMResourceTypeFilter** オプションを設定します。このオプションは、Adobe Experience Manager で作成された Adobe Campaign 用のコンテンツタイプを認識します。
   * 電子メールテンプレートを作成し、Adobe Experience Managerコンテンツであることを指定して、以前に作成した外部アカウントをこのテンプレートにリンクします。

1. Adobe Experience Manager を設定します。手順は次のとおりです。

   * Adobe Experience Manager のオーサーインスタンスとパブリッシュインスタンスの間でレプリケーションを設定します。
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

