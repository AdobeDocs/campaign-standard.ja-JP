---
title: Launch テクニカルワークフロー FAQ との同期
description: Adobe Launch テクニカルワークフローに関するよくある質問
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 1%

---

# Adobe Experience Platform 同期のタグに関する FAQ {#syncwithlaunch-faq}

**[!UICONTROL Sync with Launch]** の専用テクニカルワークフローを通じて、タグモバイルプロパティをAdobe Campaign Standardに読み込むことができます。 詳しくは、この [&#x200B; ページ &#x200B;](../../administration/using/technical-workflows.md) を参照してください。

以下のセクションでは、この同期に関するよくある質問を示しています。

## タグプロパティ（組織単位 ALL の管理者以外）を作成しました。 Adobe Campaignでアプリケーションの設定の準備完了の状態が表示されますが、アプリケーションを開いたり設定したりできません。 {#configuring-property}

Adobe Campaign Standardでモバイルアプリケーションを設定できるのは、組織単位 ALL の管理者のみです。 設定が完了すると、割り当てられた組織単位（OU）のユーザーのみが、
アプリケーション。 組織単位について詳しくは、この [&#x200B; ページ &#x200B;](../../administration/using/organizational-units.md) を参照してください。

## Adobe Campaign Standardで設定済みのモバイルアプリケーションを編集できません。モバイルアプリケーションは読み取りモードのみです。 {#read-mode-mobile-app}

**[!UICONTROL Access Authorization]** のセクションで、モバイルアプリケーションの組織単位を確認します。 割り当てられた組織単位のユーザーのみがモバイルアプリケーションを編集できます。

組織単位について詳しくは、この [&#x200B; ページ &#x200B;](../../administration/using/organizational-units.md) を参照してください。

## Adobe Campaign Standardの組織単位 ALL の管理者ですが、モバイルアプリケーションを設定できません。 {#org-unit-mobile}

組織単位を「すべて」に設定した管理者は、モバイルアプリケーションを設定するために、すべてのタグモバイルプロパティに対する権限が必要です。

組織単位について詳しくは、この [&#x200B; ページ &#x200B;](../../administration/using/organizational-units.md) を参照してください。

## タグモバイルプロパティを作成しましたが、Adobe Campaign Standardにプロパティが表示されません。 {#visibility-mobile-property}

1. Adobe Campaign Standard拡張機能がデータ収集 UI のモバイルプロパティにインストールされていることを確認します。

1. インスタンスのエンドポイントが拡張機能で正しく設定されていることを確認します。

1. 「Launch_URL_Campaign」または「NmsServer_URL」が正しいことを確認します。

1. 次に、**[!UICONTROL syncWithLaunch]** のテクニカルワークフローで同期が完了していることを確認します。

## Adobe Experience PlatformのAdobe Campaignとタグの同期が完了したかどうかを確認する方法 {#sync-campaign-launch}

1. Adobe Campaign Standardの詳細メニューで、**[!UICONTROL Administration]**/**[!UICONTROL Application Settings]**/**[!UICONTROL Workflows]** を選択します。

1. **[!UICONTROL syncWithLaunch]** ワークフローを開きます。

1. ワークフローがエラーなく終了したかどうかを確認します。

1. ログで、ワークフロー同期が有効になっており、正常に完了していることを確認します。

## 設定済みのタグモバイルアプリケーションのキーをリセットしました。 データ収集 UI でキーを再度再設定する方法を教えてください。 {#configuring-pkey}

1. データ収集 UI でモバイルプロパティを開きます。

1. PKey がリセットされたAdobe Campaign Standard拡張機能に、新しい URL を設定します。

1. 保存して、ワークフローを同期させます。

1. 同期が完了したら、データ収集 UI のでモバイルプロパティを開きます。

1. PKey がリセットされたAdobe Campaign Standard拡張機能に、正しい URL を設定します。

1. 保存して、ワークフロー同期を再度実行します。

1. その場合にのみ、プロパティはAdobe Campaignに **[!UICONTROL Ready to Configure]** のように表示され、設定できるようになります。

## Adobe Campaignでモバイルプロパティを設定したいのですが、 Adobe Experience PlatformとAdobe Campaignのタグがテクニカルワークフローで同期されるまで待つ必要がありますか？

ワークフローの次の操作をすぐに実行できます。

1. Adobe Campaign Standardの詳細メニューで、**[!UICONTROL Administration]**/**[!UICONTROL Application Settings]**/**[!UICONTROL Workflows]** を選択します。

1. **[!UICONTROL syncWithLaunch]** ワークフローを開きます。

1. **[!UICONTROL Scheduler]** アクティビティをクリックし、「**[!UICONTROL Immediate execution]**」を選択します。
