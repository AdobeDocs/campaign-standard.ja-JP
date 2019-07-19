---
title: フィルター定義の設定
seo-title: フィルター定義の設定
description: フィルター定義の設定
seo-description: 大きなデータセットを管理するフィルター機能を見つけます。
page-status-flag: 常にアクティブ化されていない
uuid: c9db95fe- e9aa-40f8-40f8-9c0a- e74bb14b
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: 追加または拡張するリソース
discoiquuid: 993ab2bd- e05f-468e-9ef8- a603761247f8
context-tags: cusResource、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring filter definition{#configuring-filter-definition}

**[!UICONTROL Filter definition]** このタブでは、オーディエンスを定義するときなど、複雑なクエリを作成するときにユーザーが直接アクセスできるアドバンスフィルターを作成できます。

ワークフロー、オーディエンス、REST APIを使用してデータを入力し、そのデータにアクセスすることができるので、この手順は必須ではありません。

![](assets/custom_resource_filter-definition.png)

これらのフィルターは、事前設定されたルールの形式でクエリエディターで使用されます。必要な設定を取得するために必要なステップ数を制限できます。これは、繰り返しセグメントの場合に特に有益です。

例えば、過去3か月以内のすべてのトランザクションを選択できるフィルターを作成できます。

To do this, you need to extend the **[!UICONTROL Profiles]** resource and define a filter linking to a transaction table (that you have previously created) with a rule indicating that the transaction price must be greater than or equal to a given parameter and that the transaction date must fall within a range corresponding to the last three months.

1. トランザクションテーブルを作成して発行することを確認してください。See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >この手順では、カスタムトランザクションテーブルの例を使用します。この場合、ビジネスニーズに合わせて調整してください。

1. **[!UICONTROL Profiles]** リソース内のトランザクションテーブルに関連するフィルターを定義する前に、このテーブルへのリンクを定義して、変更を発行してください。See [Defining links with other resources](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) and [Updating the database structure](../../developing/using/updating-the-database-structure.md).
1. In the **[!UICONTROL Definition]** tab of your new filter's definition screen, select the transaction table.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. **[!UICONTROL Add a rule - Profiles/Transactions]** ウィンドウで、トランザクションテーブルをワークスペースにドラッグ&amp;ドロップします。表示される次のウィンドウで、使用するフィールドを選択します。

   ![](assets/custom_resource_filter-definition_example-field.png)

1. In the **[!UICONTROL Optional parameter settings]** of the **[!UICONTROL Add a rule - Transactions]** window, check the **[!UICONTROL Switch to parameters]** box.

   In the **[!UICONTROL Filter conditions]**, select the **[!UICONTROL Greater than or equal to]** operator. **[!UICONTROL Parameters]** フィールドに名前を入力し、プラス記号をクリックして新しいパラメーターを作成します。

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. 変更を確認します。この定義は、ユーザーが後でクエリを実行するために入力する必要がある設定可能なフィールドに対応しています。

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. このルールを他のルールと組み合わせて、トランザクション日付が直近3か月に対応する範囲内にあることを指定します。

   ![](assets/custom_resource_filter-definition_example.png)

1. フィルターを表示するカテゴリを選択します。

   ![](assets/custom_resource_filter-definition_category.png)

1. In the **[!UICONTROL Parameters]** tab of the filter definition screen, modify the description and the label to clearly indicate the subject of your filter to the users. この情報は、クエリーエディターに表示されます。

   ![](assets/custom_resource_filter-definition_parameters.png)

   複数の設定可能なフィールドを定義する場合、インターフェイスに表示される順序を変更できます。

1. 変更を保存し、リソースを公開します。For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

**[!UICONTROL Profiles]** リソース拡張機能が公開されると、このフィルターが [クエリーエディター](../../automating/using/editing-queries.md) インターフェイスのショートカットタブの下に表示されます。

これにより、過去3か月間に一定金額を支払ったすべてのクライアントに送信する電子メールの作成時に、ユーザーが簡単にオーディエンスを定義できます。

![](assets/custom_resource_filter-definition_email-audience.png)

表示されるのではなく、表示されるダイアログボックスに必要な金額を入力するだけです。

![](assets/custom_resource_filter-definition_email-audience_filter.png)

