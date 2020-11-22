---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでのメッセージのアーカイブ
description: BCC電子メールアドレスを使用して、Adobe Campaign Standardとの電子メールをアーカイブする方法を説明します。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 28%

---


# E メール BCC を使用したアーカイブ{#archiving-emails}

プラットフォームから電子メールBCCを通じて送信される電子メールのコピーを保持するようにAdobe Campaignを設定できます。

特に、組織で、アウトバウンド電子メールメッセージをすべてアーカイブして準拠する必要がある場合は、この機能を有効にできます。 対応する送信メッセージの完全に隠されたコピーを、指定する必要のあるBCC電子メールアドレス(配信受信者には見えない)に送信できます。

有効にした後は、電子メール配信テンプレートの **[!UICONTROL Archive emails]** オプションで電子メールBCCを有効にする必要があります。

>[!NOTE]
>
>Adobe Campaign自体では、アーカイブされたファイルは管理されません。 これにより、選択したメッセージを専用のアドレスに送信し、外部システムを使用して処理およびアーカイブできます。

## Recommendationsと限界 {#recommendations-and-limitations}

* この機能はオプションです。この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。
* 選択したBCCアドレスは、ユーザーに対して設定を行うAdobeチームに提供する必要があります。
* BCC電子メールアドレスは1つだけ使用できます。
* 正常に送信された電子メールのみが考慮されます。バウンスはありません。
* プライバシー上の理由から、BCC電子メールは、個人の身元を特定できる情報(PII)を安全に保存できるアーカイブシステムで処理する必要があります。
* 新しい配信テンプレートを作成する場合、購入済みの場合でも、電子メールBCCはデフォルトで有効になっていません。 使用する各配信テンプレートで手動で有効にする必要があります。

>[!NOTE]
>
>現在、拡張MTAに既にアップグレード済みの場合でも、Adobe Campaign拡張MTAでアーカイブ済みの電子メールを送信することはできません。

## 電子メールアーカイブのアクティブ化 {#activating-email-archiving}

電子メールBCCは、有効にすると、次の専用のオプションを通じて、 [電子メールテンプレート](../../start/using/marketing-activity-templates.md)(BCC)内でアクティブになります。

1. **リソース**／**テンプレート**／**配信テンプレート**&#x200B;に移動します。
1. すぐに使用できる **[!UICONTROL Send via email]** テンプレートの重複
1. 複製したテンプレートを選択します。
1. Click the **[!UICONTROL Edit properties]** button to edit the template&#39;s properties.
1. セクションを展開し **[!UICONTROL Send]** ます。
1. このテンプレートに基づいて各配信のすべての送信メッセージのコピーを保持するには、この **[!UICONTROL Archive emails]** チェックボックスをオンにします。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.