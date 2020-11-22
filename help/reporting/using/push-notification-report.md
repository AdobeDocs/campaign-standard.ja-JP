---
solution: Campaign Standard
product: campaign
title: プッシュ通知レポート
description: すぐに使用できるプッシュ通知レポートを使用して、プッシュ通知の成功について説明します。
audience: reporting
content-type: reference
topic-tags: list-of-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# プッシュ通知レポート{#push-notification-report}

>[!CAUTION]
>
>配信のタイプに応じてデータを分割するには、 **[!UICONTROL Message type]** 指標をテーブルにドラッグ&amp;ドロップする必要があります。この場合、プッシュ通知配信です。

プッ **シュ通知** レポートは、プッシュ通知のマーケティングパフォーマンスの詳細をAdobe Campaignで示します。 このすぐに使用できるレポートは、ユーザーがプッシュ通知、モバイルアプリケーションおよび配信とやり取りする方法を理解するのに役立ちます。

プッシュトラッキングを導入するには、モバイルアプリケーションで一部の設定が必要です。詳細手順については、この [ページ](../../administration/using/push-tracking.md) を参照してください。

![](assets/dynamic_report_push.png)

各表は、数値の概要とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

最初の表 **プッシュ通知エンゲージメントの概要** は、次の3つのカテゴリに分かれます。日別、モバイルアプリ別、配信別 配信に対する受信者の反応性に使用できるデータが含まれます。

* **[!UICONTROL Processed/sent]**:送信されたプッシュ通知の合計数です。
* **[!UICONTROL Delivered]**:正常に送信されたプッシュ通知の数（プッシュ通知の送信総数に関連）。
* **[!UICONTROL Impressions]**:プッシュ通知がデバイスに配信され、通知センターに何も操作されなかった回数です。 ほとんどの場合、インプレッション数は配信された数と同じになります。 これにより、デバイスはメッセージを取得し、その情報をサーバーに中継します。
* **[!UICONTROL Unique impressions]**:受信者別のインプレッション数。
* **[!UICONTROL Click through rate]**:プッシュ通知に対して何らかのアクションを起こしたユーザーの割合。
* **[!UICONTROL Open rate]**:開かれているプッシュ通知の割合。

![](assets/dynamic_report_push_2.png)

2つ目のテーブル **プッシュ通知の「Clicks &amp; opens** 」は、次の3つのカテゴリに分かれます。日別、モバイルアプリ別、配信別 配信ごとの受信者動作に使用できるデータが含まれます。

* **[!UICONTROL Impressions]**:受信者が表示したプッシュ通知の合計です。
* **[!UICONTROL Unique impressions]**:受信者別のインプレッション数。
* **[!UICONTROL Click]**:プッシュ通知がデバイスに配信され、ユーザーがクリックした回数。 ユーザーは、通知を表示したいと考え、その後プッシュオープン追跡に移動するか、削除したいと考えていました。
* **[!UICONTROL Unique clicks]**:一意のユーザーがプッシュ通知と対話する回数、例えば通知やボタンのクリック数。
* **[!UICONTROL Open]**:デバイスに配信され、ユーザーがアプリを開くためにクリックしたプッシュ通知の合計数です。 これはプッシュクリックと似ていますが、通知が閉じられた場合にプッシュ開くはトリガーされません。
* **[!UICONTROL Unique Opens]**:配信を開いた受信者の数です。

