---
title: 早期リリースノート
description: 早期リリースノート
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 104855851906b96f79a89179108548b3dde17b4f
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 24%

---

# 早期リリースノート {#new-release}

このページでは、次回の Campaign Standard リリースに含まれる新機能、改善点、修正点について説明します。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

## リリース 22.2 - 2022 年 6 月 {#rn-2022}

**改善点**

* **Adobe通知サービス** - Campaign には、Adobeが知っておくべき重要なアクティビティに関して、Experience CloudソリューションがExperience Cloudをまたいでユーザーにアラートを表示できるようにする、ユーザー通知サービスが付属しています。 22.2 バージョンより、ユーザーエクスペリエンスが向上しました。通知は優先され、製品生成通知はAdobeのステータスのお知らせとは別に表示されます。 さらに、通知が特定のワークフローを参照する場合、電子メール通知または製品内通知から直接、対応するワークフローにアクセスできるようになりました。  Adobe Campaign通知について詳しくは、 [Adobe Campaign通知](../../administration/using/sending-internal-notifications.md).

* **ワークフローの遅延開始** ：オーバーロードを避けるために、ワークフローの実行を遅延できるようになりました。 専用オプションを通じてAdobeが有効にします。このガードレールは、ワークフロー間の開始に遅延が生じることを確認します。 この機能オプションは、同時に実行できるワークフローの数と、その間の遅延（秒）を設定します。


**セキュリティのアップグレード**

* このバージョンには、Apache の脆弱性を軽減し、インスタンス環境のセキュリティを高めるセキュリティアップグレードアクティビティが付属しています。 [詳細情報](https://experienceleague.adobe.com/docs/campaign-classic/using/technotes/technote-migration/acc-apache-upgrade.html){target=&quot;_blank&quot;}。

