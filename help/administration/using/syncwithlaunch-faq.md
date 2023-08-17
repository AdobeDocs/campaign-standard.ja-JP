---
title: Launch と同期テクニカルワークフローの FAQ
description: Launch テクニカルワークフローに関するよくある質問Adobe
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Adobe Experience Platform 同期のタグに関する FAQ {#syncwithlaunch-faq}

タグモバイルプロパティは、 **[!UICONTROL Sync with Launch]** 専用のテクニカルワークフロー。 詳しくは、 [ページ](../../administration/using/technical-workflows.md)

以下の節では、この同期に関するよくある質問を示します。

## タグプロパティを作成しました（組織単位 ALL の非管理者）。 アプリケーションはAdobe Campaignで設定の準備ができましたが、開いたり設定したりできません。 {#configuring-property}

組織単位の管理者のみ ALL がAdobe Campaign Standardでモバイルアプリケーションを設定できます。 設定が完了すると、割り当てられた組織単位のユーザーのみがアプリケーションを編集できます。 組織単位の詳細については、次を参照してください。 [ページ](../../administration/using/organizational-units.md).

## 設定済みのモバイルアプリをAdobe Campaign Standardで編集できず、モバイルアプリが読み取りモードのみの場合。 {#read-mode-mobile-app}

でモバイルアプリケーションの組織単位を確認する **[!UICONTROL Access Authorization]** 」セクションに入力します。 割り当てられた組織単位のユーザーのみがモバイルアプリケーションを編集できます。

組織単位の詳細については、次を参照してください。 [ページ](../../administration/using/organizational-units.md).

## Adobe Campaign Standardで組織単位 ALL を持つ管理者ですが、モバイルアプリケーションを設定できません。 {#org-unit-mobile}

組織単位を「すべて」に設定した管理者は、すべてのタグモバイルプロパティに対して、モバイルアプリケーションを設定する権限を持っている必要があります。

組織単位の詳細については、次を参照してください。 [ページ](../../administration/using/organizational-units.md).

## タグモバイルプロパティを作成しましたが、プロパティがAdobe Campaign Standardに表示されません。 {#visibility-mobile-property}

1. データ収集 UI のモバイルプロパティにAdobe Campaign Standard拡張機能がインストールされていることを確認します。

1. 拡張機能でインスタンスのエンドポイントが正しく設定されていることを確認します。

1. 「Launch_URL_Campaign」または「NmsServer_URL」が正しいことを確認します。

1. 次に、同期が **[!UICONTROL syncWithLaunch]** テクニカルワークフロー。

## Adobe Experience PlatformのAdobe Campaignとタグの間の同期が完了したかどうかを確認する方法 {#sync-campaign-launch}

1. Adobe Campaign Standardの詳細設定メニューで、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. を開きます。 **[!UICONTROL syncWithLaunch]** ワークフロー。

1. ワークフローがエラーなく終了したかどうかを確認します。

1. ログで、ワークフローの同期が有効になり、正常に完了したことを確認します。

## 設定済みのタグモバイルアプリのキーをリセットします。 データ収集 UI でキーを再設定する方法を教えてください。 {#configuring-pkey}

1. データ収集 UI でモバイルプロパティを開きます。

1. PKey がリセットされたAdobe Campaign Standard拡張機能に新しい URL を設定します。

1. 保存し、ワークフローを同期させます。

1. 同期が完了したら、データ収集 UI でモバイルプロパティを開きます。

1. PKey がリセットされたAdobe Campaign Standard拡張機能に正しい URL を設定します。

1. 保存し、ワークフローの同期を再度実行します。

1. その場合にのみ、プロパティが **[!UICONTROL Ready to Configure]** Adobe Campaignの状態を表示し、設定できるようになりました。

## Adobe Campaignでモバイルプロパティを設定します。 テクニカルワークフローがAdobe Experience PlatformとAdobe Campaignのタグ間で同期されるのを待つ必要がありますか？

ワークフローは、すぐに実行できます。

1. Adobe Campaign Standardの詳細設定メニューで、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. を開きます。 **[!UICONTROL syncWithLaunch]** ワークフロー。

1. をクリックします。 **[!UICONTROL Scheduler]** アクティビティと選択 **[!UICONTROL Immediate execution]**.
