---
title: プッシュ通知レポート
description: 標準のプッシュ通知レポートを使用して、プッシュ通知の成功について学びます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# プッシュ通知レポート{#push-notification-report}

>[!CAUTION]
>
>なお、 **[!UICONTROL Message type]** 指標をテーブルに追加して、配信タイプに応じてデータを分割します。この場合は、プッシュ通知配信です。

The **プッシュ通知** レポートには、Adobe Campaignでのプッシュ通知のマーケティングパフォーマンスの詳細が表示されます。 この標準レポートは、ユーザーがプッシュ通知、モバイルアプリケーションおよび配信をどのように操作するかを理解するのに役立ちます。

プッシュトラッキングを実装するには、モバイルアプリケーションで一部の設定が必要です。これを参照してください。 [ページ](../../administration/using/push-tracking.md) を参照してください。

![](assets/dynamic_report_push.png)

各テーブルは、数値の概要とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

最初のテーブル **プッシュ通知エンゲージメントの概要** は、日別、モバイルアプリ別、配信別の 3 つのカテゴリに分類されます。 配信に対する受信者の反応に使用できるデータが含まれます。

* **[!UICONTROL Processed/sent]**：送信されたプッシュ通知の合計数。
* **[!UICONTROL Delivered]**：送信されたプッシュ通知の合計数に関する、正常に送信されたプッシュ通知の数。
* **[!UICONTROL Impressions]**：プッシュ通知がデバイスに配信され、通知センターに残された回数。 ほとんどの場合、インプレッション数は配信された数に類似している必要があります。 これにより、デバイスはメッセージを取得し、その情報をサーバーにリレーします。
* **[!UICONTROL Unique impressions]**：受信者別のインプレッション数。
* **[!UICONTROL Click through rate]**：プッシュ通知を操作したユーザーの割合。
* **[!UICONTROL Open rate]**：開かれたプッシュ通知の割合。

![](assets/dynamic_report_push_2.png)

2 番目のテーブル **プッシュ通知のクリック数および開封数** は、日別、モバイルアプリ別、配信別の 3 つのカテゴリに分類されます。 配信ごとの受信者の行動に使用できるデータが含まれます。

* **[!UICONTROL Impressions]**：受信者が閲覧したプッシュ通知の合計です。
* **[!UICONTROL Unique impressions]**：受信者別のインプレッション数。
* **[!UICONTROL Click]**：ユーザーがデバイスにプッシュ通知を配信し、クリックした回数。 ユーザーは、通知を表示したかったので、プッシュ開封トラッキングに移動するか、解除します。
* **[!UICONTROL Unique clicks]**：個別ユーザーがプッシュ通知を操作した回数（通知またはボタンのクリック数など）。
* **[!UICONTROL Open]**：デバイスに配信され、ユーザーがクリックしたプッシュ通知の合計数。これによりアプリが開かれました。 これは、プッシュクリックと似ていますが、通知が閉じられた場合にプッシュオープンがトリガーされない点が異なります。
* **[!UICONTROL Unique Opens]**：配信を開封した受信者の数。
