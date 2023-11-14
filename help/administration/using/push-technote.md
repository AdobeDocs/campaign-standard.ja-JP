---
title: プッシュ通知チャネルの今後の変更
description: プッシュ通知チャネルの今後の変更
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
hide: true
hidefromtoc: true
source-git-commit: f9a0d01196ac4c31e57ae14cdfa448a9ffd6106f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 3%

---

# プッシュ通知チャネルの今後の変更 {#push-upgrade}

Campaign を使用して、Android およびiOSデバイスでプッシュ通知を送信できます。 これを実行するには、Campaign は特定の購読サービスに依存しています。 Android Firebase Cloud Messaging(FCM) サービスに対する重要な変更の一部は 2024 年にリリースされ、Adobe Campaignの実装に影響を与えます。 また、iOSアプリの場合、Adobeは、管理者に証明書の設定を許可する方法を変更しています。

## 変更点 {#push-changes}

### Android {#push-android}

Googleのサービス向上のための継続的な取り組みの一環として、従来の FCM API は、 **2024 年 6 月 21 日**. Firebase Cloud Messaging HTTP プロトコルについて詳しくは、 [Google Firebase ドキュメント](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

現在、Adobe Campaign Standardは、Android プッシュ通知メッセージの送信に HTTP レガシー API を使用しており、今後数ヶ月中に HTTP v1 API にアップグレードする予定です。

### iOS {#push-ios}

また、Adobeは、iOSプッシュ通知チャネル用にAdobe Campaign Standardをアップグレードし、管理者がiOSアプリケーション用の証明書を設定できる方法を変更します。 管理者は、Adobe Campaign Standardのユーザーインターフェイスを使用して、iOS証明書をアップロードする必要があります。

## 影響の有無 {#push-impact}

Campaign Standardユーザーは、オーディエンスにプッシュ通知メッセージを送信する場合、影響を受けます。

## 移行方法 {#push-migration}

これらの更新は、モバイルCampaign Standardの設定と権限管理に影響するので、チャネルビルドのアップグレードが必要です。

移行プロセスをスムーズに進めるため、詳細な手順が近日中に提供されます。

この移行を通じて、カスタマーサポートチームがお客様をサポートします。 また、ウェビナーやイネーブルメントセッションを開催して、移行に関する技術的側面やベストプラクティスを取り上げることもできます。

当面は、必要に応じて必要な変更を加える準備が整うよう、この時間を要してAdobe Campaign Standardでの現在の設定とカスタマイズを確認することをお勧めします。

すぐにご不明な点やご質問がある場合は、アドビのサポートチームにお気軽にお問い合わせください。
