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
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 22%

---


# 早期リリースノート {#e-new-release}

このページでは、次回の Campaign Standard リリースに含まれる改善点および修正点について説明します。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

## リリース 23.2 - 2023年秋／冬リリース {#fall-23}

>[!AVAILABILITY]
>
>このリリースは、一連の組織（限定提供）でのみ利用できます。 詳しくは、Adobe担当者にお問い合わせください。

### 改善点 {#e-rn-improvements}

* **Adobe Experience Managerとの統合**. Adobe Experience Managerでトランザクションメッセージ用のパーソナライズされた配信テンプレートを作成する際に、ドロップダウンで、Campaign Standardで定義されたパーソナライゼーションフィールドを選択して使用できるようになりました。

* **Cookie の有効期限**  — フランスのデータ保護庁 (CNIL) の推奨に従って、デフォルトの cookie 有効期限が 6 ヶ月に設定されるようになりました。

* **プロファイル検索の改善**  — 検索のタイムアウトシナリオを短縮できるように、プロファイル検索が最適化されました

* **ローカリゼーション**  — メッセージの受信をターゲットとするプロファイルのグループを参照する際の「オーディエンス」という用語の翻訳は、次の言語に関して、すべての Digital Experience 製品間で調整されました。

   * ドイツ語： Zielgruppe
   * ポルトガル語（ブラジル）: público-alvo
   * スペイン語： público destinatario

  これらの変更は、次の UI およびドキュメントリリースで徐々にロールアウトされます。

### その他の変更 {#e-rn-other-changes}

* トランザクションメッセージで、複数のコンマ区切りの親和性を使用できるようになりました。

### 修正点 {#e-rn-fixes}

* 大きなワークフローを使用する際にパフォーマンスの問題が発生する可能性がある問題を修正しました。 （CAMP-53369）
* ワークフローのアラートまたは通知の電子メールリンクが機能しない問題を修正しました。 （CAMP-51874）
