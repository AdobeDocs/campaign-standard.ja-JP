---
title: キャンペーンのオプトインとオプトアウトについて
description: オプトアウト（またはブラックリスト）を使用すると、プロファイルが配信または特定のチャネルからの配信によってターゲット設定されなくなります。
page-status-flag: 非活性化の
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: 参照
topic-tags: 理解オプトイン/オプトアウトプロセス
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# キャンペーンのオプトインとオプトアウトについて{#about-opt-in-and-opt-out-in-campaign}

オプトアウト（またはブラックリスト）を使用すると、プロファイルが配信または特定のチャネルからの配信によってターゲット設定されなくなります。

プロファイルにオプトインまたはオプトアウトの機能を与えるには、専用のランディングページを作成する必要があります。 詳しくは、オプトインおよびオプトア [ウトのランディングページの設定を参照してください](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)。

プロファイルは、オペレーターが手動でオプトインまたはオプトアウトすることもできます。 詳しくは、「プロファイルからのオ [プトインとオプトアウトの管理」を参照してください](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)。

配信速度を上げるために、配信分析中にオプトアウトプロファイルは自動的に除外されます（エラー率は配信速度に大きな影響を与えます）。

>[!NOTE]
>
>オプトアウトは、電子メールア **ドレス**&#x200B;や電話番号にリンクされている検疫とは異なり、 **プロファイルに適** 用されます ****。 したがって、プロファイルをオプトアウトすると、そのプロファイルにリンクされているすべてのアドレスが配信から除外されます。 ユーザーがデータベースに2つのプロファイルを持っている場合、そのユーザーのプロファイルの1つのみがオプトアウトなので、配信のターゲットとなります。 彼の住所をすべて除外するには、隔離所の住所に追加します。 詳しくは、[このページ](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)を参照してください。

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
