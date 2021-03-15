---
solution: Campaign Standard
product: campaign
title: ドメイン別の分類
description: '[ドメイン別の分類]の標準レポートを使用すると、顧客の各ドメインに応じた配信のパフォーマンスデータを知ることができます。'
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: レポート
role: リーダー
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 4%

---


# ドメイン別の分類{#breakdown-by-domains}

このレポートには、電子メール配信のオーディエンスに表示される各ドメインのパフォーマンスデータが含まれます。 キャンペーンレポートまたはプログラムレポートの場合は、パフォーマンスデータを複数のオーディエンスで使用できます。 このデータを使用すると、特定のイベントに対する各ドメインの動作を分析できます。 例えば、リンク表示、ブロックリスト上のURLなど。

![](assets/delivery_reports_6.png)

テーブル&#x200B;**ブロードキャスト統計**&#x200B;には、各ドメインで発生した可能性のあるエラーに関して使用可能なデータが含まれます。例：

* **処理済み/送信済み**:送信された電子メールの数。
* **配信済み**:配信された電子メールの数。
* **バウンス+エラー**:配信できなかったメッセージの数です。
* **ハードバウンス**:誤った電子メールアドレスなど、永続的なエラーの合計数です。
* **ソフトバウンス**:完全なインボックスなどの一時エラーの合計数です。

2つ目のテーブル&#x200B;**トラッキング統計情報**&#x200B;には、配信に対する受信者の反応性に使用できる次のようなデータが含まれます。

* **配信済み**:配信された電子メールの数
* **開く**:配信でメッセージが開かれた回数。
* **クリック**:配信内のコンテンツがクリックされた回数。
* **登録解除**:購読リンクのクリック数。
* **ミラーページ**:ミラーページリンクのクリック数。
* **ブロックリスト時**:電子メールをスパムまたは迷惑メールとして宣言した受信者の数です。[詳細情報](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

