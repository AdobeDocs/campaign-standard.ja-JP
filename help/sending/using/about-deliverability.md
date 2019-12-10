---
title: Adobe Campaign Standardの配信品質について
description: 配信品質に関する概念とベストプラクティス、および配信を最適化するためにAdobe Campaign Standardが提供するツールについて説明します。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# 配信品質について{#about-deliverability}

配信品質や、受信者の受信トレイに届くキャンペーンの成功を測定する方法。バウンスを発生させたり、スパムとしてマークされたりすることはありません。

Adobe Campaignの配信品質は、様々なオファーで利用できる有料サービスです。 配信品質または商用サービスに問い合わせてください。

配信品質は、特に多くの要因に依存します。

* インスタンスの正しい設定
* IPアドレスの評判
* 対象とするアドレスの質
* 苦情と直帰率の低さ
* メッセージの内容
* メッセージ認証(SPF、DKIM、DMARC)
* 送信者の評判

## 確認する主なポイント {#deliverability-key-points}

Adobe Campaignの電子メールの配信品質を最適化するには、以下に示すベストプラクティスを使用することをお勧めします。 配信品質の問題は、一般に、インターネットサービスプロバイダやメールサーバ管理者が実装したスパムに対する保護の対策と関連しています。

電子メールの配信品質とは、メッセージの送信先に到達する能力を、個人の電子メールアドレスを介して、短時間で判断し、コンテンツや形式に関して期待される品質を持つ特性の集まりを指します。 これらの特性は、主に4つのカテゴリに分類されます。データ品質、メッセージとコンテンツ、インフラストラクチャの送信、評判 Eメール配信品質プログラムの基盤を構築します。

配信品質率は、受信者に正常に配信された送信済み電子メールの数です。
以下に、適切な配信品質を確認するための重要なポイントを示します。

## 配信品質ツール {#deliverability-tools}

まず、Campaign Standardで提供される配信品質ツールに関するドキュメントを参照します。
* [配信のベストプラクティス](https://helpx.adobe.com/campaign/kb/delivery-best-practices.html)
* [送信者名の個人設定](../../designing/using/personalization.md#personalizing-the-sender)
* [電子メールの件名行のテスト](../../sending/using/testing-subject-line-email.md)
* [送信時間の最適化](../../sending/using/optimizing-the-sending-time.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [E メールのレンダリング](../../sending/using/email-rendering.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
* [エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)
* [配信エラーの理解](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [検疫とブラックリスト](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting)
* [動的レポート](../../reporting/using/about-dynamic-reports.md)

## ネットワーク構成を確認しています {#network-configuration}

スパマーは自分の本当のアイデンティティを隠そうとし、その結果、サーバの識別が困難になります。 サーバのIDを隠そうとしない正規のネットワーク設定は、大量の電子メールを送信する場合に不可欠です。

## 有効なアドレスへの送信 {#valid-addresses}

スパマーは、頻繁な名前と名のリストに基づいてアドレスジェネレーターを使うことが多い。また、メールサーバから返送された技術通知を処理することはほとんどありません。 無効なアドレスの割合が高いと、多くの場合、スパムの兆候と解釈されます。 二重のオプトインメカニズムと技術的なバウンスメッセージの効果的な処理により、この問題を回避できます。

## 苦情率の低減 {#reduce-complaint-rate}

通常、ISPは、受信したメッセージをスパムとして報告する顕著な手段を持っています。 これにより、信頼性の低いソースを特定できます。 オプトアウト要求を迅速に実行し、特定のリストを定期的に使用し、ダブルオプトインシステムを使用して同意を確認し、フィードバックループを実装することで、苦情の発生率を低減できます。

## 新婚旅行先への送信 {#honeypot-addresses}

ISPや他の組織(http://www.projecthoneypot.org/を参照)は、物理的な人に対応していないが、単にスパムメーカーを騙すために作成されたメールボックスを利用します。 いわゆる「はちみつポット」のアドレスは、スパンボットによって収集され、不正な送信者を捕らえるために、ウェブ上で公開されている。 ダブルオプトインメカニズムを使用すると、この種のアドレスがリストに追加されなくなります。 サードパーティのリストを使用する場合は、その管理者が使用する方法を確実に確認する必要があります。

## メッセージ内容の適合 {#adapt-message-content}

より少ない程度には、特定のメッセージの内容が原因で、特定のフィルターがスパムとして検出される可能性があります。 特定の単語の使用、件名行とメッセージ内での感嘆符の使用は、スパムの告知的な兆候として読み取られます。 スパムマーは、スパム対策フィルターによって不正なテキストが自動的に分析されるのを防ぐために、テキストを画像に置き換えることも知られています。 これに対して、画像または画像の割合が高い（HTML形式の）メッセージが添付ファイルとしてブロックされる場合があります。

## 定期的な送信 {#regular-deliveries}

スパマーは、時間の経過と共に評判を維持するために、プログラム配信を行う。 ISPが定めたベストプラクティスを満たすためにマーケティング計画を適合させる必要が生じる場合があり、評判のピーク（増加）後は、定期的な配信を設定します。
