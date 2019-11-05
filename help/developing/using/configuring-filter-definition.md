---
title: フィルター定義の設定
description: 大きなデータセットを管理するフィルター機能を見つけます。
page-status-flag: 非活性化の
uuid: c9db95fe-e9aa-40f8-9c0a-e74bb21ac14b
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: リソースの追加または拡張
discoiquuid: 993ab2bd-e05f-468e-9ef8-a603761247f8
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# フィルター定義の設定{#configuring-filter-definition}

このタブで **[!UICONTROL Filter definition]** は、オーディエンスの定義時など、複雑なクエリの作成時にユーザーが直接アクセスできるアドバンスフィルターを作成できます。

この手順は必須ではありません。この手順は、引き続き、ワークフロー、オーディエンスおよびREST APIを使用してリソースにデータを入力し、そのデータにアクセスできるためです。

![](assets/custom_resource_filter-definition.png)

これらのフィルターは、事前設定されたルールの形でクエリーエディターで使用されます。 これにより、必要な設定を得るために必要な手順の数を制限でき、繰り返しのセグメント化に特に役立ちます。

例えば、過去3か月間に特定の金額を超えるすべてのトランザクションを選択できるフィルターを作成できます。

これを行うには、リソースを拡張し、（以前に作成した）トランザクションテーブルにリンクするフィルターを定義する必要があります。このルールは、トランザクション価格が指定したパラメーター以上で、トランザクション日が過去3か月に対応する範囲内にあることを示します。 **[!UICONTROL Profiles]**

1. トランザクションテーブルは必ず作成して発行してください。 See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >この手順では、カスタムトランザクションテーブルの例を使用します。 お客様の場合は、ビジネスニーズに合わせて調整します。

1. リソース内のトランザクションテーブルに関連するフィルタを定義する前に、 **[!UICONTROL Profiles]** このテーブルへのリンクを定義し、変更を発行する必要があります。 詳しくは、 [他のリソースを使用したリンクの定義](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) およびデ [ータベース構造の更新を参照してください](../../developing/using/updating-the-database-structure.md)。
1. 新しいフ **[!UICONTROL Definition]** ィルタの定義画面のタブで、トランザクションテーブルを選択します。

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. ウィンドウで、 **[!UICONTROL Add a rule - Profiles/Transactions]** トランザクションテーブルをワークスペースにドラッグ&amp;ドロップします。 次に表示されるウィンドウで、使用するフィールドを選択します。

   ![](assets/custom_resource_filter-definition_example-field.png)

1. ウィンドウ **[!UICONTROL Optional parameter settings]** のので、ボ **[!UICONTROL Add a rule - Transactions]** ックスをオンに **[!UICONTROL Switch to parameters]** します。

   で、演算子 **[!UICONTROL Filter conditions]**&#x200B;を選択し **[!UICONTROL Greater than or equal to]** ます。 フィールド **[!UICONTROL Parameters]** に名前を入力し、プラス記号をクリックして新しいパラメータを作成します。

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. 変更を確認します。 この定義は、クエリーを実行するためにユーザーが後で入力する必要がある設定可能なフィールドに対応します。

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. このルールを別のルールと組み合わせて、トランザクション日を過去3か月に対応する範囲内に含める必要があることを指定します。

   ![](assets/custom_resource_filter-definition_example.png)

1. フィルタを表示するカテゴリを選択します。

   ![](assets/custom_resource_filter-definition_category.png)

1. フィルタ **[!UICONTROL Parameters]** ー定義画面のタブで、説明とラベルを変更して、フィルターの対象をユーザーに明確に示します。 この情報は、クエリエディターに表示されます。

   ![](assets/custom_resource_filter-definition_parameters.png)

   複数の設定可能なフィールドを定義する場合は、インターフェイスに表示される順序を変更できます。

1. 変更を保存し、リソースを発行します。 詳しくは、「データベース構造の更新 [」の節を参照してください](../../developing/using/updating-the-database-structure.md) 。

リソース拡張 **[!UICONTROL Profiles]** が公開されると、クエリーエディターインターフェイスの「ショートカット」タブにこのフィルター [が表示され](../../automating/using/editing-queries.md) ます。

これにより、過去3か月間に一定金額を超える支払いを行ったすべての顧客に送信する電子メールを作成する際に、ユーザーはオーディエンスを簡単に定義できます。

![](assets/custom_resource_filter-definition_email-audience.png)

表示されるダイアログボックスに必要な金額を入力するだけで、自分で設定するのではなく、

![](assets/custom_resource_filter-definition_email-audience_filter.png)

