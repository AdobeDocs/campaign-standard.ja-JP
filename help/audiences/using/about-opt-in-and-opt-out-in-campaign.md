---
title: Campaign のオプトインとオプトアウトについて
description: オプトアウトすると、プロファイルは、任意の配信または特定のチャネルからの配信によってターゲットにされなくなります。
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
TQID: 'https://experienceleague.adobe.com/9fzQiPrBRAFlTxX5EKo-Qvph3nYZYoA29kMrm6cXVLs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 10%
---
# Campaign のオプトインとオプトアウトについて{#about-opt-in-and-opt-out-in-campaign}

オプトアウトすると、プロファイルは、任意の配信または特定のチャネルからの配信によってターゲットにされなくなります。

プロファイルにオプトインやオプトアウトの機能を提供するには、専用のランディングページを作成する必要があります。 詳しくは、[&#x200B; オプトインとオプトアウトのランディングページの設定](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)を参照してください。

プロファイルは、オペレーターが手動でオプトインまたはオプトアウトすることもできます。 詳しくは、「[&#x200B; プロファイルからのオプトインとオプトアウトの管理](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile)」を参照してください。

配信を高速化するために、配信分析中にオプトアウトプロファイルが自動的に除外されます（エラー率は配信速度に大きな影響を与えます）。

>[!NOTE]
>
>**電子メールアドレス**&#x200B;または&#x200B;**電話番号**&#x200B;にリンクされている強制隔離とは対照的に、**プロファイル**&#x200B;にオプトアウトが適用されます。 したがって、プロファイルをオプトアウトすると、そのプロファイルにリンクされているすべてのアドレスが配信から除外されます。 ただし、ユーザーがデータベース内に2つのプロファイルを持っている場合、そのプロファイルの1つのみがオプトアウトされるので、このユーザーは引き続き配信のターゲットとなります。 すべてのアドレスが除外されていることを確認するには、強制隔離されたアドレスに追加します。 詳しくは、[このページ](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)を参照してください。

サービスのサブスクリプションについて詳しくは、[このページ &#x200B;](../../audiences/using/about-subscriptions.md)を参照してください。
