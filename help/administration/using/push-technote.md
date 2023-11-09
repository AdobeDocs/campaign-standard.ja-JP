---
title: プッシュ通知チャネルの今後の変更
description: プッシュ通知チャネルの今後の変更
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: 6d1a5cb1d467d7d74fe41e66125fe0fcbf2e3d9b
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# プッシュ通知チャネルの今後の変更 {#push-upgrade}

Android およびiOSデバイスにまたがるプッシュ通知チャネルの今後の変更に関して、Adobe Campaign Standardの実装に影響を与える可能性のある重要なアップデートがあります。

## Android {#push-android}

Googleは、サービス向上に向けた継続的な取り組みの一環として、Google社は、 [Firebase Cloud Messaging HTTP プロトコル](https://firebase.google.com/docs/cloud-messaging/http-server-ref). その結果、2023 年 6 月 20 日に廃止された Firebase Cloud Messaging 「HTTP レガシー API」は、2024 年 6 月に「HTTP v1 API」に置き換えられます。

現在、Adobe Campaign Standardは、Android プッシュ通知メッセージの送信に HTTP レガシー API を使用しており、今後数ヶ月中に HTTP v1 API にアップグレードする予定です。 これらの変更に関する詳細は、Adobeがこれらの更新で作業する際に提供されます。

## iOS {#push-ios}

また、Adobeは、iOSプッシュ通知チャネル用にAdobe Campaign Standardをアップグレードし、管理者がiOSアプリケーション用の証明書を設定できる方法を変更します。 管理者は、Adobe Campaign Standardのユーザーインターフェイスを使用して、iOS証明書をアップロードする必要があります。

お客様は、マーケティングキャンペーンやコミュニケーションニーズに対してこれらのサービスを利用し、今後の計画やサポートを確実に把握していただきたいと考えています。

## 何をしてる？

* **製品の変更点**:Android/iOSのプッシュ通知チャネルでテクニカルスタックのアップグレードをサポートするために、製品の変更に対する作業。

* **詳細な手順**：スムーズな移行プロセスを実現するための詳細な手順ガイドやその他のリソースを提供します。

* **サポート**：この移行を通じて、アドビのカスタマーサポートチームが支援を受けることができます。 また、ウェビナーやイネーブルメントセッションを開催して、移行に関する技術的側面やベストプラクティスを取り上げることもできます。

## これはどのように影響を与えますか？

* **常に情報を提供**：詳細な移行計画を含む、アドビからの詳細なコミュニケーションについて、インボックスに目を通してください。

* **現在の設定を確認**：ここで、Adobe Campaign Standardでの現在の設定とカスタマイズを確認し、必要に応じて必要な変更をおこなう準備をします。

* **お問い合わせ**：すぐに関心や質問がある場合は、アドビのサポートチームに気軽にお問い合わせください。

## 次の手順

今後数週間で、タイムラインやアクション項目を含め、Android/iOS向けプッシュチャネルに予定されている変更に関する詳細を共有する予定です。 主な目標は、お客様とお客様のチームに対し、できる限りシームレスにこの移行を行うことです。

これらの変化に対応して、ご理解いただきありがとうございます。 お客様の成功が最優先事項であり、お客様のサポートに全力で取り組んでいます。