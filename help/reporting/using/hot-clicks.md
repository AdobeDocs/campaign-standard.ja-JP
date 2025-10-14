---
title: ホットクリック
description: 標準のホットクリック レポートを使用すると、顧客が配信をクリックした場所を確認できます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 5af37156-e93b-4ae9-9856-053364f211ef
source-git-commit: d0ef11f26a52603107af28231d70821b44753abb
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# ホットクリック{#hot-clicks}

>[!IMPORTANT]
>
>ホットクリック レポートは、HTML版のメールのみを表示するもので、テキスト版をサポートしていません。

このレポートには、各配信またはトランザクションメッセージの「**[!UICONTROL Reports]**」ボタンからアクセスできます。

![](assets/delivery_reports_hot-clicks_4.png)

各リンクのクリック率をメッセージコンテンツに表示します。

![](assets/delivery_reports_10.png)

配信の動的コンテンツを作成した場合は、定義した各条件に対する割合を表示できます。 配信への条件付きコンテンツの挿入について詳しくは、[&#x200B; 動的コンテンツの定義 &#x200B;](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) を参照してください。

例えば、次の条件を持つ配信を作成したとします。

* 受信者が男性または女性の場合、メイン画像のリンクは異なります。
* また、25 歳以上の受信者にのみ表示される特別なオファーへのリンクを追加しました。

メッセージが送信されたら、配信ダッシュボードから **[!UICONTROL Reports]**/**[!UICONTROL Hot clicks]** を選択します。

デフォルトでは、プロファイルは選択されていません。 性別が不明な受信者、25 歳未満または年齢が不明な受信者に対するクリックのみが表示されます。

![](assets/delivery_reports_hot-clicks_1.png)

女性のクリックを表示するには、「**[!UICONTROL Change profile]**」ボタンをクリックし、女性のテストプロファイルを選択します。 男性のクリックを表示するには、同様に進んで、男性のテストプロファイルを選択します。

![](assets/delivery_reports_hot-clicks_2.png)

25 を超える受信者のクリック数を表示するには、「**[!UICONTROL Change profile]**」ボタンをクリックし、生年月日がこの条件に一致するテストプロファイルを選択します。

テストプロファイルについて詳しくは、[&#x200B; テストプロファイルについて &#x200B;](../../audiences/using/managing-test-profiles.md) を参照してください。

>[!NOTE]
>
>特定のリンクでのクリック数は、配信内のすべての条件付きコンテンツの合計クリック数の割合です。 したがって、動的コンテンツを定義した場合、特定のテストプロファイルに対して表示されるパーセンテージの合計は 100 にならない場合があります。

同様に、繰り返し配信およびトランザクションメッセージの場合は、表示する動的コンテンツに対応するテストプロファイルを選択できるだけでなく、選択した実行配信に応じてクリック率を表示することもできます。

実行配信は、次の場合に作成される、アクションから解放される機能しないテクニカルメッセージです。

* 繰り返し配信が実行または更新されるたびに。

  例えば、この配信を管理するワークフローが月に 1 回実行される場合、実行配信は月に 1 回になります。 これに加えて、配信のコンテンツが更新されるたびに、追加の実行配信が作成されます。

  繰り返しメール配信について詳しくは、「[&#x200B; メール配信 &#x200B;](../../automating/using/email-delivery.md)」を参照してください。

* デフォルトでは、トランザクションメッセージは月に 1 回で、トランザクションメッセージを編集して再度公開するたびに行われます。

  トランザクションメッセージについて詳しくは、[&#x200B; トランザクションメッセージの概要 &#x200B;](../../channels/using/getting-started-with-transactional-msg.md) を参照してください。

>[!NOTE]
>
>トラッキングされる URL の ID は実行ごとに異なるので、特定のメッセージのすべての実行配信について、ホットクリックのデータを集計することはできません。 一度に表示できる実行配信は 1 つだけです。

メッセージが送信されたら、配信ダッシュボードから **[!UICONTROL Reports]**/**[!UICONTROL Hot clicks]** を選択します。

デフォルトでは、最後の実行配信が選択されます。 「**[!UICONTROL Change execution delivery]**」ボタンをクリックして、別のボタンを選択します。

![](assets/delivery_reports_hot-clicks_3.png)

選択した配信実行のクリック率のみが表示されます。
