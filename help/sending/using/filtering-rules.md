---
title: フィルタールール
description: フィルタリングルールを使用して、メッセージのオーディエンスを絞り込みます。
page-status-flag: never-activated
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ba1fcca02ce9582d85e57bde815ccf3f551ac7a3

---


# フィルタールール {#filtering-rules}

フィルタリングルールを使用すると、隔離されたプロファイルや、特定の数の電子メールが既に送信されたプロファイルなど、クエリで定義された条件に従って、メッセージターゲットの一部を除外できます。

## デフォルトのフィルタータイポロジルール {#default-filtering-typology-rules}

次の表に、標準搭載のフィルタールールとその関連チャネルを示します。

| ラベル | チャネル | 説明 |
---------|----------|---------
| **[!UICONTROL Address not specified]** | すべて | 指定したターゲット（電子メール、住所など）のないアドレスを含む訪問者を除外します。 をチャネル)。 |
| **[!UICONTROL Blacklisted address]** | すべて | ブラックリスト登録済みアドレスを除外します。 |
| **[!UICONTROL Duplicate]** | すべて | 重複母集団フィールドに基づいてターゲットを除外 **[!UICONTROL Address]** します。 |
| **[!UICONTROL Exclude mobile applications]** | モバイルアプリケーション | メッセージで定義された購読と一致しないアプリのアプリを除外します。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | アプリ内 | メッセージで定義されたモバイル購読（アプリ内テンプレート）と一致しないアプリテンプレートを除外します。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | アプリ内 | メッセージで定義されたモバイル購読（アプリ内ブロードキャストテンプレート）と一致しないアプリテンプレートを除外します。 |
| **[!UICONTROL Exclude mobile applications for Push]** | モバイルアプリケーション | メッセージで定義されたモバイル購読と一致しないアプリアプリアプリを除外します（プッシュ用） |
| **[!UICONTROL Quarantined address]** | すべて | 隔離されたアドレスを除外します。 |
| **[!UICONTROL Target limited in size]** | すべて | 最大配信サイズに達したかどうかを確認します。 「配信制限」オプションが有効なダイレクトメール配信に適用されます。 |

これらのデフォルトのフィルタールールに加え、2つの除外ルールを使用できます。

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

電子メールの分析時には、配信性能インスタンスで管理された暗号化グローバル抑止リストに含まれている禁止アドレスや禁止ドメイン名がこれらのルールによって照合され、受信者の電子メールアドレスが該当していないかどうかの確認処理が実行されます。該当した場合、その受信者宛てにはメッセージが送信されません。

これは、Spamtrap などの悪意あるアクティビティによってブラックリストに登録されることを防ぐためです。例えば、会社の Web フォーム経由で Spamtrap を使用して購読処理が実行されると、Spamtrap 宛てに確認メールが自動送信され、お使いのアドレスが自動的にブラックリスト登録される結果になります。

>[!NOTE]
>
>グローバル抑止リストに含まれているアドレスやドメイン名は非公開です。除外された受信者の数に関する情報だけが配信分析ログに記録されます。

## フィルタールールの作成 {#creating-a-filtering-rule}

必要に応じて独自のフィルタールールを作成できます。 例えば、ニュースレターのターゲット人口をフィルタリングして、18歳未満の購読者が通信を受け取らないようにすることができます。

フィルタリングタイポロジルールを作成するには：

1. 新しいタイポロジルールを作成 この節では、タイポロジルールを作成する主な手順を [説明します](../../sending/using/managing-typology-rules.md)。

1. ルールタイプ **[!UICONTROL Filtering]** を選択し、目的のチャネルを指定します。

1. タブで、 **[!UICONTROL Filtering criteria]** カテゴリ内のオプションを選択し **[!UICONTROL Subscription]** ます。

   ![](assets/typology_create-rule-subscription.png)

1. ノードエ **[!UICONTROL Explorer]** ディターのタブで、クエリを画面のメ **[!UICONTROL Subscriber]** インパーツにドラッグ&amp;ドロップします。

   ![](assets/typology_create-rule-subscriber.png)

1. フィールド **[!UICONTROL Age]** を選択し、購読者の年齢が18才以上になるようにフィルター条件を定義します。

   ![](assets/typology_create-rule-age.png)

1. タブで、こ **[!UICONTROL Typologies]** のルールをタイポロジにリンクします。

   ![](assets/typology_create-rule-typology.png)

1. 使用する配信または配信テンプレートでタイポロジが選択されていることを確認します。 詳しくは、[この節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)を参照してください。

   ![](assets/typology_template.png)

このルールがメッセージで使用されると、未成年と見なされる購読者は自動的に除外されます。

## フィルタールールのターゲットコンテキストの設定 {#configuring-filtering-rules-targeting-context}

Campaign Standardを使用すると、ターゲット **するデー** タに応じて **** 、使用するターゲットディメンションとフィルターディメンションを設定できます。

これを行うには、タイポロジルールのプロパティを開き、セクションにアクセス **[!UICONTROL Advanced information]** します。

デフォルトでは、フィルタリングはに対して実行されま **[!UICONTROL Profiles]**&#x200B;す。 例えば、ルールがモバイルアプリケーションを対象としている場合、をに変 **[!UICONTROL Filtering dimension]** 更することができま **[!UICONTROL Subscriptions to an application]**&#x200B;す。

![](assets/typology_rule-order_2.png)

## フィルタリングルールの適用の制限 {#restricting-the-applicability-of-a-filtering-rule}

送信するメッセージに従って、フィルタリングルールの適用を制限できます。

1. タイポロジルールのタブで、 **[!UICONTROL Application criteria]** オプションのチェッ **[!UICONTROL Apply the rule on all deliveries]** クを外します（デフォルトで有効）。

   ![](assets/typology_limit.png)

1. フィルターを定義するには、クエリエディターを使用します。 例えば、特定の単語を持つラベル開始や特定の文字を含むIDを持つメッセージにのみルールを適用できます。

   ![](assets/typology_limit-rule.png)

この場合、ルールは、定義された条件に対応するメッセージにのみ適用されます。
