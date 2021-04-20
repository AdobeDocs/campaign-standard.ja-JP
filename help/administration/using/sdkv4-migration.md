---
solution: Campaign Standard
product: campaign
title: Adobe Experience PlatformSDKへのSDK v4モバイルアプリケーションの移行
description: このドキュメントを使用すると、モバイルアプリケーションをSDK v4からAdobe Experience PlatformSDKに移行できます
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 1%

---


# SDK v4 からAdobe Experience Platform SDK にモバイルアプリケーションを移行する方法 {#sdkv4-migration}

>[!IMPORTANT]
>
> 移行プロセスは元に戻せません。
>
> SDK V4モバイルアプリケーションのAdobe Experience PlatformSDKへの移行を開始する前に、ドキュメントをよくお読みください。

## SDK V4への移行について

Adobe Campaign Standardは、SDK V4を使用して、Adobe Experience PlatformSDKを使用するアプリケーションとは別のアプリケーションとしてモバイルアプリケーションを処理します。
AdobeSDKのバージョンをv4からAdobe Experience Platformにアップグレードした後、モバイルアプリケーションは、既存のアプリケーション加入者のデータとキャンペーンを引き続き使用する必要があります。そのため、移行が必要です。

>[!NOTE]
>
> このページでは、新しく作成したAdobe Experience PlatformSDKアプリケーションへのSDK v4モバイルアプリケーションの移行をドキュメントします。 SDK v4モバイルアプリケーションは、**[!UICONTROL Configured]** **[!UICONTROL Property status]**&#x200B;を持つAdobe Experience PlatformSDKモバイルアプリケーションとは結合されません。

| 移行後に変更されないもの |
|:-:|
| 移行されたSDK V4アプリケーションを使用する既存の配信とキャンペーンには影響しません。 |
| モバイルアプリケーションの名前は変更されません。 |
| iOSとAndroidのプラットフォーム資格情報は保持されます。 |
| アプリケーションのすべてのサブスクライバーとそのデータは保持されます。 |
| 既存のSDK v4モバイルアプリケーションは、引き続きデータ（PIIデータ、加入者、トークン情報）をAdobe Campaign Standardに送信します。 |
| モバイルアプリケーションの&#x200B;**[!UICONTROL Organizational unit]**&#x200B;は同じままです。 |

| 移行後の変更点 |
|:-:|
| モバイルアプリケーションは、**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;で入手できます。 移行前は、**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;で利用できました。 |
| アプリケーションの&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;が変更されます。 古い&#x200B;**[!UICONTROL Collect PII Endpoint]**&#x200B;は引き続き動作し、送信されたデータは失われません。 |
| アプリケーションはAdobe Experience Platform Launch **[!UICONTROL Mobile Property]**&#x200B;に結び付けられます。 新しく作成したモバイルアプリケーションとして処理されます。 |
| 移行に使用する元のAdobe Experience PlatformSDKアプリケーションは、別のアプリケーションとしては存在しません。 移行されたSDK v4アプリケーションのみが使用可能になります。 |

## SDK v4からAdobe Experience PlatformSDK {#how-to-migrate}へのモバイルアプリケーションの移行

移行する前に、次の推奨事項を考慮する必要があります。

* 移行プロセスは元に戻せません。
* 複数のアプリケーションの移行を同時に実行しないでください。 また、同じアプリケーションの移行が複数のウィンドウで同時にトリガーされないようにする必要もあります。
* 移行する前に、移行するモバイルアプリケーションと、移行に使用するAdobe Experience Platformアプリケーションの&#x200B;**[!UICONTROL Organizational unit]**&#x200B;が割り当てられていることを確認してください。
* 移行後、アプリケーションはAdobe Experience PlatformSDKアプリケーションになります。 変更は、対応する起動&#x200B;**[!UICONTROL Mobile Property]**&#x200B;にリンクされます。

1. 新しい&#x200B;**[!UICONTROL Mobile property]**&#x200B;をAdobe Experience Platform Launchに作成します。 詳しくは、[Adobe Experience Platform Launchのドキュメント](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property)を参照してください。

1. Adobe Campaign Standardの詳細メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;を選択し、**[!UICONTROL syncWithLaunch]**&#x200B;ワークフローを開きます。 ワークフローがエラーなく終了したかどうかを確認します。

1. ワークフローの完了後、**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;メニューで、モバイルアプリケーションがAdobe Campaign Standardで使用可能で、**[!UICONTROL Ready to Configure]**&#x200B;状態になっているかどうかを確認します。

   ![](assets/aep_v4_2.png)

1. **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**&#x200B;で、移行するSDK V4アプリケーションを選択します。

1. 「**[!UICONTROL Mobile application migration to AEP SDK]**」タブを選択します。

   ![](assets/aep_v4_3.png)

1. **[!UICONTROL Select AEP SDK mobile application to merge current application with]**&#x200B;ドロップダウンから、以前に作成したAdobe Experience PlatformSDKモバイルアプリを選択します。

1. 「**[!UICONTROL Migrate]**」をクリックします。

   ![](assets/aep_v4_4.png)

1. **[!UICONTROL Migration application]**&#x200B;ウィンドウで&#x200B;**[!UICONTROL Ok]**&#x200B;をクリックします。

   ![](assets/aep_v4_5.png)

1. 正常に完了したときのウィンドウが表示されたら、「**[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**」をクリックします。

1. Adobe Experience PlatformSDKのチャネルリストページで、以前のV4モバイルアプリケーションが&#x200B;**[!UICONTROL Ready To Configure]**&#x200B;に設定されていることを確認します。

1. モバイルアプリケーションを選択し、**[!UICONTROL Save]**&#x200B;をクリックして移行を完了します。

この移行後、V4バージョンのモバイルアプリケーションで収集されたサブスクリプションおよびAEPバージョンのモバイルアプリケーションで収集された新しいサブスクリプションは、移行されたアプリケーションで使用できるようになります。

2種類のサブスクライバを区別するために、カスタムリソース&#x200B;**[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**&#x200B;を`sdkversion`や`appVersion`のように拡張する場合、**[!UICONTROL Text]**&#x200B;型の新しいカスタムフィールドを追加できます。 カスタムリソースを拡張する方法の詳細については、[ページ](../../developing/using/creating-or-extending-the-resource.md)を参照してください。
次に、関連するLaunch **[!UICONTROL Mobile property]**&#x200B;を設定して、このカスタムフィールド値をCollect PII呼び出しで送信し、それに応じてモバイルアプリケーションの設定を変更する必要があります。

## よくある質問{#faq}

### Q:SDK v4モバイルアプリケーションで、「Adobe Experience PlatformSDKへのモバイルアプリケーションの移行」タブが表示されません。{#tab-not-visible}

A:詳細設定メニュー&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**&#x200B;から、**[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**&#x200B;オプションの値を確認します。 デフォルトでは1に設定され、有効にする必要があります。 管理者が手動で無効にしている可能性があります。

![](assets/aep_v4_1.png)

### Q:「モバイルアプリケーションからAdobe Experience PlatformSDK」タブに移行すると、「データなし」というメッセージが表示されます。{#no-data}

A:**[!UICONTROL Organizational unit]**&#x200B;の適格な申し込みのみがリストに表示されます。 移行に適したAdobe Experience Platformアプリケーションがあることを確認してください。 Adobe Experience Platformアプリケーションの&#x200B;**[!UICONTROL Property Status]**&#x200B;は&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;に、**[!UICONTROL Mobile app migration status]**&#x200B;は&#x200B;**[!UICONTROL Not Migrated]**&#x200B;に設定する必要があります。

![](assets/aep_v4_6.png)

### Q:プロパティステータスが設定済みのAdobe Experience PlatformSDKアプリケーションを移行に使用できないのはなぜですか。{#property-status}

A:移行プロセスでは、SDK v4サブスクライバーと属性が保持されます。 Launch関連情報は、Adobe Experience PlatformSDKアプリケーションからのみ保持されます。 購読者と、Adobe Experience PlatformSDKアプリケーションからの他のデータは失われます。 データの損失を防ぐため、**[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]**&#x200B;を持つAdobe Experience PlatformのSDKアプリケーションのみが移行の資格を持ちます。

### Q:移行後、以前のSDK v4モバイルアプリケーションはどこで見つかりましたか？{#v4-app-not-visible}

A:移行後のモバイルアプリケーションは、アドバンスメニュー&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**&#x200B;から確認できます。

### Q:移行後、新しく作成したAdobe Experience PlatformSDKアプリケーションはどこで見つかりますか。{#aep-not-visible}

A:移行に使用する新しく作成したAdobe Experience PlatformSDKアプリケーションは、別のアプリケーションとしては存在しません。 移行されたSDK v4アプリケーションのみが使用可能になります。

### Q:SDK v4モバイルアプリケーションの組織単位がA（組織単位ALLの子）に、Adobe Experience PlatformSDKがALLに設定されている場合。 モバイルアプリケーションを移行する方法を教えてください。{#v4-org-unit}

A:**[!UICONTROL Organizational unit]** ALLの管理者は、両方のモバイルアプリケーションを管理する権限を持ち、移行を担当します。

### Q:SDK v4モバイルアプリケーションの組織単位がAに、Adobe Experience PlatformSDKアプリケーションがB（組織単位Aの兄弟）に設定されている場合。 モバイルアプリケーションを移行する方法を教えてください。{#aep-org-unit}

A:兄弟&#x200B;**[!UICONTROL Organizational unit]**&#x200B;のアセットとなるAdobe Experience PlatformSDKアプリケーションは、**[!UICONTROL Organizational unit]** Aのユーザーには表示されません。モバイルアプリケーションは、**[!UICONTROL Organizational unit]** ALLの管理者には利用できますが、モバイルアプリケーションの移行はお勧めしません。
この場合、モバイルアプリケーションを同じ**[!UICONTROL Organizational unit]**&#x200B;または親リンクの&#x200B;**[!UICONTROL Organizational unit]**内に移動する必要があります。
**[!UICONTROL Organizational unit]**&#x200B;の詳細は、[](../../administration/using/organizational-units.md)を参照してください。

### Q:（v4モバイルアプリケーションから移行された）Adobe Experience PlatformSDKモバイルアプリケーションページの「プッシュチャネル設定」ドロップダウンの下に、AndroidキーまたはiOS証明書{#no-information-v5}に対して、アップロードされた日付/名前などの情報は表示されません。

A:SDK V4モバイルアプリケーションの作成時に、この情報はシステムに保存されません。 SDK V4モバイルアプリケーションをAdobe Experience PlatformSDKモバイルアプリケーションに移行する場合、移行したモバイルアプリケーションにもこのような情報はありません。 ユーザーが新しいiOS証明書またはAndroidキーをアップロードするとすぐに、キーまたは証明書の異なる詳細が保存され、**[!UICONTROL Push channel settings]**&#x200B;ドロップダウンに正しく表示されます。
