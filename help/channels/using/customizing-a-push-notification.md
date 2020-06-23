---
title: プッシュ通知のカスタマイズ
description: 様々な高度なオプションを使用してプッシュ通知をカスタマイズする方法について説明します。
page-status-flag: never-activated
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d4ac80810a77c0a6b512b3ed4c925fa0fb8a219c
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 1%

---


# プッシュ通知のカスタマイズ{#customizing-a-push-notification}

プッシュ通知を微調整するために、Adobe Campaignでは、プッシュ通知の設計時に一連の高度なオプションにアクセスできます。

エキスパートユーザーとして、Adobe Campaignでモバイルアプリケーションを設定するには、次のテクノ [ト『Campaign Standardプッシュ通知ペイロード構造について](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)』を参照してください。

![](assets/push_notif_advanced.png)

**関連コンテンツ：**

* [プッシュ通知レポート](../../reporting/using/push-notification-report.md)
* [ワークフロー内でのプッシュ通知の送信](../../automating/using/push-notification-delivery.md)

## サウンドを再生 {#play-a-sound}

この機能 **[!UICONTROL Play a sound]** により、アプリケーションが実行されていない場合に、プッシュ通知の配信を使用して、デバイス上でサウンドを再生できます。

サウンドは、プッシュ通知をユーザーに通知し、ユーザーの視認性を高めます。 モバイルアプリにサウンドを含めるには：

1. プッシュ通知を開き、セク **[!UICONTROL Advanced options]** ションにアクセスします。
1. この **[!UICONTROL Play a sound]** フィールドに、通知を受信したときにモバイルデバイスが再生するサウンドファイルのファイル名（拡張子なし）を入力します。

   サポートされるメディア形式について詳しくは、 [Apple](https://support.apple.com/kb/PH16864?locale=en_US) および [Androidのドキュメントを参照してください](https://developer.android.com/guide/topics/media/media-formats) 。

   ![](assets/push_notif_advanced_7.png)

1. サウンドファイルがモバイルアプリケーションのパッケージに定義されている場合、サウンドファイルは通知の配信時に再生されます。 それ以外の場合は、デバイスのデフォルトのサウンドが再生されます。

その後、ユーザーは、電話がミュートになっていない場合にのみ、プッシュ通知とサウンドを受信します。

## バッジ値を更新します {#refresh-the-badge-value}

新しい未読情報の数をアプリアイコンに直接表示するには、バッジを使用します。 バッジの値は、ユーザーがアプリケーションから新しいコンテンツを開くか読むとすぐに消えます。

デバイスで通知を受け取ると、関連アプリのバッジ値を更新または追加できます。 サーバー側からバッジ値を送信するには：

1. プッシュ通知を開き、セク **[!UICONTROL Advanced options]** ションにアクセスします。
1. バッジの値は整数にする必要があり、様々な方法で更新できます。

   * バッジを更新するには、フィー **[!UICONTROL Value of the badge]** ルドに「0」と入力します。 これにより、アプリケーションアイコンからバッジが削除されます。
   * バッジ値を追加するには、フィールドに任意の数値を入力し **[!UICONTROL Value of the badge]** ます。 この番号は、ユーザーがプッシュ通知を受け取るとすぐにバッジに自動的に表示されます。
   * フィールドが空であるか、整数を含まない場合、バッジの値は変更されません。
   ここで、ユーザーにアプリケーションに新しい情報が入力されたことを知らせるために、 **[!UICONTROL Value of the badge]** フィールドに「1」と入力します。

   ![](assets/push_notif_advanced_8.png)

1. メッセージを送信した後、ユーザーはプッシュ通知を受け取り、そのユーザーのアプリケーションは新しいバッジ値を自動的に表示します。

   ![](assets/push_notif_advanced_1.png)

## 追加欠陥 {#add-a-deeplink}

ディープリンクを使用すると、（Webブラウザーページを開く代わりに）アプリケーション内のコンテンツにユーザーを直接移動できます。

ディープリンクには、カスタムのアプリ内エクスペリエンスのためのパーソナライズデータを含めることができます。 例えば、受信者の名は、アプリが指示するページに自動的に入力されます。

プッシュ通知にディープリンクを追加するには：

1. プッシュ通知を開き、セク **[!UICONTROL Advanced options]** ションにアクセスします。
1. フィールドにリンクを入力し **[!UICONTROL Add a deeplink]** ます。

   ![](assets/push_notif_advanced_3.png)

1. メッセージを送信した後、ユーザーはプッシュ通知を受け取り、通知を操作して（例：「行動喚起」ボタンをタップまたはクリックする）、アプリ内の特定のページにアクセスします。

   ![](assets/push_notif_advanced_4.png)

## アクションの定義 {#define-an-action}

モバイルアプリケーションでカテゴリIDが使用可能な場合はそれを追加し、アクションボタンを表示します。 これらの通知により、アプリケーションを開いたり、アプリケーション内を移動したりせずに、通知に応じて異なるタスクを迅速に実行できます。

ユーザーの電話に表示されるダイアログでは、続行するかどうかの決定が必要です。 ユーザがアクションの1つを選択すると、関連するタスクを実行できるように、アプリケーションに通知します。

プッシュ通知にカテゴリを追加するには：

1. プッシュ通知を開き、セク **[!UICONTROL Advanced options]** ションにアクセスします。
1. 定義済みのカテゴリ名を **[!UICONTROL Category]** フィールドに入力し、プッシュ通知を受け取ったときに実行可能なボタンを表示します。

   モバイルアプリケーション開発者は、カテゴリIDと、アプリケーションでのボタンの予期される動作を定義する必要があります。 詳しくは、 [Apple Developerドキュメント](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (**カテゴリの設定と実行可能な通知** )または [Android開発者ドキュメントを参照してください](https://developer.android.com/guide/topics/ui/notifiers/notifications.html)。

   ![](assets/push_notif_advanced_9.png)

1. ユーザーは、プッシュ通知を送信した後に受信し、以前に設定した対応可能なボタンを使用して対応を行う必要があります。

   ![](assets/push_notif_actionable_buttons.png)

ユーザーのアクションに応じて、関連するタスクを実行できるように、アプリに通知されます。

## 有追加効期限 {#add-expiration-date}

有効期限をプッシュ通知に設定すると、メッセージがApple([APNS](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns))またはAndroid([FCM](https://firebase.google.com/docs/cloud-messaging/concept-options))から送信されなくなる特定の有効期限を設定できます。

プッシュ通知に有効期限を追加するには：

1. オプションをチェックし **[!UICONTROL Expire message]** ます。

   >[!NOTE]
   >
   >この **[!UICONTROL Expire message]** オプションを選択すると、期間が自動的に0に設定されます。 値を変更しない場合、APNSとFCMの両方がメッセージの送信を直ちに試みます。 失敗した場合、メッセージは再送されません。

1. フィールドで、プッシュ通知の有効性を選択し **[!UICONTROL Duration]** ます。

   ![](assets/push_expiration.png)

1. プッシュ通知を送信した後、電話がオンになっていない、または信号がないことが原因でユーザーがすぐにプッシュ通知を受信しなかった場合、有効期限の時間帯内にプッシュが送信されます。

有効期限より前にプッシュ通知が送信されていない場合は、破棄されます。

## 追加カスタムフィールド {#add-custom-fields}

カスタムフィールドを使用すると、キーと値のペアの形式でペイロード内のカスタムデータを渡すことができます。 このオプションは、事前定義されたキー以外の追加のデータをアプリケーションに渡す場合に使用できます。

これをおこなうには：

1. プッシュ通知を開き、セク **[!UICONTROL Advanced options]** ションにアクセスします。
1. カテゴリで、 **[!UICONTROL Custom fields]** ボタンをクリックし **[!UICONTROL Add an element]** ます。
1. キーを入力 **[!UICONTROL Keys]** し、各キーに **[!UICONTROL Values]** 関連付けられているを入力します。

   ![](assets/push_notif_advanced_10.png)

1. カスタムフィールドの処理と目的は、モバイルアプリに完全に依存します。 以下のプッシュ通知では、アプリでカスタムフィールドを使用して、プッシュ通知のボタンラベルを表示しています。

   ![](assets/push_notif_actionable_buttons.png)

## リ追加ッチメディアコンテンツ {#add-rich-media-content}

リッチメディアコンテンツを使用すると、より優れたユーザーエンゲージメントが可能になり、ユーザーはプッシュ通知を開く傾向が強くなります。

通知自体で再生または表示する画像、gif、オーディオまたはビデオファイルを含めることができます。 アプリを表示するために、アプリを開く必要はありません。

プッシュ通知にリッチメディアを含めるには：

1. プッシュ通知を開き、セク **[!UICONTROL Advanced options]** ションにアクセスします。
1. 各形式の **[!UICONTROL Rich media content URL]** フィールドにファイルのURLを入力します。 iOSとAndroid。

   iOS 10以降では、画像、gif、オーディオおよびビデオファイルを挿入できます。 以前のiOSバージョンでは、プッシュ通知はリッチコンテンツなしで表示されます。 iOSデバイスでAdobe Campaignのプッシュ通知から画像を表示する方法について詳しくは、この [ページを参照してください](https://helpx.adobe.com/campaign/kb/display-image-push.html)。

   Androidでは、画像のみを含めることができます。

   ![](assets/push_notif_advanced_6.png)

1. メッセージを送信した後、ユーザーはプッシュ通知を受け取り、リッチメディアコンテンツを表示できます。

   ![](assets/push_notif_advanced_2.png)

## iOSの通知動作の変更 {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

iOS 10以降では、プッシュ通知の **[!UICONTROL Advanced options]** セクションに、次の2つの追加オプションがあります。 **[!UICONTROL Mutable content]** と **[!UICONTROL Content available]**。

この **[!UICONTROL Mutable content]** オプションをオンにした場合、またはリッチメディアコンテンツURLが追加された場合、可変コンテンツフラグはプッシュペイロードに送信され、iOS SDKで提供される通知サービスアプリケーション拡張によってプッシュ通知コンテンツを変更できます。 For more on this, refer to [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).

その後、モバイルアプリの拡張機能を利用して、Adobe Campaignから送信される着信プッシュ通知のコンテンツや表示をさらに変更できます。 例えば、ユーザーはこのオプションを次の目的に利用できます。

* 暗号化された形式で配信されたデータの復号化
* 画像または他のメディアファイルをダウンロードし、添付ファイルとして通知に追加する
* 通知の本文またはタイトルテキストの変更
* 通追加知のスレッド識別子

チェック **[!UICONTROL Content available]** すると、コンテンツ使用可能フラグがプッシュペイロードに送信され、アプリがプッシュ通知を受け取るとすぐに起動されること、つまりアプリがペイロードデータにアクセスできることを確認します。 これは、アプリがバックグラウンドで実行されていて、ユーザーの操作（プッシュ通知のタップなど）が不要な場合でも機能しますが、アプリが実行されていない場合は適用されません。 For more on this, refer to the [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Androidの通知動作の変更 {#change-the-notification-behavior-for-android}

Androidの場合は、「 **リッチメディアコンテンツのURL** 」フィールドにファイルのURLを入力できます。 iOSバージョンでは、Androidでは画像のみを含めることができますが、gif、オーディオ、ビデオファイルは含めることができません。

この **[!UICONTROL High priority]** チェックボックスを使用すると、プッシュ通知の優先度を高く設定するか、通常どおりに設定できます。 メッセージの優先順位の詳細については、 [Google Developerのドキュメントを参照してください](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message)。

![](assets/push_notif_advanced_11.png)

