---
title: モバイルアプリケーションの設定
description: Experience Platform SDKを使用してプッシュ通知またはアプリ内メッセージを送信するようにAdobe Campaignを設定する方法について説明します
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: 58b07f023f52e2bf4972b4a86bf4412f613f38da
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 2%

---

# モバイルアプリケーションの設定{#configuring-a-mobile-application}

## Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定 {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
> Adobe Experience Platform Launchは、Adobe Experience Platformのデータ収集テクノロジースイートとしてリブランドされました。 その結果、製品ドキュメント全体でいくつかの用語が変更されました。 用語の変更点の一覧については、[&#x200B; 次のドキュメント &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=ja){target="_blank"} を参照してください。

プッシュ通知とアプリ内実装は、エキスパートユーザーが実行する必要があります。 サポートが必要な場合は、Adobeアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。

Experience PlatformSDK アプリケーションでプッシュ通知およびアプリ内メッセージを送信するには、データ収集 UI でモバイルアプリケーションを設定し、Adobe Campaignで設定する必要があります。

モバイルアプリケーションを設定すると、収集した PII データを取得して、データベースからプロファイルを作成または更新できます。 詳しくは、この節 [&#x200B; モバイルアプリケーションデータに基づくプロファイル情報の作成と更新 &#x200B;](../../channels/using/updating-profile-with-mobile-app-data.md) を参照してください。

Adobe Experience Platform SDK を使用してAdobe Campaign Standardでサポートされている様々なモバイルユースケースについて詳しくは、この [&#x200B; ページ &#x200B;](../../administration/using/supported-mobile-use-cases.md) を参照してください。

設定を完了するには、次の手順を実行します。

1. Adobe Campaignで、次の場所にアクセスできることを確認します。
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   そうでない場合は、アカウントチームにお問い合わせください。

1. ユーザーがAdobe Campaign StandardとAdobe Experience Platformのタグで必要な権限を持っていることを確認します。

   * Adobe Campaign Standardで、IMS ユーザーが標準のユーザー/管理者製品プロファイルに属していることを確認します。 この手順を実行すると、ユーザーはAdobe Campaign Standardにログインし、Experience Platform SDK モバイルアプリページに移動して、データ収集 UI で作成したモバイルアプリプロパティを表示できます。

   * データ収集 UI で、IMS ユーザーがExperience Platform Launchの製品プロファイルに属していることを確認します。
この手順を使用すると、ユーザーはデータ収集 UI にログインして、プロパティを作成および表示できます。 データ収集 UI の製品プロファイルについて詳しくは、[&#x200B; 製品プロファイルの作成 &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/manage-permissions.html?lang=ja#gain-admin-rights-for-a-tags-product-profile) を参照してください。 製品プロファイルでは、会社やプロパティに対する権限は設定されていないはずですが、ユーザーは引き続きログインできます。

   拡張機能のインストール、アプリの公開、環境の設定などの追加タスクを実行するには、製品プロファイルで権限を設定する必要があります。

1. データ収集 UI で、**[!UICONTROL Mobile property]** を作成します。 詳しくは、[モバイルプロパティの設定](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property)を参照してください。

1. データ収集 UI で、「**[!UICONTROL Extensions]**」タブをクリックし、「**[!UICONTROL Catalog]**」に移動して **[!UICONTROL Adobe Campaign Standard]** 拡張機能を検索します。 詳しくは、[Adobe Campaign Standard](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard) を参照してください。

1. Campaign Standardでの場所のユースケースをサポートするには、データ収集 UI で **[!UICONTROL Places]** 拡張機能をインストールします。 この[ページ](https://developer.adobe.com/client-sdks/solution/places)を参照してください。

1. Adobe Campaign Standardで、データ収集 UI で作成したモバイルプロパティを設定します。 [Adobe CampaignでのAdobe Experience Platform Launch アプリケーションの設定 &#x200B;](../../administration/using/configuring-a-mobile-application.md#set-up-campaign) を参照してください。

1. モバイルアプリケーション設定にチャネル固有の設定を追加します。
詳しくは、[Adobe Campaign のチャネル固有のアプリケーション設定](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)を参照してください。

1. 必要に応じて、タグプロパティを削除できます。
詳しくは、[&#x200B; アプリケーションの削除 &#x200B;](../../administration/using/configuring-a-mobile-application.md#delete-app) を参照してください。

## Launch テクニカルワークフローからのモバイルアプリ AEPSDK の同期 {#aepsdk-workflow}

データ収集 UI でモバイルプロパティを作成および設定した後、**[!UICONTROL Sync Mobile app AEPSDK from Launch]** のテクニカルワークフローを使用して、Adobe Campaign Standardに読み込まれたタグモバイルプロパティを同期できるようになりました。

デフォルトでは、テクニカルワークフローは 15 分ごとに開始します。 必要に応じて、手動で再開できます。

1. Adobe Campaign Standardの詳細メニューで、**[!UICONTROL Administration]**/**[!UICONTROL Application Settings]**/**[!UICONTROL Workflows]** を選択します。
1. **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** ワークフローを開きます。

   ![](assets/launch_10.png)

1. **[!UICONTROL Scheduler]** アクティビティをクリックします。

1. 「**[!UICONTROL Immediate execution]**」を選択します。

   ![](assets/launch_11.png)

これで、ワークフローが再起動し、Adobe Campaign Standardに読み込まれたタグモバイルプロパティが同期されます。

## Adobe Campaignでのアプリケーションの設定 {#set-up-campaign}

Campaign でタグモバイルプロパティを使用するには、Adobe Campaignでこのプロパティも設定する必要があります。 Adobe Campaignで、IMS ユーザーが標準のユーザー/管理者製品プロファイルに属していることを確認します。

テクニカルワークフローが実行されるのを待ち、タグモバイルプロパティをAdobe Campaignに同期する必要があります。 その後、Adobe Campaignで設定できます。

Launch テクニカルワークフローからのモバイルアプリ AEPSDK の同期について詳しくは、この [&#x200B; 節 &#x200B;](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) を参照してください。

>[!NOTE]
>
>デフォルトでは、組織単位を「すべて」に設定した管理者は、モバイルアプリケーションを編集できます。

1. 詳細メニューから、**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (AEP SDK)]** を選択します。

   ![](assets/launch.png)

1. データ収集 UI で作成したモバイルアプリケーションを選択します。
その **[!UICONTROL Property Status]** は **[!UICONTROL Ready to configure]** であるべきです。

   >[!NOTE]
   >
   >デフォルトでは、データ収集 UI で作成されたモバイルアプリケーションのリストを取得するために、Campaign Standardは NmsServer_URL オプションで定義された値を使用して、一致するプロパティを検索します。
   >
   >場合によっては、モバイルアプリケーションの Campaign エンドポイントが、NmsServer_URL で定義されたものと異なる可能性があります。 その場合は、`Launch_URL_Campaign` オプションでエンドポイントを定義します。 Campaign はこのオプションの値を使用して、データ収集 UI で一致するプロパティを検索します。

   ![](assets/launch_4.png)

1. **[!UICONTROL Access Authorization]** セクションでモバイルアプリケーションの組織単位を変更して、このモバイルアプリケーションへのアクセスを特定の組織単位に制限できます。 詳しくは、このページを参照してください。

   ここでは、管理者はドロップダウンからサブ組織単位を選択して割り当てることができます。

   ![](assets/launch_12.png)

1. Campaign とAdobe Experience Platformのタグを連携させるには、「**[!UICONTROL Save]**」をクリックします。

1. モバイルアプリのステータスが **[!UICONTROL Ready to Configure]** から **[!UICONTROL Configured]** に変更されたことを確認します。

   Campaign 拡張機能でキーが正常に設定されたことが表示されたら、Campaign でプロパティが正常に設定されたことを確認することもできます。

   ![](assets/launch_5.png)

1. この設定を有効にするには、変更をデータ収集 UI で公開する必要があります。

   詳しくは、[Publishの設定を参照してください &#x200B;](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

## Adobe Campaignでのチャネル固有のアプリケーション設定 {#channel-specific-config}

これで、Campaign でプッシュ通知やアプリ内配信にモバイルアプリケーションを使用する準備が整いました。 必要に応じて、アプリ内メッセージをトリガーするイベントを作成したり、プッシュ証明書をアップロードしたりして、さらに設定できるようになりました。

1. 詳細メニューから、**[!UICONTROL Administration]**/**[!UICONTROL Channels]**/**[!UICONTROL Mobile app (AEP SDK)]** を選択します。

1. データ収集 UI で作成および設定したモバイルアプリケーションを選択します。

1. 「**[!UICONTROL Mobile application properties]**」タブで、モバイルアプリケーションで使用できるイベントをアプリ内メッセージに追加します。

1. イベントを設定するには、「**[!UICONTROL Create Element]**」をクリックします。

   ![](assets/launch_6.png)

1. 名前と説明を入力します。

   ![](assets/launch_7.png)

1. 「**[!UICONTROL Add]**」をクリックします。

   アプリ内メッセージを作成する際に、「トリガー」タブでイベントを使用できるようになりました。 詳しくは、[&#x200B; アプリ内メッセージの準備と送信 &#x200B;](../../channels/using/preparing-and-sending-an-in-app-message.md) を参照してください。

1. モバイルアプリケーションダッシュボードの「**[!UICONTROL Device-specific settings]**」セクションで、デバイスごとにアプリケーションの詳細を指定します。

   +++*  iOS用

     次のアプリケーション詳細を入力します。

      * **アプリ ID （iOS バンドル ID）**：バンドル ID について詳しくは、[Apple ドキュメント &#x200B;](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids){target="_blank"} を参照してください。
      * **iOS証明書（P8） ファイル**: .p8 認証キーをドラッグ&amp;ドロップします。 .p8 認証ファイルの生成方法については、[Apple開発者アカウント &#x200B;](https://developer.apple.com/account/ios/authkey/create){target="_blank"} を参照してください。
      * **キー ID**：キー ID について詳しくは、[Apple ドキュメント &#x200B;](https://developer.apple.com/help/account/manage-keys/get-a-key-identifier/){target="_blank"} を参照してください。
      * **iOS Team ID**:iOS Team ID について詳しくは、[Apple ドキュメント &#x200B;](https://developer.apple.com/help/account/manage-your-team/locate-your-team-id/){target="_blank"} を参照してください。

        ![](assets/mobile_app_ios_config.png)
   +++

   +++*  Android の場合

     次のアプリケーション詳細を入力します。

      * **アプリ ID （Android パッケージ名）**：パッケージ名について詳しくは、[Android ドキュメント &#x200B;](https://support.google.com/admob/answer/9972781?hl=en#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores){target="_blank"} を参照してください。
      * **Android キー（Json） ファイル**: .json 秘密鍵ファイルをドラッグ&amp;ドロップします。 .json 秘密鍵ファイルの生成方法については、[Firebase 開発者向けドキュメント &#x200B;](https://firebase.google.com/docs/admin/setup#initialize_the_sdk_in_non-google_environments){target="_blank"} を参照してください。

        ![](assets/mobile_app_android_config.png)
   +++

1. 証明書がアップロードされると、アップロードが成功したことを示すメッセージと証明書の有効期限が表示されます。

1. 「**[!UICONTROL Mobile application subscribers]**」タブをクリックして、購読者のリストと、これらの購読者に関するその他の情報（通知をオプトアウトしたかどうかなど）を表示します。

## アプリケーションの削除 {#delete-app}

>[!CAUTION]
>
>アプリケーションを削除すると、元に戻すことはできません。

アプリケーションを削除するには、[&#x200B; モバイルプロパティの削除 &#x200B;](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#deleting-mobile-properties-in-the-data-collection-ui) の手順を実行します。

アプリケーションを削除した後、Adobe Campaignで、アプリケーションのプロパティのステータスが Launch で正しく「削除済み」に更新されているかどうかを確認します。

Campaign でアプリをクリックすると、「Adobe Campaignから削除」をクリックして、Adobe Campaignからこのアプリを完全に削除できます。

![](assets/launch_9.png)
