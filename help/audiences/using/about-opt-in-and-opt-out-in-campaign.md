---
title: Campaign のオプトインとオプトアウトについて
description: オプトアウトの結果、プロファイルがどの配信や特定のチャネルの配信によってターゲット設定されることはなくなりました。
page-status-flag: never-activated
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---


# Campaign のオプトインとオプトアウトについて{#about-opt-in-and-opt-out-in-campaign}

オプトアウトの結果、プロファイルがどの配信や特定のチャネルの配信によってターゲット設定されることはなくなりました。

プロファイルに対して権限を与えるには、専用のランディングページを作成するオプトイン必要があります。 詳しくは、オプトインおよびオプトアウトランディングページの [設定を参照してください](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

プロファイルは、オペレーターが手動でオプトインまたはオプトアウトすることもできます。 詳しくは、「プロファイルからのオプトインおよびオプトアウトの [管理](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)」を参照してください。

配信を高速化するため、配信分析中にオプトアウトプロファイルが自動的に除外されます(配信速度に大きな影響があります)。

>[!NOTE]
>
>オプトアウトは、 **電子メールアドレス**&#x200B;や **電話番号にリンクされている強制隔離に対して、** プロファイルに適用されます ****。 したがって、プロファイルをオプトアウトすると、その配信にリンクされているすべてのアドレスがから除外されます。 データベースに2つのプロファイルが含まれている場合、プロファイルの1つのみがオプトアウトになるので、配信のターゲットになります。 すべての住所を除外するには、強制隔離の住所に住所を追加します。 詳しくは、[このページ](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)を参照してください。

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
