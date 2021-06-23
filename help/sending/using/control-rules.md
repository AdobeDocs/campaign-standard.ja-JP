---
solution: Campaign Standard
product: campaign
title: コントロールルール
description: 制御ルールを使用して、メッセージの品質チェックを強化する方法を説明します。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: タイポロジルール
role: Business Practitioner
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
source-git-commit: c41d51538b8a8376a034c7d2db77b66b21256fd8
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 19%

---

# コントロールルール {#control-rules}

コントロールルールを使用すると、文字表示、SMSメッセージのサイズ、アドレス形式など、メッセージが送信される前に、メッセージの有効性と品質を確認できます。

>[!NOTE]
>
>セキュリティ上の理由から、コントロールルールは読み取り専用で、変更できません。

## デフォルトのコントロールルール {#default-control-rules}

一連のデフォルトのルールによって、標準のコントロールが保証されます。 次の表に、これらのルールに関する情報と、関連するチャネルおよび[実行フェーズ](#control-rules-execution-phases)を示します。

| ラベル | チャネル | 実行段階 | 説明 |
|---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | メール | パーソナライゼーションの開始時 | A/Bテストを使用して配信のテスト母集団を抽出します。 |
| **[!UICONTROL Check delivery size]** | すべて | ターゲティングの終了時 | メッセージのサイズをチェックします。 |
| **[!UICONTROL Check email content is not empty]** | メール | ターゲティングの終了時 | メッセージの内容が空の場合にエラーを生成します。 |
| **[!UICONTROL Check In-App content for broadcast template]** | アプリ内 | パーソナライゼーションの開始時 | ブロードキャストテンプレートのアプリ内コンテンツ/トリガーが空でないことを確認します。 |
| **[!UICONTROL Check In-App content for profile template]** | アプリ内 | パーソナライゼーションの開始時 | プロファイルテンプレートのアプリ内コンテンツ/トリガーが空でないことを確認します。 |
| **[!UICONTROL Check In-App content for subscriber template]** | アプリ内 | パーソナライゼーションの開始時 | 購読者テンプレートのアプリ内コンテンツ/トリガーが空でないことを確認します。 |
| **[!UICONTROL Check proof size]** | すべて | ターゲティングの終了時 | 配達確認のターゲット母集団が100人を超える場合にエラーメッセージを生成します。 |
| **[!UICONTROL Check social network sharing link]** | メール | パーソナライゼーションの開始時 | コンテンツにソーシャルネットワーク共有リンク(ViralLinks)を含める場合、ミラーページへのリンクの有無を確認します。 |
| **[!UICONTROL Check subject]** | メール | パーソナライゼーションの開始時 | 件名と送信者のアドレスに、特定のメール転送エージェントで問題を引き起こす可能性のある特殊文字が含まれていないかを確認し、メッセージの件名が完了したかどうかを確認します。 |
| **[!UICONTROL Check unsubscription link]** | メール | パーソナライゼーションの開始時 | 各コンテンツ（HTMLおよびテキスト）に購読解除（オプトアウト）URLが少なくとも1つ存在するかどうかを確認します。 |
| **[!UICONTROL Check URL labels]** | メール | パーソナライゼーションの開始時 | 各トラッキングURLにラベルがあることを確認します。 |
| **[!UICONTROL Check URLs]** | メール | パーソナライゼーションの開始時 | トラッキングURLをチェックします（&amp;文字が含まれている）。 |

## コントロールルールの実行フェーズ {#control-rules-execution-phases}

コントロールルールは、配信のライフサイクルの様々なフェーズで適用できます。

* **ターゲティングの開始時**:このフェーズでコントロールルールを適用して、エラーが発生した場合にパーソナライゼーション手順を実行しないようにすることができます。

* **ターゲット設定後**:ターゲティング後に実行すると、コントロールルールを適用するために、ターゲットのボリュームを把握できます。

   例えば、「配達確認のサイズを確認&#x200B;**」コントロールルールは、ターゲティングステージの後に適用されます。このルールは、配達確認の受信者が多すぎる場合に、メッセージのパーソナライゼーションを準備しないようにします。**

* **パーソナライゼーションの開始時**:チェックがメッセージのパーソナライゼーションの承認に関連する場合に適用されます。メッセージのパーソナライゼーションは、分析フェーズで実行されます。

* **分析の終了時**:チェックでメッセージのパーソナライゼーションを完了する必要がある場合。
