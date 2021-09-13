---
title: Adobe Experience Platform SDKへのSDK v4モバイルアプリケーションの移行
description: このドキュメントでは、モバイルアプリケーションをSDK v4からAdobe Experience Platform SDKに移行できます
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 1%

---

# SDK v4 からAdobe Experience Platform SDK にモバイルアプリケーションを移行する方法 {#sdkv4-migration}

>[!IMPORTANT]
>
> 移行プロセスは元に戻せません。
>
> SDK V4モバイルアプリケーションのAdobe Experience Platform SDKへの移行を開始する前に、ドキュメントをよくお読みください。

## SDK V4移行について

Adobe Campaign Standardは、SDK V4を使用するモバイルアプリケーションを、Adobe Experience Platform SDKを使用するアプリケーションとは別のアプリケーションとして処理します。
AdobeSDKのバージョンをv4からAdobe Experience Platformにアップグレードした後、モバイルアプリケーションは、既存のアプリケーション購読者データとキャンペーンを引き続き使用する必要があります。移行が必要です。

>[!NOTE]
>
> このページでは、SDK v4モバイルアプリケーションから新しく作成したAdobe Experience Platform SDKアプリケーションへの移行について説明します。 SDK v4モバイルアプリケーションは、**[!UICONTROL Configured]** **[!UICONTROL Property status]**&#x200B;を持つAdobe Experience Platform SDKモバイルアプリケーションと結合されません。

| 移行後に変更されない内容 |
|:-:|
| 移行されたSDK V4アプリケーションを使用する既存の配信およびキャンペーンには影響しません。 |
| モバイルアプリケーションの名前は変わりません。 |
| iOSおよびAndroidのプラットフォーム資格情報は保持されます。 |
| アプリケーションの購読者とそのデータはすべて保持されます。 |
| 既存のSDK v4モバイルアプリケーションは、引き続きデータ（PIIデータ、購読者およびトークン情報）をAdobe Campaign Standardに送信します。 |
| モバイルアプリケーションの&#x200B;**[!UICONTROL Organizational unit]**&#x200B;は同じままです。 |

| 移行後の変更点 |
|:-:|
| モバイルアプリケーションは、 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;で使用できます。 移行前は、 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;で使用できました。 |
| アプリケーションの&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;が変更されます。 古い&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;は引き続き機能し、送信されたデータは失われません。 |
| アプリケーションはAdobe Experience Platform Launch **[!UICONTROL Mobile Property]**&#x200B;に結び付けられます。 新しく作成されたモバイルアプリケーションとして処理されます。 |
| 移行に使用する元のAdobe Experience Platform SDKアプリケーションは、別個のアプリケーションとしては存在しません。 移行されたSDK v4アプリケーションのみを使用できます。 |

## SDK v4からAdobe Experience Platform SDKへのモバイルアプリケーションの移行 {#how-to-migrate}

移行する前に、次の推奨事項を考慮する必要があります。

* 移行プロセスは元に戻せません。
* 複数のアプリケーションの移行を同時に実行しないでください。 また、同じアプリケーションの移行が複数のウィンドウで同時にトリガーされないようにする必要があります。
* 移行する前に、移行するモバイルアプリケーションの&#x200B;**[!UICONTROL Organizational unit]**&#x200B;と、移行に使用するAdobe Experience Platformアプリケーションのが割り当てられていることを確認します。
* 移行後、アプリケーションはAdobe Experience Platform SDKアプリケーションになります。 変更は、対応するローンチ&#x200B;**[!UICONTROL Mobile Property]**&#x200B;にリンクされます。

1. Adobe Experience Platform Launchに新しい&#x200B;**[!UICONTROL Mobile property]**&#x200B;を作成します。 詳しくは、[Adobe Experience Platform Launchのドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property)を参照してください。

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** / **[!UICONTROL Application Settings]** / **[!UICONTROL Workflows]**&#x200B;を選択し、**[!UICONTROL syncWithLaunch]**&#x200B;ワークフローを開きます。 ワークフローがエラーなく終了したかどうかを確認します。

1. ワークフローが完了したら、 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;メニューで、モバイルアプリケーションがAdobe Campaign Standardで使用可能で、**[!UICONTROL Ready to Configure]**&#x200B;状態になっているかどうかを確認します。

   ![](assets/aep_v4_2.png)

1. **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;で、移行するSDK V4アプリケーションを選択します。

1. 「**[!UICONTROL Mobile application migration to AEP SDK]**」タブを選択します。

   ![](assets/aep_v4_3.png)

1. **[!UICONTROL Select AEP SDK mobile application to merge current application with]**&#x200B;ドロップダウンから、以前に作成したAdobe Experience Platform SDKモバイルアプリケーションを選択します。

1. 「**[!UICONTROL Migrate]**」をクリックします。

   ![](assets/aep_v4_4.png)

1. **[!UICONTROL Migration application]**&#x200B;ウィンドウで&#x200B;**[!UICONTROL Ok]**&#x200B;をクリックします。

   ![](assets/aep_v4_5.png)

1. 正常に完了したウィンドウが表示されたら、「**[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**」をクリックします。

1. Adobe Experience Platform SDKチャネルリストページで、以前のV4モバイルアプリケーションが&#x200B;**[!UICONTROL Ready To Configure]**&#x200B;に設定されていることを確認します。

1. モバイルアプリケーションを選択し、**[!UICONTROL Save]**&#x200B;をクリックして移行を完了します。

この移行後、モバイルアプリケーションのV4バージョンで収集された購読者と、モバイルアプリケーションのAEPバージョンで収集された新しい購読者を、移行されたアプリケーションで使用できるようになります。

2つの異なるタイプの購読者を区別するために、カスタムリソース&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;を`sdkversion`や`appVersion`などとして拡張する場合に、**[!UICONTROL Text]**&#x200B;タイプの新しいカスタムフィールドを追加できます。 カスタムリソースの拡張方法について詳しくは、この[ページ](../../developing/using/creating-or-extending-the-resource.md)を参照してください。
次に、関連するLaunch **[!UICONTROL Mobile property]**&#x200B;を設定して、このカスタムフィールド値をCollect PII呼び出しで送信し、それに応じてモバイルアプリケーション設定を変更する必要があります。

## FAQ {#faq}

### Q:SDK v4モバイルアプリケーションでは、「 Adobe Experience Platform SDKへのモバイルアプリケーションの移行」タブは表示されません。 {#tab-not-visible}

回答：詳細設定メニューの&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;で、**[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**&#x200B;オプションの値を確認します。 これは1に設定し、デフォルトで有効にする必要があります。 管理者が手動で無効にしている可能性があります。

![](assets/aep_v4_1.png)

### Q:「モバイルアプリケーションからAdobe Experience Platform SDKへの移行」タブに、「データなし」というメッセージが表示されます。 {#no-data}

回答：リストには、**[!UICONTROL Organizational unit]**&#x200B;の適格なアプリケーションのみが表示されます。 移行に適したAdobe Experience Platformアプリケーションがあることを確認してください。 Adobe Experience Platformアプリケーションの&#x200B;**[!UICONTROL Property Status]**&#x200B;は&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;に、**[!UICONTROL Mobile app migration status]**&#x200B;は&#x200B;**[!UICONTROL Not Migrated]**&#x200B;に設定する必要があります。

![](assets/aep_v4_6.png)

### Q:プロパティステータスが設定されたAdobe Experience Platform SDKアプリケーションを移行に使用できないのはなぜですか？ {#property-status}

回答：移行プロセスでは、SDK v4の購読者と属性が保持されます。 Adobe Experience Platform SDKアプリケーションからLaunch関連情報を保持するだけです。 Adobe Experience Platform SDKアプリケーションからの購読者およびその他のデータは失われます。 データの損失を避けるために、**[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]**&#x200B;を持つAdobe Experience Platform SDKアプリケーションのみ移行が可能です。

### Q:移行後、以前のSDK v4モバイルアプリケーションはどこで見つかりますか。 {#v4-app-not-visible}

回答：移行後のモバイルアプリケーションは、詳細設定メニュー&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;から表示されます。

### Q:移行後、新しく作成したAdobe Experience Platform SDKアプリケーションはどこにありますか。 {#aep-not-visible}

回答：移行に使用する新しく作成したAdobe Experience Platform SDKアプリケーションは、別のアプリケーションとしては存在しません。 移行されたSDK v4アプリケーションのみを使用できます。

### Q:SDK v4モバイルアプリケーションのOrganizational unitがA（Organizational unit ALLの子）に、Adobe Experience Platform SDKがALLに設定されている場合。 モバイルアプリケーションを移行するにはどうすればよいですか？ {#v4-org-unit}

回答：**[!UICONTROL Organizational unit]** ALLの管理者は、両方のモバイルアプリケーションを管理する権限を持ち、移行を担当します。

### Q:SDK v4モバイルアプリケーションの組織単位がAに、Adobe Experience Platform SDKアプリケーションがB（組織単位Aの兄弟）に設定されている場合。 モバイルアプリケーションを移行するにはどうすればよいですか？ {#aep-org-unit}

回答：兄弟&#x200B;**[!UICONTROL Organizational unit]**&#x200B;のアセットであるAdobe Experience Platform SDKアプリケーションは、**[!UICONTROL Organizational unit]** Aのユーザーにはモバイルアプリケーションを表示できません。**[!UICONTROL Organizational unit]**の管理者は、モバイルアプリケーションを移行することはお勧めしません。
この場合、同じ**[!UICONTROL Organizational unit]**&#x200B;内または&#x200B;**[!UICONTROL Organizational unit]**内で親リンクを使用してモバイルアプリケーションを移動する必要があります。
**[!UICONTROL Organizational unit]**&#x200B;の詳細は、[](../../administration/using/organizational-units.md)を参照してください。

### Q:Adobe Experience Platform SDKモバイルアプリケーション（v4モバイルアプリケーションから移行済み）ページの「プッシュチャネル設定」ドロップダウンに、AndroidキーやiOS証明書用にアップロードされた日付や名前などの情報は表示されません {#no-information-v5}

回答：SDK V4モバイルアプリケーションを作成する際、システムはこの情報を保存しません。 SDK V4モバイルアプリケーションをAdobe Experience Platform SDKモバイルアプリケーションに移行する場合、移行したモバイルアプリケーションにもこの種の情報は含まれません。 ユーザーが新しいiOS証明書またはAndroidキーをアップロードするとすぐに、キーまたは証明書の様々な詳細が保存され、**[!UICONTROL Push channel settings]**&#x200B;ドロップダウンの下に正しく表示されます。
