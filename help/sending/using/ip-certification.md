---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardの許可リスト
description: Adobe Campaign Standardで許可リストを最適化する方法を学びます。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 配信品質
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 81%

---


# IP 証明書 {#ip-certification}

IP 証明書は、スパム対策フィルターや他の E メールブロックシステムによってブロックされることなく、E メールが確実に受信されるようにする、送信のベストプラクティスのプログラムです。

現在、Return Path および Certified Senders Alliance の 2 社のプロバイダーが IP 証明書を提供しています。

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

ISP は、これらのサービスを自由に使用するので、ISP の数は許可リストによって異なる可能性があります。

ただし、メッセージコンテンツの分析よりも受信ボックス所有者の行動に基づいてスパム対策フィルターを構築する ISP が増えているため、IP 証明書を使用すれば受信ボックスへ配置や配信が保証されるわけではありません。
