---
title: ホットクリック
description: 標準のホットクリック数レポートでは、顧客が配信をクリックした場所を確認できます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 5af37156-e93b-4ae9-9856-053364f211ef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---

# ホットクリック{#hot-clicks}

このレポートは、 **[!UICONTROL Reports]** ボタンをクリックします。

![](assets/delivery_reports_hot-clicks_4.png)

メッセージの内容 (HTMLやテキスト ) と各リンクでのクリック率が表示されます。

![](assets/delivery_reports_10.png)

配信用に動的コンテンツを作成した場合は、定義した各条件に対する割合が表示されます。 配信への条件付きコンテンツの挿入について詳しくは、 [動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

例えば、次の条件を持つ配信を作成したとします。

* 受信者が男性または女性の場合、メイン画像のリンクは異なります。
* また、25 歳以上の受信者にのみ表示される特別オファーへのリンクを追加しました。

メッセージを送信したら、 **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** 配信ダッシュボードから。

デフォルトでは、プロファイルは選択されていません。 性別が不明な受信者と 25 歳未満または年齢が不明な受信者のクリックのみが表示されます。

![](assets/delivery_reports_hot-clicks_1.png)

女性のクリック数を表示するには、 **[!UICONTROL Change profile]** ボタンをクリックし、女性テストプロファイルを選択します。 男性のクリック数を表示するには、同様に、男性のテストプロファイルを選択します。

![](assets/delivery_reports_hot-clicks_2.png)

25 歳以上の受信者のクリック数を表示するには、 **[!UICONTROL Change profile]** ボタンをクリックし、生年月日がこの条件に一致するテストプロファイルを選択します。

テストプロファイルについて詳しくは、 [テストプロファイルについて](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>特定のリンクでのクリック数は、配信内のすべての条件付きコンテンツに対する合計クリック数の割合です。 したがって、動的コンテンツを定義した場合は、特定のテストプロファイルに表示される割合の合計が 100 に等しくないことがあります。

同様に、繰り返し配信やトランザクションメッセージの場合は、表示する動的コンテンツに対応するテストプロファイルを選択できますが、選択した実行配信に応じて、クリックの割合も表示できます。

実行配信は、次の場合に作成される、アクションにつながることのできない、機能しない技術メッセージです。

* 繰り返し配信が実行または更新されるたびに、

   例えば、この配信を管理するワークフローが月に 1 回実行される場合、1 ヶ月に 1 回実行配信がおこなわれます。 これに加えて、配信のコンテンツが更新されるたびに、追加の実行配信が作成されます。

   繰り返し E メール配信について詳しくは、 [E メール配信](../../automating/using/email-delivery.md).

* デフォルトでは、トランザクションメッセージに対して 1 ヶ月に 1 回、トランザクションメッセージが編集されて再公開されるたびに使用されます。

   トランザクションメッセージについて詳しくは、 [トランザクションメッセージの概要](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>トラッキングされる URL の ID は実行ごとに異なるので、特定のメッセージのすべての実行配信について、ホットクリックのデータを集計することはできません。 一度に 1 つの実行配信に対してのみ表示できます。

メッセージを送信したら、 **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** 配信ダッシュボードから。

デフォルトでは、最後の実行配信が選択されています。 次をクリック： **[!UICONTROL Change execution delivery]** ボタンをクリックして別のボタンを選択します。

![](assets/delivery_reports_hot-clicks_3.png)

選択した配信の実行でのクリックの割合のみが表示されます。
