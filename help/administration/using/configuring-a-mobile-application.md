---
title: モバイルアプリケーションの設定
description: SDK V4 またはExperience PlatformSDK を使用して、Adobe Campaignからプッシュ通知またはアプリ内メッセージを送信するように設定する方法を確認します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 6%

---

# モバイルアプリケーションの設定{#configuring-a-mobile-application}

## Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定 {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>プッシュ通知およびアプリ内実装は、エキスパートユーザーが実行する必要があります。 不明な点は、担当のAdobeアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

Experience PlatformSDK アプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリケーションをAdobe Experience PlatformExperience PlatformExperience Platform Launchで設定し、Adobe Campaignで設定する必要があります。

非推奨（廃止予定）の機能 Mobile version 4 SDK について詳しくは、この [ ページ ](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html) を参照してください。

モバイルアプリケーションを設定したら、収集した PII データを取得して、データベースからプロファイルを作成または更新できます。 詳しくは、この節を参照してください。[ モバイルアプリケーションデータに基づいてプロファイル情報を作成し、更新します ](../../channels/using/updating-profile-with-mobile-app-data.md)。

Adobe Experience Platform SDK を使用してAdobe Campaign Standardでサポートされる様々なモバイル使用例について詳しくは、この [ ページ ](https://helpx.adobe.com/jp/campaign/kb/configure-launch-rules-acs-use-cases.html) を参照してください。

設定を完了するには、次の手順を実行します。

1. Adobe Campaignで、次にアクセスできることを確認します。
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   そうでない場合は、アカウントチームにお問い合わせください。

1. ユーザーがAdobe Campaign StandardとExperience Platform Launchで必要な権限を持っていることを確認します。
   * Adobe Campaign Standardで、IMS ユーザーが Standard User および Administrator 製品プロファイルに含まれていることを確認します。 この手順を使用すると、Adobe Campaign Standardにログインし、Experience PlatformSDK モバイルアプリページに移動して、Experience Platform Launchで作成したモバイルアプリのプロパティを表示できます。

   * Experience Platform Launchで、IMS ユーザーが製品プロファイルに含まれていることをExperience Platform Launchします。
この手順では、ユーザーがExperience Platform Launchにログインして、プロパティを作成および表示できます。 製品プロファイルの詳細については、「Experience Platform Launchの作成」を参照してください。 製品プロファイルには、会社やプロパティに権限は設定されていませんが、ユーザーは引き続きログインできます。

   拡張機能のインストール、アプリの公開、環境の設定など、追加のタスクを完了するには、製品プロファイルで権限を設定する必要があります。

1. Experience Platform Launchで、 **[!UICONTROL Mobile property]** を作成します。 詳しくは、[モバイルプロパティの設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)を参照してください。

1. Experience Platform Launchで、「**[!UICONTROL Extensions]**」タブをクリックし、「**[!UICONTROL Catalog]**」に移動して、「**[!UICONTROL Adobe Campaign Standard]**」拡張子を検索します。 詳しくは、[Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) を参照してください。

1. Campaign Standardで場所の使用例をサポートするには、 **[!UICONTROL Places]** 拡張機能と **[!UICONTROL Places Monitor]** 拡張機能をインストールします。
   * Experience Platform Launchに **[!UICONTROL Places]** 拡張機能をインストールします。 この[ページ](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html)を参照してください。
   * Experience Platform Launchに **[!UICONTROL Places Monitor]** 拡張機能をインストールします。 この[ページ](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)を参照してください。

1. Adobe Campaign Standard で、Experience Platform Launch で作成したモバイルプロパティを設定します。[Adobe CampaignでのAdobe Experience Platform Launchアプリケーションの設定 ](../../administration/using/configuring-a-mobile-application.md#set-up-campaign) を参照してください。

1. モバイルアプリケーションの設定にチャネル固有の設定を追加します。詳しくは、[Adobe Campaign のチャネル固有のアプリケーション設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)を参照してください。

1. 必要に応じて、Experience Platform Launchプロパティを削除できます。
詳しくは、[Experience Platform Launchアプリケーションの削除 ](../../administration/using/configuring-a-mobile-application.md#delete-app) を参照してください。

## Launch からのモバイルアプリ AEPSDK の同期テクニカルワークフロー {#aepsdk-workflow}

モバイルプロパティを作成してExperience Platform Launchで設定した後、 **[!UICONTROL Sync Mobile app AEPSDK from Launch]** テクニカルワークフローは、Adobe Campaign Standardで読み込まれたAdobeLaunch モバイルプロパティを同期するようになりました。

デフォルトでは、テクニカルワークフローは 15 分ごとに開始されます。 必要に応じて、手動で再起動できます。

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** を選択します。
1. **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** ワークフローを開きます。

   ![](assets/launch_10.png)

1. 「**[!UICONTROL Scheduler]**」アクティビティをクリックします。

1. 「**[!UICONTROL Immediate execution]**」を選択します。

   ![](assets/launch_11.png)

ワークフローが再起動し、Adobe Campaign Standardで読み込まれたAdobeLaunch モバイルプロパティが同期されます。

## Adobe CampaignでのAdobe Experience Platform Launchアプリケーションの設定 {#set-up-campaign}

Campaign でExperience Platform Launchモバイルプロパティを使用するには、Adobe Campaignでもこのプロパティを設定する必要があります。 Adobe Campaignで、IMS ユーザーが Standard User および Administrator 製品プロファイルに含まれていることを確認します。

テクニカルワークフローが実行され、Launch モバイルプロパティがAdobe Campaignに同期されるのを待つ必要があります。 その後、Adobe Campaignで設定できます。

Launch からのモバイルアプリ AEPSDK の同期テクニカルワークフローについて詳しくは、この [ 節 ](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) を参照してください。

>[!NOTE]
>
>デフォルトでは、組織単位が「すべて」に設定された管理者は、モバイルアプリケーションを編集できます。

1. 詳細設定メニューから、**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** を選択します。

   ![](assets/launch.png)

1. 「Experience Platform Launch」で作成したモバイルアプリを選択します。
**[!UICONTROL Property Status]** は **[!UICONTROL Ready to configure]** にする必要があります。

   >[!NOTE]
   >
   >デフォルトでは、AdobeLaunch で作成されたモバイルアプリケーションのリストを取得するために、Campaign Standardは「 NmsServer_URL 」オプションで定義された値を使用して、一致するプロパティを探します。
   >
   >場合によっては、モバイルアプリケーションの Campaign エンドポイントが NmsServer_URL で定義されたエンドポイントと異なることがあります。 その場合は、「 Launch_URL_Campaign 」オプションでエンドポイントを定義します。 Campaign は、このオプションの値を使用して、Launch で一致するプロパティを検索します。Adobe。

   ![](assets/launch_4.png)

1. **[!UICONTROL Access Authorization]** セクションでモバイルアプリケーションの組織単位を変更して、このモバイルアプリケーションへのアクセスを特定の組織単位に制限できます。 詳しくは、このページを参照してください。

   ここでは、管理者は、ドロップダウンからサブ組織単位を選択して割り当てることができます。

   ![](assets/launch_12.png)

1. Campaign とExperience Platform Launchを接続するには、**[!UICONTROL Save]** をクリックします。

1. モバイルアプリのステータスが **[!UICONTROL Ready to Configure]** から **[!UICONTROL Configured]** に変更されたことを確認します。

   Experience Platform LaunchCampaign 拡張機能でキーが正常に設定されたことが示されたら、Campaign でプロパティが正常に設定されたことを確認することもできます。

   ![](assets/launch_5.png)

1. この設定を有効にするには、変更をExperience Platform Launchで公開する必要があります。

   詳しくは、[ 公開設定 ](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration) を参照してください。

## Adobe Campaignでのチャネル固有のアプリケーション設定 {#channel-specific-config}

これで、モバイルアプリケーションを Campaign でプッシュ通知やアプリ内配信に使用する準備が整いました。 必要に応じて、アプリ内メッセージをトリガーするイベントを作成したり、プッシュ証明書をアップロードしたりするためのイベントを作成するために、さらに設定できるようになりました。

1. 詳細設定メニューから、**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** を選択します。

1. 作成し、「Experience Platform Launch」で設定したモバイルアプリを選択します。

1. 「**[!UICONTROL Mobile application properties]**」タブで、アプリ内メッセージ用のモバイルアプリケーションで使用できるイベントの追加を開始できます。

1. イベントを設定するには、**[!UICONTROL Create Element]** をクリックします。

   ![](assets/launch_6.png)

1. 名前と説明を入力します。

   ![](assets/launch_7.png)

1. 「**[!UICONTROL Add]**」をクリックします。

   これで、アプリ内メッセージを作成する際に、「トリガー」タブでイベントを利用できるようになりました。 詳しくは、「[ アプリ内メッセージの準備と送信 ](../../channels/using/preparing-and-sending-an-in-app-message.md)」を参照してください。

1. モバイルアプリケーションダッシュボードの **[!UICONTROL Device-specific settings]** セクションで、各デバイスに対して、iOS 用の証明書や Android 用のサーバーキーなど、アプリケーションの詳細を指定します。

   証明書がアップロードされると、アップロードが成功したことを示すメッセージが表示され、証明書の有効期限が表示されます。

   >[!NOTE]
   >
   >MCPNS アプリに追加できる APNS プラットフォーム（実稼動またはサンドボックス）は 1 つだけなので、Adobe Campaign Standardで証明書を正常に追加すると、設定を元に戻すことはできなくなります。

   ![](assets/launch_8.png)

1. 「 **[!UICONTROL Mobile application subscribers]** 」タブをクリックして、購読者のリストと、その購読者に関するその他の情報（例えば、通知をオプトアウトしたかどうか）を表示します。

## Adobe Experience Platform Launchアプリケーションの削除 {#delete-app}

Experience Platform Launchアプリの削除を元に戻すことはできません。

>[!CAUTION]
>
>Experience Platform Launchアプリの削除を元に戻すことはできません。

Experience Platform Launchアプリケーションを削除するには、[ モバイルプロパティの削除 ](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch) の手順を実行します。

アプリケーションを削除した後、Adobe Campaignで、アプリケーションのプロパティのステータスが Launch で正しく「削除済み」に更新されているかどうかを確認します。

Adobe Campaignでアプリをクリックして、「 Campaign から削除」をクリックして、Adobe Campaignからこのアプリを完全に削除するように選択できます。

![](assets/launch_9.png)
