---
title: Adobe Campaign Standardのプッシュ通知からの画像を表示
description: iOS デバイスでAdobe Campaignのプッシュ通知の画像を表示する方法を説明します
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 474c8002-4263-4617-9480-6a9b603bde8e
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 12%

---

# 画像とビデオの追加（iOS） {#image-push}

>[!NOTE]
>
>このドキュメントは、iOS デバイスにのみ適用されます。

このドキュメントでは、Adobe Campaign Standard iOSのプッシュ通知から画像を表示する方法を説明します。

## 手順 1：プッシュ通知の設定 {#set-up-push}

プッシュ通知は、Experience Platform SDK でサポートされています。

プッシュ通知を受け取るモバイルアプリケーションは、Adobe Campaign インターフェイスで管理者が設定する必要があります。

Adobe CampaignとAdobe Mobile Services の両方を設定すると、モバイルアプリケーションのデータをキャンペーンに使用できます。 詳しくは、この[ページ](../../administration/using/configuring-a-mobile-application.md)を参照してください。

Experience CloudSDK アプリケーションでプッシュ通知を送信するには、データ収集 UI でモバイルアプリを設定し、Adobe Campaignで設定する必要があります。 詳しくは、この[ページ](../../administration/using/configuring-a-mobile-application.md#channel-specific-config)を参照してください。

## 手順 2:Adobe Campaignでのプッシュ通知のカスタマイズ {#customize-push}

Adobe Campaign では、プッシュ通知のデザイン中に一連の詳細設定オプションにアクセスして、プッシュ通知を微調整することができます。

1. プッシュ通知を作成します。 詳しくは、この[ページ](../../channels/using/preparing-and-sending-a-push-notification.md)を参照してください。

1. プッシュ通知のコンテンツページから、「**[!UICONTROL Advanced options]**」セクションにアクセスします。

1. ファイルの URL を「**[!UICONTROL Rich media content URL]**」フィールドに入力します。
iOS 10 以降では、画像、gif、オーディオおよびビデオファイルを挿入できます。

   ![](assets/push_notif_advanced_6.png)

1. プッシュ通知をプレビューして保存します。

## 手順 3：モバイルアプリケーションコードの適応 {#mobile-app-code}

Adobe Campaignでプッシュ通知をカスタマイズした後、デバイスに画像を表示するようにモバイルアプリケーションを設定する必要があります。

>[!NOTE]
>
>アプリケーションが Objective-C の場合は、次の [ ドキュメント ](https://experienceleague.adobe.com/docs/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html?lang=ja) を参照してください。

アプリが [!DNL Swift] の場合は、次の手順に従います。

1. [!DNL Xcode] プロジェクトを開きます。

1. [!DNL Xcode] プロジェクトで、**[!UICONTROL File]**/**[!UICONTROL New]**/**[!UICONTROL Target]** を選択します。

1. 「**[!UICONTROL Notification Service Extension]**」を選択します。

   ![](assets/push_notif_advanced_12.png)

1. **NotificationService.swift** ファイルクラスが作成されていることを確認します。

1. このクラスを編集し、デフォルトコンテンツを次のコンテンツに置き換えます。
これにより、アプリケーションは、受信パラメーターとイメージ URL を処理し、解析して、ローカルにコピーしてから、プッシュ通知から表示することができます。

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

通知が送信されると、モバイルは次のペイロードを受け取ります。

画像 URL は、キー media-attachment-url でマッピングされます。 画像をダウンロードして表示するには、アプリケーションコードの観点から処理する必要があるキーと値のペアです。

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

## 手順 4：プッシュの送信をテスト {#test-send-push}

これで、上記の手順 2 で作成したアプリケーションと配信の作成をテストできます。 プッシュ通知の準備と送信について詳しくは、この [ ページ ](../../channels/using/preparing-and-sending-a-push-notification.md) を参照してください

![](assets/push_notif_advanced_34.png)
