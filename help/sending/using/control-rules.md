---
title: コントロールルール
description: 制御ルールを使用してメッセージの品質チェックを強化する方法について説明します。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
TQID: 'https://experienceleague.adobe.com/lpPFofV3IPl7zmbaR4TOuyCcVqgjwI3maxr-jKzkd0Q'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: e5fb657f-3c0a-4fcc-9980-3589a23ab4de
    internal-label: Typology rules
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 17%
---
# コントロールルール {#control-rules}

コントロールルールを使用すると、文字表示、SMS メッセージサイズ、アドレス形式など、送信される前にメッセージの有効性と品質を確認できます。

>[!NOTE]
>
>セキュリティ上の理由から、コントロールルールは読み取り専用であり、変更できません。

## デフォルトのコントロールルール {#default-control-rules}

一連のデフォルトのルールにより、標準コントロールが確保されます。 以下の表は、これらのルールに関する情報と、関連するチャネルと[実行フェーズ ](#control-rules-execution-phases)に関する情報を示しています。

| ラベル | チャネル | 実行フェーズ | 説明 |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | メール | パーソナライゼーションの開始時 | A/B テストを使用して、配信のテスト母集団を抽出します。 |
| **[!UICONTROL Check delivery size]** | すべて | ターゲティングの終了時 | メッセージのサイズを確認します。 |
| **[!UICONTROL Check email content is not empty]** | メール | ターゲティングの終了時 | メッセージの内容が空の場合にエラーを生成します。 |
| **[!UICONTROL Check In-App content for broadcast template]** | アプリ内 | パーソナライゼーションの開始時 | ブロードキャストテンプレートにアプリ内コンテンツ/トリガーが空でないことを確認します。 |
| **[!UICONTROL Check In-App content for profile template]** | アプリ内 | パーソナライゼーションの開始時 | プロファイルテンプレートにアプリ内コンテンツ/トリガーが空でないことを確認します。 |
| **[!UICONTROL Check In-App content for subscriber template]** | アプリ内 | パーソナライゼーションの開始時 | サブスクライバーテンプレートにアプリ内コンテンツ/トリガーが空でないことを確認します。 |
| **[!UICONTROL Check proof size]** | すべて | ターゲティングの終了時 | プルーフのターゲット母集団が100人の受信者を超える場合、エラーメッセージを生成します。 |
| **[!UICONTROL Check social network sharing link]** | メール | パーソナライゼーションの開始時 | コンテンツにソーシャルネットワーク共有リンク（ViralLinks）を含める場合、ミラーページへのリンクの存在を確認します。 |
| **[!UICONTROL Check subject]** | メール | パーソナライゼーションの開始時 | 件名と送信者アドレスに、特定のメール転送エージェントで問題が発生する可能性のある特殊文字が含まれていないことを確認し、メッセージの件名が完了していることを確認します。 |
| **[!UICONTROL Check unsubscription link]** | メール | パーソナライゼーションの開始時 | 各コンテンツ（HTMLとテキスト）に少なくとも1つの購読解除（オプトアウト） URLが存在することを確認します。 |
| **[!UICONTROL Check URL labels]** | メール | パーソナライゼーションの開始時 | 各トラッキング URLにラベルがあることを確認します。 |
| **[!UICONTROL Check URLs]** | メール | パーソナライゼーションの開始時 | トラッキング URL （「&amp;」文字の有無）を確認します。 |

## 制御ルール実行フェーズ {#control-rules-execution-phases}

コントロールルールは、配信のライフサイクルのさまざまなフェーズで適用できます。

* **ターゲティング開始時**：このフェーズで制御ルールを適用して、エラーが発生した場合にパーソナライゼーションステップを実行しないようにすることができます。

* **ターゲティング後**: ターゲティング後に実行すると、コントロールルールを適用するためにターゲットのボリュームを把握できます。

  例えば、**プルーフサイズを確認**&#x200B;制御ルールは、ターゲティングステージの後に適用されます。このルールは、プルーフ受信者が多すぎる場合、メッセージのパーソナライゼーションの準備を妨げます。

* **パーソナライゼーションの開始時**：チェックがメッセージのパーソナライゼーションの承認に関連する場合に適用されます。 メッセージのパーソナライゼーションは、分析フェーズで実行されます。

* **分析の終了時**：チェックを実行するには、メッセージのパーソナライゼーションを完了する必要がある場合。
