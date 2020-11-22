---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでの電子メールコンテンツの制御
description: 電子メールコンテンツを編集する際に、Adobe Campaign Standardでの配信品質を向上させる方法を説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 38%

---


# E メールコンテンツの制御{#control-email-content}

電子メールの配信率を向上させ、電子メールが受信者に届くようにするには、電子メールが一定数のルールを順守する必要があります。

* **送信者の名前とアドレス**:このアドレスは、送信者を明示的に識別する必要があります。 ドメインは、送信者によって所有され、登録されている必要があります。ドメイン登録は、プライベートにしません。
* **件名**:大文字と小文字の使い過ぎ、句読点、スパマーが頻繁に使用する単語（「Win」、「Free」など）の使用を避けます。
* **電子メールのパーソナライズ**:電子メールをパーソナライズすると、メッセージを開く確率が高くなります。
* **画像とテキスト**:適切なテキスト/画像の比率を考慮します（例えば、60%テキストと40%画像）。
* **購読解除リンクとランディングページ**:購読解除リンクは必須です。 購読解除リンクが表示され、有効である必要があり、フォームが機能する必要があります。
* **Adobe Campaignが提供するツール** (配信分析、スパム対策分析)を使用して、電子メールの内容を最適化します。

電子メールコンテンツの編集について詳しくは、 [電子メールデザイナーの概要](../../designing/using/designing-content-in-adobe-campaign.md) 、および [メッセージデザインのベストプラクティスを参照してください](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## Sender name and address {#sender-name}

特定の ISP は、メッセージを受け付ける前に、送信者アドレス（From）の有効性をチェックします。正しくない形式のアドレスは、受信サーバーによって拒否される可能性があります。インスタンスレベルまたは最も頻繁に使用されるシナリオで、正しいアドレスが与えられていることを確認する必要があります。 管理者に問い合わせてください。

![](assets/delivery_content_edition16.png)

詳しくは、「送信者名の [個人設定](../../designing/using/personalization.md#personalizing-the-sender)」を参照してください。

## 件名 {#subject-line}

電子メールを編集する際は、送信前に別の件名行を試して、開放率の見積もりを受け取ることができます。 詳しくは、「電子メールの件名行の [テスト](../../sending/using/testing-subject-line-email.md)」を参照してください。

![](assets/predictive_subject_line_example.png)

電子メールの件名行の定義について詳しくは、 [この節を参照してください](../../designing/using/subject-line.md)。

## Send time optimization {#send-time-optimization}

メッセージの成功率を向上させるために、受信者ごとの送信時間を手動で定義できます。 各プロファイルは、可能な限り、それぞれ指定された日時にメッセージを受信します。

詳しくは、「送信時間の [最適化](../../sending/using/optimizing-the-sending-time.md)」を参照してください。

## オプトアウトリンクとフォーム {#opt-out}

デフォルトでは、メッセージが分析される場合、タイポロジルールでオプトアウトリンクが含まれているかどうかがチェックされ、見つからない場合は警告が表示されます。

毎回、送信前に、オプトアウトリンクが適切に機能することを確認する必要があります。例えば、配達確認を送信する際に、リンクが有効であること、フォームがオンラインであること、およびこれを検証すると「連絡先なし」ボックスの値がチェックされていることを確認します。 リンクの入力時やフォームの変更時にヒューマンエラーが発生する可能性は常にあるので、このチェックは体系的におこなう必要があります。

オプトアウトリンクをクリックした受信者が選択を確認できないとしても、配信開始後に購読解除に関する問題が検出された場合は購読解除を手動で実行できます（一括更新機能を使用するなど）。

原則として、例えば E メールアドレスや名前などのフィールドを入力するよう求めることで、オプトアウトしたい受信者を邪魔しないでください。購読解除ランディングページには、検証ボタンが1つだけ必要です。 追加の確認のリクエストは信頼できません。ユーザーが 2 つの E メールアドレスを同じボックスにリダイレクトさせている可能性があります（firstname.lastname@club.com と firstname.lastname@internet-club.com など）。プロファイルが最初のアドレスのみを記憶でき、他のアドレスに送信されたメッセージを介して登録解除を希望する場合、暗号化されたIDと入力された電子メールアドレスが一致しないので、フォームはこの処理を拒否します。

## スパム対策分析 {#anti-spam-analysis}

Adobe Campaignのメッセージエディターは、 **スパム対策分析を統合し** 、メッセージをスコアして、受信時に使用されるスパム対策ツールによってスパムと見なされる危険性があるかどうかを判断できます。 For more on this, see [Previewing messages](../../sending/using/previewing-messages.md).

メッセージコンテンツエディターでをクリックし **[!UICONTROL Preview]**&#x200B;ます。 スパム対策チェックで、このメッセージに高いリスクが検出された場合は、警告メッセージが表示されます。 表示 **[!UICONTROL Anti-spam analysis]** の詳細をクリックします。

![](assets/sending_anti-spam_analysis.png)

## メッセージの応答性の確認 {#message-responsiveness}

メッセージを送信する前に、別のデバイスでメッセージがどのように表示されるかを確認できます。 これは、様々なWebクライアント、Webメール、デバイスに最適な方法で表示されるようにするためです。

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

詳しくは、[E メールレンダリング](../../sending/using/email-rendering.md)を参照してください。

![](assets/inbox_rendering_report_3.png)
