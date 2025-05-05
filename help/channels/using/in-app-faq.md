---
title: アプリ内 FAQ
description: アプリ内メッセージに関するよくある質問（FAQ）
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 0101773d-b109-49a3-89d4-b4bb226d9ebd
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 0%

---

# アプリ内 FAQ {#in-app-faq}

## Adobe Campaign Standardのアプリ内チャネルについて詳しく知るのに役立つリソースの推奨事項を教えてください。 {#resources-inapp}

以下のリソースを確認してください。

* [ ビデオTutorials](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html?lang=ja)
* [ ブログ投稿 ](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [ コミュニティページ ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community?profile.language=ja)

## Campaign 拡張機能 API の setLinkageField および resetLinkageField の目的は何ですか？ {#extensions-apis}

アプリ内メッセージはSDKによって Campaign から取り込まれるので、PII データを含んだアプリ内メッセージが悪意のあるユーザーの手に渡らないようにする安全なメカニズムを提供する必要があります。 そのため、デバイスへのメッセージの安全な配信を確保するために、次のメカニズムが用意されています。

* 顧客は、この特定の情報を安全に配信する必要がある場合、モバイルプロファイルフィールド（appSubscriberRcp テーブル）フィールドを個人用および機密としてマークします。
* そのようにマークされたフィールドは、追加のセキュリティメカニズムが組み込まれたプロファイルテンプレート（appSubscriber テンプレートまたはブロードキャストテンプレートではない）でのみ使用できます。
* プロファイルテンプレートを使用して作成されたメッセージは、ユーザーがアプリにログインした場合にのみ提供されます。
* この安全なハンドシェイクを容易にするために、モバイルアプリ開発者は setLinkageField API を使用して、追加の認証詳細を渡す必要があります。 リンケージフィールドは、appSubscriberRcp テーブルの拡張時にモバイルプロファイルと CRM プロファイル間のリンクとして識別されるフィールドです。
* ユーザーが resetLinkageField を使用してアプリからログアウトすると、デバイスと resetLinkageFields に保存されているアプリ内メッセージをフラッシュする必要があります。 これにより、別のユーザーがアプリにログインした場合、以前のユーザー向けのメッセージが表示されなくなります。
* このセキュリティ機構をクライアントサイドで実装するには、[Mobile SDK API](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/) を参照してください。

## Campaign でアプリ内レポートを有効にするには、どうすればよいですか？ {#enable-inapp-reporting}

アプリ内トラッキングのポストバックを設定する必要があります。 手順については、[ こちら ](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback) を参照してください。

ローカル通知トラッキングを実装するには、この [ ページ ](../../administration/using/local-tracking.md) を参照してください。

## アプリ内チャネルで使用できるレポートはどれですか？ {#report-inapp}

アプリ内チャネル用のAdobe Campaignでは、標準レポートを使用できます。 この [ ドキュメント ](../../reporting/using/in-app-report.md) を参照してください。

各アプリ内指標の計算方法については、この [ ページ ](../../reporting/using/indicator-calculation.md#in-app-delivery) を参照してください。

## プッシュと同様に、アプリ内の多言語コンテンツのバリエーションをサポートしていますか？ {#multilingual-inapp}

現在、アプリ内メッセージで使用できる多言語テンプレートはありません。

ただし、英語以外の言語でアプリ内メッセージを送信することが目的の場合は、使用可能なテキストボックスにコンテンツを直接貼り付けることができます。

![](assets/faq_inapp.png)

## Campaign のパーソナライゼーションフィールドをカスタムHTMLに追加できますか？ {#custom-html-inapp}

いいえ、まだサポートされていません。

## アラートメッセージを設定しましたが、デバイスに表示されません。 {#alert-message}

アラートメッセージの場合は、少なくとも 1 つの解除ボタン（プライマリまたはセカンダリにアクションの解除が必要）が必要です。 それ以外の場合は、メッセージを保存することは可能ですが、受信されません。

## ローカル通知でiOSのカスタムサウンドが再生されない場合は、デフォルトのサウンドが再生されますか？ {#local-notification-sound}

iOSのカスタムサウンドの場合は、ローカル通知を作成する際に、拡張子を付けたファイル名を指定する必要があります（例：sound.caf）。 この拡張機能が指定されていない場合、デフォルトのサウンドが使用されます。

## ディープリンクはアプリ内メッセージでサポートされていますか？ {#inapp-deeplinks}

はい、ディープリンクはアプリ内メッセージでサポートされています。 ディープリンクには、次を含める必要があります。

* ディープリンクを機能させるには、配信トラッキングを無効にする必要があることを示す言語です。
* ディープリンクトラッキングを実行できるパートナーとして支店を持つ Appsflyer。 ブランチとAdobe Campaign Standardの統合について詳しくは、この [ ページ ](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1) を参照してください。

## ユーザーがプッシュ通知からアプリを起動すると、アプリ内メッセージをトリガーできますか？ {#inapp-push-trigger}

はい、これらのメッセージはデイジーチェーンメッセージとも呼ばれます。 次の手順に従います。

1. アプリ内メッセージを作成します。

1. カスタムイベントを定義し、この IAM のイベントトリガーとして選択します（例：「秋のプレビュープッシュからのトリガー」）。

1. プッシュメッセージをオーサリングする際に、IAM のトリガーに使用するイベントとして値を設定できるカスタム変数を定義します（例：Key = &quot;inappkey&quot;、value = &quot;秋のプレビュープッシュのトリガー&quot;）。

1. モバイルアプリコードで、次のようにイベントトリガーを実装します。

   ![](assets/faq_inapp_2.png)
