---
title: プロファイルの編集
description: 既存のプロファイルを編集し、連絡先情報、優先チャネル、トラッキングログ、購読などにアクセスする方法を説明します。
page-status-flag: 非活性化の
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参照
topic-tags: 管理プロファイル
discoiquuid: 8d3ba7bf-90ae-4c6d-aeb-a48572a69f2f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# プロファイルの編集{#editing-profiles}

## プロファイルプロパティへのアクセス {#accessing-profile-properties}

既存のプロファイルを編集し、関連付けられたデータを参照または変更するには、次の手順を実行します。

1. Adobe Campaignのホームページで、カードまたはタ **[!UICONTROL Customer profiles]** ブをクリックし **[!UICONTROL Profiles]** ます。
1. 連絡先を選択します。
1. アイコンをク **[!UICONTROL Edit profile properties]** リックして、プロファイルの詳細情報にアクセスします。

   ![](assets/profile_creation2.png)

   プロファイルのプロパティウィンドウには、すべてのプロファイル情報にアクセスできる複数のタブが用意されています。

   また、Adobe Campaignで作成または拡張されたカスタムリソースに応じて、他のタブが表示される場合もあります。 カスタムリソースについて詳しくは、「カスタムリソースにつ [いて」を参照してくださ](../../developing/using/data-model-concepts.md)い。

   >[!NOTE]
   >
   >タブ内の情報は、セクションを除き、 **[!UICONTROL General]** 変更することのみ可能 **[!UICONTROL Traceability]** です。

Profiles Editionは、Adobe Campaign Standard APIを使用しても可能です。 For more on this, refer to the [dedicated documentation](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) .

関連トピック：

* [統合された顧客プロファイル](../../audiences/using/integrated-customer-profile.md)
* [受信者のタイムゾーンでの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般的なプロファイルデータ {#general-profile-data}

このタ **[!UICONTROL General]** ブには、プロファイルに関する次の情報がグループ化されます。

* 連絡先情報。受信者の名、姓、生年月日、写真、お気に入りの言語(多言語電子メール [の](../../channels/using/creating-a-multilingual-email.md))などが含まれます。
* プロファイルに接続できるチャネル。受信者の電子メールアドレス、携帯電話番号、オプトアウト情報が含まれます。
* 郵便番号(ダイレ [クトメール](../../channels/using/about-direct-mail.md))、および連絡先のタイムゾーン(タイムゾーンでメ [ッセージをスケジュールする](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* アクセス許可。受信者の組織単位(権限を管理する [ため](../../administration/using/about-access-management.md))を示します。 プロファイルの分割も参 [照してください](../../administration/using/organizational-units.md#partitioning-profiles)。

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

タブと **[!UICONTROL Sending logs]** タブに **[!UICONTROL Tracking logs]** は、プロファイルに送信された配信のリストと、関連するすべての追跡データがグループ化されます。

ログの送信と追跡について詳しくは、配信ログとトラッキング [メッセージ](../../sending/using/monitoring-a-delivery.md#delivery-logs) の節を参 [照してください](../../sending/using/tracking-messages.md) 。

## 購読 {#subscriptions}

連絡先の購読が対応するタブに表示されます。 サービスのサブスクリプションについて詳しくは、この節を参 [照してくださ](../../audiences/using/about-subscriptions.md)い。

タブ **[!UICONTROL Mobile App Subscriptions]** はプッシュ通知を参照します。 詳しくは、プッシュ通知チャネルを参 [照してください](../../channels/using/about-push-notifications.md) 。
