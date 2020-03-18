---
title: Adobe Campaign Standardでのメッセージのアーカイブ
description: BCC電子メールアドレスを使用して、Adobe Campaign Standardで電子メールをアーカイブする方法を説明します。
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2bf1f8acb581645a6f89f50443a8d9a49d8acaf1

---


# 電子メールBCCでのアーカイブ{#archiving-emails}

Adobe Campaignを設定して、プラットフォームから電子メールBCC経由で送信された電子メールのコピーを保持できます。

特に、組織がコンプライアンスのためにすべての送信電子メールメッセージをアーカイブする必要がある場合は、この機能を有効にできます。 対応する送信メッセージの完全に隠されたコピーを、指定する必要のあるBCC電子メールアドレス（配信の受信者には見えない）に送信できます。

有効にしたら、電子メール配信テンプレートのオプションから電子メ **[!UICONTROL Archive emails]** ールBCCをアクティブにする必要があります。

>[!NOTE]
>
>Adobe Campaign自体はアーカイブされたファイルを管理しません。 選択したメッセージを専用のアドレスに送信し、外部システムを使用して処理およびアーカイブできます。

## 推奨事項と制限事項 {#recommendations-and-limitations}

* この機能はオプションです。この機能を有効にするには、ライセンス契約を確認したうえで、アカウント担当者にお問い合わせください。
* 選択したBCCアドレスは、アドビのチームに提供され、アドビのチームがお客様に代わって設定します。
* BCC電子メールアドレスは1つだけ使用できます。
* 正常に送信された電子メールのみが考慮されます。 バウンスはありません。
* プライバシー上の理由から、BCC電子メールは、個人を安全に識別できる情報(PII)を保存できるアーカイブシステムで処理する必要があります。
* 新しい配信テンプレートを作成する場合、オプションが購入されていても、電子メールBCCはデフォルトで有効になっていません。 使用する各配信テンプレートで、手動で有効にする必要があります。

>[!NOTE]
>
>現在、拡張MTAにアップグレード済みの場合でも、 [Adobe Campaign拡張MTAでアーカイブ済みの電子メールを送信することはできません](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)。

## 電子メールアーカイブのアクティブ化 {#activating-email-archiving}

電子メールBCCは、有効になると、次の専用のオプションを通じて、電 [子メールテンプレー](../../start/using/marketing-activity-templates.md)トでアクティブになります。

1. **リソース**／**テンプレート**／**配信テンプレート**&#x200B;に移動します。
1. 標準搭載のテンプレートを複製し **[!UICONTROL Send via email]** ます。
1. 複製したテンプレートを選択します。
1. テンプレートの **[!UICONTROL Edit properties]** プロパティを編集するには、ボタンをクリックします。
1. セクションを展 **[!UICONTROL Send]** 開します。
1. このテンプレ **[!UICONTROL Archive emails]** ートに基づいて各配信用に送信されたすべてのメッセージのコピーを保持する場合は、チェックボックスをオンにします。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.