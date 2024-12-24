---
title: 最新のリリースノート
description: このページでは、Adobe Campaign Standard の最新リリースを紹介します。
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---


# 最新のリリースノート {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## 早期リリースノート {#e-new-release}

この節では、次回の Campaign Standard リリースに含まれる改善点および変更点について説明します。

>[!CAUTION]
>
>この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

### リリース 25.1 - 2025年冬リリース {#winter-25}

#### セキュリティ関連の修正 {#winter-25-security}

* このリリースでは、セキュリティ上の問題が修正されています。
* このリリースには、次のセキュリティアップグレードが含まれています。Apache Tomcat が v10.1.33 にアップグレードされました。

#### その他の修正点 {#winter-25-fixes}

* テンプレートでの重複の問題を修正しました（CAMP-56340）
* Adobe Experience Manager テンプレートで動的 URL が使用された際のトラッキングリグレッションを修正しました（CAMP-51932）
* 請求プロセスのパフォーマンスの問題を修正しました（CAMP-56796）
* JSSP web ページの `>` 文字の HTML エンコーディングの問題を修正しました（CAMP-56497）
* 「**選択した行に表示**」オプションを使用する際の動的レポートの問題を修正しました（CAMP-55895）


## リリース 24.2 - 2024年夏リリース（LA） {#summer-24}

### 改善点 {#summer-24-rn-improvements}

**OAuth サーバー間の資格情報への移行**

このバージョン以降、サービスアカウント（JWT）資格情報はアドビによって廃止され、アドビのソリューションおよびアプリとの Campaign アウトバウンド統合は OAuth サーバー間の資格情報に依存するようになりました。アドビでは、Campaign と Analytics 統合や Experience Cloud トリガー統合などのアウトバウンド統合に対して、JWT から OAuth への移行を実行します。

Campaign とのインバウンド統合を実装していて、[Campaign API](../../api/using/get-started-apis.md) を使用している場合は、[このドキュメント](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}の説明に従って、テクニカルアカウントを移行する必要があります。既存のサービスアカウント（JWT）資格情報は、**2025年1月27日（PT）**&#x200B;に機能しなくなります。

### 修正点 {#summer-24-rn-fixes}

* ワークフロースケジューラーがスケジュールされた時間より前に開始される問題を修正しました。（CAMP-55412）
* トランザクションプッシュ通知でカスタムフィールドを複製する際にエラーが発生する問題を修正しました。（CAMP-54459）
* アプリ内メッセージングの日時スケジューラーの使いやすさに影響を与える問題を修正しました。（CAMP-54495）
* カスタムトラッキングエイリアス機能を使用し、リンク全体が動的な場合に、トラッキングが機能しない問題を修正しました。（CAMP-56044）
* 検索を使用して特定のテンプレートを検索する際に、表示されるテンプレートの数が制限される問題を修正しました。（CAMP-55273）
* 優先言語ドロップダウンリストに en_kz（英語 - カザフスタン）および en_ua（英語 - ウクライナ）を追加しました。（CAMP-55336）
* スケジューラー設定で時間調整ボタンが機能しない問題を修正しました。（CAMP-53602）
* スケジューラー設定の時間調整バーに関するいくつかのユーザーインターフェイスの問題を修正しました。（CAMP-55291）
