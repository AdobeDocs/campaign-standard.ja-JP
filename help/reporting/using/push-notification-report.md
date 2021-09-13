---
title: プッシュ通知レポート
description: 標準のプッシュ通知レポートを使用して、プッシュ通知の成功を確認できます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---

# プッシュ通知レポート{#push-notification-report}

>[!CAUTION]
>
>**[!UICONTROL Message type]**&#x200B;指標をテーブルにドラッグ&amp;ドロップして、配信タイプ（この場合はプッシュ通知配信）に応じてデータを分割する必要があります。

**プッシュ通知**&#x200B;レポートは、Adobe Campaignでのプッシュ通知のマーケティングパフォーマンスの詳細を提供します。 この標準レポートは、ユーザーがプッシュ通知、モバイルアプリケーション、配信とやり取りする方法を理解するのに役立ちます。

プッシュトラッキングを実装するには、モバイルアプリケーションで一部の設定が必要です。詳細な手順については、この[ページ](../../administration/using/push-tracking.md)を参照してください。

![](assets/dynamic_report_push.png)

各テーブルは、概要の数値とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

最初の表&#x200B;**プッシュ通知のエンゲージメントの概要**&#x200B;は、次の3つのカテゴリに分かれています。日別、モバイルアプリ別、および配信別。 配信に対する受信者の反応度に使用可能なデータが含まれます。

* **[!UICONTROL Processed/sent]**:送信されたプッシュ通知の合計数。
* **[!UICONTROL Delivered]**:送信されたプッシュ通知の合計数に関する、正常に送信されたプッシュ通知の数。
* **[!UICONTROL Impressions]**:プッシュ通知がデバイスに配信され、通知センターに何も残されていない回数。ほとんどの場合、インプレッション数は配信された数に似ている必要があります。 これにより、デバイスはメッセージを取得し、その情報をサーバーにリレーします。
* **[!UICONTROL Unique impressions]**:受信者別のインプレッション数。
* **[!UICONTROL Click through rate]**:プッシュ通知を操作したユーザーの割合。
* **[!UICONTROL Open rate]**:開封されたプッシュ通知の割合。

![](assets/dynamic_report_push_2.png)

2つ目の表&#x200B;**プッシュ通知のクリック&amp;オープン**&#x200B;は、次の3つのカテゴリに分かれています。日別、モバイルアプリ別、および配信別。 受信者の配信ごとの行動に使用できるデータが含まれます。

* **[!UICONTROL Impressions]**:受信者が確認したプッシュ通知の合計。
* **[!UICONTROL Unique impressions]**:受信者別のインプレッション数。
* **[!UICONTROL Click]**:ユーザーがデバイスにプッシュ通知を配信し、クリックした回数。ユーザーは、通知を表示し、プッシュ開封トラッキングに移動するか、閉じます。
* **[!UICONTROL Unique clicks]**:ユニークユーザーがプッシュ通知を操作した回数（通知またはボタンのクリックなど）。
* **[!UICONTROL Open]**:デバイスに配信され、ユーザーがクリックしてアプリを開いたプッシュ通知の合計数。これは、プッシュクリックと似ていますが、通知が閉じられた場合にプッシュオープンがトリガーされない点が異なります。
* **[!UICONTROL Unique Opens]**:配信を開封した受信者の数。
