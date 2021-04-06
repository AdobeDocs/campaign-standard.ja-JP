---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでのメッセージのアーカイブ
description: BCC電子メールアドレスを使用して、Adobe Campaign Standardとの電子メールをアーカイブする方法を説明します。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: パフォーマンス監視
role: ビジネス従事者
level: 中級者
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
translation-type: tm+mt
source-git-commit: f7d77f524a6c141066056e53fc8616f35189fc39
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 29%

---

# E メール BCC を使用したアーカイブ{#archiving-emails}

プラットフォームから電子メールBCCを通じて送信される電子メールのコピーを保持するようにAdobe Campaignを設定できます。

特に、組織で、アウトバウンド電子メールメッセージをすべてアーカイブして準拠する必要がある場合は、この機能を有効にできます。 対応する送信メッセージの完全に隠されたコピーを、指定する必要のあるBCC電子メールアドレス(配信受信者には見えない)に送信できます。

有効にした後は、電子メール配信テンプレートの&#x200B;**[!UICONTROL Archive emails]**&#x200B;オプションから電子メールBCCを有効にする必要があります。

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
>現在、アーカイブされた電子メールは、シンプルなSMTPリレーを使用するレガシーアーカイブモジュールによって送信されます。

## 電子メールアーカイブのアクティブ化{#activating-email-archiving}

電子メールBCCは、[電子メールテンプレート](../../start/using/marketing-activity-templates.md)で有効になると、次の専用のオプションを使用して有効になります。

1. **リソース**／**テンプレート**／**配信テンプレート**&#x200B;に移動します。
1. 標準の&#x200B;**[!UICONTROL Send via email]**&#x200B;テンプレートを重複します。
1. 複製したテンプレートを選択します。
1. **[!UICONTROL Edit properties]**&#x200B;ボタンをクリックして、テンプレートのプロパティを編集します。
1. **[!UICONTROL Send]**&#x200B;セクションを展開します。
1. **[!UICONTROL Archive emails]**&#x200B;チェックボックスをオンにして、このテンプレートに基づいて各配信の送信済みメッセージのコピーを保存します。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>BCCアドレスに送信された電子メールが開かれ、クリックスルーされた場合は、送信分析の&#x200B;**[!UICONTROL Total opens]**&#x200B;と&#x200B;**[!UICONTROL Clicks]**&#x200B;を考慮に入れます。これにより、何らかの誤算が発生する可能性があります。
