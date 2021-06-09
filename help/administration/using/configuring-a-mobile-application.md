---
solution: Campaign Standard
product: campaign
title: モバイルアプリケーションの設定
description: SDK V4またはExperience PlatformSDKを使用して、Adobe Campaignからプッシュ通知またはアプリ内メッセージを送信する方法を確認します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: インスタンス設定
role: Administrator
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: 0080adf32cb011535004391e7468012a07b59a9f
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 7%

---

# モバイルアプリケーションの設定{#configuring-a-mobile-application}

## Adobe Experience Platform SDKを使用したモバイルアプリケーションの設定{#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>プッシュ通知およびアプリ内実装は、エキスパートユーザーが実行する必要があります。 支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

Experience PlatformSDKアプリケーションでプッシュ通知とアプリ内メッセージを送信するには、Adobe Experience PlatformExperience PlatformExperience Platform Launchでモバイルアプリケーションを設定し、Adobe Campaignで設定する必要があります。

非推奨（廃止予定）の機能Mobileバージョン4 SDKについて詳しくは、この[ページ](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html)を参照してください。

モバイルアプリケーションを設定したら、収集したPIIデータを取得して、データベースからプロファイルを作成または更新できます。 詳しくは、この節を参照してください。[モバイルアプリケーションデータに基づいてプロファイル情報を作成し、更新します](../../channels/using/updating-profile-with-mobile-app-data.md)。

Adobe Experience Platform SDKを使用してAdobe Campaign Standardでサポートされる様々なモバイル使用例について詳しくは、この[ページ](https://helpx.adobe.com/jp/campaign/kb/configure-launch-rules-acs-use-cases.html)を参照してください。

設定を完了するには、次の手順を実行します。

1. Adobe Campaignで、次の項目にアクセスできることを確認します。
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   そうでない場合は、アカウントチームにお問い合わせください。

1. ユーザーがAdobe Campaign StandardとExperience Platform Launchで必要な権限を持っていることを確認します。
   * Adobe Campaign Standardで、IMSユーザーがStandard UserおよびAdministrator製品プロファイルに含まれていることを確認します。 この手順を使用すると、ユーザーはAdobe Campaign Standardにログインし、Experience PlatformSDKモバイルアプリページに移動して、Experience Platform Launchで作成したモバイルアプリのプロパティを表示できます。

   * Experience Platform Launchで、IMSユーザーがAdobe Analytics製品プロファイルに属していることをExperience Platform Launchします。
この手順では、ユーザーがExperience Platform Launchにログインして、プロパティを作成および表示できます。 製品プロファイルについて詳しくは、「Experience Platform Launchの製品プロファイルの作成」を参照してください。 製品プロファイルには、会社やプロパティに権限が設定されていないが、ユーザーは引き続きログインできる。

   拡張機能のインストール、アプリの公開、環境の設定などの追加タスクを完了するには、製品プロファイルで権限を設定する必要があります。

1. Experience Platform Launchで、**[!UICONTROL Mobile property]**&#x200B;を作成します。 詳しくは、[モバイルプロパティの設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)を参照してください。

1. Experience Platform Launchで、「**[!UICONTROL Extensions]**」タブをクリックし、「**[!UICONTROL Catalog]**」に移動して、拡張子&#x200B;**[!UICONTROL Adobe Campaign Standard]**&#x200B;を検索します。 詳しくは、[Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)を参照してください。

1. Campaign Standardで場所の使用例をサポートするには、拡張機能&#x200B;**[!UICONTROL Places]**&#x200B;と拡張機能&#x200B;**[!UICONTROL Places Monitor]**&#x200B;をインストールします。
   * Experience Platform Launchに&#x200B;**[!UICONTROL Places]**&#x200B;拡張機能をインストールします。 この[ページ](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html)を参照してください。
   * Experience Platform Launchに&#x200B;**[!UICONTROL Places Monitor]**&#x200B;拡張機能をインストールします。 この[ページ](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)を参照してください。

1. Adobe Campaign Standard で、Experience Platform Launch で作成したモバイルプロパティを設定します。[Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)でのAdobe Experience Platform Launchアプリケーションの設定を参照してください。

1. モバイルアプリケーションの設定にチャネル固有の設定を追加します。詳しくは、[Adobe Campaign のチャネル固有のアプリケーション設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)を参照してください。

1. 必要に応じて、Experience Platform Launchプロパティを削除できます。
詳しくは、[Experience Platform Launchアプリケーションの削除](../../administration/using/configuring-a-mobile-application.md#delete-app)を参照してください。

## LaunchテクニカルワークフローからのモバイルアプリAEPSDKの同期{#aepsdk-workflow}

モバイルプロパティを作成してExperience Platform Launchで設定した後、**[!UICONTROL Sync Mobile app AEPSDK from Launch]**&#x200B;テクニカルワークフローは、Adobe Campaign Standardで読み込まれたAdobeLaunchモバイルプロパティを同期するようになりました。

デフォルトでは、テクニカルワークフローは15分ごとに開始されます。 必要に応じて、手動で再起動できます。

1. Adobe Campaign Standardの詳細設定メニューで、**[!UICONTROL Administration]** / **[!UICONTROL Application Settings]** / **[!UICONTROL Workflows]**&#x200B;を選択します。
1. **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**&#x200B;ワークフローを開きます。

   ![](assets/launch_10.png)

1. 「**[!UICONTROL Scheduler]**」アクティビティをクリックします。

1. 「**[!UICONTROL Immediate execution]**」を選択します。

   ![](assets/launch_11.png)

これで、ワークフローが再起動し、Adobe Campaign Standardで読み込まれたAdobeLaunchモバイルプロパティが同期されます。

## Adobe Campaign {#set-up-campaign}でのAdobe Experience Platform Launchアプリケーションの設定

CampaignでExperience Platform Launchモバイルプロパティを使用するには、Adobe Campaignでもこのプロパティを設定する必要があります。 Adobe Campaignで、IMSユーザーがStandard UserおよびAdministrator製品プロファイルに含まれていることを確認します。

テクニカルワークフローが実行され、LaunchモバイルプロパティがAdobe Campaignに同期されるのを待つ必要があります。 その後、Adobe Campaignで設定できます。

LaunchからのモバイルアプリAEPSDKの同期テクニカルワークフローについて詳しくは、この[節](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)を参照してください。

>[!NOTE]
>
>デフォルトでは、組織単位が「すべて」に設定された管理者は、モバイルアプリケーションを編集できます。

1. 詳細設定メニューから、**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**&#x200B;を選択します。

   ![](assets/launch.png)

1. 「Experience Platform Launch」で作成したモバイルアプリを選択します。
**[!UICONTROL Property Status]**&#x200B;は&#x200B;**[!UICONTROL Ready to configure]**&#x200B;にする必要があります。

   >[!NOTE]
   >
   >デフォルトでは、AdobeLaunchで作成されたモバイルアプリケーションのリストを取得するために、Campaign Standardは、 NmsServer_URLオプションで定義された値を使用して、一致するプロパティを探します。
   >
   >場合によっては、モバイルアプリケーションのCampaignエンドポイントがNmsServer_URLで定義されたエンドポイントと異なることがあります。 その場合は、「 Launch_URL_Campaign 」オプションでエンドポイントを定義します。 Campaignは、このオプションの値を使用して、Campaign Launchで一致するプロパティを検索します。Adobe。

   ![](assets/launch_4.png)

1. **[!UICONTROL Access Authorization]**&#x200B;セクションでモバイルアプリケーションの組織単位を変更して、このモバイルアプリケーションへのアクセスを特定の組織単位に制限できます。 詳しくは、このページを参照してください。

   ここでは、管理者は、ドロップダウンからサブ組織単位を選択して割り当てることができます。

   ![](assets/launch_12.png)

1. CampaignとExperience Platform Launchを接続するには、**[!UICONTROL Save]**&#x200B;をクリックします。

1. モバイルアプリのステータスが&#x200B;**[!UICONTROL Ready to Configure]**&#x200B;から&#x200B;**[!UICONTROL Configured]**&#x200B;に変わったことを確認します。

   Experience Platform Launchキャンペーン拡張機能でキーが正常に設定されたことが示されたら、Campaignでプロパティが正常に設定されたことを確認することもできます。

   ![](assets/launch_5.png)

1. この設定を有効にするには、変更をExperience Platform Launchで公開する必要があります。

   詳しくは、[公開設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)を参照してください。

## Adobe Campaign {#channel-specific-config}でのチャネル固有のアプリケーション設定

これで、モバイルアプリケーションをCampaignでプッシュ通知またはアプリ内配信に使用する準備が整いました。 必要に応じて、アプリ内メッセージをトリガーするイベントを作成したり、プッシュ証明書をアップロードしたりするために、さらに詳細な設定をおこなうことができます。

1. 詳細設定メニューから、**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**&#x200B;を選択します。

1. 作成し、「Experience Platform Launch」で設定したモバイルアプリを選択します。

1. 「**[!UICONTROL Mobile application properties]**」タブで、アプリ内メッセージ用のモバイルアプリで使用できるイベントの追加を開始できます。

1. イベントを設定するには、**[!UICONTROL Create Element]**&#x200B;をクリックします。

   ![](assets/launch_6.png)

1. 名前と説明を入力します。

   ![](assets/launch_7.png)

1. 「**[!UICONTROL Add]**」をクリックします。

   これで、アプリ内メッセージを作成する際に、「トリガー」タブでイベントを利用できるようになりました。 詳しくは、「[アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)」を参照してください。

1. モバイルアプリケーションダッシュボードの&#x200B;**[!UICONTROL Device-specific settings]**&#x200B;セクションで、各デバイスに対して、iOS用の証明書やAndroid用のサーバーキーなど、アプリケーションの詳細を指定します。

   証明書がアップロードされると、アップロードが成功したことを示すメッセージが表示され、証明書の有効期限が表示されます。

   >[!NOTE]
   >
   >Adobe Campaign Standardで証明書が正常に追加されると、MCPNSアプリに追加できるAPNSプラットフォーム（実稼動またはサンドボックス）は1つだけなので、設定を元に戻すことはできなくなります。

   ![](assets/launch_8.png)

1. 「 **[!UICONTROL Mobile application subscribers]** 」タブをクリックして、購読者のリストと、その購読者に関するその他の情報（例えば、通知をオプトアウトしたかどうか）を表示します。

## Adobe Experience Platform Launchアプリケーション{#delete-app}の削除

Experience Platform Launchアプリの削除を元に戻すことはできません。

>[!CAUTION]
>
>Experience Platform Launchアプリの削除を元に戻すことはできません。

Experience Platform Launchアプリケーションを削除するには、[モバイルプロパティの削除](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)の手順を実行します。

アプリケーションを削除した後、Adobe Campaignで、アプリケーションのプロパティのステータスがLaunchで正しく「削除済み」に更新されているかどうかを確認します。

Adobe Campaignでアプリをクリックして、「 Campaignから削除」をクリックすると、Adobe Campaignからこのアプリを完全に削除できます。

![](assets/launch_9.png)
