---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでの配信品質について
description: 配信品質に関する概念とベストプラクティス、および配信の送信を最適化するためにAdobe Campaign Standardが提供するツールについて説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 配信品質
role: ビジネス従事者
level: 中級者
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 8%

---


# 配信品質とは{#about-deliverability}

配信品質を使用すると、バウンスを発生させたりスパムとしてマークされたりすることなく、受信者の受信トレイに届いたキャンペーンの成功を測定できます。 [配信品質が重要な理由を学ぶ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters)。

より正確に言うと、電子メールの配信品質とは、メッセージが宛先に到達する能力を、個人の電子メールアドレスを介して、短時間で、コンテンツや形式に関して期待される品質を持つ特性の集まりを指します。<!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

配信品質の概要と、主な配信品質の用語、概念、アプローチの詳細については、『[Adobe配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html)』を参照してください。

## 配信品質の向上方法{#deliverability-key-points}

配信品質の問題は、通常、インターネットサービスプロバイダーやメールサーバ管理者が実装したスパムに対する保護の対策に関連しています。

* 成功する電子メールマーケティングキャンペーンを設計する方法に関する一般的な推奨事項については、[配信品質の戦略と定義](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html)を参照してください。

* Adobe Campaign電子メールの配信品質を最適化する方法について、より具体的な推奨事項を示す場合は、この節に示すベストプラクティスを使用することをお勧めします。

>[!NOTE]
>
>ISPは、顧客をスパム業者から保護するために、新しい高度なフィルタリング技術を継続的に開発する必要があるので、電子メールの配信品質は、常に変化する基準とルールに特徴付けられています。 定期的に更新される『[Adobe配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html)』を参照してください。

### 配信品質率

配信品質率は、受信者の受信トレイに届いたメッセージの数を、配信されたメッセージの数と比較した値です。 配信品質を向上させるために、この率を上げる作業を行う場合があります。

Adobe Campaignにより、配信品質は、特に多くの要因に左右されます。

* インスタンスの正しい設定：Adobeの担当者にお問い合わせください。
* 正当なネットワーク構成：[このセクション](../../sending/using/optimize-delivery.md#network-config)と[ドメインの設定と方法](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy)を参照してください。
* IPアドレスの評価：[IP戦略](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy)を参照してください。
* 対象となるアドレスの質：「[強制隔離管理](../../sending/using/optimize-delivery.md#quarantine-management)」を参照してください。
* [苦情](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html)と[ハードバウンス](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)率が低い。
* メッセージの内容：[電子メールコンテンツの制御](../../sending/using/control-email-content.md)を参照してください。
* メッセージ認証(SPF、DKIM、DMARC):[このセクション](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication)を参照してください。
* 送信者の評価：主なISPが送り手の評判を評価する方法については、[このセクション](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html)を参照してください。

## キャンペーン配信品質ツール{#deliverability-tools}

Adobe Campaignには、プラットフォームの配信パフォーマンスを追跡し、改善するためのツールが多数用意されています。 また、キャンペーンを使用する際の配信品質を最適化するために考慮すべき主な原則についても説明します。

### 注意深くメッセージを作成する

メッセージを設定、デザイン、テストする場合は、次の節に示すベストプラクティスに従っていることを確認してください。 Adobe Campaignが提供するすべての機能を活用すると、配信品質を向上できます。

* [配信のベストプラクティス](../../sending/using/delivery-best-practices.md)
* [E メールコンテンツの制御](../../sending/using/control-email-content.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [配達確認の送信](../../sending/using/sending-proofs.md)

### 重複のオプトイン{#double-opt-in}を通じて同意を確認

Adobeでは、無効なアドレスへのメッセージの送信を避け、不適切な通信を制限し、送信者の評判を向上させるために、重複オプトインメカニズムの実装をお勧めします。 これにより、受信者が意図的に購読していることを確認できます。

詳しくは、[キャンペーンでのオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)を参照してください。

お客様からデータを収集する際のベストプラクティスについて詳しくは、『[Adobe配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene)』を参照してください。

### 強制隔離管理の活用

Adobe Campaignは、一貫して発生するスパムの苦情、ハードバウンス、ソフトバウンスを収集するリストを管理します。

配信品質を保護するため、そのリスト上の住所を持つ受信者は、デフォルトでは、これらの連絡先に送信すると、送信の評判が悪くなる可能性があるので、将来のすべての配信から除外されます。

一部のインターネットアクセスプロバイダーは、無効なアドレスの割合が高すぎる場合、E メールを自動的にスパムとみなします。したがって、強制隔離を使用すると、これらのプロバイダーによってブロックリストに追加されるのを回避できます。

この点について詳しくは、以下の節を参照してください。

* [配信エラーの理解](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [強制隔離対ブロックリスト](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### 監視ツールとレポートツールの使用

Adobe Campaignが提供する機能を使用して、配信品質を監視します。

Adobe Campaignを使用すると、組み込みのリアルタイムインジケーターを使用して、配信のパフォーマンスを確認できます。 <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->また、配信に関するインサイトを向上させるために、完全にカスタマイズ可能なリアルタイムレポートを作成することもできます。

この点について詳しくは、以下の節を参照してください。

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
