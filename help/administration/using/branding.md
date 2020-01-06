---
title: ブランディング
description: ブランドIDを管理するために使用できるすべてのツールを見つけます。
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
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# ブランディング{#branding}

## ブランドアイデンティティについて {#about-brand-identity}

すべての企業には、ブランドの視覚的・技術的なガイドラインがあります。 Adobe Campaignを使用すると、ロゴから電子メールの送信者、URL、ドメインなどの技術的側面に至るまで、一貫したブランドを顧客に提供する仕様を定義できます。

技術管理者は、1つまたは複数のブランドを定義して、ブランドのIDに影響を与えるパラメータを一元的に入力できます。 これには、ブランドロゴ、ランディングページのアクセスURLのドメイン、メッセージ追跡設定が含まれます。 Adobe Campaignを使用すると、これらのブランドを作成し、メッセージやランディングページにリンクできます。 この設定はテンプレートで管理されます。

## ブランドの設定と使用 {#configuring-and-using-brands}

ブランドの設定と使用の主な原則は、次のとおりです。

1. ブランドの作成と設定 — この操作には特定の権限が必要で、Adobe Campaignテクニカル管理者が実行します。
1. このブランド用に1つまたは複数の配信およびランディングページテンプレートを作成します。 詳しくは、「テンプレ [ートの作成](../../start/using/marketing-activity-templates.md) 」を参照してください。
1. このテンプレートに基づいてメッセージおよびランディングページを作成します。 「電子メールの作 [成」および「ランディン](../../channels/using/creating-an-email.md) グページの作成 [」の節を参照してください](../../channels/using/designing-a-landing-page.md) 。

>[!CAUTION]
>
>ブランドはエンドユーザーが作成または変更できません。これらの操作は、Adobe Campaignテクニカル管理者が実行する必要があります。 ご要望はアドビカスタマーケアにお問い合わせください。 マルチブランドは、トランザクションメッセージングのコンテキストでは使用できません。 詳しくは、トランザクションメッセージとブラ [ンディングを参照してくださ](../../channels/using/about-transactional-messaging.md#permissions-and-branding)い。

ブランドはメニューに表示され **[!UICONTROL Administration > Instance settings > Brand configuration]**ます。

デフォルトでは、新しく作成されたブランドは、管理者によって対応する権限を持つユーザーにのみ表示されます。

ブラ **ンドは** 、次の特徴によって定義されます。

* ブランド **を定義**、パーソナライズする「ID」。 この節では、以下のフィールドについて説明します。

   ![](assets/branding_01.png)

   * **インターフェイス** に表示されるラベル
   * **ブランド名**
   * **ブランドのWebサ** イトURL **** 、Webサイトラベル
   * **ブランドロゴ**

* **[!UICONTROL Header parameters of sent emails]**キャンペーンの受信者に表示される情報をパーソナライズします。 この節では、以下のフィールドについて説明します。

   ![](assets/branding_04_header.png)

   * **ブランドの電子メールアドレスを含む** 、送信者（電子メールアドレス）。
   * **ブランド名を含む** 、送信者（名前）。
   * **（電子メールアドレス）に** 、顧客が返信できる電子メールアドレスで返信します。
   * **（名前）にブランド名** で返信します。
   * **エラー（電子メールアドレス）** 。エラーが発生した場合に使用する電子メールアドレスを指定します。
   >[!CAUTION]
   >
   >電子メールのヘッダーパラメーターを更新した後、送信者の名前と電子メールアドレスがテンプレートから作成された電子メール内で変更されていない場合は、テンプレートの詳細設定を確認します。

* **インターネット上で公開されているサーバは** 、トラッキングに使用するサーバとランディングページアクセスに使用するサーバを定義します。 この節では、以下のフィールドについて説明します。

   ![](assets/configure_branding_04.png)

   * **作成した様々なランディングページのホスト** /アクセスに使用するアプリケーションサーバーの外部URL。
   * **配信中に追跡URLとして使用される** 、トラッキングサーバーの外部URL。
   * **配信でデフォルトのミラーページとして使用される** 、ミラーページサーバの外部URL。

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**」をクリックします。

   Adobe AnalyticsやGoogle AnalyticsなどのWeb解析ツールなど、外部システム上でリンクを追跡するための追加のパラメーターをここで定義します。

   ![](assets/branding_05.png)

## 電子メールへのブランドの割り当て {#assigning-a-brand-to-an-email}

### ブランドのテンプレートへのリンク {#linking-a-brand-to-a-template}

ブランド用に定義されたパラメーターを使用するには、そのパラメーターを配信テンプレートまたはランディングページテンプレートにリンクする必要があります。 これを行うには、テンプレートを作成または編集する必要があります。

>[!NOTE]
>
>テンプレートの作成の詳細については、「テンプレートの作成」の節 [を参照してください](../../start/using/marketing-activity-templates.md) 。

テンプレートを作成したら、ブランドにリンクできます。 手順は次のとおりです。

1. ボタンをクリックし **[!UICONTROL Edit properties]**て、テンプレートのプロパティにアクセスします。

   ![](assets/branding_04.png)

1. ドロップダウンリストを使用して、テンプレートにリンクするブランドを選択します。

   >[!NOTE]
   >
   >デフォルトでは、が選 **[!UICONTROL Default brand (branding)]**択されます。

   ![](assets/branding_05.png)

   選択したブランドの構成を表示するには、アイコンをクリック **[!UICONTROL Navigate to the detail of the element selected]**します。

   ![](assets/branding_06.png)

1. 選択を確定し、テンプレートを保存します。

テンプレートがブランドにリンクされています。 電子メールエディターでは、デフォルトの送信者の **Eメールアドレス**、 **Default sender name**、 **** Logoなどの要素が、設定済みのブランドデータを使用します。

### ブランドの使用例 {#branding-use-case}

この例では、新しい旅行関連ブランドを作成し、電子メールで使用します。

#### 新しいブランドの設定 {#configure-a-new-brand}

>[!CAUTION]
>
>ブランド設定は、特定の権限と技術的な設定が必要なので、アドビによってのみ管理されます。

1. Adobe Campaign管理者がでブランドを作成します **[!UICONTROL Administration > Instance settings > Brand configuration]**。 彼はアドバンスメ**&#x200B;ニューからトロピクス要素にバカンスを加え&#x200B;**、ブランドの**[!UICONTROL ID]** 状況と **[!UICONTROL Header parameters of sent emails]**状況を設定します。

   ![](assets/branding_07.png)

1. 次に、ランディングページを使用し **て、トラッキングURLを使用できるように、管理者がインターネットに公開されるサーバのURL** を設定します。

   この例で使用される **Web Analytics** ツールは **Google Analyticsです**。 管理者は、次のように追跡URLを設定します。

   ![](assets/branding_12.png)

ブランドが正しく作成され、設定されている。 これで、マーケティングチームが使用できるようになりました。

#### 新しいブランドの実装 {#implement-a-new-brand}

配信マネージャーは、新しいブランドを使用する配信テンプレートの作成を担当します。 これを行うには、次の手順に従います。

1. アドバンスメニューで、組 **[!UICONTROL Resources > Templates > Delivery templates]**み込みのテンプレートを複製して、新しい配信テンプレートを設定します。

   ![](assets/branding_08.png)

1. このテンプレートをトロピックスブ **ランドの休暇にリンクするには** 、テンプレートのプロパティを編集し、ドロップダウンリストからブランドを選択します。

   ![](assets/branding_09.png)

1. ブランドIDを反映するようにこの電子メールテンプレートを設定します。
1. テンプレートが完成したら、保存できます。

   ![](assets/branding_10.png)

   配信テンプレートを使用して、オーディエンスに送信する電子メールを作成できるようになりました。

#### 新しいブランドの提供 {#use-the-new-brand-in-a-delivery}

ブランドにリンクした電子メールを作成するには、次の手順に従います。

1. メニューから **[!UICONTROL Create]**ボタンをクリック**[!UICONTROL Marketing activities]** します。

   ![](assets/branding_14.png)

1. アクティビティ **[!UICONTROL Email]**を選択し、新しいブランドにリンクされたテンプレートを選択します。

   ![](assets/branding_15.png)

1. 電子メールは既に設定されています。 テストプロファイルを使用して情報をテストする前に情報を確認し、オーディエンスに送信することができます。

   ![](assets/branding_16.png)

