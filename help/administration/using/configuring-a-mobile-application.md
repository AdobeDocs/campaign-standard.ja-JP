---
solution: Campaign Standard
product: campaign
title: モバイルアプリケーションの設定
description: SDK V4またはExperience PlatformSDKを使用して、プッシュ通知またはアプリ内メッセージを送信するAdobe Campaignの設定方法を確認します。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1283'
ht-degree: 8%

---


# モバイルアプリケーションの設定{#configuring-a-mobile-application}

## Adobe Experience PlatformSDKを使用したモバイルアプリの設定{#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>プッシュ通知およびアプリ内実装は、エキスパートユーザーが実行する必要があります。 支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

Experience PlatformSDKアプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリをAdobe Experience PlatformExperience PlatformExperience Platform Launchで設定し、Adobe Campaignで設定する必要があります。

非推奨の機能であるMobile Version 4 SDKについて詳しくは、[ページ](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html)を参照してください。

モバイルアプリケーションを設定したら、収集したPIIデータを取得して、プロファイルの作成や更新をデータベースから行うことができます。 この点について詳しくは、次の節を参照してください。[モバイルアプリケーションデータ](../../channels/using/updating-profile-with-mobile-app-data.md)に基づくプロファイル情報の作成と更新。

Adobe Experience PlatformSDKを使用してAdobe Campaign Standardでサポートされている様々なモバイル使用例について詳しくは、[ページ](https://helpx.adobe.com/jp/campaign/kb/configure-launch-rules-acs-use-cases.html)を参照してください。

設定を完了するには、次の手順を実行します。

1. Adobe Campaignで、次の項目にアクセスできることを確認します。
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   そうでない場合は、アカウントチームにお問い合わせください。

1. ユーザーがAdobe Campaign StandardおよびExperience Platform Launchで必要な権限を持っていることを確認します。
   * Adobe Campaign Standardで、IMSユーザーがStandard UserおよびAdministratorの製品プロファイルの一部であることを確認します。 この手順では、ユーザーがAdobe Campaign Standardにログインし、Experience PlatformSDKモバイルアプリページに移動して、Experience Platform Launchで作成したモバイルアプリのプロパティを表示できます。

   * Experience Platform Launchで、IMSユーザーがExperience Platform Launch製品プロファイルの一部であることを確認します。
この手順では、Experience Platform Launchにログインして、プロパティを作成し表示できます。 Experience Platform Launchでの製品のプロファイルについて詳しくは、「製品プロファイルの作成」を参照してください。 製品プロファイルでは、会社やプロパティに権限が設定されていないはずですが、ユーザーはログイン可能です。

   拡張機能のインストール、アプリの公開、環境の設定など、追加のタスクを実行するには、製品プロファイルで権限を設定する必要があります。

1. Experience Platform Launchで、**[!UICONTROL Mobile property]**&#x200B;を作成します。 詳しくは、[モバイルプロパティの設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)を参照してください。

1. Experience Platform Launchで、「**[!UICONTROL Extensions]**」タブをクリックし、**[!UICONTROL Catalog]**&#x200B;に移動して&#x200B;**[!UICONTROL Adobe Campaign Standard]**&#x200B;拡張子を検索します。 詳しくは、[Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)を参照してください。

1. Campaign Standardでの場所の使用例をサポートするには、**[!UICONTROL Places]**&#x200B;拡張子と&#x200B;**[!UICONTROL Places Monitor]**&#x200B;拡張子をインストールします。
   * Experience Platform Launchに&#x200B;**[!UICONTROL Places]**&#x200B;拡張機能をインストールします。 この[ページ](https://docs.adobe.com/content/help/ja-JP/places/using/places-ext-aep-sdks/places-extension/places-extension.html)を参照してください。
   * Experience Platform Launchに&#x200B;**[!UICONTROL Places Monitor]**&#x200B;拡張機能をインストールします。 この[ページ](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)を参照してください。

1. Adobe Campaign Standard で、Experience Platform Launch で作成したモバイルプロパティを設定します。[Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)でのAdobe Experience Platform Launchアプリの設定を参照してください。

1. モバイルアプリケーションの設定にチャネル固有の設定を追加します。詳しくは、[Adobe Campaign のチャネル固有のアプリケーション設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)を参照してください。

1. 必要に応じて、Experience Platform Launchのプロパティを削除できます。
詳しくは、[Experience Platform Launchアプリケーションの削除](../../administration/using/configuring-a-mobile-application.md#delete-app)を参照してください。

## テクニカルワークフローの起動からMobileアプリAEPSDKを同期{#aepsdk-workflow}

Experience Platform Launchでモバイルプロパティを作成および設定した後、**[!UICONTROL Sync Mobile app AEPSDK from Launch]**&#x200B;テクニカルワークフローは、Adobe Campaign Standardで読み込んだAdobe起動モバイルプロパティを同期します。

デフォルトでは、技術ワークフローの開始は15分ごとに行われます。 必要に応じて、手動で再起動できます。

1. Adobe Campaign Standardの詳細メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**&#x200B;を選択します。
1. **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**&#x200B;ワークフローを開きます。

   ![](assets/launch_10.png)

1. **[!UICONTROL Scheduler]**&#x200B;アクティビティをクリックします。

1. 「**[!UICONTROL Immediate execution]**」を選択します。

   ![](assets/launch_11.png)

ワークフローは再起動され、Adobe Campaign StandardでインポートされたAdobe起動モバイルプロパティの同期が行われます。

## Adobe Campaign{#set-up-campaign}でのAdobe Experience Platform Launchアプリのセットアップ

キャンペーンでExperience Platform Launchモバイルプロパティを使用するには、Adobe Campaignでこのプロパティを設定する必要もあります。 Adobe Campaignで、IMSユーザーがStandard UserおよびAdministratorの製品プロファイルの一部であることを確認します。

テクニカルワークフローが実行され、モバイルの起動プロパティをAdobe Campaignに同期するまで待つ必要があります。 その後、Adobe Campaignで設定できます。

「Launch technical workflow」の「Sync Mobile app AEPSDK」について詳しくは、[セクション](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)を参照してください。

>[!NOTE]
>
>デフォルトでは、組織単位を「すべて」に設定した管理者は、モバイルアプリケーションを編集できます。

1. 詳細設定メニューで、**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (AEP SDK)]**&#x200B;を選択します。

   ![](assets/launch.png)

1. Experience Platform Launchで作成したモバイルアプリを選択します。
**[!UICONTROL Property Status]**&#x200B;は&#x200B;**[!UICONTROL Ready to configure]**&#x200B;にする必要があります。

   >[!NOTE]
   >
   >デフォルトでは、「Adobeの起動」で作成されたモバイルアプリケーションのリストを取得するために、Campaign StandardはNmsServer_URLオプションで定義された値を使用して、一致するプロパティを探します。
   >
   >場合によっては、モバイルアプリケーションのキャンペーンエンドポイントがNmsServer_URLで定義されているエンドポイントと異なることがあります。 その場合は、「Launch_URL_キャンペーン」オプションでエンドポイントを定義します。 キャンペーンは、このオプションの値を使用して、「Adobeの起動」で一致するプロパティを探します。

   ![](assets/launch_4.png)

1. **[!UICONTROL Access Authorization]**&#x200B;セクションでモバイルアプリケーションの組織単位を変更して、このモバイルアプリケーションへのアクセスを特定の組織単位に制限できます。 詳しくは、このページを参照してください。

   ここでは、管理者は、ドロップダウンから副組織単位を選択して、副組織単位を割り当てることができます。

   ![](assets/launch_12.png)

1. キャンペーンとExperience Platform Launchを接続するには、**[!UICONTROL Save]**&#x200B;をクリックします。

1. モバイルアプリのステータスが&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;から&#x200B;**[!UICONTROL Configured]**&#x200B;に変更されたことを確認します。

   Experience Platform Launchキャンペーンの拡張で、キーが正常に設定されたことが示された場合は、キャンペーンでプロパティが正常に設定されたことを確認することもできます。

   ![](assets/launch_5.png)

1. この設定を有効にするには、変更をExperience Platform Launchで公開する必要があります。

   詳しくは、[公開設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)を参照してください。

## Adobe Campaign{#channel-specific-config}のチャネル固有のアプリケーション設定

これで、モバイルアプリケーションをキャンペーンでプッシュ通知またはアプリ内配信に使用できる状態になりました。 必要に応じて、アプリ内メッセージをトリガーするイベントを作成したり、プッシュ証明書をアップロードしたりするために、さらに設定できるようになりました。

1. 詳細設定メニューで、**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (AEP SDK)]**&#x200B;を選択します。

1. Experience Platform Launchで作成および設定したモバイルアプリケーションを選択します。

1. 「**[!UICONTROL Mobile application properties]**」タブで、アプリ内メッセージ用のモバイルアプリで使用できるイベントの追加を開始できます。

1. イベントを設定するには、**[!UICONTROL Create Element]**&#x200B;をクリックします。

   ![](assets/launch_6.png)

1. 名前と説明を入力します。

   ![](assets/launch_7.png)

1. 「**[!UICONTROL Add]**」をクリックします。

   イベントは、アプリ内メッセージの作成時に「トリガー」タブで使用できるようになりました。 詳しくは、[アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)を参照してください。

1. モバイルアプリケーションダッシュボードの&#x200B;**[!UICONTROL Device-specific settings]**&#x200B;セクションで、各デバイスに対して、iOS用の証明書やAndroid用のサーバーキーなど、アプリケーションの詳細を指定します。

   証明書がアップロードされると、アップロードが成功したことを示すメッセージが表示され、証明書の有効期限が表示されます。

   >[!NOTE]
   >
   >Adobe Campaign Standardで証明書を正常に追加すると、MCPNSアプリに追加できるAPNSプラットフォーム（実稼働環境またはサンドボックス）は1つだけなので、設定を元に戻すことができなくなります。

   ![](assets/launch_8.png)

1. 「**[!UICONTROL Mobile application subscribers]**」タブをクリックすると、購読者のリストや、通知をオプトアウトしたかどうかなど、購読者に関するその他の情報が表示されます。

## Adobe Experience Platform Launchアプリケーションを削除しています{#delete-app}

Experience Platform Launchアプリの削除を元に戻すことはできません。

>[!CAUTION]
>
>Experience Platform Launchアプリの削除を元に戻すことはできません。

Experience Platform Launchアプリを削除するには、[モバイルプロパティの削除](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)の手順を実行します。

アプリケーションを削除した後、Adobe Campaignで、アプリケーションのプロパティのステータスが「起動時に削除されました」に正しく更新されているかどうかを確認します。

Adobe Campaignでアプリをクリックすると、「キャンペーンから削除」をクリックして、Adobe Campaignからこのアプリを完全に削除できます。

![](assets/launch_9.png)
