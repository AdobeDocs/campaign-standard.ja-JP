---
title: メッセージのトラッキング
description: 動作を追跡する方法を配信受信者。
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
source-git-commit: 50aeb40d891f6a089a556ef25eba87e568a88e94

---


# メッセージのトラッキング{#tracking-messages}

## 追跡について {#about-tracking}

追跡機能により、Adobe Campaignを使用して、ユーザーの配信受信者を追跡できます。 そのために、Adobe Campaign ではセッション Cookie および永続 Cookie を使用します。

認証リクエスト（ページ上に表示されるなど）を介してサイトにWebトラッキングツールが備わっていることをユーザーに通知し、cookieの使用を許可するチェックボックスを付けたり、ランディングページの先頭にバナーを追加したりできます。 ポップアップウィンドウはブラウザーでブロックされることが多いので、避ける必要があります。

追跡情報は、データベースのの各連絡先に対して使用できま **[!UICONTROL integrated customer profiles]**&#x200B;す。 詳しくは、[この節](../../audiences/using/integrated-customer-profile.md)を参照してください。

Adobe Campaign は、次の 2 つのタイプの Cookie を使用します。

* セッションcookie（無効）。 連絡先に送信される電子メールの識別子(broadlogId)と、メッセージテンプレートの識別子(deliveryId)が含まれます。 Adobe Campaign が送信した E メールに含まれている URL を連絡先のユーザーがクリックすると追加され、この連絡先での Web 上の行動をトラッキングできるようになります。このセッション Cookie は、ブラウザーが閉じられると自動的に消去されます。連絡先のユーザーは、Cookie を拒否するようにブラウザーを設定できます。
* Adobe Experience Cloudソリューション間で共有されるcookie。 これにより、Webサイトを訪問したときにExperience Cloudソリューションとやり取りするユーザーを特定できます。 このcookieの説明は、次のURLから入手できます。 [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html)。

Adobe Campaign標準を使用した追跡では、次の機能にアクセスできます。

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="conditions" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/campaign/kb/push-tracking.html"><img width="60px" alt="conditions" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="conditions" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="conditions" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="conditions" src="assets/icon_report.png"/></a>
</tr>
<tr>
<td>E メールトラッキング</td>
<td>プッシュ追跡</td>
<td>トラッキングされる URL</td>
<td>トラッキングログ</td>
<td>追跡レポート</td>
</tr>
</table>

## トラッキングログ {#tracking-logs}

The **[!UICONTROL Tracking logs]** tab lists the tracking history for this delivery. このタブには、送信されたメッセージの追跡情報（メッセージ別に追跡されたすべてのURLなど）が表示されます。Adobe Campaign このタブの追跡情報は、10分ごとに更新されます。

>[!NOTE]
>
>追跡が配信に対して有効でない場合、このタブは表示されません。 トラッキングログは、電子メールおよびプ **ッシュ通** 知 **** チャネルでのみ使用できます。

![](assets/tracking_logs.png)

上の例では、次の受信者です。

* メッセージを開きました。
* 「詳細情報」のカスタムリンクをクリックしました。
* 購読解除とミラーページリンク

この列で **[!UICONTROL Type]** は、次の値を指定できます。

* **[!UICONTROL Email click]**:受信者がカスタムリンクをクリックしました。
* **[!UICONTROL Mirror page]**:受信者がリンクをクリックしました。ミラーページ
* **[!UICONTROL Open]**:受信者が電子メールを開いた。
* **[!UICONTROL Opt-out]**:受信者がリンクをクリックしました。

>[!NOTE]
>
>プッシュ通知 **チャネルの場合** 、モバイル通知のクリックのみが追跡されます。 この場合、値は次のようになります **[!UICONTROL Click on mobile notification]**。

トラッキングリンクの挿入方法について詳しくは、このページを参照 [してください](../../designing/using/links.md#inserting-a-link)。

## トラッキングされる URL {#tracked-urls}

このタ **[!UICONTROL Tracked URLs]** ブでは、送信されたメッセージに含まれるURLを、URLタイプとソースURLを含めて再グループ化します。

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
