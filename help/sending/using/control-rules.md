---
title: コントロールルール
description: 制御ルールを使用して、メッセージの品質チェックを強化する方法を説明します。
page-status-flag: never-activated
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 40de67f4c918b26de6d306ce6af5cb8832741d6f

---


# コントロールルール {#control-rules}

制御ルールを使用すると、メッセージが送信される前に、メッセージの有効性と質（文字表示、SMSメッセージのサイズ、アドレスの形式など）を確認できます。

>[!NOTE]
>
>セキュリティ上の理由から、制御ルールは読み取り専用で、変更できません。

## デフォルトのコントロールルール {#default-control-rules}

一連のデフォルトのルールによって、標準のコントロールが保証されます。 次の表に、これらのルールに関する情報と、関連するチャネルおよび実行フェーズを示 [します](#control-rules-execution-phases)。

| ラベル | チャネル | 実行段階 | 説明 |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | E メール | パーソナライゼーションの開始時 | A/Bテストを含む配信のテスト母集団を抽出します。 |
| **[!UICONTROL Check delivery size]** | すべて | ターゲティングの終了時 | メッセージのサイズを確認します。 |
| **[!UICONTROL Check email content is not empty]** | E メール | ターゲティングの終了時 | メッセージの内容が空の場合にエラーを生成します。 |
| **[!UICONTROL Check In-App content for broadcast template]** | アプリ内 | 開始パーソナライゼーション | アプリ内コンテンツ/トリガーが、ブロードキャストテンプレートに対して空でないことを確認します。 |
| **[!UICONTROL Check In-App content for profile template]** | アプリ内 | パーソナライゼーションの開始時 | アプリ内コンテンツ/トリガーが、テンプレートテンプレートの空でないことをプロファイルします。 |
| **[!UICONTROL Check In-App content for subscriber template]** | アプリ内 | パーソナライゼーションの開始時 | 購読者テンプレートのアプリ内コンテンツ/トリガーが空でないことを確認します。 |
| **[!UICONTROL Check proof size]** | すべて | ターゲティングの終了時 | エラーメッセージを生成します(配達確認ターゲットの母集団が100受信者を超える場合)。 |
| **[!UICONTROL Check social network sharing link]** | E メール | パーソナライゼーションの開始時 | コンテンツにソーシャルネットワーク共有リンク(ViralLinks)を含める場合に、ミラーページへのリンクの存在を確認します。 |
| **[!UICONTROL Check subject]** | E メール | パーソナライゼーションの開始時 | 件名と送信者のアドレスに、特定のメール転送エージェントで問題を引き起こす特殊文字が含まれていないことを確認し、メッセージの件名が完了していることを確認します。 |
| **[!UICONTROL Check unsubscription link]** | E メール | パーソナライゼーションの開始時 | 各コンテンツ（HTMLおよびテキスト）に少なくとも1つの購読解除（オプトアウト）URLが存在するかどうかを確認します。 |
| **[!UICONTROL Check URL labels]** | E メール | パーソナライゼーションの開始時 | 各追跡URLにラベルが付いていることを確認します。 |
| **[!UICONTROL Check URLs]** | E メール | パーソナライゼーションの開始時 | 追跡URL（「&amp;」文字の存在）をチェックします。 |

## 制御ルールの実行フェーズ（制御ルール — 実行フェーズ）

制御ルールは、配信のライフサイクルの異なる段階で適用できます。

* **ターゲット設定の開始**:この段階で制御規則を適用し、パーソナライゼーション手順がエラーのイベントで実行されないようにする。

* **ターゲット設定後**:ターゲット設定の後で実行すると、制御ルールを適用するためにターゲットの量を知ることができます。

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **パーソナライゼーションの開始**:チェックがメッセージのパーソナライゼーションの承認に関連する場合に適用されます。 メッセージのパーソナライゼーションは、分析フェーズで実行されます。

* **分析の終了時**:チェックでメッセージのパーソナライゼーションを完了する必要がある場合。
