---
title: Adobe Campaign Standardでの配信の監視
description: Adobe Campaign Standardで配信を監視する方法を確認します。
page-status-flag: never-activated
uuid: 7772c607-debd-40fd-8322-4d49119979b4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af

---


# 配信の監視{#monitoring-a-delivery}

配信を監視し、その影響を測定するには、いくつかの方法があります。

* **メッセージログ**:これらのログは、メッセージダッシュボードから直接アクセスできます。 送信の詳細、ターゲットが除外された理由、および開封数やクリック数などの追跡情報が表示されます。

   メッセージログを表示するには、ブロックの右下にあるアイコンをクリックし **[!UICONTROL Deployment]** ます。

   いくつかのタブには、、、、およびに関する情報(存在する場 **[!UICONTROL Sending logs]**&#x200B;合)が **[!UICONTROL Exclusion logs]**&#x200B;含ま **[!UICONTROL Exclusion causes]**&#x200B;れて **[!UICONTROL Tracking logs]** いま **[!UICONTROL Tracked URLs]**&#x200B;す。 「配信 [ログ」を参照](#delivery-logs)。

   ![](assets/sending_delivery1.png)

   ログには、配信と校正に関するすべてのメッセージが含まれます。 特定のアイコンを使用すると、エラーや警告を識別できます。 詳しくは、「メッセージの承認」を参 [照してください](../../sending/using/previewing-messages.md)。

   ボタンをクリックしてログを書き出すことがで **[!UICONTROL Export list]** きます。

   ![](assets/sending_delivery2.png)

* **配信アラート**:配信の成功または失敗を追跡するために、Adobe Campaignは、重要なシステムアクティビティをユーザーに通知する通知を送信する電子メールアラートシステムを提供します。
* **レポート**:メッセージダッシュボードから、この特定のメッセージに関する複数のレポートにアクセスできます。 また、組み込みレポ **[!UICONTROL Reports]** ートやカスタムレポートの完全なリストにアクセスできるメニューもあり、メッセージやキャンペーンに関連する特定の指標の概要を示すのに使用できます。
* 管理者は、独自のレポートまたはBIツールで処理できる別のファイルにログをエクスポートすることもできます。 詳しくは、「ログの書き出し」を参照 [してください](../../automating/using/exporting-logs.md)。

**関連トピック：**

* [エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)
* [レポート](../../reporting/using/about-dynamic-reports.md)

## 配信ログ {#delivery-logs}

### ログの送信 {#sending-logs}

このタ **[!UICONTROL Sending logs]** ブには、この配信のすべての発生の履歴が表示されます。 送信されたメッセージとそのステータスのリストがここに保存されます。 各受信者の配信ステータスを表示できます。

ステータスを持つ各プロファ **[!UICONTROL Sent]** イルに対して、 **[!UICONTROL Date]** この列にはメッセージの送信日時が表示されます。

![](assets/sending_delivery3.png)

特定の送信ログの詳細にアクセスするには、対応する行の右側にある鉛筆アイコンをクリックします。

![](assets/sending_access-sending-log.png)

送信ログの詳細はすべて読み取り専用です。 ミラーページのプレビューも表示できます。

![](assets/sending_sending-log.png)

>[!NOTE]
>
>ミラーページのレンダリングをCampaignユーザーインターフェイスに表示するには、ミラーページサーバーのURLがセキュリティで保護されている必要があります。 この場合、ブランドの設定時に、http://ではなくhttps://を使用してこのURL [を設定します](../../administration/using/branding.md#configuring-and-using-brands)。

### 除外ログ {#exclusion-logs}

このタ **[!UICONTROL Exclusion logs]** ブには、送信されたターゲットから除外されたすべてのメッセージが一覧表示され、送信失敗の理由が示されます。

![](assets/sending_delivery4.png)

### 除外の原因 {#exclusion-causes}

タブ **[!UICONTROL Exclusion causes]** には、ターゲット送信から除外されたメッセージの量（メッセージ数）が表示されます。

![](assets/sending_delivery5.png)
