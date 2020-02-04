---
title: モバイルアプリケーションの設定
description: SDK V4またはExperience Platform SDKを使用して、プッシュ通知またはアプリ内メッセージを送信するAdobe Campaignの設定方法を確認します。
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
source-git-commit: e31e8c63fa94d190211c7a51e7f1091657c9f479

---


# モバイルアプリケーションの設定{#configuring-a-mobile-application}

使用するチャネルに応じてAdobe Campaign Standardで設定する必要があるモバイルアプリケーションで、プッシュ通知またはアプリ内メッセージが受信されます。

アプリ内メッセージとプッシュ通知を送信するには、Adobe Experience Platform SDKを利用して、モバイルアプリケーションをAdobe Campaignで設定する必要があります。 詳しくは、 [Adobe Experience Platform SDKの使用を参照してください](#using-adobe-experience-platform-sdk)。

Experience Cloud Mobile SDK V4またはExperience Platform SDKを利用してAdobe Campaignでモバイルアプリを設定したら、/メニューで管理者が設定する必要があ [!UICONTROL Administration] り [!UICONTROL Channels] ま [!UICONTROL Mobile app] す。

>[!IMPORTANT]
>
>プッシュ通知とアプリ内実装は、エキスパートユーザーが実行する必要があります。 支援が必要な場合は、アドビアカウントエグゼクティブまたはプロフェッショナルサービスパートナーにお問い合わせください。

モバイルアプリケーションの設定が完了すると、収集したPIIデータを取得して、データベースからプロファイルを作成または更新できます。 詳しくは、次の節を参照してください。モバイ [ルアプリケーションデータに基づくプロファイル情報の作成と更新](../../channels/using/updating-profile-with-mobile-app-data.md)。

Adobe Campaign Standardでのモバイル配信の一般的なガイドラインについては、このページを参照してくだ [さい](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Adobe Experience Platform SDKの使用 {#using-adobe-experience-platform-sdk}

>[!N注]
>
>Adobe Experience Platform SDKを使用してAdobe Campaign Standardでサポートされる様々なモバイル使用例について詳しくは、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)。

Experience Platform SDKアプリケーションでプッシュ通知とアプリ内メッセージを送信するには、モバイルアプリケーションをAdobe Experience Platform Experience Platform Launchで設定し、Adobe Campaignで設定する必要があります。 Experience Platform SDKを使用してモバイルアプリケーションを設定する手順について詳しくは、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)。

次の手順に従って設定を開始します。

1. チャネルにアクセスできることを確認し **[!UICONTROL Mobile]**ます。Adobe Campaignのプッシュ通知とアプリ内メッセージを参照してください。 そうでない場合は、アカウントチームにお問い合わせください。

   ![](assets/launch_1.png)

1. Mobileタイプのプロパティを作成して、Experience Platform Launchでモバイルアプリケーションを作成します。 詳しくは、 [Experience Platform Launchのドキュメントを参照](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) してください。
1. Experience Platform Launchにモバ **[!UICONTROL Adobe Campaign Standard]**イルアプリケーション用の拡張機能をインストールします。

   拡張機能について詳しくは、『 [Experience Platform Launch』ドキュメントを参照してください](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) 。

1. Adobe Launchでのアプリケーションのルールの設定については、「Launchでのアプリケ [ーションの設定」を参照してください。](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Adobe Campaign StandardでAdobe Launchアプリケーションを設定する方法については、「Adobe CampaignでのAdobe Launch [アプリケーションの設定」を参照してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign)。
1. モバイルアプリケーションの設定にチャネル固有の設定を追加します。詳しくは、Adobe Campaign [でのチャネル固有のアプリケーション設定を参照してください](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)。

   ![](assets/launch_2.png)
