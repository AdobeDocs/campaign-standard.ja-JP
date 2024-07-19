---
title: サブスクリプションについて
description: Campaign Standard のサービスとサブスクリプションについての詳細。
feature: Audiences
role: User
level: Intermediate
exl-id: 177f0115-d269-44e8-94e0-123360ea6299
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 40%

---

# 購読について{#about-subscriptions}

Adobe Campaignを使用すると、一連の **services** を介して、ニュースレターとクロスチャネルコミュニケーションを作成および管理できます。メッセージは、サービス（オプトイン）を購読しているプロファイルにのみ送信されます。 これらのプロファイルは、メッセージを作成する際に、専用のフィルターを使用して特定されます。

サブスクリプションメカニズムの設定により、顧客がこれらのサービスを（特にメール&#x200B;**と**&#x200B;ランディングページ&#x200B;**から）購読できるようにすることができます。**

各サービスには次の機能があります。

* **サブスクリプション**（オプトイン）および **[!UICONTROL Unsubscription]**（オプトアウト）メカニズム。
* 購読と購読解除の&#x200B;**確認メカニズム**。
* サブスクリプションの&#x200B;**履歴**。

サブスクリプションは、Adobe Campaign Standard API を使用して管理することもできます。詳しくは、[該当するドキュメント](../../api/using/creating-a-service.md)を参照してください。

## 購読を設定および管理するための主な手順

購読メカニズムを作成するには、次の手順に従います。

1. **サービスの作成** – 購読サービスを作成するには、[ この節 ](../../audiences/using/creating-a-service.md) で説明されている手順に従います
1. **リンクを共有** - サービスを昇格および共有する方法については、このページを参照してください [ このページ ](../../audiences/using/promoting-a-service.md)
1. **購読の監視** - サービスの購読を監視する方法をいくつか紹介します [ この節 ](../../audiences/using/monitoring-subscriptions.md)。
1. **購読を確認** - [ このチュートリアル ](../../audiences/using/confirming-subscription-to-a-service.md) に従って、購読確認メッセージを送信します

## その他のリソース

* [ユースケース：サービス購読者に対する増分クエリ](../../automating/using/incremental-query-on-subscribers.md)
* [ユースケース：ファイルからの複数の購読ステータスの更新](../../automating/using/updating-subscriptions-from-file.md)
* [ファイルのインポート後の特定のサービスへのプロファイルの購読](../../automating/using/subscribing-profiles-from-file.md)
* [Campaign のオプトインとオプトアウト](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
