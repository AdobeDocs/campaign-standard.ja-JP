---
title: 早期リリースノート
description: 早期リリースノート
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 46c5454ad712910c88bfda7c067fda0337b043d9
workflow-type: ht
source-wordcount: '235'
ht-degree: 100%

---


# 早期リリースノート {#e-new-release}

このページでは、次回の Campaign Standard リリースに含まれる改善点および修正点について説明します。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

## リリース 23.2 - 2023年秋／冬リリース {#fall-23}

>[!AVAILABILITY]
>
>このリリースは、一連の組織のみが使用できます（限定提供）。詳しくは、アドビ担当者にお問い合わせください。

### 改善点 {#e-rn-improvements}

* **Adobe Experience Manager との統合**。Adobe Experience Manager でトランザクションメッセージ用のパーソナライズされた配信テンプレートを作成する際に、Campaign Standard で定義されたパーソナライゼーションフィールドをドロップダウンで選択して使用できるようになりました。

* **cookie の有効期限** - フランスのデータ保護局（CNIL）の推奨事項に合わせて、デフォルトの cookie の有効期限が 6 か月に設定されました。

* **プロファイル検索の改善** - プロファイル検索が最適化され、検索タイムアウトのシナリオを短縮できるようになりました

* **ローカライゼーション** - メッセージの受信をターゲットとしたプロファイルのグループを参照する際の「オーディエンス」という用語の翻訳は、次の言語に関して、すべてのデジタルエクスペリエンス製品で統一されました。

   * ドイツ語：Zielgruppe
   * ポルトガル語（ブラジル）：público-alvo
   * スペイン語：público destinatario

  これらの変更は、次の UI およびドキュメントのリリースで段階的にロールアウトされます。

### その他の変更 {#e-rn-other-changes}

* トランザクションメッセージでは、複数のコンマ区切りのアフィニティの使用をサポートするようになりました。

### 修正点 {#e-rn-fixes}

* 大規模なワークフローの使用時にパフォーマンスの問題を引き起こす可能性があるリグレッションを修正しました。（CAMP-53369）
* ワークフローのアラートまたは通知のメールリンクが機能しない問題を修正しました。（CAMP-51874）
