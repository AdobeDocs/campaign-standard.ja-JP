---
title: ブランディング
seo-title: ブランディング
description: ブランディング
seo-description: ブランドIDの管理に使用できるすべてのツールを見つけます。
page-status-flag: 常にアクティブ化されていない
uuid: d66ac5a2-2ae1-4870- b48e-7f276744ffdd
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: アプリケーション設定
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32bf8
context-tags: ブランド、概要;branding， main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Branding{#branding}

## About brand identity {#about-brand-identity}

各社には、ブランドの視覚的なガイドラインと技術的ガイドラインがあります。Adobe Campaignでは、一連の仕様を定義して、電子メールの送信者、URL、ドメインなどの技術的な観点から、顧客に一貫したブランドを提示することができます。

技術者は1つまたは複数のブランドを定義して、ブランドのIDに影響を与えるパラメーターを一元的に入力できます。これには、ブランドロゴ、ランディングページのアクセスURLのドメイン、メッセージトラッキング設定が含まれます。Adobe Campaignでは、これらのブランドを作成して、メッセージやランディングページにリンクできます。この設定はテンプレートで管理されます。

## Configuring and using brands {#configuring-and-using-brands}

ブランドを設定し、使用する主な原則は次のとおりです。

1. ブランドを作成および設定します。この操作には特定の権限が必要で、Adobe Campaignテクニカル管理者によって実行されます。
1. このブランドの配信およびランディングページテンプレートを1つまたは複数作成します。Refer to the [Creating a template](../../start/using/about-templates.md) section.
1. このテンプレートに基づいてメッセージおよびランディングページを作成します。Refer to the [Creating an email](../../channels/using/creating-an-email.md) and [Creating a landing page](../../channels/using/designing-a-landing-page.md) sections.

>[!CAUTION]
>
>ブランドはエンドユーザーによって作成または変更できません。これらの操作は、Adobe Campaignのテクニカル管理者が実行する必要があります。リクエストについては、アドビカスタマーケアにお問い合わせください。マルチブランディングはトランザクションメッセージングのコンテキストでは使用できません。For more on this, see [Transactional messages and branding](../../channels/using/about-transactional-messaging.md#permissions-and-branding).

Brands can be found in the **[!UICONTROL Administration > Instance settings > Brand configuration]** menu.

デフォルトでは、新規作成されたブランドは、管理者によって割り当てられた対応する権限で割り当てられたユーザーにのみ表示されます。

**ブランド** は、次の特性によって定義されます。

* **ブランド**&#x200B;を定義し、パーソナライズするID。この節では、以下のフィールドについて説明します。

   ![](assets/branding_01.png)

   * **インターフェイスに表示さ** れるラベル
   * **ブランド名**
   * **WebサイトのURL** と **Webサイトのラベル**
   * **ブランドロゴ**

* **[!UICONTROL Header parameters of sent emails]** これにより、キャンペーンの受信者がどのように表示されるかがわかります。この節では、以下のフィールドについて説明します。

   ![](assets/branding_04_header.png)

   * **Sender（電子メールアドレス）** とブランドの電子メールアドレス。
   * **Sender（名前）** とブランド名。
   * **顧客が返信できる電子メールアドレス** に対する返信（電子メールアドレス）。
   * **ブランド名** による返信（名前）。
   * **エラーの場合に使用する電子メールアドレス** を持つエラー（電子メールアドレス）。
   >[!CAUTION]
   >
   >電子メールのヘッダーパラメーターを更新した後、送信者の名前と電子メールアドレスがテンプレートから作成された電子メール内で変更されていない場合は、テンプレートの詳細設定を確認してください。

* **インターネット** に公開されているサーバーは、トラッキングに使用するサーバーを定義し、ランディングページへのアクセスも定義します。この節では、以下のフィールドについて説明します。

   ![](assets/configure_branding_04.png)

   * **作成した様々なランディングページにアクセスしてアクセスするために** 使用されるアプリケーションサーバーの外部URL。
   * **配信中にトラッキングされたURLとして** 使用されるトラッキングサーバーの外部URL。
   * **配信のデフォルトミラーページとし** て使用されるミラーページサーバの外部URL。

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**&#x200B;を使用して、ブランドのURLトラッキングの設定を定義します。

   Adobe AnalyticsやGoogle Analyticsなどの外部システムでリンクを追跡するための追加のパラメーターは、ここで定義します。

   ![](assets/branding_05.png)

## Assigning a brand to an email {#assigning-a-brand-to-an-email}

### Linking a brand to a template {#linking-a-brand-to-a-template}

ブランド用に定義されたパラメーターを使用するには、配信テンプレートまたはランディングページテンプレートにリンクされている必要があります。これを行うには、テンプレートを作成または編集する必要があります。

>[!NOTE]
>
>For more information about creating a template, refer to the [Creating a template](../../start/using/about-templates.md) section.

テンプレートを作成したら、それをブランドにリンクできます。これを行うには、次の手順に従います。

1. Click the **[!UICONTROL Edit properties]** button to access the template properties.

   ![](assets/branding_04.png)

1. ドロップダウンリストを使用して、テンプレートにリンクするブランドを選択します。

   >[!NOTE]
   >
   >By default, the **[!UICONTROL Default brand (branding)]** is selected.

   ![](assets/branding_05.png)

   To view how the brand selected is configured, click the **[!UICONTROL Navigate to the detail of the element selected]** icon.

   ![](assets/branding_06.png)

1. 選択を確認し、テンプレートを保存します。

テンプレートはブランドにリンクされています。In the email editor, the elements such as the **Email address of default sender**, the **Default sender name**, or the **Logo** will use the configured brand data.

### Branding use case {#branding-use-case}

この例では、新しい旅行関連ブランドを作成して電子メールで使用します。

#### Configure a new brand {#configure-a-new-brand}

>[!CAUTION]
>
>ブランド設定は、特定の権限および技術設定が必要な場合にのみアドビによって管理されます。

1. The Adobe Campaign administrator creates the brand in **[!UICONTROL Administration > Instance settings > Brand configuration]**. He adds the **Vacations in the Tropics** element from the advanced menu and configures the **[!UICONTROL ID]** and the **[!UICONTROL Header parameters of sent emails]** of the brand.

   ![](assets/branding_07.png)

1. The administrator then configures the URL of the **Server(s) exposed on the Internet** so that landing pages can be used, then the tracking URLs.

   In this example, the **Web Analytics** tool used is **Google Analytics**. 管理者は、次のようにトラッキングURLを設定します。

   ![](assets/branding_12.png)

ブランドが正しく作成および設定されている。これで、マーケティングチームが使用できるようになりました。

#### Implement a new brand {#implement-a-new-brand}

配信マネージャーとして、新しいブランドを使用するための配信テンプレートを作成します。これを達成するには、次の手順に従います。

1. In the advanced menu **[!UICONTROL Resources > Templates > Delivery templates]**, duplicate a built-in template to configure a new delivery template.

   ![](assets/branding_08.png)

1. To link this template to the **Vacations in the Tropics** brand, edit the template properties and select the brand from the drop-down list.

   ![](assets/branding_09.png)

1. ブランドIDを反映するようにこの電子メールテンプレートを設定します。
1. テンプレートが完成したら、保存できます。

   ![](assets/branding_10.png)

   配信テンプレートを使用して、オーディエンスに送信される電子メールを作成できるようになりました。

#### Use the new brand in a delivery {#use-the-new-brand-in-a-delivery}

ブランドにリンクされた電子メールを作成するには、次の手順に従います。

1. Click the **[!UICONTROL Create]** button from the **[!UICONTROL Marketing activities]** menu.

   ![](assets/branding_14.png)

1. **[!UICONTROL Email]** アクティビティを選択し、新しいブランドにリンクされているテンプレートを選択します。

   ![](assets/branding_15.png)

1. 電子メールが既に設定されています。テストプロファイルを使用してテストして、オーディエンスに送信する前に、情報を確認できます。

   ![](assets/branding_16.png)

