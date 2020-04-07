---
title: タイポロジルール
description: 使い方を知るタイポロジルール。
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c5b1882e143924f94530c166b6af61a1bce30d72

---


# タイポロジルール {#managing-typology-rules}

## タイポロジルールについて {#about-typology-rules}

タイポロジルールとは、メッセージを送信する前にメッセージのチェックとフィルタリングを実行できるビジネスルールです。 使用できるタイポロジルールの種類：

* **フィルタリング** ・ルール：この種のルールでは、隔離されたプロファイルや、特定の数の電子メールが既に送信されたプロファイルなど、クエリで定義された条件に従って、メッセージターゲットの一部を除外できます。 詳しくは、[この節](../../sending/using/filtering-rules.md)を参照してください。

* **疲労ルール** :この種のルールでは、過剰な要請を避けるために、プロファイルごとの最大メッセージ数を定義できます。 詳しくは、[この節](../../sending/using/fatigue-rules.md)を参照してください。

* **制御規則** :この種のルールを使用すると、メッセージが送信される前に、文字表示、SMSメッセージのサイズ、アドレスの形式など、メッセージの有効性と品質を確認できます。 詳しくは、[この節](../../sending/using/control-rules.md)を参照してください。

タイポロジルールは、 > > > **[!UICONTROL Administration]** >のメニュ **[!UICONTROL Channels]** ーで使用 **[!UICONTROL Typologies]** でき **[!UICONTROL Typology rules]** ます。

デフォルトでは、あらかじめ用意されている複数のフィルタリング **** /制御 **** タイポロジルールが使用できます。 詳細は、「フィルタリングルール [」と「制御ルール](../../sending/using/fatigue-rules.md)[」の節](../../sending/using/control-rules.md) に記載されています。

必要に応じて、既存のタイポロジルールを変更したり、新しいを作成したりできます。ただし、ルールは読み取り専用で、 **[!UICONTROL Control]** 変更することはできません。

## タイポロジルールの作成 {#creating-a-typology-rule}

タイポロジルールを作成する主な手順は次のとおりです。

1. / **[!UICONTROL Administration]** / **[!UICONTROL Channels]** /メニューにア **[!UICONTROL Typologies]** クセ **[!UICONTROL Typology rules]** スし、をクリックしま **[!UICONTROL Create]**&#x200B;す。

![](assets/typology_create-rule.png)

1. タイポロジを入力 **[!UICONTROL Label]**&#x200B;し、ルールを適 **[!UICONTROL Channel]** 用する対象を指定します。

![](assets/typology-rule-label.png)

1. タイポロジルールを **[!UICONTROL Type]**&#x200B;指定し、必要に応じて設定します。 タイポロジルールの設定はタイプによって異なります。 詳しくは、「フィルタリングルール」および「疲 **[労ルール](../../sending/using/filtering-rules.md)**」の節を**[&#x200B;参照してください](../../sending/using/fatigue-rules.md)** 。

1. 新しいルールを含めるタイポロジを選択します。 これを行うには、タブを選択し **[!UICONTROL Typologies]** て、ボタンをクリック **[!UICONTROL Create element]** します。

![](assets/typology-typologies-tab.png)

1. 目的のタイポロジを選択し、をクリックしま **[!UICONTROL Confirm]**&#x200B;す。

![](assets/typology-link.png)

1. すべてのタイポロジを選択したら、をクリックし **[!UICONTROL Create]** てタイポロジの作成をタイポロジルールします。

## タイポロジルールの実行順序 {#typology-rules-execution-order}

タイポロジルールは、ターゲット設定、分析、メッセージパーソナライゼーションの各段階で指定された順序で実行されます。

標準の操作モードでは、ルールは次の順序で適用されます。

1. ターゲティングの開始時に適用されるコントロールルール
1. フィルタールール:

   * デフォルトで適用されるアドレス選定ルール（定義されたアドレス／検証されていないアドレス／ブラックリストに登録されたアドレス／強制隔離されたアドレス／アドレスの質）
   * ユーザーによって定義されたフィルタールール

1. ターゲティングの終了時に適用されるコントロールルール
1. パーソナライゼーションの開始時に適用されるコントロールルール
1. 制御ルール（パーソナライゼーションの最後に適用される場合）。

ただし、各タイポロジで同じタイプのルールの実行順序を適応させることができます。 実際、同じメッセージ処理段階で複数のルールが実行される場合、適用する順序を選択できます。

例えば、実行順序が20のフィルタリングルールは、実行順序が30のフィルタリングルールよりも前に実行されます。

の実行順 **[!UICONTROL Properties]** 序はタイポロジルールで設定できます。 複数のルールを適用する必要がある場合、各ルールの実行順序によって、最初に処理するルールが決まります。 詳しくは、「 [タイポロジルールの実行順序](#typology-rules-execution-order) 」を参照。

![](assets/typology_rule-active.png)

タイポロジルールは、ルールに関連す **[!UICONTROL Properties]** るメッセージを分析する際にルールを適用しない場合、そのルールを通じて非アクティブ化できます。

![](assets/typology_rule-order.png)