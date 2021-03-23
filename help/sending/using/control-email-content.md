---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでの電子メールコンテンツの制御
description: 電子メールコンテンツを編集する際に、Adobe Campaign Standardでの配信品質を向上させる方法を学びます。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 配信品質
role: ビジネス従事者
level: 中級者
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 31%

---


# E メールコンテンツの制御{#control-email-content}

<!--TO KEEP because specific to Campaign-->

電子メールがお客様の受信者に届き、電子メールの配信速度を向上させるためには、Eメールが様々なルールを尊重する必要があります。 そうしないと、特定のメッセージの内容がスパムとして検出される場合があります。 Adobe Campaignには、コンテンツをこれらのルールに準拠させるためのツールがいくつか用意されています。

メッセージの内容を設計する際は、次の原則に従います。

* [送信者の名前とアドレス](#sender-name):このアドレスは、送信者を明示的に識別する必要があります。ドメインは、送信者によって所有され、登録されている必要があります。ドメイン登録は、プライベートにしません。

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [パーソナライゼーションと送信時間の最適化](#perso-send-time-optimization):コンテンツをパーソナライズし、受信者ごとの送信時間を定義すると、メッセージが開かれる可能性が高くなります。
* 画像とテキスト：適切なテキスト/画像の比率を考慮します（例えば、60%テキストと40%画像）。
* [購読解除](#opt-out) リンクとランディングページ:購読解除リンクは必須です。購読解除リンクが表示され、有効である必要があり、フォームが機能する必要があります。
* プレビュー:Adobe Campaignが提供するツールを使用して、電子メールの内容を確認し、最適化します([スパム対策分析](#anti-spam-analysis)、[電子メールレンダリング](#message-responsiveness))。

コンテンツのデザイン時に配信品質を最適化するためのその他のヒントについては、『Adobe配信品質のベストプラクティスガイド』を参照してください。[](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html)

>[!NOTE]
>
>電子メールコンテンツの編集について詳しくは、[電子メールデザイナーの概要](../../designing/using/designing-content-in-adobe-campaign.md)および[メッセージデザインのベストプラクティス](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)を参照してください。

## 送信者の名前とアドレス{#sender-name}

一部のISPは、メッセージを受け付ける前に、送信者のアドレス(**[!UICONTROL From]**)の有効性をチェックします。 正しくない形式のアドレスは、受信サーバーによって拒否される可能性があります。

![](assets/delivery_content_edition16.png)

インスタンスレベルまたは最も頻繁に使用されるシナリオで、正しいアドレスが与えられていることを確認する必要があります。 これを行うには、管理者に問い合わせてください。

詳しくは、[電子メール](../../designing/using/subject-line.md#email-sender)の電子メール送信者の定義を参照してください。

## パーソナライゼーションと送信時間の最適化{#perso-send-time-optimization}

受信者の体験を向上させ、電子メールを開くように、Adobe Campaignを使用してメッセージをパーソナライズできます。 詳しくは、[この節](../../designing/using/personalization.md)を参照してください。

メッセージの開封率を高めるために、受信者ごとの送信時間を手動で定義することもできます。 各プロファイルは、可能な限り、それぞれ指定された日時にメッセージを受信します。詳しくは、[送信時間の最適化](../../sending/using/optimizing-the-sending-time.md)を参照してください。

## オプトアウトリンクとフォーム {#opt-out}

デフォルトでは、メッセージが分析される場合、タイポロジルールでオプトアウトリンクが含まれているかどうかがチェックされ、見つからない場合は警告が表示されます。リンクの管理について詳しくは、[このセクション](../../designing/using/links.md)を参照してください。

毎回、送信前に、オプトアウトリンクが適切に機能することを確認する必要があります。例えば、[配達確認](../../sending/using/sending-proofs.md)を送信する際に、リンクが有効であり、フォームがオンラインであること、およびこれを検証することで&#x200B;**[!UICONTROL No longer contact]**&#x200B;ボックスがチェックされることを確認します。 リンクの入力時やフォームの変更時にヒューマンエラーが発生する可能性は常にあるので、このチェックは体系的におこなう必要があります。オプトインとオプトアウトの管理について詳しくは、[このセクション](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)を参照してください。

![](assets/optin_landingpage_3.png)

オプトアウトリンクをクリックした受信者が選択を確認できないとしても、配信開始後に購読解除に関する問題が検出された場合は購読解除を手動で実行できます（一括更新機能を使用するなど）。

原則として、例えば電子メールアドレスや名前などのフィールドに入力するように受信者に求め、オプトアウトを希望するユーザーの邪魔をしないでください。 購読解除ランディングページには、検証ボタンが1つだけ必要です。

追加の確認のリクエストは信頼できません。ユーザーが 2 つの E メールアドレスを同じボックスにリダイレクトさせている可能性があります（firstname.lastname@club.com と firstname.lastname@internet-club.com など）。プロファイルが最初のアドレスのみを記憶でき、他のアドレスに送信されたメッセージを介して登録解除を希望する場合、暗号化されたIDと入力された電子メールアドレスが一致しないので、フォームはこの処理を拒否します。

## スパム対策分析 {#anti-spam-analysis}

Adobe Campaignのメッセージエディタは、**スパム対策分析**&#x200B;を統合しており、受信時に使用するスパム対策ツールによって、電子メールのスコアを付け、スパムと見なされる危険性があるかどうかを判断できます。 詳しくは、[メッセージのプレビュー](../../sending/using/previewing-messages.md)を参照してください。

メッセージコンテンツエディターで、**[!UICONTROL Preview]**&#x200B;をクリックします。 スパム対策チェックで、このメッセージに高いリスクが検出された場合は、警告メッセージが表示されます。 表示の詳細を表示するには、**[!UICONTROL Anti-spam analysis]**&#x200B;をクリックします。

![](assets/sending_anti-spam_analysis.png)

## E メールのレンダリング {#message-responsiveness}

メッセージを送信する前に、異なるデバイスでメッセージがどのように表示されるかを確認して、メッセージの応答性をテストできます。 これは、様々なWebクライアント、Webメール、デバイスに最適な方法で表示されるようにするためです。

![](assets/inbox_rendering_report_3.png)

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

詳しくは、[E メールレンダリング](../../sending/using/email-rendering.md)を参照してください。