---
title: パーソナライズされたコンテンツの作成
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: メッセージコンテンツをデザインし、配信の実行を妨げる可能性がある一般的な問題を回避する方法を説明します。 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 69%

---

# パーソナライズされたコンテンツの作成 {#build-personalized-content}

メッセージコンテンツを設計するときは、配信の実行を妨げる可能性がある一般的な問題が発生しないようにします。ほとんどの場合、考えられるエラーは [パーソナライズ](../../designing/using/personalization.md)、書式設定 [既存のコンテンツの使用](../../designing/using/using-existing-content.md)  — および [変換，HTMLの内容](../../designing/using/using-existing-content.md#converting-an-html-content)  — および [画像](../../designing/using/images.md).

## パーソナライゼーションの最適化 {#optimize-personalization}

配信の実行を妨げる可能性がある一般的な問題を回避し、受信者のエクスペリエンスを向上させるために、Adobe Campaign でメッセージをパーソナライズできます。

Adobe Campaign データベースに保存されている受信者データや、トラッキング、ランディングページ、購読などを通じて収集した受信者データを使用できます。パーソナライゼーションの基本については、[この節](../../designing/using/personalization.md)を参照してください。

エラーを避けるために、メッセージコンテンツが適切に設計されていることを確認します。多くのエラーはパーソナライゼーションに関係しています。

動的コンテンツを手動で追加して、式エディターで定義した条件に従って、受信者に異なるコンテンツを表示できます。 動的コンテンツを追加する場合は、選択した条件を満たさない受信者に対しては、常にデフォルトのバリアントのままにする必要があります。
動的コンテンツについて詳しくは、 [この節](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**ヒント**  — 様々なテストプロファイルで E メールをプレビューし、動的なコンテンツが正しく設定されていることを確認します。

## 最適化されたコンテンツの作成 {#optimize-content}

E メールを作成する際は、以下の一般的なベストプラクティスを考慮してください。

* デザインをシンプルにします

* モバイルユーザーを考慮します

* 画像のみの E メールは避けます

* E メールセーフフォントを使用します

* 特殊文字をエンコードします

### 件名

メールの開封率を向上させる[件名](../../designing/using/subject-line.md)にします。

* 長すぎる件名は避けます。最大 50 文字にします

* 「無償」や「オファー」など、スパムと見なされる可能性がある単語を繰り返し使用することは避けます

* 大文字や、「!」、「£」、「€」、「$」などの特殊文字の使用を避けます

### ミラーページ

ミラーページリンクを必ず含めます。E メールの先頭がお勧めです。[詳細情報](../../designing/using/personalization.md#adding-a-content-block)

### 購読解除リンク

購読解除リンクは不可欠です。購読解除リンクが表示され、有効である必要があり、フォームが機能する必要があります。購読解除リンクのガイドラインを説明します [この節](../../designing/using/personalization.md#about-targeting-dimension).

デフォルトでは、メッセージが分析される際に、コントロール [タイポロジルール](../../sending/using/control-rules.md) オプトアウトリンクが含まれているかどうかを確認し、見つからない場合は警告を生成します。

**ヒント**：ヒューマンエラーが発生する可能性は常にあるので、毎回、送信前に、オプトアウトリンクが適切に機能することを確認する必要があります。例えば、配達確認を送信するときは、リンクが有効であること、フォームがオンラインであること、「今後のこの受信者への連絡は不要」フィールドが「はい」に変更されていることを確認します。

オプトアウトリンクを挿入する方法については、[この節](../../designing/using/personalization.md#adding-a-content-block)を参照してください。

### E メールのサイズ {#email-size}

パフォーマンスや配信品質の問題を回避するため、E メールの最大サイズは約 **35** KB です。

E メールの制限を守るには、以下を考慮してください。

* 冗長なスタイル、または使用されていないスタイルの削除

* E メールコンテンツの一部を [ランディングページ](../../channels/using/getting-started-with-landing-pages.md)

* コードの縮小

最終送信の前に、必ず変更をテストしてください。

Adobe Campaignでは、E メールのデフォルトの最大サイズはに設定されています。 **100 MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

上限に達すると、上限を超えたメッセージは失敗し、エラーメッセージが配信ログに表示されます。 同じ配信のその他のメッセージには影響しません。 その場合は、E メールテンプレートまたは配信で使用されるコンテンツフラグメントの動的部分を適応させる必要があります。 <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobeでは、最大メッセージサイズのデフォルト値を維持することをお勧めします。 ただし、この値は **[!UICONTROL Maximum message size]** オプション、 **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** メニュー、基準 [機能管理者](../../administration/using/users-management.md#functional-administrators) のみ。

>[!IMPORTANT]
>
>この値をゼロに設定した場合、制限は適用されません。

### SMS の長さ

デフォルトでは、SMS の文字数は GSM（Global System for Mobile Communications）標準に準じています。GSM エンコードを使用する SMS メッセージは 160 文字以内に制限されています。複数の部分に分けて送信されるメッセージの場合は、SMS 1 件につき 153 文字以内です。

表記変換では、SMS の特定の文字が GSM 標準に準じていない場合に、別の文字に置き換えられます。パーソナライゼーションフィールドを SMS メッセージのコンテンツに入れると、GSM エンコードに対応していない文字が含まれる場合があります。文字の表記変換を許可するには、対応する **[!UICONTROL External account]**.
詳しくは、[この節](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)を参照してください。

**ヒント**：

* SMS メッセージのすべての文字をそのまま維持するには（例えば、固有名詞が改変されないようにするには）、表記変換を有効にしないでください。

* ただし、SMS メッセージに GSM 標準に準じていない文字が多数含まれる場合は、表記変換を有効にしてメッセージ送信のコストを抑えることができます。

詳しくは、[この節](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration)を参照してください。

### レスポンシブ E メールデザイン

レスポンシブデザインを使用すると、E メールを開封するデバイスに応じて E メールを最適に表示できます。

* web HTML ではなく、レスポンシブ E メール HTML を使用します

* プレビューモードと配達確認を使用して、できるだけ多くのデバイス上でレンダリングをテストします. 方法を学ぶ [プレビューメッセージ](../../sending/using/previewing-messages.md) 送信する前に

* Campaign E メールデザイナーには、モバイル用のレスポンシブデザインでフォーマットされたテンプレートが付属しています。 詳しくは、[このページ](../../designing/using/using-reusable-content.md#content-templates)を参照してください。

## 画像の管理 {#manage-images}

画像を使用する場合は、次のガイドラインに従ってください。

### 画像のブロックを回避

一部の E メールクライアントはデフォルトで画像をブロックし、一部のユーザーはデータ使用時に保存する画像をブロックするように設定を変更します。したがって、画像がダウンロードされなければ、メッセージ全体が失われる可能性があります。これを回避するには：

* コンテンツと画像とテキストのバランスを取ります。画像のみの E メールは避けます。

* 画像にテキストを含める必要がある場合は、代替テキストやタイトルテキストを使用して、必ずメッセージが伝わるようにします。代替テキストやタイトルテキストのスタイルを設定して、外観を改善します。

* 背景画像は一部の E メールクライアントでサポートされていないので、使用しないようにします。

### 画像をレスポンシブにする

画像をレスポンシブでサイズ変更可能にします。これは作成に時間がかかるので、コストに影響する可能性があります。

### 絶対画像参照を使用する

キャンペーンに関連する E メールやパブリックリソースで使用される画像を外部からアクセスできるようにするには、その画像を外部からアクセスできるサーバー上に置く必要があります。

## メッセージのプレビュー {#preview-msg}

メッセージをプレビューして、パーソナライゼーションと受信者に対する配信の表示を確認することをお勧めします。

E メールデザイナーで、 **[!UICONTROL Preview]** 「 」ボタンを使用すると、特定の受信者向けに各コンテンツをレンダリングした結果を表示できます。 コンテンツのパーソナライゼーションフィールドや条件付き要素は、選択したプロファイル内の対応する情報で置き換えられます。[詳細情報](../../sending/using/previewing-messages.md)
