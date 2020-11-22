---
solution: Campaign Standard
product: campaign
title: プロファイルの編集
description: 既存のプロファイルを編集し、連絡先情報、優先チャネル、トラッキングログ、購読などにアクセスする方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 12%

---


# プロファイルの編集{#editing-profiles}

## プロファイルのプロパティへのアクセス {#accessing-profile-properties}

既存のプロファイルを編集し、それに関連付けられたデータを問い合わせたり、変更したりするには、次の手順に従います。

1. Adobe Campaign ホームページで、**[!UICONTROL Customer profiles]**&#x200B;カードまたは「**[!UICONTROL Profiles]**」タブをクリックします。
1. 連絡先を選択します。
1. アイコンをクリックして、プロファイルの詳細情報にアクセスします。 **[!UICONTROL Edit profile properties]**

   ![](assets/profile_creation2.png)

   プロファイルのプロパティウィンドウには、すべてのプロファイル情報へのアクセスを提供するいくつかのタブがオファーされます。

   その他のタブは、Adobe Campaignで作成または拡張したカスタムリソースに応じて表示される場合があります。 カスタムリソースについて詳しくは、「カスタムリソース [について](../../developing/using/data-model-concepts.md)」を参照してください。

   >[!NOTE]
   >
   >変更できるのは、 **[!UICONTROL General]** タブ内の情報( **[!UICONTROL Traceability]** セクションを除く)のみです。

プロファイル版は、Adobe Campaign StandardAPIを使用しても可能です。 詳しくは、[該当するドキュメント](../../api/using/updating-profiles.md)を参照してください。

関連トピック：

* [統合顧客プロファイル](../../audiences/using/integrated-customer-profile.md)
* [受信者のタイムゾーンでの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般的なプロファイルデータ {#general-profile-data}

この **[!UICONTROL General]** タブでは、プロファイルに関する次の情報がグループ化されます。

* 連絡先情報。受信者の名、姓、生年月日、写真、好みの言語( [多言語電子メール](../../channels/using/creating-a-multilingual-email.md))などが含まれます。
* プロファイルに接続できるチャネル。受信者の電子メールアドレス、携帯電話番号、オプトアウト情報が含まれます。
* 住所( [ダイレクトメールの場合](../../channels/using/about-direct-mail.md))、連絡先のタイムゾーン(タイムゾーンでメッセージ [をスケジュールする場合](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md))。
* アクセス許可。受信者の組織単位(権限の [管理](../../administration/using/about-access-management.md))を示します。 [プロファイルの分割](../../administration/using/organizational-units.md#partitioning-profiles)も参照してください。

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

[ ] **[!UICONTROL Sending logs]** と[ ] **[!UICONTROL Tracking logs]** タブでは、プロファイルに送信された配信のリストと、関連するすべての追跡データがグループ化されます。

送信とトラッキングログについて詳しくは、 [配信ログ](../../sending/using/monitoring-a-delivery.md#delivery-logs) および [追跡メッセージ](../../sending/using/tracking-messages.md) の節を参照してください。

## 購読 {#subscriptions}

連絡先の購読は、対応するタブに一覧表示されます。 サービスのサブスクリプションについて詳しくは、 [この節を参照してください](../../audiences/using/about-subscriptions.md)。

タブはプッシュ通知を参照し **[!UICONTROL Mobile App Subscriptions]** ます。 詳しくは、 [プッシュ通知](../../channels/using/about-push-notifications.md) チャネルを参照してください。
