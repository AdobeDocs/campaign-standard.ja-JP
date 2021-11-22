---
title: モバイルアプリケーションの設定
description: SDK V4 またはExperience PlatformSDK を使用して、Adobe Campaignでプッシュ通知またはアプリ内メッセージを送信するように設定する方法を説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 6%

---

# モバイルアプリケーションの設定{#configuring-a-mobile-application}

## Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定 {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>プッシュ通知およびアプリ内実装は、エキスパートユーザーが実行する必要があります。 不明な点は、担当のAdobeアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

Experience PlatformSDK アプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリケーションをAdobe Experience PlatformExperience PlatformExperience Platform Launchで設定し、Adobe Campaignで設定する必要があります。

モバイルアプリケーションを設定したら、収集した PII データを取得して、データベースからプロファイルを作成または更新できます。 詳しくは、この節を参照してください。 [モバイルアプリケーションデータに基づくプロファイル情報の作成と更新](../../channels/using/updating-profile-with-mobile-app-data.md).

Adobe Experience Platform SDK を使用してAdobe Campaign Standardでサポートされる様々なモバイル使用例について詳しくは、こちらを参照してください [ページ](../../administration/using/supported-mobile-use-cases.md).

設定を完了するには、次の手順を実行します。

1. Adobe Campaignで、次にアクセスできることを確認します。
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   そうでない場合は、アカウントチームにお問い合わせください。

1. ユーザーがAdobe Campaign StandardおよびExperience Platform Launchで必要な権限を持っていることを確認します。
   * Adobe Campaign Standardで、IMS ユーザーが Standard User および Administrator 製品プロファイルに含まれていることを確認します。 この手順を使用すると、ユーザーはAdobe Campaign Standardにログインし、Experience PlatformSDK モバイルアプリページに移動して、Experience Platform Launchで作成したモバイルアプリのプロパティを表示できます。

   * Experience Platform Launchで、IMS ユーザーが製品プロファイルに含まれていることをExperience Platform Launchします。
この手順では、ユーザーはExperience Platform Launchにログインして、プロパティを作成および表示できます。 製品プロファイルの詳細については、「Experience Platform Launchプロファイルの作成」を参照してください。 製品プロファイルには、会社やプロパティに対する権限は設定されていませんが、ユーザーは引き続きログインできます。

   拡張機能のインストール、アプリの公開、環境の設定などの追加のタスクを完了するには、製品プロファイルに権限を設定する必要があります。

1. Experience Platform Launchで、 **[!UICONTROL Mobile property]**. 詳しくは、[モバイルプロパティの設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)を参照してください。

1. Experience Platform Launchで、 **[!UICONTROL Extensions]** タブ、移動 **[!UICONTROL Catalog]**&#x200B;を検索し、 **[!UICONTROL Adobe Campaign Standard]** 拡張子。 詳しくは、 [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. 場所の使用例をサポートするには、Campaign Standardで **[!UICONTROL Places]** 拡張機能と **[!UICONTROL Places Monitor]** 拡張子。
   * のインストール **[!UICONTROL Places]** Experience Platform Launchの拡張。 この[ページ](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html)を参照してください。
   * のインストール **[!UICONTROL Places Monitor]** Experience Platform Launchの拡張。 この[ページ](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)を参照してください。

1. Adobe Campaign Standard で、Experience Platform Launch で作成したモバイルプロパティを設定します。参照： [Adobe CampaignでのAdobe Experience Platform Launchアプリケーションの設定](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. モバイルアプリケーションの設定にチャネル固有の設定を追加します。詳しくは、[Adobe Campaign のチャネル固有のアプリケーション設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)を参照してください。

1. 必要に応じて、Experience Platform Launchプロパティを削除できます。
詳しくは、 [Experience Platform Launch・アプリケーションの削除](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Launch からのモバイルアプリ AEPSDK の同期テクニカルワークフロー {#aepsdk-workflow}

モバイルプロパティをExperience Platform Launchで作成および設定した後、 **[!UICONTROL Sync Mobile app AEPSDK from Launch]** テクニカルワークフローは、Adobe Campaign Standardで読み込まれたAdobeLaunch モバイルプロパティを同期するようになりました。

デフォルトでは、テクニカルワークフローは 15 分ごとに開始されます。 必要に応じて、手動で再起動できます。

1. Adobe Campaign Standardの詳細設定メニューで、「 」を選択します。 **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. を開きます。 **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** ワークフロー。

   ![](assets/launch_10.png)

1. をクリックします。 **[!UICONTROL Scheduler]** アクティビティ。

1. 「**[!UICONTROL Immediate execution]**」を選択します。

   ![](assets/launch_11.png)

これで、ワークフローが再起動し、Adobe Campaign Standardで読み込まれたAdobeLaunch モバイルプロパティが同期されます。

## Adobe CampaignでのAdobe Experience Platform Launchアプリケーションの設定 {#set-up-campaign}

Campaign でExperience Platform Launchモバイルプロパティを使用するには、Adobe Campaignでもこのプロパティを設定する必要があります。 Adobe Campaignで、IMS ユーザーが Standard User および Administrator 製品プロファイルに含まれていることを確認します。

テクニカルワークフローが実行され、Launch モバイルプロパティがAdobe Campaignに同期されるまで待つ必要があります。 その後、Adobe Campaignで設定できます。

Launch からのモバイルアプリ AEPSDK の同期テクニカルワークフローについて詳しくは、これを参照してください。 [セクション](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>デフォルトでは、組織単位が「すべて」に設定されている管理者は、モバイルアプリケーションを編集できます。

1. 詳細設定メニューから、 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. 「Experience Platform Launch」で作成したモバイルアプリケーションを選択します。
その **[!UICONTROL Property Status]** は、 **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >デフォルトでは、Campaign Standardは、AdobeLaunch で作成されたモバイルアプリケーションのリストを取得するために、 NmsServer_URL オプションで定義された値を使用して、一致するプロパティを検索します。
   >
   >場合によっては、モバイルアプリケーションの Campaign エンドポイントが NmsServer_URL で定義されたエンドポイントと異なることがあります。 その場合は、 Launch_URL_Campaign オプションでエンドポイントを定義します。 Campaign は、このオプションの値を使用して、Launch で一致するプロパティを検索します。Adobe

   ![](assets/launch_4.png)

1. モバイルアプリケーションの組織単位は、 **[!UICONTROL Access Authorization]** セクションを使用して、このモバイルアプリケーションへのアクセスを特定の組織単位に制限します。 詳しくは、このページを参照してください。

   ここでは、管理者がドロップダウンから選択して、サブ組織単位を割り当てることができます。

   ![](assets/launch_12.png)

1. Campaign とExperience Platform Launchの間で **[!UICONTROL Save]**.

1. モバイルアプリのステータスが **[!UICONTROL Ready to Configure]** から **[!UICONTROL Configured]**.

   Experience Platform Launchキャンペーン拡張機能でキーが正常に設定されたことが示されたら、Campaign でプロパティが正常に設定されたことを確認することもできます。

   ![](assets/launch_5.png)

1. この設定を有効にするには、変更をExperience Platform Launchで公開する必要があります。

   詳しくは、 [公開設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Adobe Campaignでのチャネル固有のアプリケーション設定 {#channel-specific-config}

これで、モバイルアプリケーションを Campaign でプッシュ通知やアプリ内配信に使用する準備が整いました。 必要に応じて、アプリ内メッセージをトリガーするイベントを作成したり、プッシュ証明書をアップロードしたりするために、さらに設定できるようになりました。

1. 詳細設定メニューから、 **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. 作成し、「Experience Platform Launch」で設定したモバイルアプリケーションを選択します。

1. の **[!UICONTROL Mobile application properties]** 「 」タブを使用して、モバイルアプリケーションでアプリ内メッセージに使用できるイベントの追加を開始できます。

1. イベントを設定するには、 **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. 名前と説明を入力します。

   ![](assets/launch_7.png)

1. 「**[!UICONTROL Add]**」をクリックします。

   イベントは、アプリ内メッセージの作成時に「トリガー」タブで使用できるようになりました。 詳しくは、 [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. 内 **[!UICONTROL Device-specific settings]** モバイルアプリケーションダッシュボードの「 」セクションで、各デバイスに対して、iOSの証明書や Android のサーバーキーなど、アプリケーションの詳細を指定します。

   証明書がアップロードされると、アップロードが成功したことを示すメッセージが表示され、証明書の有効期限が表示されます。

   >[!NOTE]
   >
   >Adobe Campaign Standardで証明書が正常に追加されると、設定を元に戻すことはできなくなります。MCPNS アプリに追加できる APNS プラットフォームは 1 つ（実稼動またはサンドボックス）だけです。

   ![](assets/launch_8.png)

1. 次をクリック： **[!UICONTROL Mobile application subscribers]** 「 」タブを使用して、購読者のリストと、これらの購読者に関するその他の情報（通知をオプトアウトしたかどうかなど）を確認できます。

## Adobe Experience Platform Launchアプリケーションの削除 {#delete-app}

Experience Platform Launchアプリの削除を元に戻すことはできません。

>[!CAUTION]
>
>Experience Platform Launchアプリの削除を元に戻すことはできません。

Experience Platform Launch・アプリケーションを削除するには、 [モバイルプロパティの削除](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

アプリケーションを削除した後、Adobe Campaignで、アプリケーションのプロパティのステータスが Launch で正しく「削除済み」に更新されているかどうかを確認します。

Adobe Campaignでアプリをクリックすることで、「 Campaign から削除」をクリックして、Adobe Campaignからこのアプリを完全に削除するよう選択できます。

![](assets/launch_9.png)
