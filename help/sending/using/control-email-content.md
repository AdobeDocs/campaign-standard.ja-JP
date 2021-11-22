---
title: Adobe Campaign Standardでの E メールコンテンツの制御
description: E メールコンテンツを編集する際に、Adobe Campaign Standardで配信品質を向上させる方法を説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 54%

---

# メールコンテンツの制御{#control-email-content}

<!--TO KEEP because specific to Campaign-->

E メールが受信者に確実に届くようにし、E メールの配信品質率を向上させるには、E メールがいくつかのルールに従う必要があります。 従わない場合は、特定のメッセージのコンテンツがスパムとして検出される可能性があります。 Adobe Campaign には、コンテンツがこれらのルールに従うようにするためのツールがいくつか用意されています。

メッセージのコンテンツを設計する際は、以下の原則に従います。

* [送信者の名前とアドレス](#sender-name):アドレスは、送信者を明示的に識別する必要があります。 ドメインは、送信者に所有および登録されている必要があります。ドメイン登録は非公開にはしません。

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [パーソナライゼーションと送信時間の最適化](#perso-send-time-optimization):コンテンツをパーソナライズし、受信者ごとに送信時間を定義すると、メッセージが開かれる可能性が高くなります。
* 画像とテキスト：適切なテキスト／画像比率（例：テキスト 60%、画像 40％）に従います。
* [購読解除リンク](#opt-out)とランディングページ：購読解除リンクは必須です。表示されており、有効である必要があります。また、フォームは機能している必要があります。
* プレビュー：Adobe Campaignが提供するツールを使用して、E メールの内容を確認および最適化します ([スパム対策分析](#anti-spam-analysis), [E メールのレンダリング](#message-responsiveness)) をクリックします。

コンテンツの設計時に配信品質を最適化するためのその他のヒントについては、[アドビの配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=ja)を参照してください。

>[!NOTE]
>
>E メールコンテンツの編集について詳しくは、 [E メールデザイナーの概要](../../designing/using/designing-content-in-adobe-campaign.md) そして [メッセージデザインのベストプラクティス](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## 送信者の名前とアドレス {#sender-name}

一部の ISP は、メッセージを受け付ける前に、送信者アドレス（**[!UICONTROL From]**）の有効性をチェックします。不正な形式のアドレスは、受信サーバーによって拒否される可能性があります。

![](assets/delivery_content_edition16.png)

インスタンスレベルまたは最も頻繁に使用されるシナリオで、正しいアドレスが指定されていることを確認する必要があります。 これをおこなうには、管理者に問い合わせてください。

詳しくは、 [E メールの E メール送信者の定義](../../designing/using/subject-line.md#email-sender).

## パーソナライゼーションと送信時間の最適化 {#perso-send-time-optimization}

受信者のエクスペリエンスを向上させ、受信者が E メールを開くようにするために、Adobe Campaign ではメッセージをパーソナライズできます。詳しくは、[この節](../../designing/using/personalization.md)を参照してください。

メッセージの開封率を上げるには、受信者ごとに送信時間を手動で定義することもできます。 各プロファイルは、可能な限り、それぞれ指定された日時にメッセージを受信します。詳しくは、 [送信時間の最適化](../../sending/using/optimizing-the-sending-time.md).

## オプトアウトリンクとフォーム {#opt-out}

デフォルトでは、メッセージが分析される場合、タイポロジルールでオプトアウトリンクが含まれているかどうかがチェックされ、見つからない場合は警告が表示されます。リンクの管理について詳しくは、 [この節](../../designing/using/links.md).

毎回、送信前に、オプトアウトリンクが適切に機能することを確認する必要があります。例えば、 [配達確認の送信](../../sending/using/sending-proofs.md)をクリックし、リンクが有効であること、フォームがオンラインであること、およびこれを検証することで **[!UICONTROL No longer contact]** ボックス。 リンクの入力時やフォームの変更時にヒューマンエラーが発生する可能性は常にあるので、このチェックは体系的におこなう必要があります。オプトインおよびオプトアウトの管理について詳しくは、 [この節](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md).

![](assets/optin_landingpage_3.png)

オプトアウトリンクをクリックした受信者が選択を確認できないとしても、配信開始後に購読解除に関する問題が検出された場合は購読解除を手動で実行できます（一括更新機能を使用するなど）。

原則として、例えば E メールアドレスや名前などのフィールドに入力するよう求めて、オプトアウトしたい受信者を邪魔しないようにする必要があります。 購読解除ランディングページには、1 つの検証ボタンのみを含める必要があります。

追加の確認のリクエストは信頼できません。ユーザーが 2 つの E メールアドレスを同じボックスにリダイレクトさせている可能性があります（firstname.lastname@club.com と firstname.lastname@internet-club.com など）。プロファイルが最初のアドレスのみを記憶し、もう一方のアドレスに送信されたメッセージを使用して購読解除する場合、暗号化された識別子と入力された E メールアドレスが一致しないので、フォームは拒否します。

## スパム対策分析 {#anti-spam-analysis}

Adobe Campaignのメッセージエディターは **スパム対策分析** これを使用すると、e メールをスコアリングして、受信時に使用されるスパム対策ツールによってメッセージがスパムと見なされるリスクがあるかどうかを判断できます。 詳しくは、 [メッセージのプレビュー](../../sending/using/previewing-messages.md).

メッセージコンテンツエディターで、 **[!UICONTROL Preview]**. スパム対策チェックで、このメッセージのリスクが高いことが検出されたかどうかを示すメッセージが表示されます。 クリック **[!UICONTROL Anti-spam analysis]** をクリックして詳細を表示します。

![](assets/sending_anti-spam_analysis.png)

## E メールのレンダリング {#message-responsiveness}

メッセージを送信する前に、メッセージが様々なデバイスでどのように表示されるかを確認して、メッセージの応答性をテストできます。 これは、各種の web クライアント、web メール、デバイスでメッセージの表示が確実に最適化されるようにするためです。

![](assets/inbox_rendering_report_3.png)

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

詳しくは、[E メールレンダリング](../../sending/using/email-rendering.md)を参照してください。
