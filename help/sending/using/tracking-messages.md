---
title: メッセージの追跡
seo-title: メッセージの追跡
description: メッセージの追跡
seo-description: 配信先の動作を追跡する方法を説明します。
page-status-flag: 未活性化の
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: 送信と追跡のメッセージ
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# メッセージの追跡{#tracking-messages}

## 追跡について {#about-tracking}

Adobe Campaignでは、追跡機能により、配信先の動作を追跡できます。 これを行うには、Adobe CampaignでセッションCookieと恒久Cookieを使用します。

Cookieの使用を許可するチェックボックスが付いた（例えば、ページ上に表示される）承認要求を通じて、サイトにWeb追跡ツールが備わっていることをユーザーに通知したり、最初のページの先頭にバナーを追加したりできます。 ポップアップウィンドウは、ブラウザによってブロックされる場合が多いので、これは避ける必要があります。

Adobe Campaignでは、次の2種類のCookieを使用します。

* セッションCookie(nlid)。 連絡先に送信される電子メールの識別子(broadlogId)と、メッセージテンプレートの識別子(deliveryId)が含まれます。 Adobe Campaignが送信した電子メールに含まれるURLを連絡先がクリックすると追加され、Web上でその動作を追跡できます。 このセッションCookieは、ブラウザが閉じると自動的に消去されます。 連絡先は、Cookieを拒否するようにブラウザを構成できます。
* Adobe Experienceクラウドソリューション間で共有されるCookie。 これにより、Webサイトにアクセスする際にExperience Cloudソリューションと対話するユーザーを特定できます。 このCookieの説明は、次の場所で入手できます。 [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html)。

追跡情報は、データベースの各連絡先に対してに提供されま **[!UICONTROL integrated customer profiles]**&#x200B;す。 For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## ログの追跡 {#tracking-logs}

この配 **[!UICONTROL Tracking logs]** 信の追跡履歴がタブに表示されます。 このタブには、Adobe Campaignで追跡されたすべてのURLなど、送信されたメッセージの追跡情報が表示されます。 このタブの追跡情報は10分ごとに更新されます。

>[!NOTE]
>
>搬送の追跡が有効になっていない場合、このタブは表示されません。 追跡ログは、Eメールおよびプッシュ通 **知チャネ** ルでのみ使用でき **** ます。

![](assets/tracking_logs.png)

上の例では、受信者は次のようになります。

* メッセージを開きました。
* [詳細]カスタムリンクをクリックしました。
* 「Unsubscription」と「Mirror」ページのリンクをクリック。

列には、次 **[!UICONTROL Type]** の値を指定できます。

* **[!UICONTROL Email click]**:受信者がユーザー設定のリンクをクリックしました。
* **[!UICONTROL Mirror page]**:受信者がミラーページへのリンクをクリックしました。
* **[!UICONTROL Open]**:受信者が電子メールを開きました。
* **[!UICONTROL Opt-out]**:受信者がサブスクリプション解除リンクをクリックしました。

>[!NOTE]
>
>プッシュ通知チ **ャネルの場合** 、モバイル通知のクリックのみが追跡されます。 その場合、値はになります **[!UICONTROL Click on mobile notification]**。

追跡リンクの挿入方法の詳細については、このページを参照し [てください](../../designing/using/links.md#inserting-a-link)。

## 追跡URL {#tracked-urls}

このタ **[!UICONTROL Tracked URLs]** ブは、送信されたメッセージに含まれるURLを、URLの種類とソースURLを含めて再グループ化します。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
