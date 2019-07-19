---
title: プロファイルの編集
seo-title: プロファイルの編集
description: プロファイルの編集
seo-description: 既存のプロファイルを編集し、連絡先情報、優先されるチャネル、トラッキングログ、購読などにアクセスする方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 6fcdb719-6149-48fc- b400-64c24a51487f
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: オーディエンス
content-type: 参照
topic-tags: 管理プロファイル
discoiquuid: 8d3ba7bf-90ae-4c6d- aaeb- a48572a69f2f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Editing profiles{#editing-profiles}

## Accessing profile properties {#accessing-profile-properties}

既存のプロファイルを編集し、それに関連するデータを確認または変更するには、次の手順を実行します。

1. From the Adobe Campaign home page, click the **[!UICONTROL Customer profiles]** card or the **[!UICONTROL Profiles]** tab.
1. 連絡先を選択します。
1. **[!UICONTROL Edit profile properties]** アイコンをクリックして、プロファイルの詳細情報にアクセスします。

   ![](assets/profile_creation2.png)

   プロファイルのプロパティウィンドウには、すべてのプロファイル情報にアクセスするためのタブがいくつか用意されています。

   その他のタブは、Adobe Campaignで作成または拡張されたカスタムリソースによっても表示される場合があります。For more information about custom resources, see [About custom resources](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >You can only modify the information in the **[!UICONTROL General]** tab - except for the **[!UICONTROL Traceability]** section.

プロファイルのエディションは、Adobe Campaign Standard APIを使用しても可能です。For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) .

関連トピック:

* [統合された顧客プロファイル](../../audiences/using/integrated-customer-profile.md)
* [受信者のタイムゾーンでの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## General profile data {#general-profile-data}

**[!UICONTROL General]** タブには、プロファイルに関する次の情報が含まれています。

* Contact information, which contains the recipient's first name, last name, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)), etc.
* プロファイルに接続できるチャネル。受信者の電子メールアドレス、携帯電話番号、オプトアウト情報が含まれます。
* Postal address (for [direct mail](../../channels/using/about-direct-mail.md)), and the contact's time zone (to [schedule messages in its time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Access authorization, which indicates the recipient's organisational unit (to [manage permissions](../../administration/using/about-access-management.md)). [「分割プロファイル](../../administration/using/organizational-units.md#partitioning-profiles)」も参照してください。

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

The **[!UICONTROL Sending logs]** and **[!UICONTROL Tracking logs]** tabs group the list of deliveries that were sent to the profile, and all related tracking data.

For more on sending and tracking logs, refer to the [delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs) and the [tracking messages](../../sending/using/tracking-messages.md) sections.

## Subscriptions {#subscriptions}

連絡先の購読が対応するタブに表示されます。For more on subscribing to a service, refer to [this section](../../audiences/using/about-subscriptions.md).

**[!UICONTROL Mobile App Subscriptions]** このタブはプッシュ通知を参照します。For more information, refer to the [Push notification](../../channels/using/about-push-notifications.md) channel.
