---
title: メッセージのトラッキング
description: 配信受信者の行動を追跡する方法について説明します。
page-status-flag: 非活性化の
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bcc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# メッセージのトラッキング{#tracking-messages}

## 追跡について {#about-tracking}

Adobe Campaignでは、その追跡機能により、配信受信者の行動を追跡できます。 そのために、Adobe Campaign ではセッション Cookie および永続 Cookie を使用します。

認証リクエスト（例えば、ページ上に表示される）を通じてサイトにWebトラッキングツールが備わっていることをユーザーに通知し、cookieの使用を許可するチェックボックスを付けたり、最初のページの上部にバナーを追加したりできます。 ポップアップウィンドウはブラウザーでブロックされることが多いので、避ける必要があります。

Adobe Campaign は、次の 2 つのタイプの Cookie を使用します。

* セッションcookie（無効）。 連絡先に送信される電子メールの識別子(broadlogId)とメッセージテンプレートの識別子(deliveryId)が含まれます。 Adobe Campaign が送信した E メールに含まれている URL を連絡先のユーザーがクリックすると追加され、この連絡先での Web 上の行動をトラッキングできるようになります。このセッション Cookie は、ブラウザーが閉じられると自動的に消去されます。連絡先のユーザーは、Cookie を拒否するようにブラウザーを設定できます。
* Adobe Experience cloudソリューション間で共有されるcookie。 これにより、Experience cloudソリューションとやり取りするユーザーを、Webサイトにアクセスする際に識別できます。 このcookieの説明は、次のURLから入手できます。https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html [](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

追跡情報は、データベースの各連絡先に対して使用できま **[!UICONTROL integrated customer profiles]**&#x200B;す。 詳しくは、[この節](../../audiences/using/integrated-customer-profile.md)を参照してください。

## トラッキングログ {#tracking-logs}

The **[!UICONTROL Tracking logs]** tab lists the tracking history for this delivery. このタブには、Adobe Campaignで追跡されているすべてのURLなど、送信されたメッセージの追跡情報が表示されます。 このタブの追跡情報は、10分ごとに更新されます。

>[!NOTE]
>
>配信の追跡が有効になっていない場合、このタブは表示されません。 トラッキングログは、電子メールおよびプ **ッシュ通** 知チャネルでのみ **** 使用できます。

![](assets/tracking_logs.png)

上記の例では、受信者は次のようになります。

* メッセージを開きました。
* 「詳細情報」カスタムリンクをクリックしました。
* 購読解除とミラーページのリンクをクリックしました。

この列の **[!UICONTROL Type]** 値は次のとおりです。

* **[!UICONTROL Email click]**:受信者がカスタムリンクをクリックしました。
* **[!UICONTROL Mirror page]**:受信者がミラーページへのリンクをクリックしました。
* **[!UICONTROL Open]**:受信者が電子メールを開きました。
* **[!UICONTROL Opt-out]**:受信者が購読解除リンクをクリックしました。

>[!NOTE]
>
>プッシュ通 **知チャネルでは** 、モバイル通知のクリックのみが追跡されます。 この場合、値は次のようになります **[!UICONTROL Click on mobile notification]**。

トラッキングリンクの挿入方法について詳しくは、このページを参照 [してください](../../designing/using/links.md#inserting-a-link)。

## トラッキングされる URL {#tracked-urls}

このタ **[!UICONTROL Tracked URLs]** ブでは、送信されたメッセージに含まれるURLが、URLタイプとソースURLと共に再グループ化されます。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
