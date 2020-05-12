---
title: モバイルアプリケーションの設定
description: SDK V4またはExperience Platform SDKを使用してプッシュ通知またはアプリ内メッセージを送信するAdobe Campaignの設定方法を確認します。
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f4f09556fed8c3cca44a72ac6dfeb280379d58c3
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 2%

---


# モバイルアプリケーションの設定{#configuring-a-mobile-application}

## Adobe Experience Platform SDKを使用したモバイルアプリケーションの設定 {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>プッシュ通知およびアプリ内実装は、エキスパートユーザーが実行する必要があります。 支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

Experience Platform SDKアプリケーションでプッシュ通知やアプリ内メッセージを送信するには、モバイルアプリケーションをAdobe Experience Platform Experience Platform Launchに設定し、Adobe Campaignで設定する必要があります。

Mobileバージョン4 SDKの非推奨機能について詳しくは、この [ページを参照してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html)。

モバイルアプリケーションを設定したら、収集したPIIデータを取得して、プロファイルの作成や更新をデータベースから行うことができます。 この点について詳しくは、次の節を参照してください。 [モバイルアプリケーションデータに基づくプロファイル情報の作成と更新](../../channels/using/updating-profile-with-mobile-app-data.md)。

Adobe Experience Platform SDKを使用して、Adobe Campaign標準でサポートされている様々なモバイル使用例について詳しくは、この [ページを参照してください](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

設定を完了するには、次の手順を実行します。

1. Adobe Campaignで、次の項目にアクセスできることを確認します。
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**
   そうでない場合は、アカウントチームにお問い合わせください。

1. ユーザーがPlatform StandardおよびExperience Platform Launchで必要な権限を持っていることを確認します。
   * Adobe Campaign標準で、IMSユーザーがStandardユーザーおよびAdministrator製品プロファイルの一部であることを確認します。 この手順では、Adobe Campaign標準にログインし、Experience Platform SDKモバイルアプリページに移動して、Experience Platform Launchで作成したモバイルアプリのプロパティを表示できます。

   * 「エクスペリエンスプラットフォームの起動」で、IMSユーザーがExperience Platform Launch製品プロファイルの一部であることを確認します。
この手順では、ユーザーがExperience Platform Launchにログインして、プロパティを作成し表示できます。 Experience Platform Launchの製品プロファイルについて詳しくは、「製品プロファイルの作成」を参照してください。 製品プロファイルでは、会社やプロパティに権限が設定されていないはずですが、ユーザーはログイン可能です。
   拡張機能のインストール、アプリの公開、環境の設定など、追加のタスクを実行するには、製品プロファイルで権限を設定する必要があります。

1. エクスペリエンスプラットフォームの起動で、を作成し **[!UICONTROL Mobile property]**&#x200B;ます。 詳しくは、「モバイルプロパティの [設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)」を参照してください。

1. エクスペリエンスプラットフォームの起動で、 **[!UICONTROL Extensions]** タブをクリックし、に移動して、 **[!UICONTROL Catalog]****[!UICONTROL Adobe Campaign Standard]** 拡張機能を検索します。 詳しくは、 [Adobe Campaign標準を参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)。

1. Campaign Standardでの場所の使用例をサポートするには、拡張機能と拡張機能をインスト **[!UICONTROL Places]** ールし **[!UICONTROL Places Monitor]** ます。
   * Experience Platform Launchに **[!UICONTROL Places]** 拡張機能をインストールします。 この[ページ](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html)を参照してください。
   * Experience Platform Launchに **[!UICONTROL Places Monitor]** 拡張機能をインストールします。 Refer to this [page](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. Adobe Campaign標準で、Experience Platform Launchで作成したモバイルプロパティを設定します。 詳しくは、Adobe CampaignでのAdobe Experience Platform Launchアプリケーションの [設定を参照してください](../../administration/using/configuring-a-mobile-application.md#set-up-campaign)。

1. モバ追加イルアプリケーションの設定に対するチャネル固有の設定。
詳しくは、「Adobe Campaign [」の「](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)チャネル固有のアプリケーション設定」を参照してください。

1. 必要に応じて、エクスペリエンスプラットフォーム起動プロパティを削除できます。
詳しくは、Experience Platform Launchアプリケーションの [削除を参照してください](../../administration/using/configuring-a-mobile-application.md#delete-app)。

## テクニカルワークフローの起動からのMobileアプリAEPSDKの同期 {#aepsdk-workflow}

>[!IMPORTANT]
>
>この機能は、リリース20.3以降のAdobe Campaignでのベータ版機能です。Adobe Campaignインスタンスで技術ワークフローを有効にするには、アドビカスタマーケアにチケットを（直接またはアドビの担当者を通じて）送信する必要があります。 **[!UICONTROL sync Mobile app AEPSDK from Launch]**

Experience Platform Launchでモバイルプロパティを作成および設定した後、 **[!UICONTROL Sync Mobile app AEPSDK from Launch]** テクニカルワークフローは、Adobe Campaign標準で読み込んだAdobe Launchモバイルプロパティを同期します。

デフォルトでは、技術ワークフローの開始は15分ごとに行われます。 必要に応じて、手動で再起動できます。

1. Adobe Campaign標準で、アドバンスメニューから/ **[!UICONTROL Administration]** /を選択し **[!UICONTROL Application Settings]****[!UICONTROL Workflows]**&#x200B;ます。
1. ワークフローを開き **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** ます。

   ![](assets/launch_10.png)

1. アクティビティをクリックし **[!UICONTROL Scheduler]** ます。

1. 選択 **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

ワークフローが再起動し、Adobe Standardで読み込んだAdobe Launchモバイルプロパティが同期されます。

## Adobe CampaignでのAdobe Experience Platform Launchアプリケーションのセットアップ {#set-up-campaign}

キャンペーンでExperience Platform Launchモバイルプロパティを使用するには、Adobe Campaignでこのプロパティを設定する必要もあります。 Adobe Campaignで、IMSユーザーがStandard UserおよびAdministratorの製品プロファイルの一部であることを確認します。

「テクニカルワークフロー機能の起動からMobileアプリAEPSDKを同期」フラグが有効になっているユーザーは、テクニカルワークフローが実行されるのを待ち、モバイルの起動プロパティをAdobe Campaignに同期する必要があります。 その後、Adobe Campaignで設定できます。

「テクニカルワークフロー機能の起動」のフラグから、モバイルアプリAEPSDKを同期に関する情報について詳しくは、この [節を参照してください](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow)。

>[!NOTE]
>
>デフォルトでは、組織単位を「すべて」に設定した管理者は、モバイルアプリケーションを編集できます。

1. 詳細設定メニューで、/ **[!UICONTROL Administration]** /を選択し **[!UICONTROL Channels]** ま **[!UICONTROL Mobile app (AEP SDK)]**&#x200B;す。

   ![](assets/launch.png)

1. Experience Platform Launchで作成したモバイルアプリケーションを選択します。
そ **[!UICONTROL Property Status]** うなるはず **[!UICONTROL Ready to configure]**&#x200B;だ。

   >[!NOTE]
   >
   >デフォルトでは、Adobe Launchで作成されたモバイルアプリケーションのリストを取得するために、Campaign StandardはNmsServer_URLオプションで定義された値を使用して、一致するプロパティを探します。
場合によっては、モバイルアプリケーションのキャンペーンエンドポイントがNmsServer_URLで定義されているエンドポイントと異なることがあります。 その場合は、「Launch_URL_キャンペーン」オプションでエンドポイントを定義します。 キャンペーンは、このオプションの値を使用して、Adobe Launchで一致するプロパティを探します。

   ![](assets/launch_4.png)

1. 「」の **[!UICONTROL Access Authorization]** セクションでモバイルアプリケーションの組織単位を変更して、このモバイルアプリケーションへのアクセスを特定の組織単位に制限できます。 詳しくは、このページを参照してください。

   ここでは、管理者は、ドロップダウンから副組織単位を選択して、副組織単位を割り当てることができます。

   ![](assets/launch_12.png)

1. キャンペーンとExperience Platformの起動を接続するには、をクリックし **[!UICONTROL Save]**&#x200B;ます。

1. モバイルアプリのステータスがからに変わったことを確認 **[!UICONTROL Ready to Configure]** し **[!UICONTROL Configured]**&#x200B;ます。

   Experience Platform起動キャンペーンの拡張機能で、キーが正常に設定されたことが示された場合は、キャンペーンでプロパティが正常に設定されたことを確認することもできます。

   ![](assets/launch_5.png)

1. この設定を有効にするには、変更をエクスペリエンスプラットフォームの起動に発行する必要があります。

   詳しくは、 [公開設定を参照してください](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration)。

## Adobe Campaignでのチャネル固有のアプリケーション設定 {#channel-specific-config}

これで、モバイルアプリケーションをキャンペーンでプッシュ通知またはアプリ内配信に使用できる状態になりました。 アプリ内メッセージをトリガーするイベントを作成したり、プッシュ証明書をアップロードしたりする必要がある場合に、さらに設定できるようになりました。

1. 詳細設定メニューで、/ **[!UICONTROL Administration]** /を選択し **[!UICONTROL Channels]** ま **[!UICONTROL Mobile app (AEP SDK)]**&#x200B;す。

1. Experience Platform Launchで作成および設定したモバイルアプリケーションを選択します。

1. 「 **[!UICONTROL Mobile application properties]** 」タブで、モバイルアプリでアプリ内メッセージに使用できるイベントを開始に追加できます。

1. イベントを設定するには、をクリックし **[!UICONTROL Create Element]**&#x200B;ます。

   ![](assets/launch_6.png)

1. 名前と説明を入力します。

   ![](assets/launch_7.png)

1. クリック **[!UICONTROL Add]** .

   アプリ内メッセージを作成する際に、「トリガー」タブでイベントを使用できるようになりました。 詳しくは、「アプリ内メッセージの [準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)」を参照してください。

1. モバイルアプリケーションダッシュボードの **[!UICONTROL Device-specific settings]** セクションで、各デバイスに対して、iOSの証明書やAndroidのサーバーキーなど、アプリケーションの詳細を指定します。

   証明書がアップロードされると、アップロードが成功したことを示すメッセージが表示され、証明書の有効期限が表示されます。

   >[!NOTE]
   >
   >Adobe Campaign標準で証明書が正常に追加されると、1つのAPNSプラットフォーム（実稼動またはサンドボックス）しかMCPNSアプリに追加できないので、設定を元に戻すことができなくなります。

   ![](assets/launch_8.png)

1. タブをクリックすると、 **[!UICONTROL Mobile application subscribers]** 購読者のリストと、通知をオプトアウトしたかどうかなど、これらの購読者に関する他の情報が表示されます。

## Adobe Experience Platform Launchアプリケーションの削除 {#delete-app}

Experience Platform起動アプリケーションの削除を元に戻すことはできません。

>[!CAUTION]
>
>Experience Platform起動アプリケーションの削除を元に戻すことはできません。

Experience Platform Launchアプリケーションを削除するには、モバイルプロパティの [削除の手順を実行します](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch)。

アプリケーションを削除した後、Adobe Campaignで、アプリケーションのプロパティのステータスが「起動時に削除されました」に正しく更新されているかどうかを確認します。

Adobe Campaignでアプリをクリックすると、「キャンペーンから削除」をクリックして、Adobe Campaignからこのアプリを完全に削除できます。

    ![](assets/launch_9.png)
