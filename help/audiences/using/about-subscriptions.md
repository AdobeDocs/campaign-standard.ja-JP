---
solution: Campaign Standard
product: campaign
title: サブスクリプションについて
description: Campaign Standard のサービスとサブスクリプションについての詳細。
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 53%

---


# サブスクリプションについて{#about-subscriptions}

Adobe Campaign では、一連の&#x200B;**サービス**&#x200B;を通じて、ニュースレターやチャネル間の通信を作成および管理できます。メッセージは、サービスを購入（オプトイン）しているプロファイルにのみ送信できます。これらのプロファイルは、メッセージを作成する際に、専用のフィルターを使用して特定されます。

サブスクリプションメカニズムの設定により、顧客がこれらのサービスを（特に **E メール**&#x200B;と&#x200B;**ランディングページ**&#x200B;から）購読できるようにすることができます。

各サービスには次の機能があります。

* **サブスクリプション**（オプトイン）および **[!UICONTROL Unsubscription]**（オプトアウト）メカニズム。
* 購読と購読解除の&#x200B;**確認メカニズム**。
* サブスクリプションの&#x200B;**履歴**。

サブスクリプションは、Adobe Campaign Standard API を使用して管理することもできます。詳しくは、[該当するドキュメント](../../api/using/creating-a-service.md)を参照してください。

## 購読の設定と管理の主な手順

次の手順に従って、購読メカニズムを作成します。

1. **サービスの作成** -購読サービスを作成するに [は、この節](../../audiences/using/creating-a-service.md) で説明する手順に従います。
1. **リンクを共有** — このページでサービスをプロモーションおよび共有する方法 [を説明します。](../../audiences/using/promoting-a-service.md)
1. **購読の監視** — この節では、サービスへの購読を監視する方法をいくつか [見つけます。](../../audiences/using/monitoring-subscriptions.md)
1. **購読の確認** - [このチュートリアルに従って](../../audiences/using/confirming-subscription-to-a-service.md) 、購読確認メッセージを送信します。

## その他のリソース

* [使用例：サービスの購読者の増分処理クエリ](../../automating/using/incremental-query-on-subscribers.md)
* [使用例：ファイルからの複数の購読ステータスの更新](../../automating/using/updating-subscriptions-from-file.md)
* [ファイルの読み込み後に特定のサービスにプロファイルを登録する](../../automating/using/subscribing-profiles-from-file.md)
* [キャンペーンでのオプトインとオプトアウト](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
