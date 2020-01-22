---
title: サービスの作成
description: 初めてのサービスを作成し、購読者に電子メールで確認を送信するように設定する方法について説明します。
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# サービスの作成{#creating-a-service}

購読を管理するには、まずサービスを作成して設定する必要があります。 新しいサービスを設定すると、プロファイルがサービスを購読または購読解除したときに受け取る電子メールの確認を指定できます。 また、サービスにリンクされた購読および購読解除のランディングページも定義します。 例えば、電子メールに挿入されたサービス購読リンクは、サービスで指定された購読ランディングページにプロファイルを自動的に誘導します。

サービスを設定するには：

1. アドバンスメニュー/ **[!UICONTROL Profiles & audiences]**Adobe Campaign**[!UICONTROL Services]** ロゴを使用して、新しいサービスを追加するか、既存のサービスを選択します。 新しいサービスを作成する場合は、画面に表示される手順に従ってください。

   デフォルトのサービステンプレートが使用可能です。 このテンプレートは、デフォルトのランディングページと確認電子メールで事前設定されています。 特定の設定を定義するための他のテンプレートを作成できます。 For more on this, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. サービスダッ **[!UICONTROL Service properties]**シュボードのボタンからア![](assets/edit_darkgrey-24px.png)クセスできるセクションで、購読と購読解除の確認メッセージを設定します。

   ![](assets/lp_service_parameters.png)

1. Fill in the **[!UICONTROL Service label]**field. カスタム確認メッセージを使用する場合、サービスラベルは必須です。

1. 購読と購読解除の確認メッセージテンプレートを選択します。 次の3つのモードを使用できます。

   * **[!UICONTROL No message]**:このモードを使用すると、確認メッセージを表示せずにサービスを作成できます。
   * **[!UICONTROL Default message]**:このモードでは、デフォルトの購読または購読解除の確認トランザクションメッセージが使用されます。 デフォルトの確認メッセージは汎用で、デフォルトモードを使用するすべてのサービスで同じになります。

      >[!NOTE]
      >
      >デフォルトのメッセージを変更するには、セクション内のラベルをクリックす **[!UICONTROL Service properties]**るか、ボックスをオンにした後でAdobe Campaignトランザクションメッセージリストからメッセージを選択**[!UICONTROL Show internal transactional messages]** します。

   * **[!UICONTROL Custom message]**:このモードでは、各サービスに固有のカスタム確認メッセージを処理できます。 次に、特定のトランザクシ**[!UICONTROL Custom subscription event configuration]** ョンメッセージテンプレートに関連付け [られる](../../channels/using/about-transactional-messaging.md) 。 詳しくは、「サービスの購読の確 [認」を参照してください](../../audiences/using/confirming-subscription-to-a-service.md)。

1. サービスを保存します。 これで、使用する準備が整いました。

サービスが作成されたら、そのサービスのプロモーションを開始できます。

**関連トピック：**

* [サービスと購読のビデオの管理](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/services-and-subscriptions.html) （英語のみ）
* [サービスのプロモーション](../../audiences/using/promoting-a-service.md)
* [購読者で構成されるオーディエンスの作成](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [ランディングページのサービスへのリンク](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
