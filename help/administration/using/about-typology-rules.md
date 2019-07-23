---
title: タイポロジルールについて
seo-title: タイポロジルールについて
description: タイポロジルールについて
seo-description: Adobe Campaignでタイポロジルールがどのように動作するかを確認します。
page-status-flag: 常にアクティブ化されていない
uuid: a98ebc36-172d-4f46- b6ee- b2636a1007c9
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: working- with- typography- rules
discoiquuid: 2590d94c-51ef-4c0f- b1ec- c2837e94da40
context-tags: タイポロジ、概要;TypLogyRule， main;TypLogyRule、概要
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e5532c0769fe33016eaee994bdaae9c70a7eaa5

---


# About typology rules{#about-typology-rules}

タイポロジは、メッセージの分析段階で実行される一連のルールです。これにより、ターゲット、コンテンツ、および次の要素の設定を検証できます。件名、URL、画像、購読解除リンク、配達確認のサイズなど

Adobe Campaignでは、各メッセージにタイポロジへのリンクが含まれています。This link is defined in the advanced parameters of the delivery template's properties (for more on this, refer to the [Preparation](../../administration/using/configuring-email-channel.md#preparation) section).

>[!NOTE]
>
>各メッセージには、1つのタイポロジのみ割り当てることができます。

For each typology, the **[!UICONTROL Typology rules]** section lists the set of rules for this typology.

![](assets/typology_typo-rule-list.png)

## Managing typologies {#managing-typologies}

アプリには、いくつかのタイポロジがデフォルトで存在します。必要に応じて、独自のタイポロジを作成したり、既存のタイポロジを変更したりできます。

1. **[!UICONTROL List of typologies]****[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** メニューからアクセスします。
1. コンテンツとプロパティを変更するか、新しいプロパティを作成するかを選択します。

   ![](assets/typology_list.png)

1. タイポロジのタイプを定義します。タイポロジは、「標準」または「フィルター」のいずれかです。
1. **[!UICONTROL Add an element]** ボタンを使用して必要なタイポロジルールを追加するか、使用しないものを削除します。

   特定のタイポロジにルールが適用される順序を変更できます。これを行うには、要素を移動して、画面に表示される順序を変更します。実行順序に対応する数字が自動的に再計算されます。The rule application mode is presented in the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

   この画面に表示されるルールは、読み取り専用モードでアクセスできます。

タイポロジを使用できます。メッセージプロパティまたはメッセージテンプレートプロパティで選択できます。

>[!NOTE]
>
>**[!UICONTROL IP affinity]** フィールドでは、設定に従って親和性を管理できます。これらはインスタンスの設定ファイルで定義されます。親和性を使用する場合は、管理者にお問い合わせください。

## Typology rules {#typology-rules}

タイポロジルールは、メッセージの準備中に適用されるビジネスルールです。これらは、メッセージが有効であり、品質条件を満たすかどうかを確認するために使用されます。また、ターゲットオーディエンスの各メンバーがメッセージを受信できるかどうかもチェックします。

Typology rules are available under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** menu.

ルールには2種類あります。

* **フィルタ** ルール:を使用すると、特定の数の電子メールを送信済みの隔離されたプロファイルやプロファイルなど、クエリで定義された条件に従って、メッセージターゲットの一部を除外できます。See [Filtering rules](../../administration/using/filtering-rules.md).
* **疲労** ルール:を使用すると、プロファイルごとのメッセージの最大数を定義して、それらを過度に考慮することができなくなります。[疲労ルール](../../administration/using/fatigue-rules.md)を参照してください。
* **制御** ルール:ユーザーが送信する前に、メッセージの有効性と品質（文字表示、SMSメッセージサイズ、アドレス形式など）を確認できます。See [Control rules](../../administration/using/control-rules.md).

タイポロジルールは、1つのチャネルまたはすべてのチャネルにのみ適用できます。

![](assets/typology_channel.png)

**[!UICONTROL Properties]** タイポロジルールでは、その実行順を設定できます。複数のルールを適用する必要がある場合、各ルールの実行順によって、最初に処理する処理が決定されます。For more on this, refer to the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

![](assets/typology_rule-active.png)

A typology rule can be deactivated through its **[!UICONTROL Properties]** if you do not want the rule to be applied at the moment that the messages concerned by the rule are analyzed.

![](assets/typology_rule-order.png)

**[!UICONTROL Targeting context]** カテゴリでは、ターゲット設定するデータに応じて **ターゲットディメンション** と **フィルタリングディメンション** を選択できます。

By default, filtering is carried out on the **[!UICONTROL Profiles]**. For example, if the rule is aimed at a mobile application, the **[!UICONTROL Filtering dimension]** can be changed to **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Typology rules execution order {#typology-rules-execution-order}

タイポロジルールは、ターゲット設定、分析およびメッセージのパーソナライゼーションフェーズで指定された順序で実行されます。

標準操作モードでは、ルールは次の順序で適用されます。

1. 制御ルール（ターゲット設定の開始時に適用される場合）。
1. フィルタルール:

   * アドレス選定用のネイティブアプリケーションルール:アドレス/検証されていないアドレス/ブラックリストに記載されたアドレス/隔離アドレス/アドレスの品質。
   * ユーザーによって定義されたフィルタールール。

1. ターゲットルールがターゲット設定の最後に適用されている場合は、ルールを制御します。
1. 制御ルール（パーソナライゼーションの開始時に適用される場合）。
1. 制御ルール（パーソナライゼーションの最後に適用される場合）。

ただし、各タイポロジで同じタイプのルールの実行順序を調整できます。実際には、同じメッセージ処理段階で複数のルールが実行された場合、適用される順序を選択できます。

例えば、20の位置に実行注文が配置されているフィルタリングルールは、実行順序が30であるフィルタールールの前に実行されます。
