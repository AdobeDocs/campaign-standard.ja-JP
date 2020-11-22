---
solution: Campaign Standard
product: campaign
title: コントロールルール
description: 制御ルールを使用して、メッセージの品質チェックを強化する方法を説明します。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 18%

---


# コントロールルール {#control-rules}

制御規則を使用すると、文字表示、SMSメッセージのサイズ、アドレス形式など、メッセージが送信される前に、メッセージの有効性と品質を確認できます。

>[!NOTE]
>
>セキュリティ上の理由から、制御ルールは読み取り専用で、変更できません。

## デフォルトのコントロールルール {#default-control-rules}

一連のデフォルトのルールによって、標準のコントロールが保証されます。 次の表に、これらのルールに関する情報と、そのルールに関連するチャネルおよび [実行フェーズを示します](#control-rules-execution-phases)。

| ラベル | チャネル | 実行段階 | 説明 |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | 電子メール | パーソナライゼーションの開始時 | A/Bテストを使用して配信のテスト母集団を抽出します。 |
| **[!UICONTROL Check delivery size]** | すべて | ターゲティングの終了時 | メッセージのサイズをチェックします。 |
| **[!UICONTROL Check email content is not empty]** | 電子メール | ターゲティングの終了時 | メッセージの内容が空の場合にエラーを生成します。 |
| **[!UICONTROL Check In-App content for broadcast template]** | アプリ内 | 開始のパーソナライゼーション | アプリ内コンテンツ/トリガーが、ブロードキャストテンプレート用に空でないことを確認します。 |
| **[!UICONTROL Check In-App content for profile template]** | アプリ内 | パーソナライゼーションの開始時 | アプリ内コンテンツ/トリガーが、プロファイルテンプレート用に空でないことを確認します。 |
| **[!UICONTROL Check In-App content for subscriber template]** | アプリ内 | パーソナライゼーションの開始時 | 購読者テンプレートのアプリ内コンテンツ/トリガーが空でないことを確認します。 |
| **[!UICONTROL Check proof size]** | すべて | ターゲティングの終了時 | 配達確認ターゲットの母集団が100受信者を超える場合にエラーメッセージを生成します。 |
| **[!UICONTROL Check social network sharing link]** | 電子メール | パーソナライゼーションの開始時 | コンテンツにソーシャルネットワーク共有リンク(ViralLinks)を含める場合に、ミラーページへのリンクの存在をチェックします。 |
| **[!UICONTROL Check subject]** | 電子メール | パーソナライゼーションの開始時 | 件名と送信者のアドレスに、特定のメール転送エージェントで問題を引き起こす可能性のある特殊文字が含まれていないことを確認し、メッセージの件名が完了したかどうかを確認します。 |
| **[!UICONTROL Check unsubscription link]** | 電子メール | パーソナライゼーションの開始時 | 各コンテンツ（HTMLおよびテキスト）に少なくとも1つの購読解除（オプトアウト）URLが存在するかどうかを確認します。 |
| **[!UICONTROL Check URL labels]** | 電子メール | パーソナライゼーションの開始時 | 各追跡URLにラベルが付いているかどうかを確認します。 |
| **[!UICONTROL Check URLs]** | 電子メール | パーソナライゼーションの開始時 | トラッキングURLをチェックします（「&amp;」文字の存在）。 |

## ルールの実行フェーズの制御 {#control-rules-execution-phases}

制御ルールは、配信のライフサイクルの異なるフェーズで適用できます。

* **ターゲット設定の開始**:この段階で制御ルールを適用して、パーソナライゼーション手順がエラーのイベントで実行されないようにすることができます。

* **ターゲット設定後**:ターゲット設定の後で実行すると、制御ルールを適用するためのターゲットの量を把握できます。

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **パーソナライゼーションの開始**:チェックがメッセージのパーソナライゼーションの承認に関連する場合に適用されます。 メッセージのパーソナライゼーションは、分析フェーズで実行されます。

* **分析の終了時**:チェックでメッセージのパーソナライゼーションの完了が必要な場合。
