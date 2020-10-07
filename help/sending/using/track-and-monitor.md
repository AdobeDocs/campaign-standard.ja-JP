---
title: メッセージのトラッキングと監視
seo-title: メッセージのトラッキングと監視
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 44%

---


# トラッキングと監視 {#track-and-monitor}

「送信」ボタンをクリックしましたか。何が起こるかを見てみましょう。配信の送信後、Adobe Campaign では、送信済みメッセージをトラッキングして、配信に対する受信者の反応を確認できます。これは、今後の送信を改善し、次のキャンペーンを最適化するのに役立ちます。

## 配信の監視 {#monitoring-deliveries}

キャンペーンを制御するには、メッセージが実際に受信者に配信されたことを確認する必要があります。

**ヒント**

* 配信ログ内のメッセージのステータスを制御できます。

* 配信の成功または失敗を追跡するために、Adobe Campaignは重要なシステムアクティビティをユーザーに通知する電子メール警告システムを提供します。

* メッセージダッシュボードから、このメッセージに関する複数のレポートにアクセスできます。

For more this, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

## トラッキング {#tracking-deliveries}

ターゲット設定されたプロファイルの行動をより深く知るには、配信に対するユーザーの反応を追跡します。受信、開封、リンクのクリック、購読解除など 配信の「 **トラッキングログ** 」タブを参照してください。

**ヒント**：メッセージトラッキングは、デフォルトで有効になっています。URL を設定するには、配信ウィザードの下部のセクションで「URL を表示」オプションを選択します。メッセージの URL ごとに、トラッキングを有効化するかどうかを選択できます。

For more on this, refer to the [Tracking messages](../../sending/using/tracking-messages.md) section and the [Tracking indicators](../../reporting/using/tracking-indicators.md) description.

## 動的レポート {#dyn-reports}

動的レポートを使用すると、完全にカスタマイズ可能なリアルタイムレポートを作成し、キャンペーンを監視できます。 Dimension、指標およびビジュアライゼーションを使用すると、受信者に対するキャンペーンの影響と成功を測定できます。

**ヒント** — 組み込みのレポートはキャンペーンを監視できますが、指標やディメンションをレポートにドラッグ&amp;ドロップすることでカスタマイズすることもできます。

For more on this, refer to the [Reporting guide](../../reporting/using/about-dynamic-reports.md).

## ホットクリック

ホットクリック数レポートは、メッセージの内容（HTMLやテキスト）と各リンクのクリック数の割合を表示します。 各動的コンテンツのクリックの割合を表示することで、受信者に最も訴えるコンテンツを測定できます。

この詳細については、 [ホットクリックレポートを参照してください](../../reporting/using/hot-clicks.md)。

## 配信のパフォーマンスのヒント {#performance-tips}

* 配信を失敗した状態のままインスタンス上で放置すると、一時テーブルが維持され、パフォーマンスに影響が生じるため、配信を失敗した状態のまま放置しないでください。

* アドレスの品質を維持するため、不要になった配信やアクティブでない受信者はデータベースから削除してください。

* 大規模な配信を同時にスケジュールしないようにしてください。負荷がシステム全体で均等に分散されるまでには、5～10 分かかることがあります。

**関連トピック：**

* [エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)
* [レポート](../../reporting/using/about-dynamic-reports.md)
