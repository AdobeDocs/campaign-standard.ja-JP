---
title: アプリ内 FAQ
description: アプリ内メッセージに関するよくある質問 (FAQ) です
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 0101773d-b109-49a3-89d4-b4bb226d9ebd
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 1%

---

# アプリ内 FAQ {#in-app-faq}

## Adobe Campaign Standardのアプリ内チャネルの詳細を学ぶために役立つリソースに関する推奨事項を教えてください。 {#resources-inapp}

以下のリソースを確認します。

* [ビデオチュートリアル](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [ブログ投稿](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [コミュニティページ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Campaign 拡張機能 API setLinkageField と resetLinkageField の目的は何ですか？ {#extensions-apis}

アプリ内メッセージは SDK によって Campaign から取り込まれるので、PII データを含むアプリ内メッセージが悪意のある手に渡されないようにする、安全なメカニズムを提供します。 したがって、デバイスに対するメッセージの安全な配信を確実におこなうためのメカニズムは次のように用意されています。

* 顧客は、この特定の情報が安全に配信されるようにする場合、モバイルプロファイルフィールド（appSubscriberRcp テーブル）を個人用フィールドおよび機密用フィールドとしてマークします。
* そのようにマークされたフィールドは、追加のセキュリティメカニズムが組み込まれているプロファイルテンプレート（appSubscriber テンプレートまたはブロードキャストテンプレートには含まれません）でのみ使用できます。
* プロファイルテンプレートを使用して作成されたメッセージは、ユーザーがアプリにログインしたときにのみ提供されます。
* この安全なハンドシェイクを容易にするために、モバイルアプリ開発者は setLinkageField API を使用して追加の認証の詳細を渡す必要があります。 リンケージフィールドは、appSubscriberRcp テーブルを拡張する際に、モバイルプロファイルと CRM プロファイルの間のリンクとして識別されるフィールドです。
* resetLinkageField を使用してユーザーがアプリからログアウトしたときに、デバイスと resetLinkagefields に保存されているアプリ内メッセージをフラッシュする必要があります。 これにより、別のユーザーがアプリにログインしても、以前のユーザー向けのメッセージは表示されなくなります。
* 参照： [モバイル SDK API](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/) このセキュリティメカニズムを実装するには、クライアント側を使用します。

## Campaign でアプリ内レポートを有効にするには、何をおこなう必要がありますか？ {#enable-inapp-reporting}

アプリ内トラッキングポストバックを設定する必要があります。 説明が見つかります [ここ](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback).

ローカル通知トラッキングを実装するには、 [ページ](../../administration/using/local-tracking.md).

## アプリ内チャネルで使用できるレポートは何ですか。 {#report-inapp}

Adobe Campaignのアプリ内チャネルで、標準のレポートを利用できます。 詳しくは、 [ドキュメント](../../reporting/using/in-app-report.md).

参照 [ページ](../../reporting/using/indicator-calculation.md#in-app-delivery) を参照して、各アプリ内指標の計算方法を理解してください。

## プッシュと同様の、アプリ内で複数言語のコンテンツのバリエーションをサポートしていますか？ {#multilingual-inapp}

アプリ内メッセージで使用できる多言語テンプレートは現在ありません。

ただし、アプリ内メッセージを英語以外の言語で送信する場合は、使用可能なテキストボックスにコンテンツを直接貼り付けることができます。

![](assets/faq_inapp.png)

## Campaign のパーソナライゼーションフィールドをカスタムHTMLに追加できますか？ {#custom-html-inapp}

いいえ、これはまだサポートされていません。

## アラートメッセージを設定しましたが、デバイスに表示されません。 {#alert-message}

アラートメッセージの場合、1 つ以上の却下ボタン（プライマリまたはセカンダリで、アクションを却下する必要がある）が必要です。 そうしないと、メッセージは保存できますが、受信されません。

## ローカル通知iOSカスタムサウンドが再生されない場合代わりにデフォルトのサウンドを再生しますか？ {#local-notification-sound}

iOSのカスタムサウンドの場合、ローカル通知を作成する際に、ファイル名に拡張子を付ける必要があります（例：sound.caf）。 この拡張機能を指定しない場合は、デフォルトのサウンドが使用されます。

## ディープリンクはアプリ内メッセージでサポートされていますか。 {#inapp-deeplinks}

はい、ディープリンクはアプリ内メッセージでサポートされます。 ディープリンクには次が含まれる必要があります。

* ディープリンクを機能させるには、配信トラッキングを無効にする必要があると述べた言語。
* ディープリンクトラッキングを実行できるパートナーとして、Branch を持つ Appsflyer。 Branch とAdobe Campaign Standardの統合について詳しくは、 [ページ](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## ユーザーがプッシュ通知からアプリを起動したときにアプリ内メッセージをトリガーできますか？ {#inapp-push-trigger}

はい、これらのメッセージは、デイジーチェーンメッセージとも呼ばれます。 次の手順に従います。

1. アプリ内メッセージを作成します。

1. カスタムイベントを定義し、この IAM のイベントトリガー( 例：「秋のプレビューからのトリガープッシュ」。

1. プッシュメッセージを作成する際に、IAM のトリガーに使用するトリガーとして値を設定できるカスタム変数を定義します（例： Key = &quot;inappkey&quot;、value = &quot;fall preview Push からのイベント&quot;）。

1. モバイルアプリコードで、次のようにイベントトリガーを実装します。

   ![](assets/faq_inapp_2.png)
