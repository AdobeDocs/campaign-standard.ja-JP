---
title: メッセージを送信するための主要な手順
description: Adobe Campaign でメッセージを作成して送信するには、次の手順に従います。
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Overview
role: User
level: Beginner
exl-id: a903d7e2-7654-46b3-bc61-4653a065faad
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 14%

---

# メッセージを送信するための主な手順{#key-steps-to-send-a-message}

この節では、Adobe Campaign Standardを使用してパーソナライズされたメッセージを作成し、ターゲットオーディエンスに送信する方法を学びます。

各通信チャネルの作成および設定方法に関する具体的な情報は、次の節で説明します。

* [E メールの作成](../../channels/using/creating-an-email.md)
* [SMSの作成](../../channels/using/creating-an-sms-message.md)
* [ダイレクトメール配信の作成](../../channels/using/creating-the-direct-mail.md)
* [プッシュ通知の作成](../../channels/using/preparing-and-sending-a-push-notification.md)を参照してください。
* [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)

配信のベストプラクティスについては、[配信のベストプラクティス](../../sending/using/delivery-best-practices.md)の節を参照してください。

## メッセージの作成

Campaign Standard[マーケティングアクティビティ](../../start/using/marketing-activities.md)を活用して、Eメール、SMS、ダイレクトメール、プッシュ通知またはアプリ内メッセージを作成します。

![](assets/marketing-activities.png)

メッセージは、マーケティングアクティビティリストから、または[専用のアクティビティ](../../automating/using/about-channel-activities.md)を使用したワークフローから作成できます。

![](assets/steps-channel.png)

## オーディエンスの定義

メッセージの受信者を定義します。 これをおこなうには、左側のペインの[クエリエディター](../../automating/using/editing-queries.md)を使用して、データベースに含まれるデータをフィルタリングし、オーディエンスをターゲットにするルールを作成します。

オーディエンスには、次のようなタイプがあります。

* **[!UICONTROL Target]** は、Eメールのメインターゲットです。
* **[!UICONTROL Test profiles]** は、電子メールのテストと検証に使用するプロファイルです( [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)を参照)。

![](assets/steps-audience.png)

## コンテンツの設計とパーソナライズ

**[!UICONTROL Content]**&#x200B;ブロックで、データベースのフィールドを使用して、メッセージのコンテンツを設計およびパーソナライズします。 特定のチャネルのコンテンツをデザインする方法について詳しくは、このページの上部にあるセクションを参照してください。

![](assets/steps-content.png)

## 準備とテスト

[](../../sending/using/preparing-the-send.md) メッセージを準備します。このプロセスでは、ターゲット母集団を計算し、パーソナライズされたメッセージを準備します。

![](assets/steps-prepare.png)

**メッセージを送信する前に、次の** Campaign Standard機能を使用してメッセージを確認およびテストします。プレビュー、Eメールのレンダリング、校正など詳しくは、[この節](../../sending/using/previewing-messages.md)を参照してください。

**[!UICONTROL Schedule]**&#x200B;ブロックを使用して、メッセージを送信するタイミングを定義します（[メッセージのスケジュール](../../sending/using/about-scheduling-messages.md)を参照）。

![](assets/steps-schedule.png)

## 送信と追跡

メッセージの準備が整ったら、送信を確認できます。 **[!UICONTROL Deployment]**&#x200B;ブロックは、送信の進行状況と結果を表示します。

![](assets/steps-send.png)

メッセージの配信を監視するのに役立つログがいくつか用意されています（[配信の監視](../../sending/using/monitoring-a-delivery.md)を参照）。 また、Campaign Standardの[トラッキング機能](../../sending/using/tracking-messages.md)を使用して、配信受信者の行動をトラッキングすることもできます。

![](../../sending/using/assets/tracking_logs.png)

様々な指標やグラフを使用して、メッセージの効果と、送信およびキャンペーンの推移を測定します（[レポートへのアクセス](../../reporting/using/about-dynamic-reports.md)を参照）。

![](assets/steps-reports.png)
