---
title: Adobe Campaign Standardでのメッセージのアーカイブ
description: BCC メールアドレスを使用して、Adobe Campaign Standardでメールをアーカイブする方法を説明します。
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

# メールの BCC を使用したアーカイブ{#archiving-emails}

「BCC で E メールを送信」を使用して、プラットフォームから送信された E メールのコピーを保持するようにAdobe Campaignを設定できます。

特に、組織がコンプライアンスのためにすべての送信メールメッセージをアーカイブする必要がある場合は、この機能を有効にできます。 これにより、対応する送信済みメッセージの正確な非表示コピーを、指定する必要がある BCC メールアドレス（配信の受信者には表示されません）に送信できます。

有効にしたら、メール配信テンプレートの「**[!UICONTROL Archive emails]**」オプションから「BCC でメールを送信」を有効化する必要があります。

>[!NOTE]
>
>Adobe Campaign 自体はアーカイブされたファイルを管理しません。 これにより、選択したメッセージを専用のアドレスに送信し、外部システムを使用して処理およびアーカイブできます。

## Recommendationsと制限事項 {#recommendations-and-limitations}

* この機能はオプションです。この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。
* 選択したBCCアドレスは、ユーザーに対して設定を行うAdobeチームに提供する必要があります。
* BCC に設定できるメールアドレスは 1 つだけです。
* 正常に送信されたメールのみが対象となります。 バウンスは考慮されません。
* プライバシー上の理由から、BCC メールは、個人の身元を特定できる情報（PII）を安全に保存できるアーカイブシステムで処理する必要があります。
* 新しい配信テンプレートを作成する場合、オプションが購入されていても、BCC でメールを送信はデフォルトで有効になりません。 使用する各配信テンプレートで手動で有効にする必要があります。

>[!NOTE]
>
>現在、アーカイブされた E メールは、シンプルな SMTP リレーを使用する従来のアーカイブモジュールによって引き続き送信されます。

## メールアーカイブのアクティブ化 {#activating-email-archiving}

有効にすると、専用オプションを使用して、「BCC でメールを送信 [ が ](../../start/using/marketing-activity-templates.md) メールテンプレート」で有効化されます。

1. **リソース**／**テンプレート**／**配信テンプレート**&#x200B;に移動します。
1. 標準の **[!UICONTROL Send via email]** テンプレートを複製します。
1. 複製したテンプレートを選択します。
1. 「**[!UICONTROL Edit properties]**」ボタンをクリックして、テンプレートのプロパティを編集します。
1. 「**[!UICONTROL Send]**」セクションを展開します。
1. このテンプレートに基づく各配信のすべての送信済みメッセージのコピーを保持する場合は、「**[!UICONTROL Archive emails]**」チェックボックスをオンにします。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>BCC アドレスに送信されたメールが開封され、クリックスルーされた場合は、送信分析の **[!UICONTROL Total opens]** と **[!UICONTROL Clicks]** に含められるため、計算の誤りの原因となる可能性があります。
