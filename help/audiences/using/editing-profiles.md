---
solution: Campaign Standard
product: campaign
title: プロファイルの編集
description: 既存のプロファイルを編集し、連絡先情報、優先チャネル、トラッキングログ、購読などにアクセスする方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: プロファイル
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 12%

---

# プロファイルの編集{#editing-profiles}

## プロファイルプロパティへのアクセス {#accessing-profile-properties}

既存のプロファイルを編集し、そのプロファイルに関連付けられたデータを調べたり、変更したりするには、次の手順に従います。

1. Adobe Campaign ホームページで、**[!UICONTROL Customer profiles]**&#x200B;カードまたは「**[!UICONTROL Profiles]**」タブをクリックします。
1. 連絡先を選択します。
1. **[!UICONTROL Edit profile properties]**&#x200B;アイコンをクリックして、プロファイルの詳細情報にアクセスします。

   ![](assets/profile_creation2.png)

   プロファイルのプロパティウィンドウには、すべてのプロファイル情報にアクセスできるタブがいくつか用意されています。

   Adobe Campaignで作成または拡張されたカスタムリソースに応じて、その他のタブも表示される場合があります。 カスタムリソースの詳細については、[カスタムリソースについて](../../developing/using/data-model-concepts.md)を参照してください。

   >[!NOTE]
   >
   >**[!UICONTROL General]**&#x200B;タブの情報は、**[!UICONTROL Traceability]**&#x200B;セクション以外は変更できません。

Profilesの編集は、Adobe Campaign Standard APIを使用しておこなうこともできます。 詳しくは、[該当するドキュメント](../../api/using/updating-profiles.md)を参照してください。

関連トピック：

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [受信者のタイムゾーンでの送信](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## 一般的なプロファイルデータ {#general-profile-data}

**[!UICONTROL General]**&#x200B;タブは、プロファイルに関する次の情報をグループ化します。

* 連絡先情報。受信者の名、姓、生年月日、写真、優先言語（[多言語Eメール](../../channels/using/creating-a-multilingual-email.md)の場合）などが含まれます。
* 受信者のEメールアドレス、携帯電話番号、オプトアウト情報を含む、プロファイルに連絡できるチャネル。
* 郵送先住所（[ダイレクトメール](../../channels/using/about-direct-mail.md)の場合）と、連絡先のタイムゾーン（[へのタイムゾーン](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)でメッセージをスケジュール）を入力します。
* アクセス認証。受信者の組織単位を示します（[権限の管理](../../administration/using/about-access-management.md)）。 [プロファイルの分割](../../administration/using/organizational-units.md#partitioning-profiles)も参照してください。

![](assets/profile_creation4.png)

## ログの送信とトラッキング {#sending-and-tracking-logs}

「**[!UICONTROL Sending logs]**」タブと「**[!UICONTROL Tracking logs]**」タブは、プロファイルに送信された配信と、関連するすべてのトラッキングデータのリストをグループ化します。

送信ログとトラッキングログについて詳しくは、配信ログ](../../sending/using/monitoring-a-delivery.md#delivery-logs)と[トラッキングメッセージ](../../sending/using/tracking-messages.md)の節を参照してください。[

## 購読 {#subscriptions}

連絡先の購読が対応するタブに表示されます。 サービスのサブスクリプション購入について詳しくは、[この節](../../audiences/using/about-subscriptions.md)を参照してください。

「**[!UICONTROL Mobile App Subscriptions]**」タブは、プッシュ通知を参照します。 詳しくは、[プッシュ通知](../../channels/using/about-push-notifications.md)チャネルを参照してください。
