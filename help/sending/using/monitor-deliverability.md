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
source-git-commit: 1d5bb21ab16df87e268b9eabe92965be1b052556

---


# 配信品質の監視{#monitor-deliverability}

以下に、レポートの詳細と、Adobe Campaign **[!UICONTROL Delivery throughput]** が提供する様々な監視ツールについて説明します。 配信品質の監視に関するその他のガイドラインを次に示します。
* プラットフォーム全体の配信スループットを定期的にチェックし、元の設定と一致しているかどうかを確認します。
* 配信テンプレートで、再試行が正しく設定されていることを確認します（再試行期間は30分、再試行回数は20回を超える）。
* バウンスメールボックスがアクセス可能で、アカウントの期限が切れないことを定期的に確認します。
* 各配信スループットをチェックして、配信コンテンツの有効性(例：「flash sales」は、日単位ではなく分単位で配信する必要があります。
* 波を使用する場合は、各波が次の波がトリガされる前に完了するのに十分な時間があることを確認します。
* エラーの数と新しい検疫の数が他の配信と一致していることを確認します。
* 配信ログを詳細に調べて、強調表示されているエラーの種類（灰色または黒のリスト、DNSの問題、スパム対策ルールなど）を確認します。

## 配信スループット {#delivery-throughput}

このレポートには、特定の期間のプラットフォーム全体の配信スループットに関する情報が含まれ、メッセージが配信される速度を測定します。

詳しくは、「配信スループット」を参 [照してください](../../reporting/using/delivery-throughput.md)。

![](assets/delivery_reports_1.png)

タイムスケールを変更して、表示する値を設定できます。

またはなど、他のレポートも使用で **[!UICONTROL Delivery summary]** きま **[!UICONTROL Non-deliverables and bounces]**&#x200B;す。 詳しくは、動的レポートを参照し [てください](../../reporting/using/about-dynamic-reports.md)。

## 配信の監視 {#monitoring-deliveries}

メッセージダッシュボードから、配信ログにアクセスできます。 **[!UICONTROL Sending logs]**、 **[!UICONTROL Exclusion logs]**、 **[!UICONTROL Exclusion causes]**、 **[!UICONTROL Tracking logs]** 、 **[!UICONTROL Tracked URLs]**、 送信の詳細、ターゲットが除外された理由、および開封数やクリック数などの追跡情報が表示されます。

詳しくは、「配信の監視」を [参照してください](../../sending/using/monitoring-a-delivery.md)。

![](assets/sending_delivery1.png)

## アラートの受信 {#receiving-alerts}

この機 **[!UICONTROL Delivery alerting]** 能はアラート管理システムで、ユーザーのグループは、配信の実行に関する情報を含む通知を自動的に受信できます。

詳しくは、エラー発生時のアラ [ートの受信を参照してください](../../sending/using/receiving-alerts-when-failures-happen.md)。

## 信号スパム {#signal-spam}

シグナルスパムは、フランスのISP(Orange、SFR)に匿名のフィードバックループレポートを提供するフランスのサービスです。

このサービスを使用すると、フランスのISPの評判に従って、顧客の活動の進化を追跡できます。

シグナルスパムは、エンドユーザーが専用のインターフェイスを通じてログインするという直接の苦情も提供します。 その後、その苦情は電子メールアドレスデータベースから隔離される。

## 250ok {#solution-250ok}

250okは、IP、ドメインのブラックリスト、評判のインジケータを提供する監視ソリューションです。

提供される情報はリアルタイムであり、プロアクティブな支援が可能です。 250okは、アドビの提供品質内部ツールを補完するソリューションです。
