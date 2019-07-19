---
title: キャンペーンでのオプトインとオプトアウトについて
seo-title: キャンペーンでのオプトインとオプトアウトについて
description: キャンペーンでのオプトインとオプトアウトについて
seo-description: オプトアウト（またはブラックリスト）では、配信または特定のチャネルからの配信によってプロファイルがターゲット設定されなくなりました。
page-status-flag: 常にアクティブ化されていない
uuid: 501d9485-976b-4de7- b242-6886f2814c6c
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: オーディエンス
content-type: 参照
topic-tags: understanding- opt- in- and- opt- out- processes
discoiquuid: 2f26ec22-0809-4541- b2a1- e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About opt-in and opt-out in Campaign{#about-opt-in-and-opt-out-in-campaign}

オプトアウト（またはブラックリスト）では、配信または特定のチャネルからの配信によってプロファイルがターゲット設定されなくなりました。

プロファイルをオプトインまたはオプトアウトできるようにするには、専用のランディングページを作成する必要があります。For more on this, refer to [Setting up opt-in and opt-out landing pages](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

プロファイルは、演算子によって手動でオプトインまたはオプトアウトすることもできます。For more on this, refer to [Managing opt-in and opt-out from a profile](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

配信を高速化するために、配信分析中にオプトアウトプロファイルが自動的に除外されます（エラー率は配信速度に大きく影響します）。

>[!NOTE]
>
>Opt-out applies to **Profiles**, as opposed to quarantine which is linked to an **email address** or **phone number**. プロファイルをオプトアウトすると、リンクされたすべてのアドレスが配信から除外されます。データベースに2つのプロファイルがある場合、プロファイルはオプトアウトの1つとしてのみ配信され、配信によってターゲット設定されます。すべての広告が除外されていることを確認するには、それらを四半期別アドレスに追加します。For more on this, refer to [this page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
