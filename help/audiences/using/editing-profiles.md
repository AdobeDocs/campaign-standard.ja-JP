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

## プロファイルのプロパティへのアクセス{#accessing-profile-properties}

既存のプロファイルを編集し、それに関連付けられたデータを問い合わせたり、変更したりするには、次の手順に従います。

1. Adobe Campaign ホームページで、**[!UICONTROL Customer profiles]**&#x200B;カードまたは「**[!UICONTROL Profiles]**」タブをクリックします。
1. 連絡先を選択します。
1. **[!UICONTROL Edit profile properties]**&#x200B;アイコンをクリックして、プロファイルの詳細情報にアクセスします。

   ![](assets/profile_creation2.png)

   プロファイルのプロパティウィンドウには、すべてのプロファイル情報へのアクセスを提供するいくつかのタブがオファーされます。

   その他のタブは、Adobe Campaignで作成または拡張したカスタムリソースに応じて表示される場合があります。 カスタムリソースについて詳しくは、[カスタムリソース](../../developing/using/data-model-concepts.md)についてを参照してください。

   >[!NOTE]
   >
   >**[!UICONTROL General]**&#x200B;タブの情報のみ変更できます（**[!UICONTROL Traceability]**&#x200B;セクションを除く）。

プロファイル版は、Adobe Campaign StandardAPIを使用しても可能です。 詳しくは、[該当するドキュメント](../../api/using/updating-profiles.md)を参照してください。

関連トピック：

* [統合顧客プロファイル](../../audiences/using/integrated-customer-profile.md)
* [受信者のタイムゾーンでの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般的なプロファイルデータ{#general-profile-data}

**[!UICONTROL General]**&#x200B;タブは、プロファイルに関する次の情報をグループ化します。

* 連絡先情報。受信者の名、姓、生年月日、写真、好みの言語（[多言語の電子メール](../../channels/using/creating-a-multilingual-email.md)の場合）などが含まれます。
* プロファイルに接続できるチャネル。受信者の電子メールアドレス、携帯電話番号、オプトアウト情報が含まれます。
* 住所（[ダイレクトメール](../../channels/using/about-direct-mail.md)用）、連絡先のタイムゾーン（タイムゾーン](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)内の[スケジュールメッセージ）。
* アクセス許可。受信者の組織単位（[権限の管理](../../administration/using/about-access-management.md)）を示します。 [プロファイルの分割](../../administration/using/organizational-units.md#partitioning-profiles)も参照してください。

![](assets/profile_creation4.png)

## 送信とトラッキングログ{#sending-and-tracking-logs}

**[!UICONTROL Sending logs]**&#x200B;タブと&#x200B;**[!UICONTROL Tracking logs]**&#x200B;タブは、プロファイルに送信された配信のリストと、関連するすべての追跡データをグループ化します。

送信とトラッキングログについて詳しくは、[配信ログ](../../sending/using/monitoring-a-delivery.md#delivery-logs)と[トラッキングメッセージ](../../sending/using/tracking-messages.md)の節を参照してください。

## 購読 {#subscriptions}

連絡先の購読は、対応するタブに一覧表示されます。 サービスのサブスクリプションについて詳しくは、[このセクション](../../audiences/using/about-subscriptions.md)を参照してください。

「**[!UICONTROL Mobile App Subscriptions]**」タブはプッシュ通知を参照します。 詳しくは、[プッシュ通知](../../channels/using/about-push-notifications.md)のチャネルを参照してください。
