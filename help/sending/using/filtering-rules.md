---
solution: Campaign Standard
product: campaign
title: フィルタールール
description: フィルタールールを使用して、メッセージのオーディエンスを絞り込みます。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: タイポロジルール
role: 開業医
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 23%

---


# フィルタールール {#filtering-rules}

フィルタールールを使用すると、隔離されたプロファイルや、特定の数の電子メールが既に送信されたプロファイルなど、クエリで定義された条件に従って、メッセージターゲットの一部を除外できます。

## 既定のフィルタタイポロジルール{#default-filtering-typology-rules}

次の表に、そのまま使用できるフィルタリングルールと、その関連チャネルに関する情報を示します。

| ラベル | チャネル | 説明 |
---------|----------|---------
| **[!UICONTROL Address not specified]** | すべて | 指定したアドレス（電子メール、住所など）を持たないターゲットの人口を除外します。 」をクリックします)。 |
| **[!UICONTROL Address on denylist]** | すべて | 上のアドレスを除外ブロックリストします。 |
| **[!UICONTROL Duplicate]** | すべて | ターゲット母集団&#x200B;**[!UICONTROL Address]**&#x200B;フィールドに基づいて重複を除外します。 |
| **[!UICONTROL Exclude mobile applications]** | モバイルアプリケーション | メッセージ内で定義されているモバイルアプリと一致しないアプリ購読を除外します。 |
| **[!UICONTROL Exclude mobile applications for In-App]** | アプリ内 | メッセージ内で定義されているモバイルアプリ（アプリ内テンプレート）と一致しない購読を除外します。 |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | アプリ内 | メッセージ内で定義されているモバイルアプリ（アプリ内ブロードキャストテンプレート）に一致しないアプリ購読を除外します。 |
| **[!UICONTROL Exclude mobile applications for Push]** | モバイルアプリケーション | メッセージ内で定義されているモバイルアプリと一致しないアプリ購読を除外します（プッシュの場合） |
| **[!UICONTROL Quarantined address]** | すべて | 隔離されたアドレスを除外します。 |
| **[!UICONTROL Target limited in size]** | すべて | ターゲットの最大配信サイズに達したかどうかを確認します。 「配信制限」オプションが有効になっているダイレクトメール配信に適用されます。 |

これらのデフォルトのフィルタールールに加えて、2つの除外ルールを使用できます。

* **[!UICONTROL Exclusion of addresses]** (  **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** (  **[!UICONTROL domainExclusions]** )。

電子メールの分析時には、配信性能インスタンスで管理された暗号化グローバル抑止リストに含まれている禁止アドレスや禁止ドメイン名がこれらのルールによって照合され、受信者の電子メールアドレスが該当していないかどうかの確認処理が実行されます。該当した場合、その受信者宛てにはメッセージが送信されません。

これは、Spamtrap などの悪意あるアクティビティによってブロックリストに登録されることを防ぐためです。例えば、会社の Web フォーム経由で Spamtrap を使用して購読処理が実行されると、Spamtrap 宛てに確認メールが自動送信され、お使いのアドレスが自動的にブロックリスト登録される結果になります。

>[!NOTE]
>
>グローバル抑止リストに含まれているアドレスやドメイン名は非公開です。除外された受信者の数に関する情報だけが配信分析ログに記録されます。

## フィルタールールの作成 {#creating-a-filtering-rule}

必要に応じて独自のフィルタールールを作成できます。 例えば、ニュースレターのターゲット数をフィルタリングして、18歳未満の購読者が通信を受け取らないようにすることができます。

フィルタリングタイポロジルールを作成するには、次の手順に従います。

1. 新しいタイポロジルールを作成します。 タイポロジルールを作成する主な手順については、[このセクション](../../sending/using/managing-typology-rules.md)で詳しく説明します。

1. **[!UICONTROL Filtering]**&#x200B;ルールタイプを選択し、目的のチャネルを指定します。

1. 「**[!UICONTROL Filtering criteria]**」タブで、**[!UICONTROL Subscription]**&#x200B;カテゴリの購読を選択します。

   ![](assets/typology_create-rule-subscription.png)

1. クエリエディターの「**[!UICONTROL Explorer]**」タブで、**[!UICONTROL Subscriber]**&#x200B;ノードを画面のメイン部分にドラッグ&amp;ドロップします。

   ![](assets/typology_create-rule-subscriber.png)

1. **[!UICONTROL Age]**&#x200B;フィールドを選択し、サブスクライバーの年齢が18才以上になるようにフィルター条件を定義します。

   ![](assets/typology_create-rule-age.png)

1. 「**[!UICONTROL Typologies]**」タブで、このルールをタイポロジにリンクします。

   ![](assets/typology_create-rule-typology.png)

1. 使用する配信または配信テンプレートでタイポロジが選択されていることを確認します。 詳しくは、[こちらの節](../../sending/using/managing-typologies.md#applying-typologies-to-messages)を参照してください。

   ![](assets/typology_template.png)

このルールがメッセージで使用される場合は、未成年と見なされる購読者が自動的に除外されます。

## フィルタリングルールのターゲットコンテキスト{#configuring-filtering-rules-targeting-context}の設定

Campaign Standardを使用すると、ターゲットするデータに応じて、**ターゲット設定**&#x200B;と&#x200B;**フィルター処理**&#x200B;のディメンションを使用するように設定できます。

これを行うには、タイポロジルールのプロパティを開き、**[!UICONTROL Advanced information]**&#x200B;セクションにアクセスします。

デフォルトでは、**[!UICONTROL Profiles]**&#x200B;上でフィルタリングが行われます。 例えば、モバイルアプリケーション向けのルールの場合、**[!UICONTROL Filtering dimension]**&#x200B;を&#x200B;**[!UICONTROL Subscriptions to an application]**&#x200B;に変更できます。

![](assets/typology_rule-order_2.png)

## フィルタリング規則の適用の制限{#restricting-the-applicability-of-a-filtering-rule}

送信するメッセージに従って、フィルタリングルールの適用を制限できます。

1. タイポロジルールの「**[!UICONTROL Application criteria]**」タブで、「**[!UICONTROL Apply the rule on all deliveries]**」オプションの選択を解除します。このオプションはデフォルトで有効になっています。

   ![](assets/typology_limit.png)

1. クエリエディターを使用して、フィルターを定義します。 例えば、特定の単語を含むラベル開始のメッセージや、IDに特定の文字が含まれるメッセージに対してのみ、ルールを適用できます。

   ![](assets/typology_limit-rule.png)

この場合、ルールは、定義された条件に対応するメッセージにのみ適用されます。
