---
title: Adobe Campaign Standardの許可リスト
description: Adobe Campaign Standardで許可リストを最適化する方法を学びます。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 68%

---


# IP 証明書 {#ip-certification}

IP Certificationは、送信のベストプラクティスプログラムです。スパム対策フィルターや他の電子メールブロッキングシステムによってブロックされることなく、電子メールを確実に受信できるようにします。

現在、2 社のプロバイダーが IP 証明書を提供しています。Return Path および Certified Senders Alliance です。

認証済みの送信者は、グローバルメールボックスプロバイダーや電子メールセキュリティ会社で使用される許可リスト上に存在します。 これらの商用許可リストは、送信者がスパム対策フィルターを完全に回避したり、システムに入る際に増分ポイントを割り当てることを可能にするシステムに基づいています。

[Return Path Certification](https://www.validity.com/products/returnpath/certification/) プログラムには、次のような多くの利点があります。
* Microsoft、AOL、Yahoo、Gmail、Comcast、Orange、Mail.ru など、大手メールボックスプロバイダーにおける受信ボックスへの配置率が大幅に向上
* Cloudmark、SpamAssassin および Cisco Ironport など、重要なフィルターでの有利な評判と扱い
* 24 時間 365 日の監視をおこなう専門のコンプライアンスチームが、セキュリティアラートを提供し、あらゆるセキュリティ侵害の解決のために協力
* KPI、配置および証明書パフォーマンスに関する詳細情報を提供する、メールボックスプロバイダーのデータ
* 新しい IP アドレスへの移行または取得の際の評判と認知度の強化を含む、シンプルで高速な IP ウォームアップ

[Certified Senders Alliance](https://certified-senders.org/certification-process/) 証明書には、以下のような利点があります。
* 高品質な基準に準拠できる商用 E メール送信者の認証
* 商用 E メールの配信と配信品質を改善し、受信ボックスへの配置率を上げ、スパム対策フィルターにかかる割合を削減
* 法的基準に完全に準拠して、法的リスクや経済的リスクから保護
* CSA Complaints Office からの早期警告および毎日のスパムトラップレポートにより、評判を保護

ISPはこれらのサービスを無料で使用でき、ISPの数は許可リストによって異なります。

ただし、メッセージコンテンツの分析よりも受信ボックス所有者の行動に基づいてスパム対策フィルターを構築する ISP が増えているため、IP 証明書を使用すれば受信ボックスへ配置や配信が保証されるわけではありません。
