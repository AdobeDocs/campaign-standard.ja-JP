---
title: プロファイルの編集
description: 既存のプロファイルを編集し、連絡先情報、優先チャネル、トラッキングログ、サブスクリプションなどにアクセスする方法について説明します。
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%

---

# プロファイルの編集{#editing-profiles}

## プロファイルプロパティへのアクセス {#accessing-profile-properties}

既存のプロファイルを編集し、それに関連付けられたデータを参照したり、変更したりするには、次の手順に従います。

1. Adobe Campaignのホームページで、**[!UICONTROL Customer profiles]** カードまたは「**[!UICONTROL Profiles]**」タブをクリックします。
1. 連絡先を選択します。
1. **[!UICONTROL Edit profile properties]** アイコンをクリックして、プロファイルの詳細情報にアクセスします。

   ![](assets/profile_creation2.png)

   プロファイルのプロパティウィンドウには、すべてのプロファイル情報にアクセスできる複数のタブが用意されています。

   Adobe Campaignで作成または拡張したカスタムリソースによっては、その他のタブも表示される場合があります。 カスタムリソースについて詳しくは、「[&#x200B; カスタムリソースについて &#x200B;](../../developing/using/data-model-concepts.md) を参照してください。

   >[!NOTE]
   >
   >**[!UICONTROL Traceability]** セクションを除き、「**[!UICONTROL General]**」タブの情報のみを変更できます。

Adobe Campaign Standard API を使用してプロファイルを編集することもできます。 詳しくは、[該当するドキュメント](../../api/using/updating-profiles.md)を参照してください。

関連トピック：

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [受信者のタイムゾーンでの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般的なプロファイルデータ {#general-profile-data}

「**[!UICONTROL General]**」タブには、プロファイルに関する次の情報がグループ化されます。

* 連絡先情報：受信者の名、姓、生年月日、写真、優先言語（[&#x200B; 多言語メール &#x200B;](../../channels/using/creating-a-multilingual-email.md) 用）などが含まれます。
* プロファイルに連絡できるチャネル。受信者のメールアドレス、携帯電話番号、オプトアウト情報が含まれます。
* 郵送先住所（[&#x200B; ダイレクトメール &#x200B;](../../channels/using/about-direct-mail.md) 用）と連絡先のタイムゾーン（[&#x200B; タイムゾーンでメッセージをスケジュール &#x200B;](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) するため）。
* アクセス認証。受信者の組織単位を示します（[&#x200B; 権限を管理 &#x200B;](../../administration/using/about-access-management.md)）。 [プロファイルの分割](../../administration/using/organizational-units.md#partitioning-profiles)も参照してください。

![](assets/profile_creation4.png)

## ログの送信とトラッキング {#sending-and-tracking-logs}

「**[!UICONTROL Sending logs]**」タブと「**[!UICONTROL Tracking logs]**」タブには、プロファイルに送信された配信のリストと、関連するすべてのトラッキングデータがグループ化されます。

送信ログとトラッキングログについて詳しくは、[&#x200B; 配信ログ &#x200B;](../../sending/using/monitoring-a-delivery.md#delivery-logs) および [&#x200B; トラッキングメッセージ &#x200B;](../../sending/using/tracking-messages.md) の節を参照してください。

## 購読 {#subscriptions}

連絡先の購読は、対応するタブに表示されます。 サービスの購読について詳しくは、[&#x200B; この節 &#x200B;](../../audiences/using/about-subscriptions.md) を参照してください。

「**[!UICONTROL Mobile App Subscriptions]**」タブは、プッシュ通知を参照します。 詳しくは、[&#x200B; プッシュ通知 &#x200B;](../../channels/using/about-push-notifications.md) チャネルを参照してください。
