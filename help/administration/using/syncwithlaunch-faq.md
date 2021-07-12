---
solution: Campaign Standard
product: campaign
title: Launchテクニカルワークフローと同期のFAQ
description: Launchテクニカルワークフローに関するよくある質問です。
audience: administration
content-type: reference
topic-tags: users-and-security
feature: インスタンス設定
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Adobe Launch 同期に関する FAQ {#syncwithlaunch-faq}

**[!UICONTROL Sync with Launch]**&#x200B;専用のテクニカルワークフローを使用して、AdobeLaunchモバイルプロパティをAdobe Campaign Standardに読み込むことができます。 詳しくは、この[ページ](../../administration/using/technical-workflows.md)を参照してください。

以下の節では、この同期に関するよくある質問を示します。

## [!DNL Launch]にプロパティを作成しました（組織単位ALLの管理者以外）。 アプリケーションはAdobe Campaignで設定の準備ができましたが、開く/設定できません。 {#configuring-property}

組織単位の管理者のみALLがAdobe Campaign Standardでモバイルアプリケーションを設定できます。 設定が完了すると、割り当てられた組織単位のユーザーのみが
アプリケーション。 組織単位の詳細については、[ページ](../../administration/using/organizational-units.md)を参照してください。

## Adobe Campaign Standardで設定済みのモバイルアプリケーションを編集できず、モバイルアプリケーションは読み取りモードのみです。 {#read-mode-mobile-app}

**[!UICONTROL Access Authorization]**&#x200B;セクションでモバイルアプリケーションの組織単位を確認します。 割り当てられた組織単位のユーザーのみがモバイルアプリケーションを編集できます。

組織単位の詳細については、[ページ](../../administration/using/organizational-units.md)を参照してください。

## Adobe Campaign Standardの組織単位ALLを持つ管理者ですが、モバイルアプリケーションを設定できません。 {#org-unit-mobile}

組織単位が「すべて」に設定されている管理者は、[!DNL Launch]内のすべてのモバイルプロパティに対して、モバイルアプリケーションを設定する権限を持つ必要があります。

組織単位の詳細については、[ページ](../../administration/using/organizational-units.md)を参照してください。

## [!DNL Launch]でモバイルプロパティを作成しましたが、Adobe Campaign Standardでプロパティが表示されません。 {#visibility-mobile-property}

1. Adobe Campaign Standard拡張機能が[!DNL Launch]のモバイルプロパティにインストールされていることを確認します。

1. 拡張機能でインスタンスのエンドポイントが正しく設定されていることを確認します。

1. 「Launch_URL_Campaign」または「NmsServer_URL」が正しいことを確認します。

1. 次に、[!DNL Launch]とAdobe Campaignの同期が&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;テクニカルワークフローで完了していることを確認します。

## Adobe CampaignとLaunchの間の同期が完了したかどうかを確認する方法を教えてください。 {#sync-campaign-launch}

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** / **[!UICONTROL Application Settings]** / **[!UICONTROL Workflows]**&#x200B;を選択します。

1. **[!UICONTROL syncWithLaunch]**&#x200B;ワークフローを開きます。

1. ワークフローがエラーなく終了したかどうかを確認します。

1. ワークフローの同期が有効になり、正常に完了したことをログに確認します。

## 設定済みのモバイルアプリケーションのキーをLaunchでリセットします。 Launchで再度キーを再設定する方法は？ {#configuring-pkey}

1. LaunchでモバイルプロパティをAdobeします。

1. PKeyがリセットされたAdobe Campaign Standard拡張機能に新しいURLを設定します。

1. 保存し、Adobe Campaignと[!DNL Launch]の間でワークフローを同期させます。

1. 同期が完了したら、[!DNL Launch]のモバイルプロパティを開きます。

1. PKeyがリセットされたAdobe Campaign Standard拡張機能に正しいURLを設定します。

1. 保存して、ワークフローの同期を再実行します。

1. その場合にのみ、プロパティはAdobe Campaignの&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;状態で表示され、設定できるようになります。

## Adobe Campaignでモバイルプロパティを設定したいと思います。 テクニカルワークフローがAdobeLaunchとAdobe Campaignの間で同期するのを待つ必要がありますか？

ワークフローは、すぐに実行できます。

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** / **[!UICONTROL Application Settings]** / **[!UICONTROL Workflows]**&#x200B;を選択します。

1. **[!UICONTROL syncWithLaunch]**&#x200B;ワークフローを開きます。

1. **[!UICONTROL Scheduler]**&#x200B;アクティビティをクリックし、「**[!UICONTROL Immediate execution]**」を選択します。
