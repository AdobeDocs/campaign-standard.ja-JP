---
title: Adobe Campaign Standard のプッシュ通知からの画像の表示
description: iOSデバイスでAdobe Campaignのプッシュ通知から画像を表示する方法について説明します。
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cf43edcacbab9f1f33ce29e23c0957d8bfa64e7d
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 8%

---


# 画像とビデオのiOSへの追加 {#image-push}

>[!NOTE]
>
>このドキュメントはiOSデバイスにのみ適用されます。

このドキュメントでは、Adobe Campaign StandardiOSのプッシュ通知から画像を表示する方法を説明します。

## 手順1: プッシュ通知の設定 {#set-up-push}

プッシュ通知は、Experience PlatformSDKでサポートされています。

プッシュ通知を受信するモバイルアプリケーションは、Adobe Campaignインターフェイスの管理者が設定する必要があります。

Adobe CampaignとAdobe Mobile Servicesの両方を設定すると、モバイルアプリのデータをキャンペーンに使用できるようになります。 詳しくは、この[ページ](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)を参照してください。

Experience CloudSDKアプリケーションでプッシュ通知を送信するには、モバイルアプリがAdobe Experience Platform Launchで設定され、Adobe Campaignで設定されている必要があります。 詳しくは、この[ページ](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign)を参照してください。

## 手順2: Adobe Campaignでのプッシュ通知のカスタマイズ {#customize-push}

プッシュ通知を微調整するために、Adobe Campaignでは、プッシュ通知の設計時に一連の高度なオプションにアクセスできます。

1. プッシュ通知を作成します。 詳しくは、この[ページ](../../channels/using/preparing-and-sending-a-push-notification.md)を参照してください。

1. プッシュ通知コンテンツページから、セクションにアクセスし **[!UICONTROL Advanced options]** ます。

1. ファイルのURLを **[!UICONTROL Rich media content URL]** フィールドに入力します。
iOS 10以降では、画像、gif、オーディオおよびビデオファイルを挿入できます。

   ![](assets/push_notif_advanced_6.png)

1. プレビューし、プッシュ通知を保存します。

## 手順3: モバイルアプリケーションコードの適合 {#mobile-app-code}

Adobe Campaignでプッシュ通知をカスタマイズした後、デバイスに画像を表示するようにモバイルアプリを設定する必要があります。

>[!NOTE]
>
>アプリケーションがObjective-Cである場合は、次の [ドキュメントを参照してください](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html)。

アプリケーションがインストールされている場合 [!DNL Swift]は、次の手順に従います。

1. プ [!DNL Xcode] ロジェクトを開きます。

1. プ [!DNL Xcode] ロジェクトで、 **[!UICONTROL File]** / **[!UICONTROL New]** を選択し **[!UICONTROL Target]**&#x200B;ます。

1. 選択 **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. NotificationService.swift **ファイルクラスが作成されていることを確認します** 。

1. このクラスを編集し、デフォルトコンテンツを次の内容に置き換えます。
これにより、アプリケーションは、画像URLを持つ受信パラメーターを処理し、解析してローカルにコピーし、プッシュ通知から表示できます。

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

通知の送信中に、モバイルは以下のペイロードを受け取る必要があります。

画像URLは、キーmedia-attachment-urlでマップされます。 これは、画像をダウンロードして表示するためにアプリケーションコードの観点から処理する必要があるキー/値のペアです。

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## 手順4: プッシュの送信テスト {#test-send-push}

これで、上記の手順2で作成したアプリケーションと配信の構築をテストできます。 プッシュ通知の準備と送信について詳しくは、この [ページを参照してください](../../channels/using/preparing-and-sending-a-push-notification.md)。

![](assets/push_notif_advanced_34.png)

