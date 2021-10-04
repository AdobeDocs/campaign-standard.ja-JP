---
title: Adobe Campaign Standardの配信品質について
description: 配信品質に関する概念とベストプラクティス、配信の送信を最適化するためにAdobe Campaign Standardで提供されるツールについて説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 77%

---

# 配信品質とは{#about-deliverability}

配信品質を使用すると、バウンスしたりスパムとしてマークされたりせずに、受信者の受信ボックスに到達したかに基づいて、キャンペーンの成功を測定できます。 [配信品質が重要な理由について説明します](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=ja#why-deliverability-matters)。

正確には、E メール配信品質とは、メッセージが、期待される品質の内容と形式を持ち、個人の E メールアドレスを通じて短時間で宛先に到達できるかどうかを判断するための一連の特性のことを指します。 <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

配信品質の概要と、配信品質の主要な用語、概念、アプローチの詳細については、[アドビの配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ja)を参照してください。

## 配信品質を向上させる方法 {#deliverability-key-points}

配信品質の問題は、通常、インターネットサービスプロバイダーおよびメールサーバー管理者が実行するスパム対策の指標に関係しています。

* 成功する E メールマーケティングキャンペーンを設計する方法に関する一般的な推奨事項については、[配信品質の戦略と定義](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=ja)を参照してください。

* Adobe Campaign E メールの配信品質を最適化する方法に関するより具体的な推奨事項については、この節にリストされているベストプラクティスを使用することをお勧めします。

>[!NOTE]
>
>ISP は顧客をスパム業者から保護するために、新しい高度なフィルタリング技術を継続的に開発する必要があるので、E メールの配信品質は常に変化する基準とルールを特徴としています。必ず、[アドビの配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html)を参照してください。これは定期的に更新されます。

### 配信品質率

配信品質率は、受信者のインボックスに届いたメッセージの数と配信されたメッセージの数との比率ですこの比率を高めることにより、配信品質を向上させることができます。

Adobe Campaign では、配信品質は多くの要因に左右されます。特に次のような要因があげられます。

* インスタンスの正しい設定：詳しくはアドビ担当者にお問い合わせください。
* 適切なネットワーク構成：[この節](../../sending/using/optimize-delivery.md#network-config)と[ドメインの設定と戦略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ja#transition-process)を参照してください。
* IP アドレスの評価：[IP 戦略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ja#ip-strategy)を参照してください。
* アドレスの品質の目標：[強制隔離管理](../../sending/using/optimize-delivery.md#quarantine-management)を参照してください。
* 低い[苦情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html?lang=ja)率と[ハードバウンス](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=ja#hard-bounces)率。
* メッセージコンテンツ：[E メールコンテンツの制御](../../sending/using/control-email-content.md)を参照してください。
* メッセージ認証（SPF、DKIM、DMARC）：[この節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ja#authentication)を参照してください。
* 送信者の評判：主要 ISP が送信者の評判を評価する方法については、[この節](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html?lang=ja)を参照してください。

## Campaign の配信品質ツール {#deliverability-tools}

Adobe Campaignは、プラットフォームの配信品質のパフォーマンスを追跡し改善するための様々なツールを提供します。 また、Campaign を使用する際に配信品質を最適化するために考慮すべき主な原則についても説明します。

### メッセージの慎重な作成

メッセージを設定、設計、テストする際は、以下の節で説明するベストプラクティスに従ってください。 Adobe Campaign で提供されるすべての機能を活用すると、配信品質の向上に役立ちます。

* [配信のベストプラクティス](../../sending/using/delivery-best-practices.md)
* [メールコンテンツの制御](../../sending/using/control-email-content.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)

### ダブルオプトインによる同意確認 {#double-opt-in}

無効なアドレスへのメッセージ送信を回避し、不適切な通信を制限し、送信者の評判を向上させるには、ダブルオプトインのメカニズムの実装をお勧めします。これにより、受信者が意図的に購読したことを確認できます。

詳しくは、[Campaign のオプトインとオプトアウトについて ](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md) を参照してください。

顧客からデータを収集する際のベストプラクティスについて詳しくは、[アドビの配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html?lang=ja#data-quality-and-hygiene)を参照してください。

### 強制隔離管理の活用

Adobe Campaign は、絶えず発生するスパムの苦情、ハードバウンス、ソフトバウンスを収集したリストを管理します。

配信品質を保護するため、アドレスがこのリストにある受信者は、デフォルトでは今後のすべての配信から除外されます。これらの連絡先に送信すると、送信の評判が低下する可能性があるからです。

一部のインターネットアクセスプロバイダーは、無効なアドレスの割合が高すぎる場合、E メールを自動的にスパムと見なします。したがって、強制隔離を使用すると、これらのプロバイダーによってブロックリストに追加されるのを回避できます。

詳しくは、以下の節を参照してください。

* [配信エラーについて](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理について](../../sending/using/understanding-quarantine-management.md)
* [強制隔離とブロックリストの比較](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### 監視ツールとレポートツールの使用

Adobe Campaign が提供する機能を使用して、配信品質を監視します。

Adobe Campaignでは、組み込みの一連のリアルタイム指標を使用して、配信のパフォーマンスを確認できます。 <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->また、完全にカスタマイズ可能なリアルタイムレポートを作成して、配信に関するインサイトを向上させることもできます。

詳しくは、以下の節を参照してください。

* [配信品質の監視](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)
* [動的レポート](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
