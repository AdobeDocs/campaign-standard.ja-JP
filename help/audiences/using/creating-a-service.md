---
title: サービスの作成
seo-title: サービスの作成
description: サービスの作成
seo-description: 最初のサービスを作成して、購読者に電子メールの確認を送信する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 0d95d852-0f22-4b7b- b301-8fb4844c3ca2
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: オーディエンス
content-type: 参照
topic-tags: 管理-購読
discoiquuid: 6b7788fe- fa6c-472a-97db-765595ce1589
context-tags: service，ウィザード;サービス、メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Creating a service{#creating-a-service}

購読を管理できるようにするには、まずサービスを作成して設定する必要があります。新しいサービスを設定すると、サービスのサブスクライブまたは登録解除時にプロファイルが受信する電子メールの確認を指定できます。また、サービスにリンクされている購読および購読解除のランディングページも定義します。例えば、電子メールに挿入されるサービス購読リンクは、サービスで指定されている購読のランディングページにプロファイルを自動的に指示します。

サービスを設定するには:

1. From the advanced menu **Profiles &amp; audiences** &gt; **Services** via the Adobe Campaign logo, add a new service or select an existing service. 新しいサービスを作成する場合は、画面に表示される手順に従います。

   デフォルトのサービステンプレートを使用できます。このテンプレートは、デフォルトのランディングページと確認電子メールを使用して事前設定されています。その他のテンプレートを作成して、特定の設定を定義できます。For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. **サービスのプロパティ** セクションで、サービスダッシュボードの ![](assets/edit_darkgrey-24px.png) ボタンを介してアクセスし、購読および購読解除の確認メッセージを設定します。

   ![](assets/lp_service_parameters.png)

1. 購読および購読解除のための確認メッセージテンプレートを選択します。3つのモードを使用できます。

   * **[!UICONTROL No message]**:このモードでは、確認メッセージなしでサービスを作成できます。
   * **[!UICONTROL Default message]**:このモードでは、デフォルトの購読または購読解除の確認トランザクションメッセージが使用されます。デフォルトの確認メッセージは汎用であり、デフォルトモードを使用するすべてのサービスで同じになります。
   * **[!UICONTROL Custom message]**:このモードでは、各サービスに固有のカスタム確認メッセージを処理できます。You then select the **[!UICONTROL Custom subscription event configuration]** which is associated with a specific transactional message template. Refer to [Transactional messages](../../channels/using/about-transactional-messaging.md) for more information on transactional event and message configuration.

1. サービスを保存します。これで、使用できるようになりました。

サービスが作成されたら、のプロモーションを開始できます。

**関連トピック:**

* [サービスと購読](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html) のビデオの管理
* [サービスの推進](../../audiences/using/promoting-a-service.md)
* [サブスクライバーによるオーディエンスの作成](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [ランディングページのサービスへのフォームのリンク](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)

