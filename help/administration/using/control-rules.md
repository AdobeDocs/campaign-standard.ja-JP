---
title: 制御ルール
seo-title: 制御ルール
description: 制御ルール
seo-description: 制御ルールを使用して、メッセージの品質チェックを強化する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 33a1c90c-534e-4fe1-982c- f4e1858d4d2d
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: working- with- typography- rules
discoiquuid: 305cde-6424-4c6f- b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Control rules{#control-rules}

制御ルールを使用すると、ユーザーはメッセージの送信前にメッセージの有効性と品質（文字表示、SMSメッセージサイズ、アドレス形式など）を確認できます。

Adobe Campaignで使用できるデフォルトルールのセットにより、標準コントロールが確認されます。

* **[!UICONTROL Check subject]** （電子メール）:件名および送信者のアドレスに、特定のメール転送エージェントで問題が発生する可能性がある特殊文字が含まれていないことを確認し、メッセージの件名が完了したことを確認します。
* **[!UICONTROL Check URL labels]** （電子メール）:各トラッキングURLにラベルがあることを確認します。
* **[!UICONTROL Check URLs]** （電子メール）:トラッキングURL（"&amp;"文字の存在）をチェックします。
* **[!UICONTROL Check proof size]** （すべてのチャネル）:は、配達確認ターゲット母集団が100人を超えるとエラーメッセージを生成します。
* **購読解除リンク** （電子メール）をチェック:は、各コンテンツに少なくとも1つの購読（オプトアウト） URLが存在するかどうかを確認します（HTMLおよびテキスト）。
* **[!UICONTROL Check delivery size]** （すべてのチャネル）:メッセージのサイズをチェックします。
* **[!UICONTROL Check social network sharing link]** （電子メール）:コンテンツにソーシャルネットワーク共有リンク（virallLinks）を含めるときにミラーページへのリンクが存在するかどうかをチェックします。
* **[!UICONTROL A/B Test]**:テスト用母集団を抽出して、A/Bテストを使用して配信します。

配信のライフサイクルのいずれかの段階からルールを適用するタイミングを選択できます。Select the value to apply in the drop-down list from the **[!UICONTROL Phase]** field of the typology rule.

![](assets/typology_phase.png)

使用できる値は次のとおりです。

* **ターゲット設定の開始時**

   このフェーズで制御ルールを適用すると、エラーが発生した場合にパーソナライゼーションステップが実行されないようになります。

* **ターゲティング後**

   コントロールルールを適用するためにターゲットのボリュームを把握する必要がある場合は、この段階を選択します。

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **パーソナライゼーションの開始時**

   メッセージのパーソナライゼーションを承認するには、この段階を選択する必要があります。メッセージのパーソナライゼーションは、分析段階で実行されます。

* **分析の最後**

   チェックにメッセージパーソナライゼーションが必要な場合は、この段階を選択します。

