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
source-git-commit: f0580e1ab75d4250bfb1cb801ff08b31b91cdc5a

---


# 電子メールコンテンツの制御{#control-email-content}

電子メールの配信品質を向上させ、電子メールが受信者に届くようにするには、電子メールが一定の数のルールを順守する必要があります。

* **送信者の名前とアドレス**:このアドレスは、送信者を明示的に識別する必要があります。 ドメインを所有し、送信者に登録する必要があります。 ドメインレジストリを民営化してはならない。
* **件名**:大文字と小文字の使用、およびスパマー（「Win」、「Free」など）によく使用される単語は使用しないでください。
* **電子メールのパーソナライズ**:電子メールをパーソナライズすると、メッセージが開く可能性が高くなります。
* **画像とテキスト**:適切なテキスト/画像の比率（例えば、60%のテキストと40%の画像）を考慮します。
* **購読解除リンクとランディングページ**:購読解除リンクは必須です。 これは表示可能で有効で、フォームが機能している必要があります。
* **Adobe Campaignが提供する** ツールを使用して、電子メールの内容を最適化します（配信分析、スパム対策分析）。

電子メールコンテンツの編集について詳しくは、電子メールデザイナーの概要 [およびメッセージデザイン](../../designing/using/designing-content-in-adobe-campaign.md) のベス [トプラクティスを参照してください](../../designing/using/overview.md#content-design-best-practices)。

## 送信者の名前とアドレス {#sender-name}

特定のISPは、メッセージを受け入れる前に、送信者アドレス(From)の有効性をチェックします。 アドレスの形式が正しくないと、受信サーバーによって拒否される可能性があります。 インスタンスレベルまたは最も頻繁に使用されるシナリオで、正しいアドレスが与えられていることを確認する必要があります。 管理者に問い合わせてください。

![](assets/delivery_content_edition16.png)

詳しくは、「送信者名の個人 [化」を参照してください](../../designing/using/personalization.md#personalizing-the-sender)。

## 件名行 {#subject-line}

電子メールを編集する場合は、送信する前に別の件名を試して、開封率の見積もりを受け取ることができます。 詳しくは、「電子メールの件 [名行のテスト」を参照してください](../../sending/using/testing-subject-line-email.md)。

![](assets/predictive_subject_line_example.png)

電子メールの件名行の定義について詳しくは、この節を参照し [てください](../../designing/using/subject-line.md)。

## 送信時間の最適化 {#send-time-optimization}

メッセージの成功率を向上させるために、受信者1人あたりの送信時間を手動で定義できます。 各プロファイルは、可能な限り、指定した日時にメッセージを受信します。

詳しくは、送信時間の最 [適化を参照してください](../../sending/using/optimizing-the-sending-time.md)。

## オプトアウトリンクとフォーム {#opt-out}

デフォルトでは、メッセージが分析されると、タイポロジルールはオプトアウトリンクが含まれているかどうかを確認し、含まれていない場合は警告を生成します。

送信するたびにオプトアウトリンクが正しく機能することを確認する必要があります。 例えば、証明を送信する際に、リンクが有効であること、フォームがオンラインであること、およびこれを検証することによって、「今後の連絡先なし」ボックスの値がチェックされていることを確認します。 リンクに入るときやフォームを変更するときに人為的なエラーが常に発生するので、このチェックは体系的に行う必要があります。

配信開始後に購読解除に関する問題が検出された場合でも、選択を確認できない場合でも、オプトアウトリンクをクリックする受信者に対して、手動で（一括更新機能を使用して）購読解除を実行できます。

原則として、例えば電子メールアドレスや名前などのフィールドに入力するように要求して、オプトアウトを希望する受信者の邪魔をしないでください。 購読解除のランディングページには、検証ボタンを1つだけ含める必要があります。 追加の確認を要求するのは信頼できません：ユーザーが同じボックスにリダイレクトされる電子メールアドレスを2つ持つ場合(例：firstname.lastname@club.comおよびfirstname.lastname@internet-club.com)。 プロファイルが最初のアドレスのみを記憶でき、他のアドレスに送信されたメッセージを介して登録解除を希望する場合、暗号化された識別子と入力された電子メールアドレスが一致しないので、フォームはこれを拒否します。

## スパム対策分析 {#anti-spam-analysis}

Adobe Campaignのメッセージエディターは、スパム対策分析を統合し **** 、電子メールをスコアして、受信時に使用されるスパム対策ツールによって、メッセージがスパムと見なされるリスクがあるかどうかを判断できます。 詳しくは、メッセージのプレビューを参 [照してください](../../sending/using/previewing-messages.md)。

メッセージコンテンツエディターで、をクリックしま **[!UICONTROL Preview]**&#x200B;す。 スパム対策チェックでこのメッセージのリスクが高いことが検出された場合は、メッセージが表示されます。 詳細を表 **[!UICONTROL Anti-spam analysis]** 示するには、をクリックします。

![](assets/sending_anti-spam_analysis.png)

## メッセージの応答性の確認 {#message-responsiveness}

メッセージを送信する前に、異なるデバイスでメッセージがどのように表示されるかを確認できます。 これは、様々なWebクライアント、Webメール、デバイスで最適な方法で表示されるようにするためです。

これを可能にするために、Adobe Campaignはレンダリングをキャプチャし、専用のレポートで使用できるようにします。 これにより、送信されたメッセージを受信する様々なコンテキストでプレビューできます。

詳しくは、電子メールのレンダリングを参 [照してください](../../sending/using/email-rendering.md)。

![](assets/inbox_rendering_report_3.png)
