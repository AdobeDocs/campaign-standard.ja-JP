---
solution: Campaign Standard
product: campaign
title: サービスの作成
description: 最初のサービスを作成し、登録者に確認メールを送信するように設定する方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
context-tags: service,wizard;service,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

---


# サービスの作成{#creating-a-service}

サブスクリプションを管理するには、まずサービスを作成し、設定する必要があります。新しいサービスを設定すると、プロファイルがサービスを登録または登録解除する際に受け取る電子メール確認を指定できます。また、サービスにリンクされている購読と購読解除のランディングページも定義します。例えば、電子メールにサービスサブスクリプションリンクを挿入すると、サービスで指定されたサブスクリプションランディングページにプロファイルが自動的に誘導されます。

サービスを設定するには、次の手順に従います。

1. Adobe Campaign のロゴから、詳細設定メニューの **[!UICONTROL Profiles & audiences]**／**[!UICONTROL Services]** を選択し、新しいサービスを追加するか、既存のサービスを選択します。新しいサービスを作成する場合は、画面に表示される手順に従います。

   デフォルトのサービステンプレートを使用できます。このテンプレートには、デフォルトのランディングページと確認電子メールが事前設定されています。その他のテンプレートを作成して、特定の設定を定義することもできます。詳しくは、[テンプレートの管理](../../start/using/marketing-activity-templates.md)の節を参照してください。

1. サービスダッシュボードの「**[!UICONTROL Service properties]**」ボタンから「![](assets/edit_darkgrey-24px.png)」セクションにアクセスして、購読および購読解除の確認メッセージを設定します。

   ![](assets/lp_service_parameters.png)

1. サブスクリプションの有効期間を設定するには、この「**[!UICONTROL Subscriptions with an expiration date]**」オプションを選択します。

   ![](assets/lp_service_expiration.png)

   セグメント化アクティビティの有効期限を使用すると、期限切れでないサービスを登録しているプロファイルをターゲットに設定できます。

1. 「**[!UICONTROL Service label]**」フィールドに値を入力します。カスタムの確認メッセージを使用する場合、サービスラベルは必須です。

1. 購読および購読解除の確認メッセージテンプレートを選択します。次の 3 つのモードを選択できます。

   * **[!UICONTROL No message]**：このモードを使用すると、確認メッセージを表示せずにサービスを作成できます。
   * **[!UICONTROL Default message]**：このモードでは、デフォルトの購読または購読解除確認トランザクションメッセージが使用されます。デフォルトの確認メッセージは汎用で、デフォルトのモードを使用するすべてのサービスで同じになります。

      >[!NOTE]
      >
      >デフォルトのメッセージを変更するには、「**[!UICONTROL Service properties]**」セクション内のラベルをクリックするか、「**[!UICONTROL Show internal transactional messages]**」ボックスをオンにした後で Adobe Campaign トランザクションメッセージリストからデフォルトのメッセージを選択します。

   * **[!UICONTROL Custom message]**：このモードでは、各サービス特有のカスタム確認メッセージを処理できます。次に、特定の[トランザクションメッセージ](../../channels/using/getting-started-with-transactional-msg.md)テンプレートに関連付けられている **[!UICONTROL Custom subscription event configuration]** を選択します。詳しくは、[サービスのサブスクリプションを確認](../../audiences/using/confirming-subscription-to-a-service.md)を参照してください。

1. サービスを保存します。これで、使用できる状態になりました。

サービスが作成されたら、そのサービスのプロモーションを開始できます。

**関連トピック：**

* [サービスとサブスクリプションの管理](https://docs.adobe.com/content/help/ja-JP/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/services-and-subscriptions.html)（ビデオ）
* [サービスのプロモーション](../../audiences/using/promoting-a-service.md)
* [購読者で構成されたオーディエンスの作成](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [ランディングページのサービスへのリンク](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
