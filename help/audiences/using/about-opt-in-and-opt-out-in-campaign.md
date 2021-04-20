---
solution: Campaign Standard
product: campaign
title: Campaign のオプトインとオプトアウトについて
description: オプトアウトの結果、プロファイルがどの配信や特定のチャネルの配信によってターゲット設定されることはなくなりました。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 9%

---


# Campaign のオプトインとオプトアウトについて{#about-opt-in-and-opt-out-in-campaign}

オプトアウトの結果、プロファイルがどの配信や特定のチャネルの配信によってターゲット設定されることはなくなりました。

プロファイルに対して権限を与えるには、専用のランディングページを作成するオプトイン必要があります。 詳しくは、[オプトインおよびオプトアウトランディングページの設定](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)を参照してください。

プロファイルは、オペレーターが手動でオプトインまたはオプトアウトすることもできます。 詳しくは、[プロファイルからのオプトインおよびオプトアウトの管理](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)を参照してください。

配信を高速化するため、配信分析中にオプトアウトプロファイルが自動的に除外されます(配信速度に大きな影響があります)。

>[!NOTE]
>
>オプトアウトは&#x200B;**プロファイル**&#x200B;に適用され、**電子メールアドレス**&#x200B;または&#x200B;**電話番号**&#x200B;にリンクされている強制隔離には適用されません。 したがって、プロファイルをオプトアウトすると、その配信にリンクされているすべてのアドレスがから除外されます。 データベースに2つのプロファイルが含まれている場合、プロファイルの1つのみがオプトアウトになるので、配信のターゲットになります。 すべての住所を除外するには、強制隔離の住所に住所を追加します。 詳しくは、[こちらのページ](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)を参照してください。

サービスの購読について詳しくは、[このページ](../../audiences/using/about-subscriptions.md)を参照してください。
