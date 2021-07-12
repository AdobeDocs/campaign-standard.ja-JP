---
solution: Campaign Standard
product: campaign
title: アプリ内FAQ
description: アプリ内メッセージに関するよくある質問(FAQ)
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: アプリ内
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 2%

---


# アプリ内FAQ {#in-app-faq}

## Adobe Campaign Standardのアプリ内チャネルの詳細について詳しくは、どのようなリソースをお勧めしますか？ {#resources-inapp}

以下のリソースを確認します。

* [ビデオチュートリアル](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [ブログ投稿](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [コミュニティページ](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Campaign拡張機能API setLinkageFieldとresetLinkageFieldの目的は何ですか？ {#extensions-apis}

アプリ内メッセージはCampaignからSDKによってプルされるので、PIIデータを含むアプリ内メッセージが悪意のある手に渡らないようにする、安全なメカニズムを提供します。 そのため、デバイスへのメッセージの安全な配信を確実におこなうために、次のメカニズムが整備されています。

* 顧客は、この特定の情報が安全に配信されるようにする場合、モバイルプロファイルフィールド（appSubscriberRcpテーブル）を「個人」および「機密」としてマークします。
* そのようにマークされたフィールドは、追加のセキュリティメカニズムが組み込まれているプロファイルテンプレート（appSubscriberテンプレートまたはブロードキャストテンプレートではない）でのみ使用できます。
* プロファイルテンプレートを使用して作成されたメッセージは、ユーザーがアプリにログインした場合にのみ提供されます。
* この安全なハンドシェイクを容易にするために、モバイルアプリ開発者はsetLinkageField APIを使用して追加の認証詳細を渡す必要があります。 appSubscriberRcpテーブルを拡張する際に、モバイルプロファイルとCRMプロファイルの間のリンクとして識別されるリンケージフィールドに注意してください。
* ユーザーがresetLinkageFieldを使用してアプリからログアウトする際に、デバイスに保存されているアプリ内メッセージとresetLinkagefieldをフラッシュする必要があります。 これにより、別のユーザーがアプリにログインしても、以前のユーザー向けのメッセージは表示されなくなります。
* このセキュリティメカニズムクライアント側を実装するには、[Mobile SDK API](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference)を参照してください。

## Campaignでアプリ内レポートを有効にするには、どうすればよいですか？ {#enable-inapp-reporting}

アプリ内トラッキングポストバックを設定する必要があります。 手順は[ここ](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#InApptrackingpostback)にあります。

ローカル通知トラッキングを実装するには、この[ページ](../../administration/using/local-tracking.md)を参照してください。

## アプリ内チャネルで使用できるレポートは何ですか。 {#report-inapp}

Adobe Campaignのアプリ内チャネルには、標準のレポートが用意されています。 この[ドキュメント](../../reporting/using/in-app-report.md)を参照してください。

この[ページ](../../reporting/using/indicator-calculation.md#in-app-delivery)を参照して、各アプリ内指標の計算方法を理解してください。

## プッシュと同様の、アプリ内コンテンツの多言語バリエーションをサポートしていますか。 {#multilingual-inapp}

アプリ内メッセージに使用できる多言語テンプレートはなくなりました。

ただし、英語以外の言語でアプリ内メッセージを送信する場合は、利用可能なテキストボックスにコンテンツを直接貼り付けることができます。

![](assets/faq_inapp.png)

## CampaignのパーソナライゼーションフィールドをカスタムHTMLに追加できますか？ {#custom-html-inapp}

いいえ、これはまだサポートされていません。

## アラートメッセージを設定しましたが、デバイスに表示されません。 {#alert-message}

アラートメッセージの場合、1つ以上の却下ボタン（プライマリまたはセカンダリでアクションを却下する必要がある）が必要です。 そうしないと、メッセージを保存できますが、受信されません。

## ローカル通知iOSカスタムサウンドが再生されない場合。代わりに、デフォルトのサウンドが再生されますか？ {#local-notification-sound}

iOSのカスタムサウンドの場合、ローカル通知を作成する際にファイル名に拡張子を付ける必要があります（例：sound.caf）。 この拡張子を指定しない場合は、デフォルトのサウンドが使用されます。

## ディープリンクはアプリ内メッセージでサポートされていますか。 {#inapp-deeplinks}

はい、ディープリンクはアプリ内メッセージでサポートされます。 ディープリンクには、次を含める必要があります。

* ディープリンクを機能させるには、配信トラッキングを無効にする必要があると述べた言語。
* ディープリンクトラッキングを実行できるパートナーとしてBranchを持つAppsflyer。 BranchとAdobe Campaign Standardの統合について詳しくは、この[ページ](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1)を参照してください。

## ユーザーがプッシュ通知からアプリを起動したときにアプリ内メッセージをトリガーできますか？ {#inapp-push-trigger}

はい、これらのメッセージは、デイジーチェーンメッセージとも呼ばれます。 次の手順に従います。

1. アプリ内メッセージの作成

1. カスタムイベントを定義し、このIAMのイベントトリガーとして選択します。例：「秋のプレビュープッシュからのトリガー」

1. プッシュメッセージを作成する際に、IAMのトリガーに使用するイベントとして値を設定できるカスタム変数を定義します(例：Key = &quot;inappkey&quot;、value = &quot;fall preview Pushからのトリガー&quot;)。

1. モバイルアプリコードで、次のようにイベントトリガーを実装します。

   ![](assets/faq_inapp_2.png)
