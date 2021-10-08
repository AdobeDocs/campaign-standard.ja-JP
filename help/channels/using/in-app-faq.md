---
title: アプリ内 FAQ
description: アプリ内メッセージに関するよくある質問 (FAQ)
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
source-git-commit: df7fce6f2fd98688e5a1fb5bc84603e6b3df5cd4
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 2%

---


# アプリ内 FAQ {#in-app-faq}

## Adobe Campaign Standardのアプリ内チャネルの詳細について学ぶために役立つリソース推奨事項を教えてください。 {#resources-inapp}

以下のリソースを確認します。

* [ビデオチュートリアル](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [ブログ投稿](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [コミュニティページ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Campaign 拡張機能 API setLinkageField と resetLinkageField の目的は何ですか？ {#extensions-apis}

アプリ内メッセージは SDK によって Campaign から取り込まれるので、PII データを含むアプリ内メッセージが悪意のある手に渡らないようにする、安全なメカニズムを提供します。 そのため、デバイスに安全にメッセージを配信できるように、次のメカニズムが用意されています。

* 顧客は、モバイルプロファイルフィールド（appSubscriberRcp テーブル）を「個人」および「機密」としてマークします。この特定の情報が安全に配信されるようにする場合に役立ちます。
* このようにマークされたフィールドは、追加のセキュリティメカニズムが組み込まれているプロファイルテンプレート（appSubscriber テンプレートまたはブロードキャストテンプレートではない）でのみ使用できます。
* プロファイルテンプレートを使用して作成されたメッセージは、ユーザーがアプリにログインした場合にのみ提供されます。
* この安全なハンドシェイクを容易にするために、モバイルアプリ開発者は setLinkageField API を使用して追加の認証詳細を渡す必要があります。 リンケージフィールドは、 appSubscriberRcp テーブルを拡張する際にモバイルプロファイルと CRM プロファイルの間のリンクとして識別されるものです。
* ユーザーが resetLinkageField を使用してアプリからログアウトする際に、デバイスに保存されているアプリ内メッセージと resetLinkage フィールドをフラッシュする必要があります。 これにより、別のユーザーがアプリにログインしても、以前のユーザー向けのメッセージは表示されなくなります。
* このセキュリティメカニズムクライアント側を実装するには、[Mobile SDK API](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference) を参照してください。

## Campaign でアプリ内レポートを有効にするには、どうすればよいですか？ {#enable-inapp-reporting}

アプリ内トラッキングポストバックを設定する必要があります。 手順は [ ここ ](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback) にあります。

ローカル通知の追跡を実装するには、この [ ページ ](../../administration/using/local-tracking.md) を参照してください。

## アプリ内チャネルで使用できるレポートを教えてください。 {#report-inapp}

アプリ内チャネルのAdobe Campaignでは、標準のレポートを利用できます。 この [ ドキュメント ](../../reporting/using/in-app-report.md) を参照してください。

この [ ページ ](../../reporting/using/indicator-calculation.md#in-app-delivery) を参照して、各アプリ内指標の計算方法を確認してください。

## プッシュと同様の、アプリ内コンテンツの複数言語のバリエーションをサポートしていますか？ {#multilingual-inapp}

アプリ内メッセージに使用できる複数言語テンプレートはなくなりました。

ただし、英語以外の言語でアプリ内メッセージを送信する場合は、利用可能なテキストボックスにコンテンツを直接貼り付けることができます。

![](assets/faq_inapp.png)

## Campaign のパーソナライゼーションフィールドをカスタムHTMLに追加できますか？ {#custom-html-inapp}

いいえ、これはまだサポートされていません。

## アラートメッセージを設定しましたが、デバイスに表示されません。 {#alert-message}

アラートメッセージの場合は、1 つ以上の却下ボタン（プライマリまたはセカンダリでアクションを却下する必要がある）が必要です。 そうしないと、メッセージを保存できますが、受信されません。

## ローカル通知iOSカスタムサウンドが再生されない場合代わりにデフォルトのサウンドが再生されますか？ {#local-notification-sound}

iOSのカスタムサウンドの場合、ローカル通知を作成する際に、ファイル名に拡張子を付ける必要があります（例：sound.caf）。 この拡張機能を指定しない場合は、デフォルトのサウンドが使用されます。

## ディープリンクはアプリ内メッセージでサポートされていますか。 {#inapp-deeplinks}

はい、ディープリンクはアプリ内メッセージでサポートされます。 ディープリンクには次のものが含まれます。

* ディープリンクを機能させるには、配信トラッキングを無効にする必要があると述べた言語。
* ディープリンクの追跡を実行できるパートナーとして Branch を持つ Appsflyer。 Branch とAdobe Campaign Standardの統合について詳しくは、この [ ページ ](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1) を参照してください。

## プッシュ通知からアプリを起動したときにアプリ内メッセージをトリガーできますか？ {#inapp-push-trigger}

はい、これらのメッセージはデイジーチェーンメッセージとも呼ばれます。 次の手順に従います。

1. アプリ内メッセージの作成

1. カスタムイベントを定義し、この IAM のイベントトリガーとして選択します。例：「秋のプレビュープッシュからのトリガー」

1. プッシュメッセージを作成する際に、IAM のトリガーに使用するイベントとして値を設定できるカスタム変数を定義します ( 例：Key = &quot;inappkey&quot;、value = &quot;fall preview Push からのトリガー&quot;)。

1. モバイルアプリコードで、次のようにイベントトリガーを実装します。

   ![](assets/faq_inapp_2.png)
