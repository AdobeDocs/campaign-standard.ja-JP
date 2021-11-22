---
title: フィルタリングルール
description: フィルタールールを使用して、メッセージのオーディエンスを絞り込みます。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 43e97f3c-ed82-4fcc-ac0d-fcee6a22da35
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 23%

---

# フィルタリングルール {#filtering-rules}

フィルタリングルールを使用すると、強制隔離されたプロファイルや、特定の数の E メールを既に送信したプロファイルなど、クエリで定義された条件に従って、メッセージターゲットの一部を除外できます。

## デフォルトのフィルタータイポロジルール {#default-filtering-typology-rules}

次の表に、標準のフィルタールールと、その関連チャネルに関する情報を示します。

| ラベル | チャネル | 説明 |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | すべて | 指定したアドレス（E メール、郵送先住所など）を持たないターゲット母集団を除外します。 選択したチャネルに従う )。 |
| **[!UICONTROL Address on denylist]** | すべて | アドレス上のアドレスを除外しブロックリストます。 |
| **[!UICONTROL Duplicate]** | すべて | ターゲット母集団に基づいて重複を除外 **[!UICONTROL Address]** フィールドに入力します。 |
| **[!UICONTROL Exclude mobile applications]** | モバイルアプリケーション | メッセージで定義されたモバイルアプリと一致しないアプリを除外します。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | アプリ内 | メッセージに定義されたモバイルアプリと一致しないアプリを除外します（アプリ内テンプレート）。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | アプリ内 | メッセージに定義されたモバイルアプリと一致しないアプリを除外する（アプリ内ブロードキャストテンプレート） |
| **[!UICONTROL Exclude mobile applications for Push]** | モバイルアプリケーション | メッセージで定義されたモバイルアプリと一致しないアプリの購読を除外します（プッシュの場合） |
| **[!UICONTROL Quarantined address]** | すべて | 強制隔離されたアドレスを除外します。 |
| **[!UICONTROL Target limited in size]** | すべて | ターゲットの最大配信サイズに達したかどうかを確認します。 「配信制限」オプションが有効なダイレクトメール配信に適用されます。 |

これらのデフォルトのフィルタールールに加えて、次の 2 つの除外ルールを使用できます。

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ) をクリックします。

電子メールの分析時には、配信性能インスタンスで管理された暗号化グローバル抑止リストに含まれている禁止アドレスや禁止ドメイン名がこれらのルールによって照合され、受信者の電子メールアドレスが該当していないかどうかの確認処理が実行されます。該当した場合、その受信者宛てにはメッセージが送信されません。

これは、Spamtrap などの悪意あるアクティビティによってブロックリストに登録されることを防ぐためです。例えば、会社の Web フォーム経由で Spamtrap を使用して購読処理が実行されると、Spamtrap 宛てに確認メールが自動送信され、お使いのアドレスが自動的にブロックリスト登録される結果になります。

>[!NOTE]
>
>グローバル抑止リストに含まれているアドレスやドメイン名は非公開です。除外された受信者の数に関する情報だけが配信分析ログに記録されます。

## フィルタールールの作成 {#creating-a-filtering-rule}

必要に応じて、独自のフィルタールールを作成できます。 例えば、ニュースレターのターゲット母集団をフィルタリングして、18 歳未満の購読者が通信を受け取らないようにすることができます。

フィルタータイポロジルールを作成するには、次の手順に従います。

1. 新しいタイポロジルールを作成します。 タイポロジルールを作成する主な手順について詳しくは、 [この節](../../sending/using/managing-typology-rules.md).

1. を選択します。 **[!UICONTROL Filtering]** ルールタイプを選択し、目的のチャネルを指定します。

1. 内 **[!UICONTROL Filtering criteria]** 」タブで、 **[!UICONTROL Subscription]** カテゴリ。

   ![](assets/typology_create-rule-subscription.png)

1. 内 **[!UICONTROL Explorer]** クエリエディターの「 」タブで、 **[!UICONTROL Subscriber]** ノードを画面のメイン部分に追加します。

   ![](assets/typology_create-rule-subscriber.png)

1. を選択します。 **[!UICONTROL Age]** 「 」フィールドでフィルター条件を定義し、購読者の年齢が 18 歳以上になるようにします。

   ![](assets/typology_create-rule-age.png)

1. 内 **[!UICONTROL Typologies]** 「 」タブで、このルールをタイポロジにリンクします。

   ![](assets/typology_create-rule-typology.png)

1. 使用する配信または配信テンプレートで、タイポロジが選択されていることを確認します。 詳しくは、[この節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)を参照してください。

   ![](assets/typology_template.png)

このルールがメッセージで使用されるたびに、未成年と見なされる購読者は自動的に除外されます。

## フィルタールールのターゲティングコンテキストの設定 {#configuring-filtering-rules-targeting-context}

Campaign Standardでは、  **ターゲット設定** および **フィルター** ターゲットにするデータに応じて使用するディメンション。

これをおこなうには、タイポロジルールのプロパティを開き、 **[!UICONTROL Advanced information]** 」セクションに入力します。

デフォルトでは、 **[!UICONTROL Profiles]**. 例えば、ルールの対象がモバイルアプリケーションの場合、 **[!UICONTROL Filtering dimension]** は、 **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## フィルタリングルールの適用の制限 {#restricting-the-applicability-of-a-filtering-rule}

送信するメッセージに応じて、フィルタリングルールの適用を制限できます。

1. タイポロジルールの **[!UICONTROL Application criteria]** タブを選択し、「 」チェックボックスをオフにします。 **[!UICONTROL Apply the rule on all deliveries]** オプションに含まれます。これはデフォルトで有効になっています。

   ![](assets/typology_limit.png)

1. クエリエディターを使用して、フィルターを定義します。 例えば、特定の単語で始まるラベルや、特定の文字が ID に含まれるメッセージに対してのみ、ルールを適用できます。

   ![](assets/typology_limit-rule.png)

この場合、ルールは定義された条件に対応するメッセージにのみ適用されます。
