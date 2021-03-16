---
solution: Campaign Standard
product: campaign
title: メッセージを送信するための主要な手順
description: Adobe Campaign でメッセージを作成して送信するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: 概要
role: 開業医
level: 初心者
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 12%

---


# メッセージを送信するための主要な手順{#key-steps-to-send-a-message}

この節では、Adobe Campaign Standardを使用してターゲットオーディエンスにパーソナライズしたメッセージを作成し、送信する方法を学びます。

各通信チャネルの作成および設定方法に関する具体的な情報は、次のセクションで確認できます。

* [E メールの作成](../../channels/using/creating-an-email.md)
* [SMSの作成](../../channels/using/creating-an-sms-message.md)
* [ダイレクトメール配信の作成](../../channels/using/creating-the-direct-mail.md)
* [プッシュ通知の作成](../../channels/using/preparing-and-sending-a-push-notification.md)。
* [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)

配信のベストプラクティスについては、[配信のベストプラクティス](../../sending/using/delivery-best-practices.md)のセクションを参照してください。

## メッセージの作成

Campaign Standard[マーケティングアクティビティ](../../start/using/marketing-activities.md)を活用して、電子メール、SMS、ダイレクトメール、プッシュ通知、またはアプリ内メッセージを作成します。

![](assets/marketing-activities.png)

メッセージは、マーケティングアクティビティリストから、または[専用アクティビティ](../../automating/using/about-channel-activities.md)を使用したワークフローから作成できます。

![](assets/steps-channel.png)

## オーディエンスの定義

メッセージの受信者を定義します。 これを行うには、左側のペインの[クエリエディター](../../automating/using/editing-queries.md)を使用してデータベースに含まれるデータをフィルタリングし、ルールを構築してオーディエンスをターゲットします。

使用できるオーディエンスにはいくつかの種類があります。

* **[!UICONTROL Target]** は、電子メールのメインターゲットです。
* **[!UICONTROL Test profiles]** は、電子メールのテストと検証に使用するプロファイルです(テストプロファイルの [管理を参照](../../audiences/using/managing-test-profiles.md))。

![](assets/steps-audience.png)

## コンテンツの設計とパーソナライズ

**[!UICONTROL Content]**&#x200B;ブロックで、データベースのフィールドを使用して、メッセージの内容を設計およびパーソナライズします。 特定のチャネル向けにコンテンツをデザインする方法について詳しくは、このページの上部にあるセクションを参照してください。

![](assets/steps-content.png)

## 準備とテスト

[メッセージ](../../sending/using/preparing-the-send.md) を準備します。このプロセスでは、ターゲットの母集団が計算され、パーソナライズされたメッセージが準備されます。

![](assets/steps-prepare.png)

**メッセージを送信する前に、次のCampaign Standard機能を使用してメッセージを確認し、** テストしてください。プレビュー、電子メールのレンダリング、校正など詳しくは、[こちらの節](../../sending/using/previewing-messages.md)を参照してください。

**[!UICONTROL Schedule]**&#x200B;ブロックを使用して、メッセージを送信するタイミングを定義します（[メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)を参照）。

![](assets/steps-schedule.png)

## 送信と追跡

メッセージの準備が整ったら、送信を確認できます。 **[!UICONTROL Deployment]**&#x200B;ブロックは送信の進行状況と結果を表示します。

![](assets/steps-send.png)

メッセージの配信を監視するのに役立つログがいくつかあります([配信の監視](../../sending/using/monitoring-a-delivery.md)を参照)。 また、Campaign Standardの[追跡機能](../../sending/using/tracking-messages.md)により、配信受信者の動作を追跡することもできます。

![](../../sending/using/assets/tracking_logs.png)

様々な指標やグラフを通して、メッセージの有効性と送信やキャンペーンの発展を測定します（[レポートへのアクセス](../../reporting/using/about-dynamic-reports.md)を参照）。

![](assets/steps-reports.png)
