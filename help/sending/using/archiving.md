---
title: Adobe Campaign Standardでのメッセージのアーカイブ
description: BCC 電子メールアドレスを使用してAdobe Campaign Standardで電子メールをアーカイブする方法について説明します。
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

「BCC で E メールを送信」を使用してプラットフォームから送信された E メールのコピーを保持するようにAdobe Campaignを設定できます。

特に、組織がコンプライアンスのためにすべてのアウトバウンド電子メールメッセージをアーカイブする必要がある場合、この機能を有効にすることができます。 これにより、対応する送信済みメッセージの完全に非表示のコピーを、指定する必要のある BCC 電子メールアドレス（配信受信者には表示されません）に送信できます。

有効にしたら、 **[!UICONTROL Archive emails]** 」オプションを使用します。

>[!NOTE]
>
>Adobe Campaign 自体はアーカイブされたファイルを管理しません。 これにより、選択したメッセージを専用のアドレスに送信し、外部システムを使用して処理およびアーカイブできます。

## Recommendationsと限界 {#recommendations-and-limitations}

* この機能はオプションです。この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。
* 選択したBCCアドレスは、ユーザーに対して設定を行うAdobeチームに提供する必要があります。
* BCC に設定できるメールアドレスは 1 つだけです。
* 正常に送信された E メールのみが考慮されます。バウンスはありません。
* プライバシー上の理由から、BCC 電子メールは、個人の身元を特定できる情報（PII）を安全に保存できるアーカイブシステムで処理する必要があります。
* 新しい配信テンプレートを作成する場合、このオプションを購入済みであっても、「BCC で E メールを送信」はデフォルトで有効になっていません。 使用する各配信テンプレートで手動で有効にする必要があります。

>[!NOTE]
>
>現在、アーカイブされた E メールは、シンプルな SMTP リレーを使用する従来のアーカイブモジュールによって送信されます。

## E メールアーカイブの有効化 {#activating-email-archiving}

有効にすると、BCC で E メールが有効化されます [電子メールテンプレート](../../start/using/marketing-activity-templates.md)、専用のオプションで設定：

1. **リソース**／**テンプレート**／**配信テンプレート**&#x200B;に移動します。
1. 標準搭載のを複製 **[!UICONTROL Send via email]** テンプレート。
1. 複製したテンプレートを選択します。
1. 次をクリック： **[!UICONTROL Edit properties]** ボタンを使用して、テンプレートのプロパティを編集します。
1. を展開します。 **[!UICONTROL Send]** 」セクションに入力します。
1. 次を確認します。 **[!UICONTROL Archive emails]** ボックスを使用して、このテンプレートに基づく各配信に対して送信されたすべてのメッセージのコピーを保持します。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>BCC アドレスに送信された電子メールが開封され、クリックされた場合、これは **[!UICONTROL Total opens]** および **[!UICONTROL Clicks]** 送信分析から。計算の誤りを引き起こす可能性があります。
