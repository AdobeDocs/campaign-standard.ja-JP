---
solution: Campaign Standard
product: campaign
title: メッセージのトラッキング
description: 配信受信者の行動のトラッキング方法を説明します。
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: パフォーマンス監視
role: User
level: Intermediate
exl-id: fac29bc2-57fa-40f9-a160-cd75f695b91e
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 36%

---

# メッセージのトラッキング{#tracking-messages}

## トラッキングについて {#about-tracking}

Adobe Campaignでは、トラッキング機能を使用して、配信受信者の行動をトラッキングできます。 そのために、Adobe Campaign ではセッション Cookie および永続 Cookie を使用します。

（例えば、ページ上で表示される）認証リクエストを介してサイトにWebトラッキングツールが装備されていることをユーザーに通知し、Cookieの使用を承認するか、最初のページの上部にバナーを追加します。 ポップアップウィンドウはブラウザーでブロックされていることが多いので、避ける必要があります。

追跡情報は、データベースの&#x200B;**[!UICONTROL integrated customer profiles]**&#x200B;への各連絡先に対して使用できます。 詳細については、[このセクション](../../audiences/using/integrated-customer-profile.md)を参照してください。

Adobe Campaign は、次の 2 つのタイプの Cookie を使用します。

* セッション Cookie （nlid）：連絡先に送信される E メールの識別子（broadlogId）およびメッセージテンプレートの識別子（deliveryId）が含まれています。Adobe Campaign が送信した E メールに含まれている URL を連絡先のユーザーがクリックすると追加され、この連絡先での web 上の行動をトラッキングできるようになります。このセッション Cookie は、ブラウザーが閉じられると自動的に消去されます。連絡先のユーザーは、Cookie を拒否するようにブラウザーを設定できます。
* Adobe Experience Cloudソリューション間で共有されるcookie。 これにより、Web サイトの訪問時に Experience Cloud ソリューションとやり取りするユーザーを識別できます。この Cookie の説明については、[こちら](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html)を参照してください。

Adobe Campaign Standardを使用したトラッキングでは、次の機能にアクセスできます。

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="条件" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/campaign/kb/push-tracking.html"><img width="60px" alt="条件" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="条件" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="条件" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="条件" src="assets/icon_report.png"/></a>
</tr>
<tr>
<td>E メールトラッキング</td>
<td>プッシュトラッキング</td>
<td>トラッキングされる URL</td>
<td>トラッキングログ</td>
<td>トラッキングレポート</td>
</tr>
</table>

## トラッキングログ {#tracking-logs}

「 **[!UICONTROL Tracking logs]** 」タブには、この配信のトラッキング履歴が一覧表示されます。 このタブには、Adobe Campaignが追跡したすべてのURLなど、送信されたメッセージのトラッキング情報が表示されます。 このタブのトラッキング情報は、10分ごとに更新されます。

>[!NOTE]
>
>配信トラッキングが有効になっていない場合、このタブは表示されません。トラッキングログは、**eメール**&#x200B;チャネルと&#x200B;**プッシュ通知**&#x200B;チャネルでのみ使用できます。

![](assets/tracking_logs.png)

上記の例では、受信者は次のようになります。

* メッセージを開きました。
* ミラーページのリンクをクリックしました。
* 「LEARN MORE」カスタムリンクをクリックしました。

**[!UICONTROL Type]**&#x200B;列では、次の値を指定できます。

* **[!UICONTROL Email click]**:受信者がカスタムリンクをクリックしました。
* **[!UICONTROL Mirror page]**:受信者がミラーページへのリンクをクリックしました。
* **[!UICONTROL Open]**:受信者がEメールを開きました。
* **[!UICONTROL Opt-out]**:受信者が購読解除リンクをクリックしました。

>[!NOTE]
>
>**プッシュ通知**&#x200B;チャネルの場合は、モバイル通知のクリックのみが追跡されます。 この場合、値は&#x200B;**[!UICONTROL Click on mobile notification]**&#x200B;になります。

トラッキングリンクの挿入方法について詳しくは、[このページ](../../designing/using/links.md#inserting-a-link)を参照してください。

**[!UICONTROL Tracking indicators]**&#x200B;レポートには、Eメールメッセージの受信後の行動をトラッキングするための主要指標が含まれています。 詳しくは、この[ページ](../../reporting/using/tracking-indicators.md)を参照してください。

## トラッキングされる URL {#tracked-urls}

「 **[!UICONTROL Tracked URLs]** 」タブでは、送信メッセージに含まれているURLを、そのURLタイプとソースURLを含めて再グループ化します。

![](assets/sending_delivery6.png)

トラッキングリンクについて詳しくは、[この節](../../designing/using/links.md#about-tracked-urls)を参照してください。
