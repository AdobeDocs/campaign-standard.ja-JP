---
title: プッシュ通知レポート
description: プッシュ通知の標準レポートでは、プッシュ通知の成功を確認できます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
TQID: https://experienceleague.adobe.com/Z7fXMSiDxpF6LXWMV2aYc71UvOYWlUzyOv8TS6ogS7k
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 389
ht-degree: 53%

---

# プッシュ通知レポート{#push-notification-report}

>[!CAUTION]
>
>配信タイプ（この場合はプッシュ通知配信）に応じてデータを分割するには、**[!UICONTROL Message type]**&#x200B;指標をテーブルにドラッグ&amp;ドロップする必要があることに注意してください。

**プッシュ通知**&#x200B;レポートは、Adobe Campaign におけるプッシュ通知のマーケティングパフォーマンスの詳細を提供します。 この標準レポートを使用すると、ユーザーがプッシュ通知、モバイルアプリケーション、配信に対してどのようなアクションを起こしているのかを理解できます。

プッシュトラッキングを実装するには、モバイルアプリケーションで一部の設定が必要です。詳細な手順については、この[ ページ ](../../administration/using/push-tracking.md)を参照してください。

![](assets/dynamic_report_push.png)

各テーブルは、概要の数値とグラフで表されています。 それぞれのビジュアライゼーション設定で、詳細の表示方法を変更できます。

最初のテーブルの&#x200B;**プッシュ通知エンゲージメントの概要**&#x200B;は、日別、モバイルアプリ別および配信別の 3 つのカテゴリに分類されています。 カテゴリには、配信に対する受信者の反応についての次のような利用可能なデータが含まれます。

* **[!UICONTROL Processed/sent]**：送信されたプッシュ通知の合計数。
* **[!UICONTROL Delivered]**：送信されたプッシュ通知の合計数に対して、正常に送信されたプッシュ通知の数。
* **[!UICONTROL Impressions]**: プッシュ通知がデバイスに配信され、通知センターで操作されないままになっている回数。 ほとんどの場合、インプレッション数は、配信された数とほぼ同じになります。 数が一致することで、デバイスがメッセージを取得して、その情報をサーバーに中継したことを確認できます。
* **[!UICONTROL Unique impressions]**：受信者によるインプレッション数。
* **[!UICONTROL Click through rate]**: プッシュ通知を操作したユーザーの割合。
* **[!UICONTROL Open rate]**：開封されたプッシュ通知の割合。

![](assets/dynamic_report_push_2.png)

2 つ目のテーブルの&#x200B;**プッシュ通知のクリック数および開封数**&#x200B;は、日別、モバイルアプリ別および配信別の 3 つのカテゴリに分類されます。 カテゴリには、配信ごとの受信者の行動に関する利用可能なデータが含まれます。

* **[!UICONTROL Impressions]**：受信者が確認したプッシュ通知の合計。
* **[!UICONTROL Unique impressions]**：受信者によるインプレッション数。
* **[!UICONTROL Click]**: プッシュ通知がデバイスに配信され、ユーザーがクリックした回数。 ユーザーが通知を表示（通知はその後プッシュ開封トラッキングに移動します）するか、通知を拒否します。
* **[!UICONTROL Unique clicks]**：一意のユーザーがプッシュ通知を操作した回数（通知またはボタンのクリックなど）。
* **[!UICONTROL Open]**: デバイスに配信され、ユーザーがクリックしてアプリを開いたプッシュ通知の合計数。 プッシュクリックと似ていますが、プッシュ開封は、通知が解除された場合はトリガーされません。
* **[!UICONTROL Unique Opens]**：配信を開いた受信者の数。
