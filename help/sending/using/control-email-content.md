---
title: Adobe Campaign Standardでの E メールコンテンツの制御
description: メールコンテンツの編集時にAdobe Campaign Standardの配信品質を向上させる方法を説明します。
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
source-wordcount: '787'
ht-degree: 45%

---

# メールコンテンツの制御{#control-email-content}

<!--TO KEEP because specific to Campaign-->

メールが受信者に確実に届くようにし、メールの配信品質率を向上させるには、メールがいくつかのルールに従う必要があります。 従わない場合は、特定のメッセージのコンテンツがスパムとして検出される可能性があります。 Adobe Campaign には、コンテンツがこれらのルールに従うようにするためのツールがいくつか用意されています。

メッセージのコンテンツを設計する際は、以下の原則に従います。

* [ 送信者の名前とアドレス ](#sender-name)：アドレスは送信者を明示的に識別する必要があります。 ドメインは、送信者に所有および登録されている必要があります。ドメイン登録は非公開にはしません。
  <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [Personalizationと送信時間の最適化 ](#perso-send-time-optimization): コンテンツをパーソナライズし、受信者ごとの送信時間を定義すると、メッセージが開かれる可能性が高くなります。
* 画像とテキスト：適切なテキスト／画像比率（例：テキスト 60%、画像 40％）に従います。
* [購読解除リンク](#opt-out)とランディングページ：購読解除リンクは必須です。表示されており、有効である必要があります。また、フォームは機能している必要があります。
* プレビュー：Adobe Campaignのツールを使用し、メールのコンテンツを確認し最適化します（[ スパム対策分析 ](#anti-spam-analysis)、[ メールレンダリング ](#message-responsiveness)）。

コンテンツの設計時に配信品質を最適化するためのその他のヒントについては、[アドビの配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=ja)を参照してください。

>[!NOTE]
>
>メールコンテンツの編集について詳しくは、[ メールDesignerの概要 ](../../designing/using/designing-content-in-adobe-campaign.md) および [ メッセージデザインのベストプラクティス ](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices) を参照してください。

## 送信者の名前とアドレス {#sender-name}

特定の ISP は、メッセージを受け入れる前に、送信者のアドレス（**[!UICONTROL From]**）の有効性を確認します。 不正な形式のアドレスは、受信サーバーによって拒否される可能性があります。

![](assets/delivery_content_edition16.png)

インスタンスレベルまたは最も頻繁に使用するシナリオで正しいアドレスが指定されていることを確認する必要があります。 これを行うには、管理者に問い合わせてください。

詳しくは、[ メールの送信者の定義 ](../../designing/using/subject-line.md#email-sender) を参照してください。

## Personalizationと送信時間の最適化 {#perso-send-time-optimization}

Adobe Campaignでは、受信者のエクスペリエンスを向上させ、メールを開くことができるように、メッセージをパーソナライズできます。 詳しくは、[この節](../../designing/using/personalization.md)を参照してください。

メッセージの開封率を高めるために、受信者ごとの送信時間を手動で定義することもできます。 各プロファイルは、可能な限り指定した日時にメッセージを受信します。 詳しくは、[ 送信時間の最適化 ](../../sending/using/optimizing-the-sending-time.md) を参照してください。

## オプトアウトリンクとフォーム {#opt-out}

デフォルトでは、メッセージが分析される場合、タイポロジルールでオプトアウトリンクが含まれているかどうかがチェックされ、見つからない場合は警告が表示されます。リンクの管理について詳しくは、[ この節 ](../../designing/using/links.md) を参照してください。

毎回、送信前に、オプトアウトリンクが適切に機能することを確認する必要があります。例えば、[ 配達確認を送信 ](../../sending/using/sending-proofs.md) する場合は、リンクが有効であり、フォームがオンラインであり、これを検証することで **[!UICONTROL No longer contact]** のチェックボックスがオンになることを確認します。 リンクの入力時やフォームの変更時には常に人的エラーが発生する可能性があるので、このチェックは系統的に行う必要があります。 オプトインとオプトアウトの管理について詳しくは、[ この節 ](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) を参照してください。

![](assets/optin_landingpage_3.png)

オプトアウトリンクをクリックした受信者が選択を確認できないとしても、配信開始後に購読解除に関する問題が検出された場合は購読解除を手動で実行できます（一括更新機能を使用するなど）。

原則として、オプトアウトを希望する受信者がスムーズに手続きできるよう、メールアドレスや名前などのフィールドへの入力を要求しないようにしてください。 購読解除ランディングページには、検証ボタンを 1 つだけ配置してください。

追加の確認のリクエストは信頼できません。ユーザーが 2 つのメールアドレスを同じボックスにリダイレクトさせている可能性があります（firstname.lastname@club.com と firstname.lastname@internet-club.com など）。プロファイルが最初のアドレスしか覚えておらず、もう 1 つのアドレスに送信されたメッセージ経由で購読解除しようとすると、暗号化された識別子と入力されたメールアドレスが一致しないことから、フォームは購読解除を拒否します。

## スパム対策分析 {#anti-spam-analysis}

Adobe Campaignのメッセージエディターには、**スパム対策分析** が統合されています。これにより、E メールにスコアを付けて、受信時に使用されるスパム対策ツールで、メッセージがスパムと見なされるリスクを冒すかどうかを判断できます。 詳しくは、[ メッセージのプレビュー ](../../sending/using/previewing-messages.md) を参照してください。

メッセージコンテンツエディターで、「**[!UICONTROL Preview]**」をクリックします。 スパム対策チェックによってこのメッセージの高リスクが検出された場合は、メッセージが警告を表示します。 「**[!UICONTROL Anti-spam analysis]**」をクリックすると、詳細が表示されます。

![](assets/sending_anti-spam_analysis.png)

## メールのレンダリング {#message-responsiveness}

メッセージを送信する前に、メッセージが様々なデバイスでどのように表示されるかを確認して、メッセージの応答性をテストできます。 これは、各種の web クライアント、web メール、デバイスでメッセージの表示が確実に最適化されるようにするためです。

![](assets/inbox_rendering_report_3.png)

この確認のために、Adobe Campaign ではレンダリングをキャプチャして専用のレポートで利用できるようにしています。これにより、異なるコンテキストで受信される可能性のある送信済みのメッセージをプレビューできます。

詳しくは、[メールのレンダリング](../../sending/using/email-rendering.md)を参照してください。
