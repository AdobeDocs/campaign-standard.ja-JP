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
ht-degree: 13%

---

# メッセージを送信するための主な手順{#key-steps-to-send-a-message}

この節では、Adobe Campaign Standardを使用して、パーソナライズされたメッセージを作成し、ターゲットオーディエンスに送信する方法について説明します。

各通信チャネルを作成および設定する方法について詳しくは、次の節を参照してください。

* [メールの作成](../../channels/using/creating-an-email.md)
* [SMS の作成](../../channels/using/creating-an-sms-message.md)
* [ダイレクトメール配信の作成](../../channels/using/creating-the-direct-mail.md)
* [ プッシュ通知の作成 ](../../channels/using/preparing-and-sending-a-push-notification.md)。
* [アプリ内メッセージの準備と送信](../../channels/using/preparing-and-sending-an-in-app-message.md)

配信のベストプラクティスについては、[ 配信のベストプラクティス ](../../sending/using/delivery-best-practices.md) の節を参照してください。

## メッセージを作成

Campaign Standard[ マーケティングアクティビティ ](../../start/using/marketing-activities.md) を活用して、メール、SMS、ダイレクトメール、プッシュ通知、アプリ内メッセージを作成します。

![](assets/marketing-activities.png)

メッセージは、マーケティングアクティビティリストまたは [ 専用アクティビティ ](../../automating/using/about-channel-activities.md) を使用したワークフローから作成できます。

![](assets/steps-channel.png)

## オーディエンスを定義

メッセージの受信者を定義します。 これを行うには、左側のパネルから [ クエリエディター ](../../automating/using/editing-queries.md) を使用して、データベースに含まれるデータをフィルタリングし、オーディエンスをターゲットにするルールを作成します。

使用できるオーディエンスには、次のようないくつかのタイプがあります。

* **[!UICONTROL Target]** はメールのメインターゲットです。
* メールのテストと検証に使用するプロファイルは **[!UICONTROL Test profiles]** のとおりです（[ テストプロファイルの管理 ](../../audiences/using/managing-test-profiles.md) を参照）。

![](assets/steps-audience.png)

## コンテンツの設計とパーソナライズ

**[!UICONTROL Content]** ブロックで、データベースのフィールドを使用して、メッセージのコンテンツを設計およびパーソナライズします。 特定のチャネルのコンテンツをデザインする方法について詳しくは、このページの上部に一覧表示されている節を参照してください。

![](assets/steps-content.png)

## 準備とテスト

[ 準備 ](../../sending/using/preparing-the-send.md) メッセージ。 このプロセスにより、ターゲット母集団が計算され、パーソナライズされたメッセージが準備されます。

![](assets/steps-prepare.png)

**プレビュー、メールのレンダリング、プルーフなど** Campaign Standardの機能を使用して送信する前に、メッセージを確認およびテストします。 詳しくは、[この節](../../sending/using/previewing-messages.md)を参照してください。

**[!UICONTROL Schedule]** ブロックを使用すると、メッセージを送信するタイミングを定義できます（[ メッセージのスケジュール設定 ](../../sending/using/about-scheduling-messages.md) を参照）。

![](assets/steps-schedule.png)

## 送信とトラッキング

メッセージの準備が整ったら、送信を確認できます。 **[!UICONTROL Deployment]** ブロックには、送信の進行状況と結果が表示されます。

![](assets/steps-send.png)

メッセージの配信を監視するのに役立つ、複数のログを使用できます（[ 配信の監視 ](../../sending/using/monitoring-a-delivery.md) を参照）。 また、Campaign Standardの [ トラッキング機能 ](../../sending/using/tracking-messages.md) を使用して、配信受信者の行動をトラッキングすることもできます。

![](../../sending/using/assets/tracking_logs.png)

様々な指標とグラフを使用して、メッセージの有効性と、送信およびキャンペーンの進化を測定します（[ レポートへのアクセス ](../../reporting/using/about-dynamic-reports.md) を参照）。

![](assets/steps-reports.png)
