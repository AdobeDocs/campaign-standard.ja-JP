---
title: Campaign のオプトインとオプトアウトについて
description: オプトアウトを使用すると、プロファイルがどのような配信や特定のチャネルからの配信のターゲットにもならなくなります。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 8%

---

# Campaign のオプトインとオプトアウトについて{#about-opt-in-and-opt-out-in-campaign}

オプトアウトを使用すると、プロファイルがどのような配信や特定のチャネルからの配信のターゲットにもならなくなります。

プロファイルにオプトインまたはオプトアウト機能を付与するには、専用のランディングページを作成する必要があります。 詳しくは、[ オプトインおよびオプトアウトランディングページの設定 ](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages) を参照してください。

プロファイルは、オペレーターが手動でオプトインまたはオプトアウトすることもできます。 詳しくは、[ プロファイルからのオプトインとオプトアウトの管理 ](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile) を参照してください。

配信を高速化するために、配信分析時にオプトアウトプロファイルは自動的に除外されます（エラー率は配信速度に大きな影響を与えます）。

>[!NOTE]
>
>オプトアウトは、**E メールアドレス** または **電話番号** にリンクされている強制隔離とは異なり、**プロファイル** に適用されます。 したがって、プロファイルをオプトアウトすると、プロファイルにリンクされているすべてのアドレスが配信から除外されます。 ただし、ユーザーがデータベース内に 2 つのプロファイルを持っている場合、そのユーザーのプロファイルの 1 つのみがオプトアウトされるので、配信のターゲットとなります。 このユーザーのアドレスをすべて除外するには、強制隔離されたアドレスに追加します。 詳しくは、[このページ](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)を参照してください。

サービスの購読について詳しくは、[ このページ ](../../audiences/using/about-subscriptions.md) を参照してください。
