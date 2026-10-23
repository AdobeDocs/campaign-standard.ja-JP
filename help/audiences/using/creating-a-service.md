---
title: サービスの作成
description: 最初のサービスを作成し、登録者に確認メールを送信するように設定する方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
context-tags: service,wizard;service,main
feature: Audiences
role: User
level: Beginner
exl-id: 6f42251e-75da-4707-a855-6ba9a86256c9
TQID: 'https://experienceleague.adobe.com/uSoAvkY4kGrVnzSmHbgj1gd4YKPFFzSBC-4maW-9VEw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 92%
---
# サービスの作成{#creating-a-service}

サブスクリプションを管理するには、まずサービスを作成し、設定する必要があります。 新しいサービスを設定すると、プロファイルがサービスを登録または登録解除する際に受け取る電子メール確認を指定できます。 また、サービスにリンクされている購読と購読解除のランディングページも定義します。 例えば、電子メールにサービスサブスクリプションリンクを挿入すると、サービスで指定されたサブスクリプションランディングページにプロファイルが自動的に誘導されます。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

サービスを設定するには、次の手順に従います。

1. Adobe Campaign のロゴから、詳細設定メニューの **[!UICONTROL Profiles & audiences]**／**[!UICONTROL Services]** を選択し、新しいサービスを追加するか、既存のサービスを選択します。 新しいサービスを作成する場合は、画面に表示される手順に従います。

   デフォルトのサービステンプレートを使用できます。 このテンプレートには、デフォルトのランディングページと確認電子メールが事前設定されています。 その他のテンプレートを作成して、特定の設定を定義することもできます。 詳しくは、[テンプレートの管理](../../start/using/marketing-activity-templates.md)の節を参照してください。

1. サービスダッシュボードの「**[!UICONTROL Service properties]**」ボタンから「![](assets/edit_darkgrey-24px.png)」セクションにアクセスして、購読および購読解除の確認メッセージを設定します。

   ![](assets/lp_service_parameters.png)

1. サブスクリプションの有効期間を設定するには、この「**[!UICONTROL Subscriptions with an expiration date]**」オプションを選択します。

   ![](assets/lp_service_expiration.png)

   セグメント化アクティビティの有効期限を使用すると、期限切れでないサービスを登録しているプロファイルをターゲットに設定できます。

1. 「**[!UICONTROL Service label]**」フィールドに値を入力します。 カスタムの確認メッセージを使用する場合、サービスラベルは必須です。

1. 購読および購読解除の確認メッセージテンプレートを選択します。 次の 3 つのモードを選択できます。

   * **[!UICONTROL No message]**：このモードを使用すると、確認メッセージを表示せずにサービスを作成できます。
   * **[!UICONTROL Default message]**：このモードでは、デフォルトの購読または購読解除確認トランザクションメッセージが使用されます。 デフォルトの確認メッセージは汎用で、デフォルトのモードを使用するすべてのサービスで同じになります。

     >[!NOTE]
     >
     >デフォルトのメッセージを変更するには、「**[!UICONTROL Service properties]**」セクション内のラベルをクリックするか、「**[!UICONTROL Show internal transactional messages]**」ボックスをオンにした後で Adobe Campaign トランザクションメッセージリストからデフォルトのメッセージを選択します。

   * **[!UICONTROL Custom message]**：このモードでは、各サービス特有のカスタム確認メッセージを処理できます。 次に、特定の[トランザクションメッセージ](../../channels/using/getting-started-with-transactional-msg.md)テンプレートに関連付けられている **[!UICONTROL Custom subscription event configuration]** を選択します。 詳しくは、[サービスのサブスクリプションを確認](../../audiences/using/confirming-subscription-to-a-service.md)を参照してください。

1. サービスを保存します。 これで、使用できる状態になりました。

サービスが作成されたら、そのサービスのプロモーションを開始できます。

**関連トピック：**

* [サービスのプロモーション](../../audiences/using/promoting-a-service.md)
* [購読者で構成されたオーディエンスの作成](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [ランディングページとサービスのリンク](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)

## チュートリアルビデオ {#video}

このビデオでは、サービスの作成方法とサブスクリプションの管理方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/328371?captions=jpn&quality=12)

その他のCampaign Standardのハウツー動画は[こちら](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=ja)でご覧いただけます。
