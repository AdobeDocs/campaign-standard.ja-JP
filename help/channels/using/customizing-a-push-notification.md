---
title: プッシュ通知のカスタマイズ
seo-title: プッシュ通知のカスタマイズ
description: プッシュ通知のカスタマイズ
seo-description: 様々な高度なオプションを使用してプッシュ通知をカスタマイズする方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 8cf74CAD- b1ba-4aad-83bd-7289cb22d5f4
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: dc944c85-2059-46df- b396-676fe3617dd1
context-tags: delivery， mobileAppContent， back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Customizing a push notification{#customizing-a-push-notification}

Adobe Campaignでは、プッシュ通知を微調整するために、プッシュ通知を設計する際の高度なオプションのセットにアクセスできます。

As an expert user, to configure mobile applications in Adobe Campaign, refer to the following technote [Understanding Campaign Standard Push Notifications Payload Structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html).

![](assets/push_notif_advanced.png)

**関連コンテンツ:**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)

## Play a sound {#play-a-sound}

The function **[!UICONTROL Play a sound]** gives the application the ability to play sounds on your device with the delivery of a push notification, when the app isn't running.

サウンドはプッシュ通知のユーザーに通知され、より視認性を高めることができます。モバイルアプリにサウンドを含めるには:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. **[!UICONTROL Play a sound]** このフィールドに、通知の受信時にモバイルデバイスで再生される、拡張子なしのサウンドファイルのファイル名を入力します。

   For more information on supported media formats, refer to [Apple](https://support.apple.com/kb/PH16864?locale=en_US) and [Android](https://developer.android.com/guide/topics/media/media-formats.html) documentations.

   ![](assets/push_notif_advanced_7.png)

1. ファイルがモバイルアプリケーションのパッケージで定義されている場合、サウンドファイルは通知を配信するときに再生されます。それ以外の場合は、デバイスのデフォルトのサウンドが再生されます。

その後、ユーザーは、スマートフォンがミュートされていない場合にのみプッシュ通知とサウンドを受け取ります。

## Refresh the badge value {#refresh-the-badge-value}

バッジは、新しい未読情報の数がアプリアイコンに直接表示されます。ユーザーがアプリケーションから新しいコンテンツを開いたり読んだりすると、バッジの値はすぐに消えます。

デバイスで通知を受信すると、関連アプリのバッジ値を更新または追加できます。サーバー側からバッジ値を送信するには:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. バッジの値は整数である必要があり、更新する方法は異なります。

   * To refresh the badge, enter 0 in the **[!UICONTROL Value of the badge]** field. これにより、アプリケーションアイコンからバッジが削除されます。
   * To add a badge value, enter any number in the **[!UICONTROL Value of the badge]** field. ユーザーがプッシュ通知を受け取ると、この番号は自動的にバッジに表示されます。
   * フィールドが空の場合、または整数を含まない場合、バッジの値は変更されません。
   Here, we entered 1 in the **[!UICONTROL Value of the badge]** field to let the users know that they have a new information in their application.

   ![](assets/push_notif_advanced_8.png)

1. メッセージを送信すると、ユーザーはプッシュ通知を受け取り、そのアプリケーションに新しいバッジ値が自動的に表示されます。

   ![](assets/push_notif_advanced_1.png)

## Add a deeplink {#add-a-deeplink}

ディープリンクを使用すると、（Webブラウザーページを開くのではなく）アプリケーション内のコンテンツに直接ユーザーを移動できます。

ディープリンクには、カスタムアプリ内エクスペリエンスのパーソナライゼーションデータを含めることができます。例えば、受信者の名は、アプリケーションが指定するページ上で自動的に入力されます。

プッシュ通知にディープリンクを追加するには:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. **[!UICONTROL Add a deeplink]** フィールドにリンクを入力します。

   ![](assets/push_notif_advanced_3.png)

1. メッセージを送信した後、ユーザーはプッシュ通知を受け取り、通知を操作してアプリ内の特定のページにアクセスします（例えば、アクションボタンをタップまたはクリックする）。

   ![](assets/push_notif_advanced_4.png)

## Define an action {#define-an-action}

モバイルアプリケーションで使用できる場合はカテゴリIDを追加し、アクションボタンを表示することができます。これらの通知を使用すると、アプリケーション内で開かずに通知に応答して、通知に応じて様々なタスクを実行できます。

ユーザーの電話に表示されるダイアログには、続行する決断が必要です。ユーザーがいずれかのアクションを選択すると、関連付けられたタスクを実行できるように、アプリケーションに通知されます。

プッシュ通知にカテゴリを追加するには:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter a predefined category name in the **[!UICONTROL Category]** field to display actionable buttons when the push notification is received.

   モバイルアプリケーション開発者は、アプリケーションでカテゴリIDとボタンの予期される動作を定義する必要があります。For more on this, refer to the [Apple Developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (**Configuring Categories and Actionable Notifications** section) or the [Android Developer documentation](https://developer.android.com/guide/topics/ui/notifiers/notifications.html).

   ![](assets/push_notif_advanced_9.png)

1. プッシュ通知を送信すると、ユーザーはそれを受け取り、設定済みの実行可能なボタンでアクションを実行する必要があります。

   ![](assets/push_notif_actionable_buttons.png)

ユーザーのアクションに応じて、関連付けられたタスクを実行できるように、アプリケーションに通知が送信されます。

## Add custom fields {#add-custom-fields}

カスタムフィールドを使用すると、ペイロードでカスタムデータをキー値ペアの形式で渡すことができます。このオプションを使用して、定義済みのキー以外のデータをアプリケーションに渡すことができます。

そのためには、次の手順を実行します。

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. **[!UICONTROL Custom fields]** カテゴリで、ボタンを **[!UICONTROL Add an element]** クリックします。
1. Enter your **[!UICONTROL Keys]** then the **[!UICONTROL Values]** associated with each key.

   ![](assets/push_notif_advanced_10.png)

1. カスタムフィールドの処理と目的は、すべてモバイルアプリです。下のプッシュ通知では、アプリがカスタムフィールドを使用してプッシュ通知のボタンラベルを表示していました。

   ![](assets/push_notif_actionable_buttons.png)

## Add rich media content {#add-rich-media-content}

リッチメディアコンテンツを使用すると、ユーザーのエンゲージメントを向上させることができ、ユーザーがプッシュ通知を開くことができます。

通知自体に再生する画像、GIF、オーディオまたはビデオファイルを含めることができます。アプリケーションのユーザーはアプリケーションを開く必要がありません。

プッシュ通知にリッチメディアを含めるには:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter the URL of your file in the **[!UICONTROL Rich media content URL]** field for each format: iOS and Android.

   iOS10以降では、画像、GIF、オーディオ、ビデオファイルを挿入できます。以前のiOSバージョンでは、リッチコンテンツなしでプッシュ通知が表示されます。For detailed steps on how to display an image from an Adobe Campaign push notification on an iOS device, refer to this [page](https://helpx.adobe.com/campaign/kb/display-image-push.html).

   Androidの場合、画像のみ含めることができます。

   ![](assets/push_notif_advanced_6.png)

1. メッセージを送信すると、ユーザーはプッシュ通知を受け取り、リッチメディアコンテンツを表示できます。

   ![](assets/push_notif_advanced_2.png)

## Change the notification behavior for iOS {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

For iOS 10 or higher, two additional options are available in the **[!UICONTROL Advanced options]** section of push notifications: **[!UICONTROL Mutable content]** and **[!UICONTROL Content available]**.

**[!UICONTROL Mutable content]** このオプションをオンまたはオフにすると、/またはリッチメディアコンテンツURLが追加されると、プッシュ通知コンテンツがプッシュペイロードで送信され、iOS SDKで提供される通知サービスアプリケーション拡張によってプッシュ通知コンテンツを変更できるようになります。For more on this, refer to [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).

その後、モバイルアプリの拡張機能を活用して、Adobe Campaignから送信されたプッシュ通知のコンテンツまたは提示方法をさらに変更できます。例えば、ユーザーは次のオプションを利用できます。

* 暗号化された形式で配信されたデータの復号化
* 画像またはその他のメディアファイルをダウンロードし、通知に添付ファイルとして追加
* 通知の本文またはタイトルのテキストの変更
* 通知へのスレッド識別子の追加

**[!UICONTROL Content available]** このオプションをオンにすると、プッシュ通知を受信するとすぐにアプリケーションが呼び出されるようにプッシュペイロードでコンテンツの使用可能なフラグが送信されます。つまり、アプリケーションがペイロードデータにアクセスできるようになります。これは、アプリケーションがバックグラウンドで実行されていて、ユーザー操作（プッシュ通知をタップしている場合など）を必要としない場合でも動作しますが、アプリケーションが実行されていない場合はこの機能は適用されません。For more on this, refer to the [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Change the notification behavior for Android {#change-the-notification-behavior-for-android}

For Android, you can enter the URL of your file in the **Rich media content URL** field. iOSバージョンの場合、Android用には、GIF、オーディオ、ビデオファイルではなく、画像のみを含めることができます。

**[!UICONTROL High priority]** このチェックボックスを使用すると、プッシュ通知に高い優先度または通常の優先度を設定できます。For more information on message priority, refer to the [Google developer documentation](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message).

![](assets/push_notif_advanced_11.png)

