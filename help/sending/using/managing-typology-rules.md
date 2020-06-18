---
title: タイポロジルールの管理
description: タイポロジルールの使い方を知る。
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
source-git-commit: 7f5bc442b1dae467a6b6de3e048531940f75031f
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 16%

---


# タイポロジルールの管理 {#managing-typology-rules}

## タイポロジルールについて {#about-typology-rules}

タイポロジルールとは、メッセージを送信する前に、メッセージに対するチェックやフィルタリングを実行できるビジネスルールです。 使用できるタイポロジルールのタイプは次のとおりです。

* **フィルタリング** ・ルール： この種のルールでは、検疫済みのプロファイルや、既に一定数の電子メールが送信されたプロファイルなど、クエリで定義された条件に従って、メッセージターゲットの一部を除外できます。 詳しくは、[この節](../../sending/using/filtering-rules.md)を参照してください。

* **疲労** 規則： この種のルールでは、過度の要請を回避するために、プロファイルあたり最大メッセージ数を定義できます。 詳しくは、[この節](../../sending/using/fatigue-rules.md)を参照してください。

* **制御規則** : この種類のルールでは、文字表示、SMSメッセージサイズ、アドレス形式など、メッセージが送信される前に、メッセージの有効性と品質を確認できます。 詳しくは、[この節](../../sending/using/control-rules.md)を参照してください。

タイポロジルールは、 > > **[!UICONTROL Administration]** > **[!UICONTROL Channels]** >の **[!UICONTROL Typologies]****[!UICONTROL Typology rules]** メニューから利用できます。

デフォルトでは、あらかじめ用意されている **フィルタリング** および **** 制御タイポロジルールがいくつか使用できます。 これらの詳細は、「 [フィルタールール](../../sending/using/fatigue-rules.md) 」および「 [制御ルール](../../sending/using/control-rules.md) 」セクションを参照してください。

必要に応じて、既存のタイポロジルールを変更したり、新しく作成できます。ただし、 **[!UICONTROL Control]** ルールは読み取り専用で、変更できません。

## タイポロジルールの作成 {#creating-a-typology-rule}

タイポロジルールを作成する主な手順は次のとおりです。

1. / / **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Typologies]** メニューにアクセスし、をクリックし **[!UICONTROL Typology rules]****[!UICONTROL Create]**&#x200B;ます。

   ![](assets/typology_create-rule.png)

1. タイポロジを入力 **[!UICONTROL Label]**&#x200B;し、ルールを適用 **[!UICONTROL Channel]** する対象を指定します。

   ![](assets/typology-rule-label.png)

1. タイポロジルールを指定 **[!UICONTROL Type]**&#x200B;し、必要に応じて設定します。 タイポロジルールの設定は、タイプによって異なります。 詳しくは、「 **[フィルタリングルール](../../sending/using/filtering-rules.md)**」および「**[&#x200B;疲労ルール](../../sending/using/fatigue-rules.md)** 」の節を参照してください。

1. 新しいルールを含めるタイポロジを選択します。 これを行うには、 **[!UICONTROL Typologies]** タブを選択し、 **[!UICONTROL Create element]** ボタンをクリックします。

   ![](assets/typology-typologies-tab.png)

1. 目的のタイポロジを選択し、をクリックし **[!UICONTROL Confirm]**&#x200B;ます。

   ![](assets/typology-link.png)

1. すべてのタイポロジを選択したら、をクリックし **[!UICONTROL Create]** てタイポロジルールの作成を確認します。

## タイポロジルールの実行順序 {#typology-rules-execution-order}

タイポロジルールは、ターゲット設定、分析、およびメッセージのパーソナライゼーションの各段階で指定された順序で実行されます。

標準の操作モードでは、ルールは次の順序で適用されます。

1. ターゲティングの開始時に適用されるコントロールルール
1. フィルタールール:

   * 住所資格のネイティブアプリケーションルール： ブロックリスト上の定義済みのアドレス/未確認のアドレス/アドレス/検疫済みのアドレス/アドレスの質。
   * ユーザーによって定義されたフィルタールール

1. ターゲティングの終了時に適用されるコントロールルール
1. パーソナライゼーションの開始時に適用されるコントロールルール
1. 制御ルール（パーソナライゼーションの終了時に適用される場合）。

ただし、各タイポロジで同じタイプのルールの実行順序を適応させることができます。 実際、同じメッセージ処理段階で複数のルールが実行される場合は、適用する順序を選択できます。

例えば、実行順序が20番のフィルタリングルールは、実行順序が30番のフィルタリングルールの前に実行されます。

タイポロジルール **[!UICONTROL Properties]** ので、実行順序を設定できます。 複数のルールを適用する必要がある場合、各ルールの実行順序によって、最初に処理するルールが決まります。 詳しくは、「 [タイポロジルールの実行順序](#typology-rules-execution-order) 」の節を参照してください。

![](assets/typology_rule-active.png)

ルールに関連するタイポロジルールを分析する際に、ルールを適用しない **[!UICONTROL Properties]** 場合は、そのメッセージを通じてメッセージを非アクティブ化できます。

![](assets/typology_rule-order.png)