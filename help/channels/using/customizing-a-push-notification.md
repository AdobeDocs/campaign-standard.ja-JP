---
title: プッシュ通知のカスタマイズ
description: 様々な高度なオプションを使用してプッシュ通知をカスタマイズする方法について説明します。
page-status-flag: 非活性化の
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: プッシュ通知
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# プッシュ通知のカスタマイズ{#customizing-a-push-notification}

プッシュ通知を微調整するために、Adobe Campaignでは、プッシュ通知のデザイン中に一連の高度なオプションにアクセスできます。

エキスパートユーザーがAdobe Campaignでモバイルアプリケーションを設定するには、次のテクニカルノート「Understanding Campaign Standard Push Notifications Payload Structure [」を参照してください](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)。

![](assets/push_notif_advanced.png)

**関連コンテンツ：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)

## サウンドを再生 {#play-a-sound}

この機能を使 **[!UICONTROL Play a sound]** 用すると、アプリケーションが実行されていない場合に、プッシュ通知を配信して、デバイス上でサウンドを再生できます。

サウンドは、プッシュ通知をユーザーに通知し、ユーザーの視認性を高めます。 モバイルアプリにサウンドを含めるには：

1. プッシュ通知を開き、セクションにアクセス **[!UICONTROL Advanced options]** します。
1. このフィ **[!UICONTROL Play a sound]** ールドに、通知を受信したときにモバイルデバイスが再生するサウンドファイルのファイル名（拡張子なし）を入力します。

   サポートされるメディア形式について詳しくは、 [Apple](https://support.apple.com/kb/PH16864?locale=en_US) / [Androidのドキュメントを参照してください](https://developer.android.com/guide/topics/media/media-formats.html) 。

   ![](assets/push_notif_advanced_7.png)

1. ファイルがモバイルアプリケーションのパッケージで定義されている場合、サウンドファイルは通知の配信時に再生されます。 それ以外の場合は、デバイスのデフォルトのサウンドが再生されます。

ユーザーは、携帯電話がミュートされていない場合にのみ、プッシュ通知とサウンドを受信します。

## バッジの値を更新 {#refresh-the-badge-value}

バッジは、新しい未読情報の数をアプリアイコンに直接表示するために使用されます。 ユーザーがアプリケーションから新しいコンテンツを開くか読むと、バッジの値がすぐに消えます。

デバイスで通知を受け取ると、その通知を更新したり、関連アプリのバッジ値を追加したりできます。 サーバー側からバッジ値を送信するには：

1. プッシュ通知を開き、セクションにアクセス **[!UICONTROL Advanced options]** します。
1. バッジの値は整数である必要があり、異なる方法で更新できます。

   * バッジを更新するには、フィールドに「0」と入力 **[!UICONTROL Value of the badge]** します。 これにより、アプリケーションアイコンからバッジが削除されます。
   * バッジの値を追加するには、フィールドに任意の数を入力 **[!UICONTROL Value of the badge]** します。 この番号は、ユーザーがプッシュ通知を受け取るとすぐにバッジに自動的に表示されます。
   * フィールドが空であるか、整数を含まない場合、バッジの値は変更されません。
   ここでは、ユーザーがアプリケーシ **[!UICONTROL Value of the badge]** ョンに新しい情報を持っていることをユーザーに知らせるために、フィールドに「1」と入力します。

   ![](assets/push_notif_advanced_8.png)

1. メッセージを送信した後、ユーザーはプッシュ通知を受け取り、そのユーザーのアプリケーションは新しいバッジ値を自動的に表示します。

   ![](assets/push_notif_advanced_1.png)

## ディープリンクの追加 {#add-a-deeplink}

ディープリンクを使用すると、Webブラウザーページを開く代わりに、アプリケーション内のコンテンツにユーザーを直接移動できます。

ディープリンクには、カスタムのアプリ内エクスペリエンスのパーソナライゼーションデータを含めることができます。 例えば、受信者の名は、アプリが送信するページに自動的に入力されます。

プッシュ通知にディープリンクを追加するには：

1. プッシュ通知を開き、セクションにアクセス **[!UICONTROL Advanced options]** します。
1. フィールドにリンクを入力 **[!UICONTROL Add a deeplink]** します。

   ![](assets/push_notif_advanced_3.png)

1. メッセージを送信した後、ユーザーはプッシュ通知を受け取り、通知を操作して(例：「誘い文句（CTA：コールトゥアクション）」ボタンをタップまたはクリックする)、アプリ内の特定のページにアクセスします。

   ![](assets/push_notif_advanced_4.png)

## アクションの定義 {#define-an-action}

モバイルアプリケーションで使用できる場合はカテゴリIDを追加し、アクションボタンを表示できます。 これらの通知により、ユーザーは通知に応答して、アプリケーションを開いたり、アプリケーション内を移動したりすることなく、様々なタスクをより迅速に実行できます。

ユーザーの電話に表示されるダイアログでは、続行するかどうかを決定する必要があります。 ユーザーがアクションの1つを選択すると、関連するタスクを実行できるように、アプリケーションに通知されます。

プッシュ通知にカテゴリを追加するには：

1. プッシュ通知を開き、セクションにアクセス **[!UICONTROL Advanced options]** します。
1. プッシュ通知を受け取ったときに実行可能なボタンを表示す **[!UICONTROL Category]** るには、定義済みのカテゴリ名をフィールドに入力します。

   モバイルアプリケーション開発者は、カテゴリIDと、アプリケーションでのボタンの期待される動作を定義する必要があります。 詳しくは、 [Apple Developerドキュメント](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (「カテゴリとアクショ&#x200B;**ン可能な通知の設定」の節** )または [Android Developerドキュメントを参照して](https://developer.android.com/guide/topics/ui/notifiers/notifications.html)ください。

   ![](assets/push_notif_advanced_9.png)

1. プッシュ通知を送信した後、ユーザーはプッシュ通知を受け取り、以前に設定したアクション可能なボタンを使用してアクションを実行する必要があります。

   ![](assets/push_notif_actionable_buttons.png)

ユーザーのアクションに応じて、関連するタスクを実行できるように、アプリケーションに通知されます。

## 有効期限の追加 {#add-expiration-date}

>[!NOTE]
>
>これらの変更は、Campaign Standard 19.4リリース以降にのみ適用されます。

有効期限をプッシュ通知に設定すると、Apple([APNS](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns))またはAndroid([FCM](https://firebase.google.com/docs/cloud-messaging/concept-options))がメッセージを送信しなくなる特定の有効期限を設定できます。

プッシュ通知に有効期限を追加するには：

1. Check the **[!UICONTROL Expire message]** option.

   >[!NOTE]
   >
   >このオプションを **[!UICONTROL Expire message]** 選択すると、期間が自動的に0に設定されます。 値を変更しない場合、APNSとFCMの両方がメッセージの送信を直ちに試みます。 失敗した場合、メッセージは再送されません。

1. フィールド **[!UICONTROL Duration]** で、プッシュ通知の有効性を選択します。

   ![](assets/push_expiration.png)

1. プッシュ通知を送信した後、電話がオンになっていない、または信号がないためにユーザーがすぐに受信しなかった場合でも、プッシュは有効期限の時間帯内に送信されます。

プッシュ通知は、有効期限より前に送信されていない場合は破棄されます。

## カスタムフィールドの追加 {#add-custom-fields}

カスタムフィールドを使用すると、キーと値のペアの形式でペイロードにカスタムデータを渡すことができます。 このオプションは、事前定義されたキー以外の追加のデータをアプリケーションに渡す場合に使用できます。

これをおこなうには：

1. プッシュ通知を開き、セクションにアクセス **[!UICONTROL Advanced options]** します。
1. カテゴリ内 **[!UICONTROL Custom fields]** で、ボタンをクリック **[!UICONTROL Add an element]** します。
1. 各キーに関 **[!UICONTROL Keys]** 連付けら **[!UICONTROL Values]** れたを入力します。

   ![](assets/push_notif_advanced_10.png)

1. カスタムフィールドの処理と目的は、モバイルアプリによって完全に決まります。 以下のプッシュ通知では、アプリがカスタムフィールドを使用して、プッシュ通知のボタンラベルを表示しています。

   ![](assets/push_notif_actionable_buttons.png)

## リッチメディアコンテンツの追加 {#add-rich-media-content}

リッチメディアコンテンツを使用すると、ユーザーエンゲージメントが向上し、ユーザーはプッシュ通知を開く傾向が強くなります。

通知自体に再生または表示する画像、gif、オーディオまたはビデオファイルを含めることができます。 アプリを表示するためにアプリを開く必要はありません。

プッシュ通知にリッチメディアを含めるには：

1. プッシュ通知を開き、セクションにアクセス **[!UICONTROL Advanced options]** します。
1. 各形式のフィールドにファイルのURL **[!UICONTROL Rich media content URL]** を入力します。iOSとAndroid。

   iOS 10以降では、画像、GIF、オーディオおよびビデオファイルを挿入できます。 以前のバージョンのiOSでは、プッシュ通知はリッチコンテンツなしで表示されます。 iOSデバイスでAdobe Campaignのプッシュ通知から画像を表示する方法について詳しくは、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/display-image-push.html)。

   Androidの場合は、画像のみを含めることができます。

   ![](assets/push_notif_advanced_6.png)

1. メッセージを送信すると、ユーザーはプッシュ通知を受け取り、リッチメディアコンテンツを表示できます。

   ![](assets/push_notif_advanced_2.png)

## iOSの通知動作の変更 {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

iOS 10以降では、プッシュ通知のセクションに次の2つの追加オプシ **[!UICONTROL Advanced options]** ョンが用意されています。 **[!UICONTROL Mutable content]** と **[!UICONTROL Content available]**。

このオプシ **[!UICONTROL Mutable content]** ョンをオンにして、リッチメディアコンテンツURLが追加されると、可変コンテンツフラグがプッシュペイロードに送信され、iOS SDKで提供される通知サービスアプリケーション拡張によってプッシュ通知コンテンツを変更できます。 詳しくは、 [Apple開発者向けドキュメントを参照してください](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)。

その後、モバイルアプリの拡張機能を利用して、Adobe Campaignから送信される到着したプッシュ通知のコンテンツや表示をさらに変更できます。 例えば、ユーザーはこのオプションを次の目的で使用できます。

* 暗号化された形式で配信されたデータの復号化
* 画像または他のメディアファイルをダウンロードし、添付ファイルとして通知に追加する
* 通知の本文またはタイトルテキストの変更
* 通知へのスレッド識別子の追加

チェッ **[!UICONTROL Content available]** クすると、プッシュ通知を受け取るとすぐにアプリが起動するように、アプリがペイロードデータにアクセスできるように、コンテンツ使用可能フラグがプッシュペイロードに送信されます。 これは、アプリがバックグラウンドで実行され、ユーザーの操作（プッシュ通知のタップなど）が不要な場合でも機能しますが、アプリが実行されていない場合は適用されません。 For more on this, refer to the [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Androidの通知動作の変更 {#change-the-notification-behavior-for-android}

Androidの場合は、「リッチメディアコンテンツのURL」フィールドにフ **ァイルのURLを入力できます** 。 iOSバージョンでは、Androidでは画像のみを含めることができ、gif、オーディオ、ビデオの各ファイルは含めることができません。

このチ **[!UICONTROL High priority]** ェックボックスを使用すると、プッシュ通知の優先度を高く設定したり、通常に設定したりできます。 メッセージの優先順位の詳細については、 [Google開発者向けドキュメントを参照してください](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message)。

![](assets/push_notif_advanced_11.png)

