---
title: Adobe Campaign Standardでの配信品質の監視
description: Adobe Campaign Standardが提供するツールを使用して、プラットフォームの配信品質を監視します。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 58%

---


# 配信品質の監視{#monitor-deliverability}

Below you will find details on the **[!UICONTROL Delivery throughput]** report as well as the different monitoring tools offered by Adobe Campaign. 配信品質の監視に関する追加のガイドラインを示します。
* プラットフォーム全体で配信スループットを定期的にチェックして、元のセットアップと整合性が取れているかどうかを検証します。
* 配信テンプレートで再試行が適切に設定されていることを確認します（再試行期間が 30 分、再試行回数が 21 回以上）。
* バウンスメールボックスがアクセス可能で、アカウントの有効期限が近づいていないかを定期的に検証します。
* 各配信スループットをチェックして、配信コンテンツの有効期限と整合性が取れていることを確認します（例：「フラッシュセール」は数日ではなく、数分で配信される必要があります）。
* ウェーブを使用する場合、次のものがトリガーされる前に各ウェーブが完了するための十分な時間があることを検証します。
* エラーの数と新しい強制隔離が他の配信と整合性が取れていることをチェックします。
* 強調表示されるエラー(ブロックリスト配信ログ、DNSの問題、スパム対策ルールなど)の種類を確認するには、を注意深く調べます。

## 配信スループット {#delivery-throughput}

このレポートには、特定の期間のプラットフォーム全体の配信スループットに関する情報が含まれ、メッセージの配信速度を測定します。

詳しくは、[配信スループット](../../reporting/using/delivery-throughput.md)を参照してください。

![](assets/delivery_reports_1.png)

タイムスケールを変更して、表示する値を設定できます。

またはなど、他のレポートも使用でき **[!UICONTROL Delivery summary]** ま **[!UICONTROL Non-deliverables and bounces]**&#x200B;す。 詳しくは、 [動的レポートを参照してください](../../reporting/using/about-dynamic-reports.md)。

## 配信の監視 {#monitoring-deliveries}

メッセージダッシュボードから配信ログにアクセスできます。 **[!UICONTROL Sending logs]**、 **[!UICONTROL Exclusion logs]**、 **[!UICONTROL Exclusion causes]**、 **[!UICONTROL Tracking logs]** および **[!UICONTROL Tracked URLs]**)。 送信の詳細、除外されたターゲットとその理由、および開封数やクリック数などの追跡情報が表示されます。

詳しくは、[配信の監視](../../sending/using/monitoring-a-delivery.md)を参照してください。

![](assets/sending_delivery1.png)

## アラートの受信 {#receiving-alerts}

The **[!UICONTROL Delivery alerting]** feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries.

詳しくは、「エラー発生時にアラートを [受信する](../../sending/using/receiving-alerts-when-failures-happen.md)」を参照してください。

## Signal Spam {#signal-spam}

Signal Spam は、フランスのサービスで、フランスの ISP（Orange、SFR）用の匿名化されたフィードバックループレポートを提供します。

このサービスを使用すると、フランスの ISP のレピュテーションをフォローし、顧客のアクティビティの進化をトラッキングできます。

また、Signal Spam は、専用インターフェンスを通じてエンドユーザーが記録した直接の苦情数を提供します。これらの苦情数は、E メールアドレスデータベースから強制隔離されます。

## 250ok {#solution-250ok}

250okは、IPとドメインのブロックリスト、および評価指標を提供する監視ソリューションです。

提供される情報はリアルタイムで、これにより先を見越した支援が可能です。250ok は、アドビの配信品質の内部ツールを補完するソリューションです。
