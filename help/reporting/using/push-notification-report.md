---
title: プッシュ通知レポート
description: すぐに使用できるプッシュ通知レポートを使用して、プッシュ通知の成功を確認します。
page-status-flag: 非活性化の
uuid: 5b121a37-1c09-4749-a409-6989978ddc4c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: レポートのリスト
discoiquuid: a425cd59-edfd-42c5-a6bd-38773c353ff0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# プッシュ通知レポート{#push-notification-report}

>[!CAUTION]
>
>配信タイプに応じてデータを分割するには、指標をテーブルにドラッ **[!UICONTROL Message type]** グ&amp;ドロップする必要があります。この場合、プッシュ通知配信が行われます。

プッシュ **通知レポートは** 、Adobe Campaignでのプッシュ通知のマーケティングパフォーマンスの詳細を提供します。 このすぐに使用できるレポートは、ユーザーがプッシュ通知、モバイルアプリケーションおよび配信をどのように操作するかを把握するのに役立ちます。

プッシュトラッキングを実装するには、モバイルアプリケーションで一部の設定が必要です。詳細手順につ [いては](https://helpx.adobe.com/campaign/kb/push-tracking.html) 、このページを参照してください。

![](assets/dynamic_report_push.png)

各表は、概要番号とグラフで表されます。 各ビジュアライゼーション設定での詳細の表示方法を変更できます。

最初の表「プッシュ通 **知エンゲージメントの概要** 」は、次の3つのカテゴリに分かれます。日別、モバイルアプリ別、配信別 配信に対する受信者の反応性に使用できるデータが含まれます。

* **[!UICONTROL Processed/sent]**:送信されたプッシュ通知の合計数です。
* **[!UICONTROL Delivered]**:送信されたプッシュ通知の合計数に関連して正常に送信されたプッシュ通知の数です。
* **[!UICONTROL Impressions]**:プッシュ通知がデバイスに配信され、通知センターに何も操作されなかった回数です。 ほとんどの場合、インプレッション数は配信された数と同じになります。 これにより、デバイスはメッセージを受け取り、その情報をサーバーにリレーできます。
* **[!UICONTROL Unique impressions]**:受信者別のインプレッション数。
* **[!UICONTROL Click through rate]**:プッシュ通知に対して何らかの操作を行ったユーザーの割合。
* **[!UICONTROL Open rate]**:開かれているプッシュ通知の割合。

![](assets/dynamic_report_push_2.png)

2つ目の表「プッ **シュ通知のクリック数** &amp;オープン数」は、次の3つのカテゴリに分かれています。日別、モバイルアプリ別、配信別 配信ごとの受信者の行動に使用できるデータが含まれます。

* **[!UICONTROL Impressions]**:受信者が閲覧したプッシュ通知の合計です。
* **[!UICONTROL Unique impressions]**:受信者別のインプレッション数。
* **[!UICONTROL Click]**:プッシュ通知がデバイスに配信され、ユーザーがクリックした回数。 ユーザーが通知を表示し、その通知がプッシュオープン追跡に移動されるか、通知を閉じる必要があった。
* **[!UICONTROL Unique clicks]**:一意のユーザーがプッシュ通知を操作する回数（例：通知またはボタンのクリック）。
* **[!UICONTROL Open]**:デバイスに配信され、ユーザーがアプリを開くためにクリックしたプッシュ通知の合計数です。 これはプッシュクリックに似ていますが、通知が閉じられた場合に「プッシュ開く」がトリガーされない点が異なります。
* **[!UICONTROL Unique Opens]**:配信を開いた受信者の数。

