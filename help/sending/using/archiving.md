---
title: Adobe Campaign Standardでのメッセージのアーカイブ
description: BCC電子メールアドレスを使用してAdobe Campaign Standardで電子メールをアーカイブする方法について説明します。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 30%

---

# E メールの BCC を使用したアーカイブ{#archiving-emails}

「BCCでEメールを送信」を使用してプラットフォームから送信されたEメールのコピーを保持するようにAdobe Campaignを設定できます。

特に、組織が準拠のためにすべてのアウトバウンドEメールメッセージをアーカイブする必要がある場合、この機能を有効にできます。 これにより、対応する送信済みメッセージの完全な非表示コピーを、指定する必要のあるBCC Eメールアドレス（配信の受信者には表示されません）に送信できます。

有効にしたら、Eメール配信テンプレートの&#x200B;**[!UICONTROL Archive emails]**&#x200B;オプションで「BCCでEメールを送信」を有効にする必要があります。

>[!NOTE]
>
>Adobe Campaign 自体はアーカイブされたファイルを管理しません。 これにより、選択したメッセージを専用のアドレスに送信し、外部システムを使用して処理およびアーカイブできます。

## Recommendationsと限界 {#recommendations-and-limitations}

* この機能はオプションです。この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。
* 選択したBCCアドレスは、ユーザーに対して設定を行うAdobeチームに提供する必要があります。
* BCC に設定できるメールアドレスは 1 つだけです。
* 正常に送信された電子メールのみが考慮されます。バウンスはありません。
* プライバシー上の理由から、BCC電子メールは、個人の身元を特定できる情報(PII)を安全に保存できるアーカイブシステムで処理する必要があります。
* 新しい配信テンプレートを作成する場合、オプションを購入済みであっても、「BCCでEメールを送信」はデフォルトで有効になりません。 使用する各配信テンプレートで、手動で有効にする必要があります。

>[!NOTE]
>
>現在、アーカイブされたEメールは、シンプルなSMTPリレーを使用する従来のアーカイブモジュールによって送信されます。

## Eメールアーカイブの有効化 {#activating-email-archiving}

有効にすると、 [電子メールテンプレート](../../start/using/marketing-activity-templates.md)で、専用のオプションを使用して「BCCでEメールを送信」が有効になります。

1. **リソース**／**テンプレート**／**配信テンプレート**&#x200B;に移動します。
1. 標準の&#x200B;**[!UICONTROL Send via email]**&#x200B;テンプレートを複製します。
1. 複製したテンプレートを選択します。
1. 「**[!UICONTROL Edit properties]**」ボタンをクリックして、テンプレートのプロパティを編集します。
1. **[!UICONTROL Send]**&#x200B;セクションを展開します。
1. このテンプレートに基づく各配信で送信されるすべてのメッセージのコピーを保持するには、「 **[!UICONTROL Archive emails]** 」ボックスをオンにします。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>BCCアドレスに送信されたEメールが開封され、クリックされた場合、送信分析の&#x200B;**[!UICONTROL Total opens]**&#x200B;と&#x200B;**[!UICONTROL Clicks]**&#x200B;でこれが考慮され、計算の誤りの原因となる可能性があります。
