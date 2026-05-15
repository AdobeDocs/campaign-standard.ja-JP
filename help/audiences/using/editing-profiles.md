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
TQID: https://experienceleague.adobe.com/hTCybEq1Hfh1fxXd5JGjRWmGZXzXNebtf42NZnEMZ5c
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 315
ht-degree: 7%

---

# プロファイルの編集{#editing-profiles}

## プロファイルプロパティへのアクセス {#accessing-profile-properties}

既存のプロファイルを編集し、関連するデータを参照したり、変更したりするには、次の手順を実行します。

1. Adobe Campaignのホームページで、**[!UICONTROL Customer profiles]** カードまたは&#x200B;**[!UICONTROL Profiles]** タブをクリックします。
1. 連絡先を選択します。
1. **[!UICONTROL Edit profile properties]** アイコンをクリックして、プロファイルの詳細情報にアクセスします。

   ![](assets/profile_creation2.png)

   プロファイルのプロパティウィンドウには、すべてのプロファイル情報にアクセスできるタブがいくつか用意されています。

   Adobe Campaignで作成または拡張されたカスタムリソースによっては、他のタブが表示されることもあります。 カスタムリソースについて詳しくは、[ カスタムリソースについて](../../developing/using/data-model-concepts.md)を参照してください。

   >[!NOTE]
   >
   >**[!UICONTROL Traceability]** セクションを除き、**[!UICONTROL General]** タブ内の情報のみを変更できます。

Adobe Campaign Standard APIを使用してプロファイルを編集することもできます。 詳しくは、[該当するドキュメント](../../api/using/updating-profiles.md)を参照してください。

関連トピック：

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [受信者のタイムゾーンでの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般的なプロファイルデータ {#general-profile-data}

「**[!UICONTROL General]**」タブには、プロファイルに関する次の情報がグループ化されます。

* 連絡先情報：受信者の名前、姓、生年月日、写真、優先言語（[多言語メール ](../../channels/using/creating-a-multilingual-email.md)用）など
* 受信者のメールアドレス、携帯電話番号、オプトアウト情報を含む、プロファイルに連絡できるチャネル。
* 郵送先住所（[ ダイレクトメール ](../../channels/using/about-direct-mail.md)の場合）、連絡先のタイムゾーン（[ タイムゾーン内のメッセージのスケジュール ](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)まで）。
* アクセス認証。受信者の組織単位を示します（[権限の管理](../../administration/using/about-access-management.md)まで）。 [プロファイルの分割](../../administration/using/organizational-units.md#partitioning-profiles)も参照してください。

![](assets/profile_creation4.png)

## ログの送信と追跡 {#sending-and-tracking-logs}

「**[!UICONTROL Sending logs]**」タブと「**[!UICONTROL Tracking logs]**」タブには、プロファイルに送信された配信のリストと、関連するすべてのトラッキングデータがグループ化されます。

ログの送信とトラッキングについて詳しくは、[配信ログ ](../../sending/using/monitoring-a-delivery.md#delivery-logs)および[ トラッキングメッセージ ](../../sending/using/tracking-messages.md)の節を参照してください。

## 購読 {#subscriptions}

連絡先のサブスクリプションは、対応するタブに一覧表示されます。 サービスの購読について詳しくは、[この節](../../audiences/using/about-subscriptions.md)を参照してください。

「**[!UICONTROL Mobile App Subscriptions]**」タブは、プッシュ通知を参照します。 詳しくは、[ プッシュ通知](../../channels/using/about-push-notifications.md) チャネルを参照してください。
