---
title: プッシュ通知チャネルの今後の変更
description: プッシュ通知チャネルの今後の変更
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: ac4a52263482557a6d5c370af6df5d54a42671b4
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 25%

---

# プッシュ通知チャネルの今後の変更 {#push-upgrade}

Campaign を使用して、Android およびiOSデバイスでプッシュ通知を送信できます。 これを実行するには、Campaign を特定の購読サービスに依存させます。Android Firebase Cloud Messaging(FCM) サービスに対する重要な変更の一部は、2024 年 24 月 1 日の冬リリースでリリースされ、Adobe Campaignの実装に影響を与えます。 また、iOSアプリの場合、Adobeは、管理者に証明書の設定を許可する方法を変更しています。

## 変更点 {#push-changes}

### Android {#push-android}

Google のサービス向上への継続的な取り組みの一環として、レガシー FCM API は **2024年6月20日（PT）**&#x200B;に廃止されます。Firebase Cloud Messaging HTTP プロトコルについて詳しくは、[Google Firebase ドキュメント](https://firebase.google.com/docs/cloud-messaging/http-server-ref?hl=ja){target="_blank"}を参照してください。

現在、Adobe Campaign Standardは、Android プッシュ通知メッセージの送信に HTTP レガシー API を使用しており、今後数ヶ月中に HTTP v1 API にアップグレードする予定です。

### iOS {#push-ios}

また、Adobeは、iOSプッシュ通知チャネル用にAdobe Campaign Standardをアップグレードし、管理者がiOSアプリケーション用の証明書を設定できる方法を変更します。 2024 年 2 月 24 日以降のリリースでは、管理者は、Adobe Campaign Standardのユーザーインターフェイスを通じて、モバイルアプリケーションプロパティにiOS証明書をアップロードする必要があります。

## 影響の有無 {#push-impact}

Campaign Standardユーザーは、オーディエンスにプッシュ通知メッセージを送信する場合、影響を受けます。

## 移行方法 {#push-migration}

これらの更新は、モバイルチャネルの設定と権限管理に影響を与えるので、Campaign Standardビルドを 24.1 2024 年冬リリースにアップグレードする必要があります。

移行プロセスをスムーズに進めるため、詳細な手順が近日中に提供されます。

この移行を通じて、カスタマーサポートチームがお客様をサポートします。 また、移行に関する技術的側面とベストプラクティスを対象とするウェビナーやイネーブルメントセッションを主催する場合もあります。

当面は、必要に応じて必要な変更を加える準備が整うよう、この時間を要してAdobe Campaign Standardでの現在の設定とカスタマイズを確認することをお勧めします。

すぐにご不明な点やご質問がある場合は、アドビのサポートチームにお気軽にお問い合わせください。
