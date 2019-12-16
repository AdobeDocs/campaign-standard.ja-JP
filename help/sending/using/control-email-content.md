---
title: Adobe Campaign Standardでの電子メールコンテンツの制御
description: 電子メールコンテンツを編集する際に、Adobe Campaign Standardの配信品質を向上させる方法を説明します。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# 電子メールコンテンツの制御{#control-email-content}

電子メールの配信品質を向上させ、電子メールが受信者に届くようにするには、電子メールが一定の数のルールを順守する必要があります。

* **送信者の名前とアドレス**:このアドレスは、送信者を明示的に識別する必要があります。 ドメインは、送信者によって所有され、登録されている必要があります。ドメイン登録は、プライベートにしません。
* **件名**:大文字と小文字の使用、およびスパマー（「Win」、「Free」など）によく使用される単語は使用しないでください。
* **電子メールのパーソナライズ**:電子メールをパーソナライズすると、メッセージが開く可能性が高くなります。
* **画像とテキスト**:適切なテキスト/画像の比率（例えば、60%のテキストと40%の画像）を考慮します。
* **購読解除リンクとランディングページ**:購読解除リンクは必須です。 購読解除リンクが表示され、有効である必要があり、フォームが機能する必要があります。
* **Adobe Campaignが提供する** ツールを使用して、電子メールの内容を最適化します（配信分析、スパム対策分析）。

電子メールコンテンツの編集について詳しくは、電子メールデザイナーの概要 [およびメッセージデザイン](../../designing/using/designing-content-in-adobe-campaign.md) のベス [トプラクティスを参照してください](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)。

## Sender name and address {#sender-name}

特定の ISP は、メッセージを受け付ける前に、送信者アドレス（From）の有効性をチェックします。正しくない形式のアドレスは、受信サーバーによって拒否される可能性があります。インスタンスレベルまたは最も頻繁に使用されるシナリオで、正しいアドレスが与えられていることを確認する必要があります。 管理者に問い合わせてください。

![](assets/delivery_content_edition16.png)

詳しくは、「送信者名の個人 [化」を参照してください](../../designing/using/personalization.md#personalizing-the-sender)。

## Subject line {#subject-line}

電子メールを編集する場合は、送信する前に別の件名を試して、開封率の見積もりを受け取ることができます。 詳しくは、「電子メールの件 [名行のテスト」を参照してください](../../sending/using/testing-subject-line-email.md)。

![](assets/predictive_subject_line_example.png)

電子メールの件名行の定義について詳しくは、この節を参照し [てください](../../designing/using/subject-line.md)。

## 送信時間の最適化 {#send-time-optimization}

メッセージの成功率を向上させるために、受信者1人あたりの送信時間を手動で定義できます。 各プロファイルは、可能な限り、指定した日時にメッセージを受信します。

詳しくは、送信時間の最 [適化を参照してください](../../sending/using/optimizing-the-sending-time.md)。

## オプトアウトリンクとフォーム {#opt-out}

デフォルトでは、メッセージが分析される場合、タイポロジルールでオプトアウトリンクが含まれているかどうかがチェックされ、見つからない場合は警告が表示されます。

毎回、送信前に、オプトアウトリンクが適切に機能することを確認する必要があります。例えば、証明を送信する際に、リンクが有効であること、フォームがオンラインであること、およびこれを検証することによって、「今後の連絡先なし」ボックスの値がチェックされていることを確認します。 リンクの入力時やフォームの変更時にヒューマンエラーが発生する可能性は常にあるので、このチェックは体系的におこなう必要があります。

オプトアウトリンクをクリックした受信者が選択を確認できないとしても、配信開始後に購読解除に関する問題が検出された場合は購読解除を手動で実行できます（一括更新機能を使用するなど）。

原則として、例えば E メールアドレスや名前などのフィールドを入力するよう求めることで、オプトアウトしたい受信者を邪魔しないでください。購読解除のランディングページには、検証ボタンを1つだけ含める必要があります。 追加の確認のリクエストは信頼できません。ユーザーが 2 つの E メールアドレスを同じボックスにリダイレクトさせている可能性があります（firstname.lastname@club.com と firstname.lastname@internet-club.com など）。プロファイルが最初のアドレスのみを記憶でき、他のアドレスに送信されたメッセージを介して登録解除を希望する場合、暗号化された識別子と入力された電子メールアドレスが一致しないので、フォームはこれを拒否します。

## スパム対策分析 {#anti-spam-analysis}

Adobe Campaignのメッセージエディターは、スパム対策分析を統合し **** 、電子メールをスコアして、受信時に使用されるスパム対策ツールによって、メッセージがスパムと見なされるリスクがあるかどうかを判断できます。 詳しくは、メッセージのプレビューを参 [照してください](../../sending/using/previewing-messages.md)。

メッセージコンテンツエディターで、をクリックしま **[!UICONTROL Preview]**&#x200B;す。 スパム対策チェックでこのメッセージのリスクが高いことが検出された場合は、メッセージが表示されます。 詳細を表 **[!UICONTROL Anti-spam analysis]** 示するには、をクリックします。

![](assets/sending_anti-spam_analysis.png)

## メッセージの応答性の確認 {#message-responsiveness}

メッセージを送信する前に、異なるデバイスでメッセージがどのように表示されるかを確認できます。 これは、様々なWebクライアント、Webメール、デバイスで最適な方法で表示されるようにするためです。

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

For more on this, see [Email rendering](../../sending/using/email-rendering.md).

![](assets/inbox_rendering_report_3.png)
