---
solution: Campaign Standard
product: campaign
title: タイポロジの管理
description: タイポロジの使い方を説明します。
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# タイポロジの管理 {#managing-typologies}

## タイポロジについて {#about-typologies}

タイポロジとは、メッセージを送信する前にメッセージの有効性を確認するための一連のルールです。例えば、メッセージの内容が空ではない、購読解除が存在する、重複を除外する、などです。

タイポロジは **[!UICONTROL Administration]**／**[!UICONTROL Channels]**／**[!UICONTROL Typologies]** メニューから確認できます。初期状態では、アプリケーションでデフォルトのタイポロジが使用できます。必要に応じて、独自のタイポロジを作成したり、既存のタイポロジを変更することができます。

![](assets/typologies-list.png)

「**[!UICONTROL Typology rules]**」セクションでは、タイポロジごとに、タイポロジをメッセージと合わせて使用した場合に実行される一連のルールのリストが表示されます。

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>タイポロジルールの詳細を表示するには、目的のタイポロジルールをダブルクリックします。ルールは読み取り専用モードで表示されます。

## タイポロジの作成{#creating-a-typology}

新しいタイポロジを作成するには、次の手順に従います。

1. **[!UICONTROL Administration]**／**[!UICONTROL Channels]**／**[!UICONTROL Typologies]** メニューにアクセスします。

1. タイポロジのリストが表示されます。「**[!UICONTROL Create]**」ボタンをクリックします。

   ![](assets/typologies-create.png)

1. タイポロジの「**[!UICONTROL Label]**」を定義し、「**[!UICONTROL Add an element]**」ボタンをクリックして、追加するタイポロジルールを選択します。タイポロジルールについて詳しくは、[この節](../../sending/using/managing-typology-rules.md)を参照してください。

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >「**[!UICONTROL IP affinity]**」フィールドでは、設定に従ってアフィニティを管理できます。アフィニティはインスタンスの設定ファイルで定義されます。アフィニティを使用する場合は、管理者にお問い合わせください。

1. 「**[!UICONTROL Create]**」をクリックして選択内容を確定します。これで、メッセージでタイポロジを使用できるようになりました。

## メッセージへのタイポロジの適用 {#applying-typologies-to-messages}

タイポロジをメッセージまたはメッセージテンプレートに関連付けると、タイポロジに含まれているタイポロジルールが実行され、メッセージの有効性がチェックされます。

>[!NOTE]
>
>各メッセージまたはメッセージテンプレートに割り当てることができるタイポロジは 1 つだけです。

メッセージにタイポロジをリンクするには、次の手順に従います。

1. メッセージのプロパティにアクセスします。メッセージテンプレートは、**[!UICONTROL Resources]**／**[!UICONTROL Templates]** ナビゲーションメニューからアクセスできます。

1. **[!UICONTROL Advanced parameters]**／「**[!UICONTROL Preparation]**」セクションで、メッセージにリンクするタイポロジを選択します。

   ![](assets/typology_message.png)

1. 「**[!UICONTROL Confirm]**」をクリックします。

   選択したタイポロジがメッセージにリンクされます。関連するすべてのタイポロジルールが実行され、メッセージの有効性が確認されます。
