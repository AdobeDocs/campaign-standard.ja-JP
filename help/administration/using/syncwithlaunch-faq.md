---
title: Launch と同期テクニカルワークフローの FAQ
description: Launch テクニカルワークフローに関するよくある質問Adobe
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Adobe Launch 同期に関する FAQ {#syncwithlaunch-faq}

AdobeLaunch モバイルプロパティは、 **[!UICONTROL Sync with Launch]** 専用のテクニカルワークフロー。 詳しくは、 [ページ](../../administration/using/technical-workflows.md)

以下の節では、この同期に関するよくある質問を示します。

## でプロパティを作成しました。 [!DNL Launch] （組織単位 ALL の非管理者）。 アプリケーションはAdobe Campaignで設定の準備ができましたが、開いたり設定したりできません。 {#configuring-property}

組織単位の管理者のみ ALL がAdobe Campaign Standardでモバイルアプリケーションを設定できます。 設定が完了すると、割り当てられた組織単位のユーザーのみがアプリケーションを編集できます。 組織単位の詳細については、 [ページ](../../administration/using/organizational-units.md).

## 設定済みのモバイルアプリをAdobe Campaign Standardで編集できず、モバイルアプリが読み取りモードのみの場合。 {#read-mode-mobile-app}

でモバイルアプリケーションの組織単位を確認する **[!UICONTROL Access Authorization]** 」セクションに入力します。 割り当てられた組織単位のユーザーのみがモバイルアプリケーションを編集できます。

組織単位の詳細については、 [ページ](../../administration/using/organizational-units.md).

## Adobe Campaign Standardで組織単位 ALL を持つ管理者ですが、モバイルアプリケーションを設定できません。 {#org-unit-mobile}

組織単位が ALL に設定された管理者は、のすべてのモバイルプロパティに対する権限を持つ必要があります。 [!DNL Launch] モバイルアプリケーションを設定する場合。

組織単位の詳細については、 [ページ](../../administration/using/organizational-units.md).

## モバイルプロパティを [!DNL Launch] ただし、私のプロパティはAdobe Campaign Standardには表示されません。 {#visibility-mobile-property}

1. Adobe Campaign Standard拡張機能がのモバイルプロパティにインストールされていることを確認します。 [!DNL Launch].

1. 拡張機能でインスタンスのエンドポイントが正しく設定されていることを確認します。

1. 「Launch_URL_Campaign」または「NmsServer_URL」が正しいことを確認します。

1. 次に、 [!DNL Launch] Adobe Campaignは **[!UICONTROL syncWithLaunch]** テクニカルワークフロー。

## Adobe Campaignと Launch の間の同期が完了したかどうかを確認する方法を教えてください。 {#sync-campaign-launch}

1. Adobe Campaign Standardの詳細設定メニューで、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. を開きます。 **[!UICONTROL syncWithLaunch]** ワークフロー。

1. ワークフローがエラーなく終了したかどうかを確認します。

1. ログで、ワークフローの同期が有効になり、正常に完了したことを確認します。

## Launch で設定済みのモバイルアプリケーションのキーをリセットしました。 Launch でキーを再設定する方法は？ {#configuring-pkey}

1. Launch でモバイルプロパティを開きます。Adobe:

1. PKey がリセットされたAdobe Campaign Standard拡張機能に新しい URL を設定します。

1. 保存し、Adobe Campaignと [!DNL Launch].

1. 同期が完了したら、 [!DNL Launch].

1. PKey がリセットされたAdobe Campaign Standard拡張機能に正しい URL を設定します。

1. 保存し、ワークフローの同期を再度実行します。

1. その場合にのみ、プロパティが **[!UICONTROL Ready to Configure]** Adobe Campaignの状態を表示し、設定できるようになりました。

## Adobe Campaignでモバイルプロパティを設定します。 テクニカルワークフローがAdobeLaunch とAdobe Campaignの間で同期されるのを待つ必要がありますか？

ワークフローは、すぐに実行できます。

1. Adobe Campaign Standardの詳細設定メニューで、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. を開きます。 **[!UICONTROL syncWithLaunch]** ワークフロー。

1. をクリックします。 **[!UICONTROL Scheduler]** アクティビティと選択 **[!UICONTROL Immediate execution]**.
