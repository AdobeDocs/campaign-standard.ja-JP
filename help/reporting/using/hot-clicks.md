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

このレポートは、各配信またはトランザクションメッセージの「**[!UICONTROL Reports]**」ボタンからアクセスできます。

![](assets/delivery_reports_hot-clicks_4.png)

各リンクでのクリック率と共に、メッセージのコンテンツ（HTMLやテキスト）が表示されます。

![](assets/delivery_reports_10.png)

配信用に動的コンテンツを作成した場合は、定義した各条件に対する割合を表示できます。 配信への条件付きコンテンツの挿入について詳しくは、[動的コンテンツの定義](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)を参照してください。

例えば、次の条件を持つ配信を作成したとします。

* 受信者が男性または女性の場合、メイン画像のリンクは異なります。
* また、25歳以上の受信者にのみ表示される特別オファーへのリンクを追加しました。

メッセージを送信したら、配信ダッシュボードから&#x200B;**[!UICONTROL Reports]** /**[!UICONTROL Hot clicks]**&#x200B;を選択します。

デフォルトでは、プロファイルは選択されていません。 性別が不明な受信者と、25歳未満または年齢が不明な受信者のクリックのみが表示されます。

![](assets/delivery_reports_hot-clicks_1.png)

女性のクリック数を表示するには、「**[!UICONTROL Change profile]**」ボタンをクリックし、女性テストプロファイルを選択します。 男性のクリック数を表示するには、同様に手順を進め、男性のテストプロファイルを選択します。

![](assets/delivery_reports_hot-clicks_2.png)

25歳以上の受信者のクリック数を表示するには、「**[!UICONTROL Change profile]**」ボタンをクリックし、生年月日がこの条件に一致するテストプロファイルを選択します。

テストプロファイルについて詳しくは、[テストプロファイルについて](../../audiences/using/managing-test-profiles.md)を参照してください。

>[!NOTE]
>
>特定のリンクでのクリック数は、配信内のすべての条件付きコンテンツに対する合計クリック数の割合です。 したがって、動的コンテンツを定義した場合、特定のテストプロファイルに表示される割合の合計が100に等しくない可能性があります。

同様に、繰り返し配信やトランザクションメッセージの場合は、表示する動的コンテンツに対応するテストプロファイルを選択できますが、選択した実行配信に応じてクリックの割合を表示することもできます。

実行配信は、次の場合に作成される、アクションにつながることのない、機能しない技術メッセージです。

* 繰り返し配信を実行または更新するたびに、

   例えば、この配信を管理するワークフローが月に1回実行される場合、1ヶ月に1回実行配信が存在します。 これに加えて、配信のコンテンツが更新されるたびに、追加の実行配信が作成されます。

   繰り返しEメール配信について詳しくは、[Eメール配信](../../automating/using/email-delivery.md)を参照してください。

* デフォルトでは、トランザクションメッセージの場合は月に1回、トランザクションメッセージが再編集されて再公開されるたびにおこなわれます。

   トランザクションメッセージについて詳しくは、[トランザクションメッセージの概要](../../channels/using/getting-started-with-transactional-msg.md)を参照してください。

>[!NOTE]
>
>追跡されるURLのIDは実行ごとに異なるので、特定のメッセージの実行配信すべてについてホットクリックデータを集計することはできません。 一度に表示できる実行配信の数は1つだけです。

メッセージを送信したら、配信ダッシュボードから&#x200B;**[!UICONTROL Reports]** /**[!UICONTROL Hot clicks]**&#x200B;を選択します。

デフォルトでは、最後の実行配信が選択されます。 別の&#x200B;**[!UICONTROL Change execution delivery]**&#x200B;ボタンをクリックして選択します。

![](assets/delivery_reports_hot-clicks_3.png)

選択した配信の実行に対するクリックの割合のみが表示されます。
