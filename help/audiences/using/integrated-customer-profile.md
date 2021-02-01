---
solution: Campaign Standard
product: campaign
title: 統合顧客プロファイル
description: 「1 つのビューですべての顧客インタラクションを追跡：Adobe Campaign の統合顧客プロファイルは、顧客のライフサイクル全体を通じて更新されます。」
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: marketingHistory,main
translation-type: tm+mt
source-git-commit: b3088ed3bbb8828393e28df8f982ed36e7e74590
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 48%

---


# 統合顧客プロファイル{#integrated-customer-profile}

統合顧客プロファイルは、データベースの連絡先ごとに使用できます。このマーケティング履歴では、顧客との連絡に関するあらゆる関連マーケティング情報が 1 つのビューにまとめられます。その結果、連絡先情報、受信したメール、トラッキングログ、購読、購読解除など、すべてのデジタル動作、オンラインおよびオフラインのトランザクションに一元的にアクセスできます。

統合顧客プロファイルにアクセスする手順は次のとおりです。

1. Adobe Campaignホームページで&#x200B;**[!UICONTROL Customer profiles]**&#x200B;カードまたは&#x200B;**プロファイル**&#x200B;タブをクリックし、プロファイルリストを表示します。

1. 特定のフィールドに基づいてプロファイルを検索するには、検索パネルを開き、検索を実行するフィールドを選択します。


   ![](assets/profile-search.png)

1. 検索する値を指定し、Enterキーを押します。

   >[!NOTE]
   >
   >検索は、電子メール、名、姓の各フィールドに加え、リソースの拡張時に追加されたカスタムフィールドに基づいて実行できます。
   >
   >検索では大文字と小文字が区別され、プリフィックスでのみ実行されます。 例えば、姓の最後の文字を使用してプロファイルを検索することはできません。

1. 連絡先を選択して、プロファイルを開きます。

   ![](assets/mkt_hist_access.png)

その結果、この連絡先の&#x200B;**マーケティング履歴**&#x200B;にアクセスできます。

プロファイルに関する主要な情報は、イベントのリストと共に、このページで収集されます。

リスト内のイベントをクリックして開きます。送信されたメッセージや、プロファイルがサブスクライブしているサービスにアクセスできます。

![](assets/mkt_hist_view.png)

>[!NOTE]
>
>マーケティング履歴は、Adobe Campaign Standard API を使用してアクセスすることもできます。詳しくは、[該当するドキュメント](../../api/using/interacting-with-marketing-history.md)を参照してください。
