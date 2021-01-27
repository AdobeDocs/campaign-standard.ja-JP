---
solution: Campaign Standard
product: campaign
title: プッシュ通知のカスタマイズ
description: 様々な詳細設定オプションを使用してプッシュ通知をカスタマイズする方法について説明します。
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 98%

---


# プッシュ通知のカスタマイズ{#customizing-a-push-notification}

Adobe Campaign では、プッシュ通知のデザイン中に一連の詳細設定オプションにアクセスして、プッシュ通知を微調整することができます。

エキスパートユーザーとして、Adobe Campaign でモバイルアプリケーションを設定する場合は、[Campaign Standard プッシュ通知のペイロード構造について](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/push-notifications/push-payload.translate.html)を参照してください。

![](assets/push_notif_advanced.png)

**関連するコンテンツ：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)

## サウンドの再生 {#play-a-sound}

「**[!UICONTROL Play a sound]**」機能を使用すると、デバイス上でアプリケーションが実行されていなくても、プッシュ通知を配信してサウンドを再生できます。

サウンドにより、プッシュ通知の受信がユーザーにわかり、状況を把握しやすくなります。モバイルアプリにサウンドを組み込むには、次の手順に従います。

1. プッシュ通知を開き、「**[!UICONTROL Advanced options]**」セクションにアクセスします。
1. 通知を受信したときにモバイルデバイスが再生するサウンドファイルのファイル名（拡張子なし）を「**[!UICONTROL Play a sound]**」フィールドに入力します。

   サポートされるメディア形式について詳しくは、[Apple](https://support.apple.com/kb/PH16864?locale=en_US) および [Android](https://developer.android.com/guide/topics/media/media-formats) のドキュメントを参照してください。

   ![](assets/push_notif_advanced_7.png)

1. サウンドファイルがモバイルアプリケーションのパッケージに定義されている場合は、そのファイルが通知の配信時に再生されます。それ以外の場合は、デバイスのデフォルトのサウンドが再生されます。

プッシュ通知とサウンドは、電話がミュートされていない場合にのみ受信されます。

## バッジ値の更新 {#refresh-the-badge-value}

バッジは、新しい未読情報の数をアプリケーションアイコンに直接表示するために使用します。バッジの値は、ユーザーがアプリケーションから新しいコンテンツを開くまたは読むとすぐに消えます。

デバイスで通知を受け取ると、関連アプリのバッジ値を更新したり追加したりできます。サーバー側からバッジ値を送信するには、次の手順に従います。

1. プッシュ通知を開き、「**[!UICONTROL Advanced options]**」セクションにアクセスします。
1. バッジ値は整数にする必要があり、様々な方法で更新できます。

   * バッジ値を更新するには、「**[!UICONTROL Value of the badge]**」フィールドに 0 を入力します。そうすると、アプリケーションアイコンからバッジが削除されます。
   * バッジ値を追加するには、「**[!UICONTROL Value of the badge]**」フィールドに任意の数値を入力します。この数値は、ユーザーがプッシュ通知を受け取るとすぐに、バッジに自動的に表示されます。
   * フィールドに整数が入力されていない場合、バッジ値は変更されません。

   下の例では、アプリケーションに新しい情報が入力されたことをユーザーに知らせるために、「**[!UICONTROL Value of the badge]**」フィールドに 1 を入力しています。

   ![](assets/push_notif_advanced_8.png)

1. メッセージを送信すると、ユーザーはプッシュ通知を受け取り、アプリケーションが新しいバッジ値を自動的に表示します。

   ![](assets/push_notif_advanced_1.png)

## ディープリンクの追加 {#add-a-deeplink}

ディープリンクを使用すると、（Web ブラウザーページを開くのではなく）ユーザーをアプリケーション内のコンテンツに直接移動させることができます。

ディープリンクにパーソナライゼーションデータを組み込んで、カスタムのアプリ内エクスペリエンスを実現することができます。例えば、アプリケーションで移動先のページに受信者の名を自動的に入力するといったことが可能です。

プッシュ通知にディープリンクを追加するには、次の手順に従います。

1. プッシュ通知を開き、「**[!UICONTROL Advanced options]**」セクションにアクセスします。
1. 「**[!UICONTROL Add a deeplink]**」フィールドにリンクを入力します。

   ![](assets/push_notif_advanced_3.png)

1. メッセージを送信すると、ユーザーはプッシュ通知を受け取り、CTA（行動喚起）ボタンをタップまたはクリックするなど、通知を操作して、アプリ内の特定のページにアクセスします。

   ![](assets/push_notif_advanced_4.png)

## アクションの定義 {#define-an-action}

モバイルアプリケーションで使用可能な場合は、カテゴリ ID を追加して、アクションボタンを表示できます。これらの通知により、ユーザーは、アプリケーションを開いたりアプリケーション内を移動したりせずに、通知に応じて様々なタスクをより迅速に実行できます。

ユーザーの電話に表示されるダイアログでは、操作を続行するかどうかを決定する必要があります。ユーザーがいずれかのアクションを選択すると、関連するタスクをアプリケーションが実行できるように、システムがアプリケーションに通知します。

プッシュ通知にカテゴリを追加するには、次の手順に従います。

1. プッシュ通知を開き、「**[!UICONTROL Advanced options]**」セクションにアクセスします。
1. プッシュ通知を受け取ったときに実行可能なボタンを表示するには、定義済みのカテゴリ名を「**[!UICONTROL Category]**」フィールドに入力します。

   モバイルアプリケーション開発者は、カテゴリ ID と想定されるボタン動作をアプリケーションに定義する必要があります。詳しくは、[Apple 開発者向けドキュメント](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html)（**Configuring Categories and Actionable Notifications** の節）または [Android 開発者向けドキュメント](https://developer.android.com/guide/topics/ui/notifiers/notifications.html)を参照してください。

   ![](assets/push_notif_advanced_9.png)

1. プッシュ通知を送信すると、ユーザーがそれを受信し、事前に設定されてい実行可能なボタンを使用してアクションを実行する必要があります。

   ![](assets/push_notif_actionable_buttons.png)

ユーザーのアクションに応じて、関連するタスクを実行できるようにアプリケーションは通知を受け取ります。

## 有効期限の追加 {#add-expiration-date}

プッシュ通知に有効期限を設定すると、Apple（[APNS](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns)）または Android（[FCM](https://firebase.google.com/docs/cloud-messaging/concept-options)）からメッセージが送信されなくなる特定の有効期限を設定できます。

プッシュ通知に有効期限を追加するには、次の手順に従います。

1. **[!UICONTROL Expire message]**&#x200B;オプションを確認します。**[!UICONTROL Expire message]**&#x200B;オプションを選択すると、期間が自動的に0に設定されます。 値を変更しない場合、APNS も FCM もメッセージの送信を直ちに試みます。失敗した場合、メッセージは再送信されません。

1. 「**[!UICONTROL Duration]**」フィールドで、プッシュ通知の有効期限を選択します。

   ![](assets/push_expiration.png)

1. プッシュ通知を送信すると、電話がオンになっていない、信号がないなどの理由でユーザーがすぐにはプッシュ通知を受信しなかった場合でも、有効期限内にプッシュが送信されます。

プッシュ通知は、有効期限より前に送信されなかった場合は破棄されます。

## カスタムフィールドの追加 {#add-custom-fields}

カスタムフィールドを使用すると、キーと値のペアの形式でペイロードにカスタムデータを格納して渡すことができます。このオプションは、事前に定義されたキー以外の追加データをアプリケーションに渡す場合に使用できます。

それには、次の手順に従います。

1. プッシュ通知を開き、「**[!UICONTROL Advanced options]**」セクションにアクセスします。
1. 「**[!UICONTROL Custom fields]**」カテゴリで「**[!UICONTROL Add an element]**」ボタンをクリックします。
1. 「**[!UICONTROL Keys]**」を入力し、各キーに関連付けられている「**[!UICONTROL Values]**」を入力します。

   ![](assets/push_notif_advanced_10.png)

1. カスタムフィールドの扱い方と目的はモバイルアプリによって異なります。以下のプッシュ通知では、アプリがカスタムフィールドを使用して、プッシュ通知のボタンラベルを表示しています。

   ![](assets/push_notif_actionable_buttons.png)

## リッチメディアコンテンツの追加 {#add-rich-media-content}

リッチメディアコンテンツを使用すると、より優れたユーザーエンゲージメントが可能になり、プッシュ通知の開封度が向上します。

通知自体で再生または表示する画像、gif、オーディオまたはビデオのファイルを組み込むことができます。リッチメディアを表示するために、それ用のアプリケーションを開く必要はありません。

プッシュ通知にリッチメディアを組み込むには、次の手順に従います。

1. プッシュ通知を開き、「**[!UICONTROL Advanced options]**」セクションにアクセスします。
1. iOS と Android 形式ごとに、「**[!UICONTROL Rich media content URL]**」フィールドにファイルの URL を入力します。

   iOS 10 以降では、画像、gif、オーディオおよびビデオのファイルを挿入できます。それ以前の iOS バージョンでは、プッシュ通知はリッチコンテンツなしで表示されます。iOS デバイスで Adobe Campaign のプッシュ通知内の画像を表示する方法について詳しくは、[こちらのページ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/push-notifications/image-push-notification.translate.html)を参照してください。

   Android の場合は、画像のみを組み込むことができます。

   ![](assets/push_notif_advanced_6.png)

1. メッセージを送信すると、ユーザーはプッシュ通知を受け取り、リッチメディアコンテンツを表示できます。

   ![](assets/push_notif_advanced_2.png)

## 通知動作の変更（iOS の場合） {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

iOS 10 以降では、プッシュ通知の「**[!UICONTROL Advanced options]**」セクションで「**[!UICONTROL Mutable content]**」と「**[!UICONTROL Content available]**」の 2 つの追加オプションが使用可能でます。

「**[!UICONTROL Mutable content]**」オプションをオンにした場合や、リッチメディアコンテンツ URL を追加した場合、可変コンテンツフラグがプッシュペイロードで送信され、iOS SDK で提供される通知サービスアプリケーション拡張機能でプッシュ通知コンテンツを変更できるようになります。詳しくは、[Apple 開発者向けドキュメント](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)を参照してください。

この場合、モバイルアプリ拡張機能を利用して、Adobe Campaign から送信されて着信したプッシュ通知のコンテンツや表示をさらに変更することができます。例えば、ユーザーはこのオプションを利用して、以下をおこなうことができます。

* 暗号化された形式で配信されたデータを復号化する
* ダウンロードした画像または他のメディアファイルを添付ファイルとして通知に追加する
* 通知の本文またはタイトルテキストを変更する
* 通知にスレッド識別子を追加する

「**[!UICONTROL Content available]**」をオンにすると、コンテンツ使用可能フラグがプッシュペイロードで送信されるようになります。その結果、プッシュ通知を受け取るとすぐにアプリが起動されて、ペイロードデータにアクセスできるようになります。この動作は、アプリがバックグラウンドで実行されていてユーザーからの操作（プッシュ通知のタップなど）が不要な場合でも機能しますが、アプリが実行されていない場合は当てはまりません。詳しくは、[Apple 開発者向けドキュメント](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)を参照してください。

## 通知動作の変更（Android の場合） {#change-the-notification-behavior-for-android}

Android の場合は、「**Rich media content URL**」フィールドにファイルの URL を入力できます。Android では画像のみを含めることができます。iOS バージョンのように gif、オーディオ、ビデオのファイルは含めることはできません。

「**[!UICONTROL High priority]**」チェックボックスでは、プッシュ通知の優先度を高くするかどうかを設定できます。メッセージの優先度について詳しくは、[Google 開発者向けドキュメント](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message)を参照してください。

![](assets/push_notif_advanced_11.png)
