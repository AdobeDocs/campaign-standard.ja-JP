---
solution: Campaign Standard
product: campaign
title: Campaign のオプトインとオプトアウトについて
description: オプトアウトを使用すると、プロファイルがどの配信や特定のチャネルからの配信のターゲットにもならなくなります。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: 6b293db5bc8f299a3237aa83c003339f0e697c6f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 9%

---

# Campaign のオプトインとオプトアウトについて{#about-opt-in-and-opt-out-in-campaign}

オプトアウトを使用すると、プロファイルがどの配信や特定のチャネルからの配信のターゲットにもならなくなります。

プロファイルにオプトインまたはオプトアウト機能を付与するには、専用のランディングページを作成する必要があります。 詳しくは、[オプトインおよびオプトアウトランディングページの設定](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)を参照してください。

プロファイルは、オペレーターが手動でオプトインまたはオプトアウトすることもできます。 詳しくは、[プロファイルからのオプトインとオプトアウトの管理](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)を参照してください。

配信を高速化するために、配信分析時にオプトアウトプロファイルは自動的に除外されます（エラー率は配信速度に大きな影響を与えます）。

>[!NOTE]
>
>オプトアウトは、**Eメールアドレス**&#x200B;または&#x200B;**電話番号**&#x200B;にリンクされている強制隔離とは異なり、**プロファイル**&#x200B;に適用されます。 したがって、プロファイルをオプトアウトすると、プロファイルにリンクされているすべてのアドレスが配信から除外されます。 ただし、ユーザーがデータベースに2つのプロファイルを含んでいる場合、そのユーザーのプロファイルの1つのみがオプトアウトされるので、配信のターゲットとなります。 すべてのアドレスを除外するには、強制隔離されたアドレスに追加します。 詳しくは、[このページ](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)を参照してください。

サービスの購読について詳しくは、[このページ](../../audiences/using/about-subscriptions.md)を参照してください。
