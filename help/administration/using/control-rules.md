---
title: コントロールルール
description: 制御ルールを使用して、メッセージの品質チェックを強化する方法を説明します。
page-status-flag: 非活性化の
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: 活字体系ルール
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# コントロールルール{#control-rules}

制御ルールを使用すると、ユーザーは、メッセージが送信される前に、文字表示、SMSメッセージサイズ、アドレス形式などのメッセージの有効性と品質を確認できます。

Adobe Campaignで使用できる一連のデフォルトルールは、次の標準的なコントロールを保証します。

* **[!UICONTROL Check subject]** （電子メール）:件名と送信者のアドレスに、特定のメール転送エージェントで問題を引き起こす可能性のある特殊文字が含まれていないこと、およびメッセージの件名が完了していることを確認します。
* **[!UICONTROL Check URL labels]** （電子メール）:各追跡URLにラベルが付いているかどうかを確認します。
* **[!UICONTROL Check URLs]** （電子メール）:トラッキングURL（「&amp;」文字の存在）をチェックします。
* **[!UICONTROL Check proof size]** （すべてのチャネル）:配達確認ターゲットの母集団が100人を超える場合にエラーメッセージを生成します。
* **購読解除リンク** （電子メール）の確認：各コンテンツ（HTMLおよびテキスト）に少なくとも1つの購読解除（オプトアウト）URLが存在するかどうかを確認します。
* **[!UICONTROL Check delivery size]** （すべてのチャネル）:メッセージのサイズを確認します。
* **[!UICONTROL Check social network sharing link]** （電子メール）:コンテンツにソーシャルネットワーク共有リンク(ViralLinks)を含める場合に、ミラーページへのリンクが存在するかどうかを確認します。
* **[!UICONTROL A/B Test]**:a/Bテストを使用した配信のテスト母集団を抽出します。

配信のライフサイクルのいずれかの段階から、ルールを適用するタイミングを選択できます。 タイポロジルールのフィールドから、ドロップダウンリストに適用す **[!UICONTROL Phase]** る値を選択します。

![](assets/typology_phase.png)

次のような値を選択できます。

* **ターゲティングの開始時**

   この段階で制御ルールを適用し、エラーが発生した場合にパーソナライゼーションステップを実行しないようにすることができます。

* **ターゲティングの終了時**

   コントロールルールを適用する前にターゲットのボリュームを把握しておきたい場合は、このフェーズを選択します。

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **パーソナライゼーションの開始時**

   チェックでメッセージのパーソナライゼーションの承認に関する問題が発生した場合は、このフェーズを選択する必要があります。 メッセージのパーソナライゼーションは、分析フェーズで実行されます。

* **分析の終了時**

   メッセージのパーソナライゼーションが完了している必要がある場合は、このフェーズを選択します。

>[!NOTE]
>
>セキュリティ上の理由から、制御規則の内容を変更することはできません。 フィールド **[!UICONTROL Code]** は読み取り専用です。
