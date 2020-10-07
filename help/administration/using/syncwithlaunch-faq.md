---
title: 起動の技術的なワークフローと同期FAQ
description: 技術ワークフローの開始に関するよくある質問です。
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---


# Adobe Launch 同期 FAQ {#syncwithlaunch-faq}

専用の技術的なワークフローを使用して、Adobeの起動モバイルのプロパティをAdobe Campaign Standardにインポートでき **[!UICONTROL Sync with Launch]** ます。 For more information, refer to this [page](../../administration/using/technical-workflows.md)

以下の節では、この同期に関してよくある質問をリストします。

## I created a property in [!DNL Launch] （組織単位ALLの非管理者） アプリケーションがAdobe Campaign中に「設定準備完了」状態になっていますが、開く/設定できません。 {#configuring-property}

Adobe Campaign Standardでモバイルアプリケーションを設定できるのは、組織単位ALLの管理者だけです。 設定後は、割り当てられた組織単位(OU)のユーザーのみがアプリケーションを編集できます。 For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## 設定済みのモバイルアプリケーションをAdobe Campaign Standardで編集できません。モバイルアプリケーションは読み取りモードのみです。 {#read-mode-mobile-app}

セクションのモバイルアプリケーションの組織単位を確認し **[!UICONTROL Access Authorization ]** ます。 割り当てられた組織単位のユーザーのみがモバイルアプリケーションを編集できます。

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Adobe Campaign Standardの組織単位ALLの管理者ですが、モバイルアプリケーションを設定できません。 {#org-unit-mobile}

組織単位が「すべて」に設定されている管理者は、モバイルアプリケーションを設定する際に、すべてのモバイルプロパティに対する権限 [!DNL Launch] を持つ必要があります。

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## でモバイルプロパティを作成しましたが、 [!DNL Launch] Adobe Campaign Standardにはプロパティが表示されません。 {#visibility-mobile-property}

1. で、Adobe Campaign Standard拡張機能がモバイルプロパティにインストールされていることを確認し [!DNL Launch]ます。

1. 拡張内でインスタンスのエンドポイントが正しく設定されていることを確認します。

1. 「Launch_URL_キャンペーン」または「NmsServer_URL」が正しいことを確認します。

1. 次に、とAdobe Campaign間の同期が技術的なワークフローで完了し [!DNL Launch] ていることを確認し **[!UICONTROL syncWithLaunch]** ます。

## Adobe Campaignと起動の同期が完了したかどうかを確認する方法 {#sync-campaign-launch}

1. Adobe Campaign Standardで、アドバンスメニューから **[!UICONTROL Administration]** / **[!UICONTROL Application Settings]** /を選択し **[!UICONTROL Workflows]**&#x200B;ます。

1. ワークフローを開き **[!UICONTROL syncWithLaunch]** ます。

1. ワークフローがエラーなく終了したかどうかを確認します。

1. ワークフローの同期が有効で、正常に完了したことをログに確認します。

## 設定済みのモバイルアプリケーションのキーを「起動」でリセットします。 「起動」でキーを再設定する方法 {#configuring-pkey}

1. 「Adobeの起動」でモバイルプロパティを開きます。

1. PKeyがリセットされたAdobe Campaign Standard拡張に新しいURLを設定します。

1. 保存して、ワークフローとAdobe Campaignを同期させ [!DNL Launch]ます。

1. 同期が完了したら、でモバイルプロパティを開き [!DNL Launch]ます。

1. PKeyがリセットされたAdobe Campaign Standard拡張に正しいURLを設定します。

1. 保存して、ワークフローの同期を再実行します。

1. この場合にのみ、プロパティがAdobe Campaign内に **[!UICONTROL Ready to Configure]** 状態で表示され、設定できるようになります。

## Adobe Campaignでモバイルプロパティを設定する場合 テクニカルワークフローがAdobeの起動とAdobe Campaignの間で同期するのを待つ必要がありますか？

ワークフローを即時に実行できます。

1. Adobe Campaign Standardで、アドバンスメニューから **[!UICONTROL Administration]** / **[!UICONTROL Application Settings]** /を選択し **[!UICONTROL Workflows]**&#x200B;ます。

1. ワークフローを開き **[!UICONTROL syncWithLaunch]** ます。

1. Click on the **[!UICONTROL Scheduler]** activity and select **[!UICONTROL Immediate execution]**.
