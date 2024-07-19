---
title: Campaign のオプトインとオプトアウトについて
description: オプトアウトを使用すると、プロファイルが配信のターゲットとなったり、特定のチャネルからの配信のターゲットとなったりしなくなります。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 8%

---

# Campaign のオプトインとオプトアウトについて{#about-opt-in-and-opt-out-in-campaign}

オプトアウトを使用すると、プロファイルが配信のターゲットとなったり、特定のチャネルからの配信のターゲットとなったりしなくなります。

プロファイルにオプトインまたはオプトアウト機能を付与するには、専用のランディングページを作成する必要があります。 詳しくは、[ オプトインおよびオプトアウトランディングページの設定 ](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages) を参照してください。

プロファイルは、オペレーターが手動でオプトインまたはオプトアウトすることもできます。 詳しくは、[ プロファイルからのオプトインおよびオプトアウトの管理 ](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile) を参照してください。

配信を高速化するために、配信分析中にオプトアウトプロファイルが自動的に除外されます（エラー率は配信速度に大きな影響を与えます）。

>[!NOTE]
>
>オプトアウトは、**メールアドレス** または **電話番号** にリンクされる強制隔離とは異なり、**プロファイル** に適用されます。 したがって、プロファイルをオプトアウトすると、そのプロファイルにリンクされているすべてのアドレスが配信から除外されます。 ただし、ユーザーがデータベース内に 2 つのプロファイルを持っている場合、そのうちの 1 つのプロファイルのみがオプトアウトされるので、このユーザーは引き続き配信のターゲットになります。 すべてのアドレスが除外されていることを確認するには、強制隔離されたアドレスにそれらを追加します。 詳しくは、[このページ](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)を参照してください。

サービス購読について詳しくは、[ このページ ](../../audiences/using/about-subscriptions.md) を参照してください。
