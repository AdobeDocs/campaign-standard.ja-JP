---
title: プッシュ通知レポート
description: プッシュ通知の標準レポートを使用すると、プッシュ通知が成功した場合の動作を確認できます。
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
>配信タイプに応じてデータを分割するには、**[!UICONTROL Message type]** の指標をテーブルにドラッグ&amp;ドロップする必要があります。この場合、プッシュ通知配信です。

**プッシュ通知** レポートは、Adobe Campaignでのプッシュ通知のマーケティングパフォーマンスの詳細を提供します。 この標準レポートを使用すると、ユーザーがプッシュ通知、モバイルアプリケーション、配信とやり取りする方法を理解できます。

モバイルアプリケーションでプッシュトラッキングを実装するには、いくつかの設定が必要です。詳しい手順については、この [&#x200B; ページ &#x200B;](../../administration/using/push-tracking.md) を参照してください。

![](assets/dynamic_report_push.png)

各テーブルは、概要番号とグラフで表されます。 それぞれのビジュアライゼーション設定で、詳細の表示方法を変更できます。

最初の表 **プッシュ通知エンゲージメントの概要** は、日別、モバイルアプリ別および配信別の 3 つのカテゴリに分類されています。 配信に対する受信者の反応に使用できるデータが含まれます。

* **[!UICONTROL Processed/sent]**：送信されたプッシュ通知の合計数。
* **[!UICONTROL Delivered]**：送信されたプッシュ通知の合計数に対して、正常に送信されたプッシュ通知の数。
* **[!UICONTROL Impressions]**：プッシュ通知がデバイスに配信され、通知センターにそのまま残った回数。 ほとんどの場合、インプレッション数は、配信された数に類似している必要があります。 これにより、デバイスがメッセージを取得し、その情報をサーバーに中継します。
* **[!UICONTROL Unique impressions]**：受信者によるインプレッション数。
* **[!UICONTROL Click through rate]**：プッシュ通知でインタラクションを行ったユーザーの割合。
* **[!UICONTROL Open rate]**：開封されたプッシュ通知の割合。

![](assets/dynamic_report_push_2.png)

2 つ目の表 **プッシュ通知のクリック数と開封数** は、日別、モバイルアプリ別および配信別の 3 つのカテゴリに分類されます。 配信ごとの受信者の行動に使用できるデータが含まれます。

* **[!UICONTROL Impressions]**：受信者に表示されたプッシュ通知の合計。
* **[!UICONTROL Unique impressions]**：受信者によるインプレッション数。
* **[!UICONTROL Click]**：ユーザーがプッシュ通知をデバイスに配信し、クリックした回数。 ユーザーは通知を表示しようとしていましたが、この通知はプッシュオープントラッキングに移動されるか、拒否されます。
* **[!UICONTROL Unique clicks]**：一意のユーザーがプッシュ通知を操作した回数（通知またはボタンのクリックなど）。
* **[!UICONTROL Open]**：デバイスに配信され、ユーザーがクリックしてアプリを開いたプッシュ通知の合計数。 これは、プッシュクリックと似ていますが、通知が閉じられた場合にプッシュオープンがトリガーされない点が異なります。
* **[!UICONTROL Unique Opens]**：配信されたメッセージを開いた受信者の数。
