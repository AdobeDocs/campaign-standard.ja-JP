---
title: Experience Managerとの統合
seo-title: Experience Managerとの統合
description: Experience Managerとの統合
seo-description: Adobe Experience Managerの統合により、コンテンツをAEMで直接作成し、後でAdobe Campaignで使用できます。
page-status-flag: 常にアクティブ化されていない
uuid: ed6c1b76-87f7-4d23- b5e2-0765297a905c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 統合
content-type: 参照
topic-tags: working- with- campaign- and- experience- manager
discoiquuid: 6c0c3c5b- b596-459e-87dd- a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Integrating with Experience Manager{#integrating-with-experience-manager}

Adobe Campaign StandardとAdobe Experience Managerの統合により、Adobe Experience Managerで作成したコンテンツをAdobe Campaign電子メールで使用できます。

そのため、Adobe Experience Managerのコンテンツ編集機能を最大限に活用し、Adobe Campaignの配信およびデータ管理機能を活用することができます。

>[!NOTE]
>
>Adobe Experience Managerからインポートしたコンテンツに対してA/Bテストを実行することはできません。

Adobe Campaign Standardは、Adobe Experience Manager6.1、6.2、6.3および6.4と互換性があります。次の節では、実行できるアクションの概要について説明します。For more information, refer to the sections dedicated to [configuration](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html) and the [use](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) of the integration.

## Prerequisites {#prerequisites}

次の要素が事前にあることを確認してください。

* An Adobe Experience Manager **authoring** instance
* An Adobe Experience Manager **publishing** instance
* Adobe Campaignインスタンス

## Use case {#use-case}

Adobe Experience Managerで電子メールコンテンツを作成するには:

1. Adobe Campaign専用のテンプレートを使用して、電子メールコンテンツを作成します。
1. In the content properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.
1. テキスト、画像、パーソナライゼーションなどを挿入してコンテンツを編集します。
1. コンテンツを検証します。

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html).

![](assets/aem_content.png)

Adobe Campaignでコンテンツを取得するには:

1. Adobe Experience Managerタイプのコンテンツテンプレートに基づいて電子メールを作成します。
1. Adobe Campaign電子メールコンテンツ定義画面を使用して、Adobe Experience Managerで作成したコンテンツをリンクします。

![](assets/aem_linked_content.png)

## Configuration {#configuration}

これらの2つのソリューションを一緒に使用するには、相互に接続するように設定する必要があります。

1. Adobe Campaignの設定を参照してください。これを行うには、次の手順に従います。

   * Adobe Experience Managerタイプの外部アカウントを設定します。
   * **Adobe Experience Manager用Adobe Experience Managerで作成されたコンテンツタイプを認識するAEMresourceTypeFilter** オプションを設定します。
   * Adobe Experience Managerコンテンツであることを指定し、以前に作成した外部アカウントをこのテンプレートにリンクする電子メールテンプレートを作成します。

1. Adobe Experience Managerを設定します。これを行うには、次の手順に従います。

   * Adobe Experience Managerのオーサリングインスタンスとパブリッシュインスタンス間の複製を設定します。
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

