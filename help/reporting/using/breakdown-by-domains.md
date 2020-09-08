---
title: ドメイン別の分類
description: '[ドメイン別の分類]の標準レポートを使用すると、顧客の各ドメインに応じた配信のパフォーマンスデータを知ることができます。'
page-status-flag: never-activated
uuid: 75a64c81-325b-422f-b6ef-deb06eec7f7b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: 2ce174f9-5d7d-48b9-9235-6bf3e238ff37
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 3%

---


# ドメイン別の分類{#breakdown-by-domains}

このレポートには、電子メール配信のオーディエンスに表示される各ドメインのパフォーマンスデータが含まれます。 キャンペーンレポートまたはプログラムレポートの場合は、パフォーマンスデータを複数のオーディエンスで使用できます。 このデータを使用すると、特定のイベントに対する各ドメインの動作を分析できます。 例えば、リンク表示、ブロックリストに加えるURLなど

![](assets/delivery_reports_6.png)

「 **ブロードキャスト統計** 」テーブルには、各ドメインで発生する可能性のあるエラーに関して使用可能なデータが含まれます。例：

* **処理済み/送信済み**:送信された電子メールの数。
* **配信済み**:配信された電子メールの数。
* **バウンス+エラー**:配信できなかったメッセージの数です。
* **ハードバウンス**:誤った電子メールアドレスなど、永続的なエラーの合計数です。
* **ソフトバウンス**:完全なインボックスなどの一時エラーの合計数です。

2つ目のテーブル **「統計の追跡**」には、配信に対する受信者の反応性に使用できる次のようなデータが含まれます。

* **配信済み**:配信された電子メールの数
* **開く**:配信でメッセージが開かれた回数。
* **クリック**:配信内のコンテンツがクリックされた回数。
* **登録解除**:購読リンクのクリック数。
* **ミラーページ**:ミラーページリンクのクリック数。
* **ブロックリストに加える**:電子メールをスパムまたは迷惑メールとして宣言した受信者の数です。 [詳細情報](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

