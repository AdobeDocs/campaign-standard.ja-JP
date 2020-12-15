---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでの配信品質について
description: 配信品質に関する概念とベストプラクティス、および配信の送信を最適化するためにAdobe Campaign Standardが提供するツールについて説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1e7359db2de1a9c420af33ac85c0597c098ae3f8
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 86%

---


# 配信品質について{#about-deliverability}

配信品質を使用すると、バウンスを発生させたりスパムとしてマークされたりすることなく、受信者の受信トレイに届いたキャンペーンの成功を測定できます。

配信品質の割合は、様々な要素に依存しますが、特に以下に依存します。

* インスタンスの適切な設定
* IP アドレスのレピュテーション
* ターゲットアドレスの品質
* 低い苦情率およびハードバウンス率
* メッセージのコンテンツ
* メッセージ認証（SPF、DKIM、DMARC）
* 送信者のレピュテーション

## 重要なチェックポイント {#deliverability-key-points}

Adobe Campaign の E メールの配信品質を最適化するために、次に示すベストプラクティスを使用することをお勧めします。配信品質の問題は、通常、インターネットサービスプロバイダーおよびメールサーバー管理者が実行するスパムに対する保護の指標に関係しています。

E メール配信品質とは、期待される品質のコンテンツとフォーマットを持つメッセージが、個人の E メールアドレスを通じて短時間で宛先に到達する能力を判断する一連の特性のことを指します。これらの特性は、データ品質、メッセージとコンテンツ、送信インフラストラクチャ、レピュテーションの 4 つの主なカテゴリに分類されます。これらにより、成功する E メール配信品質プログラムの基礎が形成されます。

配信品質の割合は、受信者に適切に配信された送信 E メールの数です。次に、良好な配信品質を実現するための重要なチェックポイントを示します。

## 配信品質ツール{#deliverability-tools}

まず、Campaign Standardと共に提供される配信品質ツールに関するドキュメントを参照し、開始を行います。
* [配信のベストプラクティス](../../sending/using/delivery-best-practices.md)
* [送信者名の個人設定](../../designing/using/personalization.md#personalizing-the-sender)
* [送信時間の最適化](../../sending/using/optimizing-the-sending-time.md)
* [メッセージのプレビュー](../../sending/using/previewing-messages.md)
* [E メールのレンダリング](../../sending/using/email-rendering.md)
* [配信の監視](../../sending/using/monitoring-a-delivery.md)
* [エラー発生時のアラートの受信](../../sending/using/receiving-alerts-when-failures-happen.md)
* [配信エラーの理解](../../sending/using/understanding-delivery-failures.md)
* [強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)
* [強制隔離対ブロックリスト](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)
* [動的レポート](../../reporting/using/about-dynamic-reports.md)

## ネットワーク設定の確認 {#network-configuration}

スパム送信者は、実際の ID を隠蔽し、結果としてサーバーの識別を困難にします。大量の E メールを送信する場合は、サーバーの ID を隠そうとしない適切なネットワーク設定が不可欠です。

## 有効なアドレス{#valid-addresses}に送信中

スパム送信者は、多くの場合、よくある姓と名のリストに基づくアドレスジェネレーターを使用します。また、メールサーバーから返信される技術的な通知をほとんど処理しません。無効なアドレス率が高いと、多くの場合はスパムと解釈されます。ダブルオプトインメカニズムおよび技術的なバウンスメッセージの効果的な処理により、これを回避することができます。

## 不服申し立て率{#reduce-complaint-rate}を下げる

ISP は、通常、受け取ったメッセージをスパムとしてレポートする優れた手段を持っています。これにより、信頼性を欠くソースの特定が可能です。オプトアウトリクエストを直ちにおこない、所定のリストを定期的に使用し、ダブルオプトインシステムで同意を検証し、フィードバックループを実装することで、苦情率を減らすことができます。

## ハニーポットアドレスへの送信 {#honeypot-addresses}

ISP やその他の組織（https://www.projecthoneypot.org/ を参照）は、実際の個人としては存在しない、単にスパム送信者を欺くために作成されたメールボックスを使用します。このいわゆる「ハニーポット」アドレスは、スパムボットによって収集され、不正な送信者を捕らえるために Web で公開されます。ダブルオプトインメカニズムを使用することで、この種のアドレスがリストに追加されないようにします。サードパーティのリストを使用する場合、そのリストが信頼できる方法で管理されているか確認する必要があります。

## メッセージ内容の適応{#adapt-message-content}

可能性は高くはありませんが、特定のメッセージのコンテンツがフィルターでスパムとして検出される場合があります。ある種の単語の使用、件名およびメッセージ内での感嘆符の使用は、スパムの明らかな兆候として読み取られます。スパム送信者は、アンチスパムフィルターによってテキストが自動的に分析されるのを防ぐために、テキストを画像で置き換えることも知られています。これに対応するために、画像の比率の高いメッセージ（HTML 形式）や添付された画像はブロックされます。

## 定期的に送信{#regular-deliveries}

スパム送信者は、長期的にレピュテーションを維持するためにプログラムされた配信をおこないます。スパム送信者は、ISP などによって課せられたベストプラクティスに対応するためにマーケティングプランの変更が必要な場合があり、レピュテーションのピーク後（ランプアップ）、通常の配信を設定します。
