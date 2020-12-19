---
solution: Campaign Standard
product: campaign
title: 起動の技術的なワークフローと同期FAQ
description: 技術ワークフローの開始に関するよくある質問です。
audience: administration
content-type: reference
topic-tags: users-and-security
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Adobe Launch 同期 FAQ {#syncwithlaunch-faq}

**[!UICONTROL Sync with Launch]**&#x200B;専用の技術的なワークフローを通じて、Adobeの起動モバイルのプロパティをAdobe Campaign Standardにインポートできます。 詳しくは、[ページ](../../administration/using/technical-workflows.md)を参照してください

以下の節では、この同期に関してよくある質問をリストします。

## [!DNL Launch]にプロパティを作成しました（組織単位ALLの非管理者）。 アプリケーションがAdobe Campaign中に「設定準備完了」状態になっていますが、開く/設定できません。{#configuring-property}

Adobe Campaign Standardでモバイルアプリケーションを設定できるのは、組織単位ALLの管理者だけです。 設定後は、割り当てられた組織単位のユーザーのみが
application. 組織単位の詳細については、[ページ](../../administration/using/organizational-units.md)を参照してください。

## 設定済みのモバイルアプリケーションをAdobe Campaign Standardで編集できません。モバイルアプリケーションは読み取りモードのみです。{#read-mode-mobile-app}

**[!UICONTROL Access Authorization ]**&#x200B;セクションのモバイルアプリケーションの組織単位を確認します。 割り当てられた組織単位のユーザーのみがモバイルアプリケーションを編集できます。

組織単位の詳細については、[ページ](../../administration/using/organizational-units.md)を参照してください。

## Adobe Campaign Standardの組織単位ALLの管理者ですが、モバイルアプリケーションを設定できません。{#org-unit-mobile}

組織単位が「すべて」に設定されている管理者は、モバイルアプリケーションを設定するために、[!DNL Launch]内のすべてのモバイルプロパティに対する権限を持つ必要があります。

組織単位の詳細については、[ページ](../../administration/using/organizational-units.md)を参照してください。

## [!DNL Launch]にモバイルプロパティを作成しましたが、プロパティがAdobe Campaign Standardに表示されません。{#visibility-mobile-property}

1. [!DNL Launch]のモバイルプロパティにAdobe Campaign Standard拡張機能がインストールされていることを確認します。

1. 拡張内でインスタンスのエンドポイントが正しく設定されていることを確認します。

1. 「Launch_URL_キャンペーン」または「NmsServer_URL」が正しいことを確認します。

1. 次に、[!DNL Launch]とAdobe Campaignの同期が&#x200B;**[!UICONTROL syncWithLaunch]**&#x200B;の技術的なワークフローで完了していることを確認します。

## Adobe Campaignと起動の同期が完了したかどうかを確認する方法{#sync-campaign-launch}

1. Adobe Campaign Standardの詳細メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;を選択します。

1. **[!UICONTROL syncWithLaunch]**&#x200B;ワークフローを開きます。

1. ワークフローがエラーなく終了したかどうかを確認します。

1. ワークフローの同期が有効で、正常に完了したことをログに確認します。

## 設定済みのモバイルアプリケーションのキーを「起動」でリセットします。 「起動」でキーを再設定する方法{#configuring-pkey}

1. 「Adobeの起動」でモバイルプロパティを開きます。

1. PKeyがリセットされたAdobe Campaign Standard拡張に新しいURLを設定します。

1. 保存して、Adobe Campaignと[!DNL Launch]の間でワークフローを同期させます。

1. 同期が完了したら、[!DNL Launch]のモバイルプロパティを開きます。

1. PKeyがリセットされたAdobe Campaign Standard拡張に正しいURLを設定します。

1. 保存して、ワークフローの同期を再実行します。

1. この場合にのみ、プロパティはAdobe Campaign内で&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;状態に表示され、設定できるようになります。

## Adobe Campaignでモバイルプロパティを設定する場合 テクニカルワークフローがAdobeの起動とAdobe Campaignの間で同期するのを待つ必要がありますか？

ワークフローを即時に実行できます。

1. Adobe Campaign Standardの詳細メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;を選択します。

1. **[!UICONTROL syncWithLaunch]**&#x200B;ワークフローを開きます。

1. **[!UICONTROL Scheduler]**&#x200B;アクティビティをクリックし、**[!UICONTROL Immediate execution]**&#x200B;を選択します。
