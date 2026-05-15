---
title: Launch テクニカルワークフローとの同期に関するFAQ
description: Adobe Launch テクニカルワークフローに関するよくある質問
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
TQID: https://experienceleague.adobe.com/0ixw0iKTFcM1081kmmLNj0iPuH-XwWWKETDALpobe8k
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 497
ht-degree: 1%

---

# Adobe Experience Platform 同期のタグに関する FAQ {#syncwithlaunch-faq}

タグのモバイルプロパティは、**[!UICONTROL Sync with Launch]**&#x200B;専用のテクニカルワークフローを通じてAdobe Campaign Standardに読み込むことができます。 詳しくは、この[&#x200B; ページ &#x200B;](../../administration/using/technical-workflows.md)を参照してください

以下の節では、この同期に関する一般的な質問を示します。

## タグプロパティを作成しました（組織単位ALLの管理者以外）。 アプリケーションがAdobe Campaignの「設定の準備完了」状態になっているが、アプリケーションを開いたり設定したりできない。 {#configuring-property}

Adobe Campaign Standardでモバイルアプリケーションを設定できるのは、組織単位ALLの管理者のみです。 設定が完了すると、割り当てられた組織単位のユーザーのみが
アプリケーション： 組織単位について詳しくは、この[&#x200B; ページ &#x200B;](../../administration/using/organizational-units.md)を参照してください。

## Adobe Campaign Standardで設定済みのモバイルアプリケーションを編集できず、モバイルアプリケーションが読み取りモードのみになっています。 {#read-mode-mobile-app}

**[!UICONTROL Access Authorization]** セクションのモバイル アプリケーションの組織単位を確認してください。 割り当てられた組織単位のユーザーのみがモバイルアプリケーションを編集できます。

組織単位について詳しくは、この[&#x200B; ページ &#x200B;](../../administration/using/organizational-units.md)を参照してください。

## Adobe Campaign Standardの組織単位ALLを持つ管理者ですが、モバイルアプリケーションを設定できません。 {#org-unit-mobile}

組織単位がALLに設定されている管理者は、モバイルアプリケーションを設定するためにすべてのタグモバイルプロパティに対する権限を持っている必要があります。

組織単位について詳しくは、この[&#x200B; ページ &#x200B;](../../administration/using/organizational-units.md)を参照してください。

## タグモバイルプロパティを作成しましたが、自分のプロパティはAdobe Campaign Standardに表示されません。 {#visibility-mobile-property}

1. Adobe Campaign Standard拡張機能がData Collection UIのモバイルプロパティにインストールされていることを確認します。

1. インスタンスのエンドポイントが拡張機能で正しく設定されていることを確認します。

1. 「Launch_URL_Campaign」または「NmsServer_URL」が正しいことを確認します。

1. 次に、**[!UICONTROL syncWithLaunch]**&#x200B;のテクニカルワークフローで同期が完了したことを確認します。

## Adobe Experience PlatformのAdobe Campaignとタグの同期が完了したかどうかを確認するにはどうすればよいですか？ {#sync-campaign-launch}

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;を選択します。

1. **[!UICONTROL syncWithLaunch]** ワークフローを開きます。

1. ワークフローがエラーなしで終了したかどうかを確認します。

1. ワークフロー同期が有効になっていて、正常に完了したことをログで確認します。

## 設定したタグモバイルアプリケーションのキーをリセットします。 データ収集UIでキーを再設定するにはどうすればよいですか？ {#configuring-pkey}

1. データ収集UIでモバイルプロパティを開きます。

1. PKeyがリセットされたAdobe Campaign Standard拡張機能に新しいURLを設定します。

1. 保存して、ワークフローを同期させます。

1. 同期が完了したら、データ収集UIででモバイルプロパティを開きます。

1. PKeyがリセットされたAdobe Campaign Standard拡張機能に正しいURLを設定します。

1. 保存して、ワークフローの同期を再度実行します。

1. その場合にのみ、プロパティはAdobe Campaignの&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;状態で表示され、設定できるようになりました。

## Adobe Campaignでモバイルプロパティを設定する。 Adobe Experience PlatformとAdobe Campaignのタグ間でテクニカルワークフローが同期されるのを待つ必要がありますか？

ワークフローをすぐに実行できます。

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;を選択します。

1. **[!UICONTROL syncWithLaunch]** ワークフローを開きます。

1. **[!UICONTROL Scheduler]** アクティビティをクリックし、**[!UICONTROL Immediate execution]**&#x200B;を選択します。
