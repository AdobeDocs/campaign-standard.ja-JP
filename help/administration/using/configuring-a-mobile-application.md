---
title: モバイルアプリケーションの設定
seo-title: モバイルアプリケーションの設定
description: モバイルアプリケーションの設定
seo-description: SDK V4またはExperience Platform SDKを使用してプッシュ通知またはアプリ内メッセージを送信するようにAdobe Campaignを設定する方法を確認します。
page-status-flag: 常にアクティブ化されていない
uuid: 63e1476a-7875-4f48- ba9e-97f1a0007e42
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: configuring- channels
discoiquuid: 2a14500f-5ede-4131-8b1a- b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44be801f7bcbb3a495744ecd5fa08250585ed8cb

---


# Configuring a mobile application{#configuring-a-mobile-application}

プッシュ通知またはアプリ内メッセージは、使用するチャネルに応じてAdobe Mobile Servicesで設定する必要があるモバイルアプリケーションで受信されます。

* アプリ内メッセージおよびプッシュ通知を送信するには、Adobe Experience Platform SDKを利用してモバイルアプリケーションをAdobe Campaignで設定する必要があります。["Adobe Experience Platform SDKの使用](#using-adobe-experience-platform-sdk)」を参照してください。

* プッシュ通知のみを送信するには、SDK V4を使用してAdobe CampaignとAdobe Mobile Serviceの統合を設定できます。See [Using SDK V4](#using-sdk-v4).

After your mobile applications are set up in Adobe Campaign by leveraging the Experience Cloud Mobile SDK V4 or Experience Platform SDK, they need to be configured by an administrator under the [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>プッシュ通知およびアプリ内実装は、エキスパートユーザーが実行する必要があります。サポートを受ける必要がある場合は、アドビのアカウント担当者またはプロフェッショナルサービスパートナーにお問い合わせください。

## Using Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Ntoo]
>
>To learn more on the different mobile use cases supported in Adobe Campaign Standard by using the Adobe Experience Platform SDKs, refer to this [page](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

プッシュ通知およびアプリ内メッセージをExperience Platform SDKアプリケーションと共に送信するには、モバイルアプリケーションをAdobe Experience Platform Experience Platform Experience Platform Launchで設定し、Adobe Campaignで設定する必要があります。For the detailed steps to configure your mobile application using Experience Platform SDK, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

設定を開始するには、次の手順に従います。

1. **[!UICONTROL Mobile]** チャネルにアクセスできることを確認します。Adobe Campaignのプッシュ通知およびアプリ内メッセージ。サポートされていない場合は、アカウントチームにお問い合わせください。

   ![](assets/launch_1.png)

1. Mobileタイプのプロパティを作成して、Experience Platform Launchでモバイルアプリケーションを作成します。For more info, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) documentation.
1. Install the **[!UICONTROL Adobe Campaign Standard]** extension for your mobile application in Experience Platform Launch:

   For more information on extensions, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) documentation.

1. Configure rules for your application in Adobe Launch, see [Configuring your application in Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configure your Adobe Launch application in Adobe Campaign Standard, see [Setting up your Adobe Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Add channel specific configuration to your Mobile Application set-up, see [Channel-specific application configuration in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Using SDK V4 {#using-sdk-v4}

プッシュ通知は、アプリ内でのSDK V4およびAdobe Experience Platform SDKでサポートされています。For the detailed steps to use push notifications with your mobile app, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

プッシュ通知を受信するモバイルアプリケーションは、Adobe Campaignインターフェイスの管理者が設定する必要があります。Adobe CampaignとAdobe Mobile Servicesの両方を設定することで、モバイルアプリのデータをキャンペーンに使用できます。

プッシュ通知を送信できるようにするには、以下を行う必要があります。

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. 次の場所でモバイルアプリケーションを設定します。

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign)を参照してください。
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices)を参照してください。

1. モバイルアプリケーションの具体的な設定を実行します。

   * Adobe Mobile Servicesインターフェイスからダウンロードした設定ファイルをモバイルアプリケーションにパッケージ化します。
   * Experience Cloud Mobile SDKをモバイルアプリケーションに統合します。

1. アプリケーションのサブスクライバーから収集するデータを定義します。Adobe Campaignデータベース内のプロファイルを持つモバイルアプリの購読者は、定義した条件に基づいて調整されます。

   For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. デバイス上でモバイルアプリケーションを起動してサインインして、セットアップが正常に完了していることを確認してください。通知の受信をオプトインしてください。
1. Then, in Adobe Campaign's advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. リストからモバイルアプリケーションを選択して、そのプロパティを表示します。購読情報が購読者リストの下に表示されます。

   ![](assets/push_notif_mobile_app.png)

1. To check the mobile applications a profile has subscribed to, in the **[!UICONTROL Profiles & Audiences > Profiles]** menu, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right. The mobile applications are listed in the **[!UICONTROL Mobile App Subscriptions]** tab.

   ![](assets/push_notif_subscriptions.png)