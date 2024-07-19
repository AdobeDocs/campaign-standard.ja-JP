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
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 23%

---

# フィルタリングルール {#filtering-rules}

フィルタリングルールを使用すると、強制隔離されたプロファイルや一定数のメールが既に送信されているプロファイルなど、クエリで定義された条件に従ってメッセージターゲットの一部を除外できます。

## デフォルトのフィルタータイポロジルール {#default-filtering-typology-rules}

標準のフィルタールールと、関連チャネルの情報を次の表に示します。

| ラベル | チャネル | 説明 |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | すべて | アドレス（メール、住所など）が指定されていないターゲット母集団を除外します。 （選択したチャネルによる） |
| **[!UICONTROL Address on denylist]** | すべて | ブロックリスト上のアドレスを除外します。 |
| **[!UICONTROL Duplicate]** | すべて | ターゲット母集団の **[!UICONTROL Address]** フィールドに基づいて重複を除外します。 |
| **[!UICONTROL Exclude mobile applications]** | モバイルアプリケーション | メッセージで定義されたモバイルアプリケーションに一致しないアプリ購読を除外します。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | アプリ内 | メッセージで定義されたモバイルアプリケーション （アプリ内テンプレート）に一致しないアプリ購読を除外します。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | アプリ内 | メッセージで定義されたモバイルアプリケーション （アプリ内ブロードキャストテンプレート）に一致しないアプリ購読を除外します。 |
| **[!UICONTROL Exclude mobile applications for Push]** | モバイルアプリケーション | メッセージで定義されたモバイルアプリケーションに一致しないアプリ購読を除外します（プッシュ用） |
| **[!UICONTROL Quarantined address]** | すべて | 強制隔離されたアドレスを除外します。 |
| **[!UICONTROL Target limited in size]** | すべて | ターゲットの最大配信サイズに達したかどうかを確認します。 「配信制限」オプションが有効になっているダイレクトメール配信に適用されます。 |

これらのデフォルトのフィルタリングルールに加えて、次の 2 つの除外ルールを使用できます。

* **[!UICONTROL Exclusion of addresses]** （**[!UICONTROL addressExclusions]**）
* **[!UICONTROL Exclusion of domains]** （**[!UICONTROL domainExclusions]**）。

電子メールの分析時には、配信性能インスタンスで管理された暗号化グローバル抑止リストに含まれている禁止アドレスや禁止ドメイン名がこれらのルールによって照合され、受信者の電子メールアドレスが該当していないかどうかの確認処理が実行されます。該当した場合、その受信者宛てにはメッセージが送信されません。

これは、Spamtrap などの悪意あるアクティビティによってブロックリストに登録されることを防ぐためです。例えば、会社の Web フォーム経由で Spamtrap を使用して購読処理が実行されると、Spamtrap 宛てに確認メールが自動送信され、お使いのアドレスが自動的にブロックリスト登録される結果になります。

>[!NOTE]
>
>グローバル抑止リストに含まれているアドレスやドメイン名は非公開です。除外された受信者の数に関する情報だけが配信分析ログに記録されます。

## フィルタールールの作成 {#creating-a-filtering-rule}

必要に応じて、独自のフィルタールールを作成できます。 例えば、ニュースレターのターゲット母集団をフィルタリングして、18 歳未満の購読者がコミュニケーションを受け取らないようにすることができます。

フィルタータイポロジルールを作成するには、次の手順に従います。

1. 新しいタイポロジルールを作成します。 タイポロジルールを作成する主な手順については、[ この節 ](../../sending/using/managing-typology-rules.md) を参照してください。

1. **[!UICONTROL Filtering]** のルールタイプを選択してから、目的のチャネルを指定します。

1. 「**[!UICONTROL Filtering criteria]**」タブで、**[!UICONTROL Subscription]** カテゴリ内の購読を選択します。

   ![](assets/typology_create-rule-subscription.png)

1. クエリエディターの「**[!UICONTROL Explorer]**」タブで、**[!UICONTROL Subscriber]** ノードを画面のメイン部分にドラッグ&amp;ドロップします。

   ![](assets/typology_create-rule-subscriber.png)

1. 「**[!UICONTROL Age]**」フィールドを選択し、購読者の年齢が 18 歳未満になるようにフィルター条件を定義します。

   ![](assets/typology_create-rule-age.png)

1. 「**[!UICONTROL Typologies]**」タブで、このルールをタイポロジにリンクします。

   ![](assets/typology_create-rule-typology.png)

1. 使用する配信または配信テンプレートでタイポロジが選択されていることを確認します。 詳しくは、[この節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)を参照してください。

   ![](assets/typology_template.png)

このルールがメッセージで使用されるたびに、未成年と見なされる購読者は自動的に除外されます。

## フィルタールールのターゲティングコンテキストの設定 {#configuring-filtering-rules-targeting-context}

Campaign Standardでは、ターゲット設定するデータに応じて、使用する **ターゲティング** ディメンションと **フィルタリング** ディメンションを設定できます。

それには、タイポロジルールのプロパティを開き、「**[!UICONTROL Advanced information]**」セクションにアクセスします。

デフォルトでは、**[!UICONTROL Profiles]** ージに対してフィルタリングが実行されます。 例えば、ルールがモバイルアプリケーションを対象としている場合、**[!UICONTROL Filtering dimension]** を **[!UICONTROL Subscriptions to an application]** に変更できます。

![](assets/typology_rule-order_2.png)

## フィルタールールの適用可能性の制限 {#restricting-the-applicability-of-a-filtering-rule}

送信するメッセージに応じて、フィルタールールの適用を制限できます。

1. タイポロジルールの「**[!UICONTROL Application criteria]**」タブで、デフォルトで有効になっている「**[!UICONTROL Apply the rule on all deliveries]**」オプションのチェックを外します。

   ![](assets/typology_limit.png)

1. クエリエディターを使用してフィルターを定義します。 例えば、特定の単語でラベルが始まるメッセージや、特定の文字を含む ID のメッセージにのみルールを適用できます。

   ![](assets/typology_limit-rule.png)

この場合、ルールは、定義された条件に対応するメッセージにのみ適用されます。
