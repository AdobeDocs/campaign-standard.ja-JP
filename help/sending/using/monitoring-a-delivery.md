---
title: 配信の監視
seo-title: 配信の監視
description: 配信の監視
seo-description: 配信の監視方法を確認します。
page-status-flag: 非活性化の
uuid: 7772c607-debd-40fd-8322-4d49119979b4
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 送信
content-type: 参照
topic-tags: 監視メッセージ
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: 配信，メイン
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

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

### 除外ログ {#exclusion-logs}

このタ **[!UICONTROL Exclusion logs]** ブには、送信されたターゲットから除外されたすべてのメッセージが一覧表示され、送信失敗の理由が示されます。

![](assets/sending_delivery4.png)

### 除外の原因 {#exclusion-causes}

タブ **[!UICONTROL Exclusion causes]** には、ターゲット送信から除外されたメッセージの量（メッセージ数）が表示されます。

![](assets/sending_delivery5.png)

