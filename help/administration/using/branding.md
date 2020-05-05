---
title: ブランディング
description: ブランドIDの管理に使用できるすべてのツールを見つけます。
page-status-flag: never-activated
uuid: d66ac5a2-2ae1-4870-b48e-7f276744ffdd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32bf8
context-tags: branding,overview;branding,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e18407ab4bf70caa417b16bbc645fd2c6ba1818b

---


# ブランディング{#branding}

## ブランドIDについて {#about-brand-identity}

すべての会社には、ブランドの視覚的なガイドラインと技術的なガイドラインがあります。 Adobe Campaignにより、ロゴから電子メール送信者、URL、ドメインなどの技術的側面に至るまで、一貫したブランドを顧客に提供するための仕様を定義できます。

技術管理者は、1つまたは複数のブランドを定義して、ブランドのIDに影響を与えるパラメータを一元的に入力できます。 これには、ブランドのロゴ、ランディングページのアクセスURLのドメイン、メッセージ追跡の設定が含まれます。 Adobe Campaignを使用すると、これらのブランドを作成し、メッセージやランディングページにリンクできます。 この設定は、テンプレートで管理されます。

## ブランドの設定と使用 {#configuring-and-using-brands}

ブランドの設定と使用の主な原則は次のとおりです。

1. ブランドを作成および設定します。この操作には特定の権限が必要で、Adobe Campaignのテクニカル管理者が実行します。
1. このブランド用の1つまたは複数の配信およびランディングページテンプレートを作成します。 「テンプレートの [作成](../../start/using/marketing-activity-templates.md) 」を参照してください。
1. このテンプレートに基づいてメッセージとランディングページを作成します。 「電子メールの [作成](../../channels/using/creating-an-email.md) 」および「ランディングページの [作成](../../channels/using/designing-a-landing-page.md) 」の節を参照してください。

>[!IMPORTANT]
>
>ブランドはエンドユーザーが作成または変更できません。 これらの操作は、Adobe Campaignのテクニカル管理者が実行する必要があります。 ご要望があれば、アドビカスタマーケアにお問い合わせください。
>
>マルチブランディングは、トランザクションメッセージングのコンテキストでは使用できません。 詳しくは、「 [トランザクションメッセージとブランディング](../../channels/using/about-transactional-messaging.md#permissions-and-branding)」を参照してください。

ブランドはメニューに表示され **[!UICONTROL Administration > Instance settings > Brand configuration]** ます。

デフォルトでは、新しく作成されたブランドは、管理者によって対応する権限を持つユーザーにのみ表示されます。

ブ **ランドは** 、次の特性によって定義されます。

* ブランドを定義し、パーソナライズする **ID**。 この節では、次のフィールドについて説明します。

   ![](assets/branding_01.png)

   * **インターフェイスに表示されるラベル**
   * **ブランド名**
   * **WebサイトのURL** と **Webサイトのブランドのラベル** 。
   * **ブランドロゴ**

* **[!UICONTROL Header parameters of sent emails]** これは、キャンペーンの受信者が見るものをパーソナライズします。 この節では、次のフィールドについて説明します。

   ![](assets/branding_04_header.png)

   * **ブランドの電子メールアドレスを含む送信者（電子メールアドレス）** 。
   * **ブランド名を含む送信者（名前）** 。
   * **（電子メールアドレス）** 、お客様が返信できる電子メールアドレスを含む返信を行います。
   * **（名前）** にブランド名で返信します。
   * **エラー（電子メールアドレス）** 。エラーの場合に使用する電子メールアドレスを指定します。
   >[!IMPORTANT]
   >
   >電子メールのヘッダーパラメーターを更新した後、送信者の名前と電子メールアドレスがテンプレートから作成された電子メール内で変更されていない場合は、テンプレートの詳細設定を確認します。

* **インターネット上で公開されているサーバは、追跡に使用するサーバを定義しますが** 、ランディングページアクセスにも使用します。 この節では、次のフィールドについて説明します。

   ![](assets/configure_branding_04.png)

   * **作成した様々なランディングページのホストおよびアクセスに使用するアプリケーションサーバーの外部URL** 。
   * **配信中に追跡URLとして使用されるトラッキングサーバーの外部URL** 。
   * **配信のデフォルトミラーページとして使用されるミラーページサーバーの外部URL** 。
   >[!NOTE]
   >
   >ランディングページプレビューとミラーページレンダリングをキャンペーンユーザーインターフェイスに表示するには、アプリケーションサーバーとミラーページサーバーのURLをセキュリティで保護する必要があります。 この場合、これらのURLを設定する際は、http://ではなくhttps://を使用してください。

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**」に置き換えます。これは、ブランドのURLトラッキングの設定を定義します。

   Adobe AnalyticsやGoogle AnalyticsなどのWeb解析ツールなど、外部システムでリンクを追跡するための追加のパラメーターをここで定義します。

   ![](assets/branding_05.png)

## 電子メールへのブランドの割り当て {#assigning-a-brand-to-an-email}

### ブランドのテンプレートへのリンク {#linking-a-brand-to-a-template}

ブランドに定義されたパラメーターを使用するには、そのブランドが配信テンプレートまたはランディングページテンプレートにリンクされている必要があります。 これを行うには、テンプレートを作成または編集する必要があります。

>[!NOTE]
>
>テンプレートの作成について詳しくは、「テンプレートの [作成](../../start/using/marketing-activity-templates.md) 」を参照してください。

テンプレートを作成したら、そのテンプレートをブランドにリンクできます。 手順は次のとおりです。

1. ボタンをクリックして、テンプレートのプロパティにアクセスします。 **[!UICONTROL Edit properties]**

   ![](assets/branding_04.png)

1. ドロップダウンリストを使用して、テンプレートにリンクするブランドを選択します。

   >[!NOTE]
   >
   >デフォルトでは、が選択 **[!UICONTROL Default brand (branding)]** されています。

   ![](assets/branding_05.png)

   選択したブランドの構成を表示するには、 **[!UICONTROL Navigate to the detail of the element selected]** アイコンをクリックします。

   ![](assets/branding_06.png)

1. 選択内容を確認し、テンプレートを保存します。

テンプレートがブランドにリンクされています。 電子メールエディターでは、デフォルトの送信者の **電子メールアドレス**、 **デフォルトの送信者名**、 **** ロゴなどの要素は、設定済みのブランドデータを使用します。

### ブランディングの使用例 {#branding-use-case}

この例では、新しい旅行関連ブランドを作成し、電子メールで使用します。

#### 新しいブランドの設定 {#configure-a-new-brand}

>[!IMPORTANT]
>
>ブランド設定は、特定の権限と技術的な設定が必要な場合にのみ、アドビによって管理されます。

1. ブランドは、Adobe Campaign管理者がで作成し **[!UICONTROL Administration > Instance settings > Brand configuration]**&#x200B;ます。 彼がアドバンスメニューから **「熱帯性** 」要素に「休暇」を追加し、ブランド **[!UICONTROL ID]** の名前と名前 **[!UICONTROL Header parameters of sent emails]** を設定します。

   ![](assets/branding_07.png)

1. 次に、ランディングページを使用できるように、管理者がインターネット上で公開される **サーバのURLを設定し** 、その後追跡URLを設定します。

   この例では、 **Web Analytics** ツールとして **Google Analyticsが使用されています**。 管理者は、次のようにトラッキングURLを設定します。

   ![](assets/branding_12.png)

ブランドは正しく作成および設定されています。 これで、マーケティングチームが使用できるようになります。

#### 新しいブランドの実装 {#implement-a-new-brand}

配信マネージャーは、新しいブランドを使用する配信テンプレートの作成を担当します。 これを行うには、次の手順に従います。

1. 詳細メニューで **[!UICONTROL Resources > Templates > Delivery templates]**、組み込みのテンプレートを重複して新しい配信テンプレートを設定します。

   ![](assets/branding_08.png)

1. このテンプレートをTropics **ブランドの** 休暇にリンクするには、テンプレートのプロパティを編集し、ドロップダウンリストからブランドを選択します。

   ![](assets/branding_09.png)

1. ブランドIDを反映するように、この電子メールテンプレートを設定します。
1. テンプレートが完成したら、保存できます。

   ![](assets/branding_10.png)

   これで、配信テンプレートを使用して、オーディエンスに送信する電子メールを作成できます。

#### 配信で新しいブランドを使用する {#use-the-new-brand-in-a-delivery}

ブランドにリンクされた電子メールを作成するには、次の手順に従います。

1. メニューから **[!UICONTROL Create]** ボタンをクリックし **[!UICONTROL Marketing activities]** ます。

   ![](assets/branding_14.png)

1. アクティビティを選択し、新しいブランドにリンクされているテンプレートを選択します。 **[!UICONTROL Email]**

   ![](assets/branding_15.png)

1. 電子メールは既に設定されています。 テストプロファイルを使用してテストを実行する前に情報を確認し、オーディエンスに送信することができます。

   ![](assets/branding_16.png)

