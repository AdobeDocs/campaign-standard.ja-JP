---
title: リソースのデータ構造の設定
seo-title: リソースのデータ構造の設定
description: リソースのデータ構造の設定
seo-description: データ構造を設定する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: 60fe80c0-9df6-4808- a432-60a1977216ea
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 開発中
content-type: 参照
topic-tags: 追加または拡張するリソース
discoiquuid: 4f22ee35-1d5f-4c75-95b4-3e38b85de26e
context-tags: cusResource、main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6b642a58fc88779f88f2f860c133b36934c59d21

---


# Configuring the resource's data structure{#configuring-the-resource-s-data-structure}

新しいカスタムリソースを作成したら、データ構造を設定する必要があります。

When editing the resource, in the **[!UICONTROL Data structure]** tab, you can add:

* [フィールド](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)
* [識別キー](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [インデックス](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)
* [リンク](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)
* [ログの送信](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

## Adding fields to a resource {#adding-fields-to-a-resource}

リソースに新しいフィールドを追加して、デフォルトのデータモデルに含まれていないデータを保存することができます。

1. Use the **[!UICONTROL Create element]** button to create a field.
1. ラベル、ID、フィールドタイプを指定し、このフィールドに対して許可されている最大長を定義します。

   **[!UICONTROL ID]** フィールドは必須で、追加されるフィールドごとに一意である必要があります。

   >[!NOTE]
   >
   >If you leave the **[!UICONTROL Label]** field empty, it will automatically be completed from the ID.
   >最大30文字を使用することをお勧めします。

   ![](assets/schema_extension_4.png)

1. To modify one of the fields, check the **[!UICONTROL Edit Properties]** button.

   ![](assets/schema_extension_24.png)

1. **[!UICONTROL Field definition]** 画面で、オーディエンスとターゲット設定に使用するカテゴリを定義することも、説明を追加することもできます。

   ![](assets/schema_extension_5.png)

1. Check the **[!UICONTROL Specify a list of authorized values]** option if you need to define values that will be offered to the user (enumeration values).

   Then, click **[!UICONTROL Create element]** and specify a **[!UICONTROL Label]** and **[!UICONTROL Value]**. 必要な数だけ値を追加します。

1. Once you have added your fields, check the **[!UICONTROL Add audit fields]** box to include fields detailing the creation date, the user that created the resource, the date, and the author of the last modification.
1. **[!UICONTROL Add access authorization management fields]** このチェックボックスをオンにして、特定のリソースへのアクセス権を持つユーザーを含めます。

   これらのフィールドは、データベースの更新が実行された後に表示できるデータおよびメタデータに表示されます。For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

1. Check the **[!UICONTROL Add automatic ID]** field to automatically generate an ID. 既存のエンティティは空のままです。
1. To modify the way in which the name of the resource elements will appear in the lists and creation steps, check the **[!UICONTROL Personalize the resource title]** box. このリソース用に作成したフィールドを選択します。

   ![](assets/schema_extension_18.png)

リソースのフィールドが定義されるようになりました。

## Defining identification keys {#defining-identification-keys}

各リソースには、少なくとも1つの一意のキーが必要です。例えば、2つの製品が購入テーブルに同じIDを持つことができないようにキーを指定できます。

1. Specify it in the **[!UICONTROL Automatic primary key]** section the size for the storage if you would like to have a technical key automatically and incrementally generated.

   ![](assets/schema_extension_6.png)

1. Use the **[!UICONTROL Create element]** button to create a key.

   The **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default but you can edit them.

   >[!NOTE]
   >
   >最大30文字を使用することをお勧めします。

1. To define the elements making up this key, click **[!UICONTROL Create element]** and select the fields that you created for this resource.

   ![](assets/schema_extension_7.png)

   Created keys are displayed in the **[!UICONTROL Custom keys]** section.

リソースのIDキーが作成されるようになりました。

## Defining indexes {#defining-indexes}

インデックスは、1つまたは複数のリソースフィールドを参照できます。インデックスを使用すると、データベースはレコードをソートして、より簡単に復元できます。SQLクエリーのパフォーマンスを最適化します。

インデックスの定義は推奨されますが、必須ではありません。

1. Use the **[!UICONTROL Create element]** button to create an index.

   ![](assets/schema_extension_26.png)

1. The **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default, but you can edit them.

   >[!NOTE]
   >
   >最大30文字を使用することをお勧めします。

1. このインデックスを構成する要素を定義するには、このリソース用に作成したフィールドを選択します。

   ![](assets/schema_extension_27.png)

1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

The indexes that were created appear in the list in the **[!UICONTROL Index]** section.

## Defining links with other resources {#defining-links-with-other-resources}

リンクは、1つのテーブルに他のテーブルとの関連付けを詳細に詳細に示します。

1. Use the **[!UICONTROL Create element]** button to create a link to a target resource.
1. **[!UICONTROL Select a target resource]**&#x200B;をクリックします。

   ![](assets/schema_extension_28.png)

1. リソースはアルファベット順に表示され、名前でフィルターできます。技術的な名前は括弧で囲まれて表示されます。

   Select an element from the list and click **[!UICONTROL Confirm]**.

   ![](assets/schema_extension_9.png)

1. Select the **[!UICONTROL Link type]** according to cardinality. 選択した基数タイプに応じて、レコードが削除または複製された場合に動作が異なる可能性があります。

   様々なリンクタイプを次に示します。

   * **[!UICONTROL 1 cardinality simple link]**:ソーステーブルの1回のオカレンスには、ターゲットテーブルの対応するオカレンスを1つずつ含めることができます。
   * **[!UICONTROL N cardinality collection link]**:ソーステーブルの1回のオカレンスは、ターゲットテーブルの複数の対応するオカレンスを持つことができますが、ターゲットテーブルの1つのオカレンスには、ソーステーブルの対応するオカレンスを1つずつ含めることができます。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:ソーステーブルの1回のオカレンスには、ターゲットテーブルの対応するオカレンスを1つだけ含めることも、なしにすることもできます。Note that this kind of **[!UICONTROL Link type]** can cause performance issue.
   ![](assets/schema_extension_29.png)

1. **[!UICONTROL New link]** 画面では、デフォルトでは **[!UICONTROL Label]****[!UICONTROL ID]** フィールドが完了しますが、編集することもできます。

   >[!NOTE]
   >
   >最大30文字を使用することをお勧めします。

   >[!CAUTION]
   >
   >作成後にリンクの名前を変更することはできません。リンクの名前を変更するには、リンクを削除してから再度作成する必要があります。

1. **[!UICONTROL Category for the audience and targeting]** このリストを使用すると、このリンクをカテゴリに割り当てて、クエリエディターツールにより多くの表示を表示できます。
1. If needed, the **[!UICONTROL Reverse link definition]** section allows you to display the label and ID of the resource in the targeted resource.
1. **[!UICONTROL Behavior if deleted/duplicated]** セクション内のリンクによって参照されるレコードの動作を定義します。

   デフォルトでは、ターゲットレコードはリンクによって参照されなくなります。

   ![](assets/schema_extension_16.png)

1. **[!UICONTROL Join definition]** セクションでは、デフォルト **[!UICONTROL Use the primary keys to make the join]** のオプションが選択されていますが、次の2つのオプションを選択できます。

   * **[!UICONTROL Use the primary key to make the join]**:この結合定義を使用すると、プライマリキーを使用して購入のプライマリキーと調整できます。
   * **[!UICONTROL Define specific join conditions]**:この結合定義を使用すると、両方のリソースに結合するフィールドを手動で選択できます。Please note that if data are not correctly configured, the **Purchase** record will not be visible.
   ![](assets/schema_extension_17.png)

The links created are displayed in the list in the **[!UICONTROL Links]** section.

**例:作成したリソースを「プロファイル」リソースとリンク**

In this example, we want to link a new resource **Purchase** with the **Profiles **custom resource:

1. **新しい購入** リソースを作成します。
1. **プロファイル** カスタムリソースにリンクするには、タブの **[!UICONTROL Links]****[!UICONTROL Data structure]** セクションを展開して、をクリック **[!UICONTROL Create element]**&#x200B;します。
1. Select the target resource, here **[!UICONTROL Profiles (profile)]**.
1. In this example, keep the default **[!UICONTROL 1 cardinality simple link]** Link type selected.

   ![](assets/custom_resource_link_to_profile_2.png)

1. Choose a join definition, here keep the default **[!UICONTROL Use the primary key to make the join]**.

   ![](assets/custom_resource_link_to_profile_3.png)

1. If needed, you can define a detail screen to be able to edit **Purchase** and link it to a profile.

   **[!UICONTROL Detail screen configuration]** セクションを展開して **[!UICONTROL Define a detail screen]** 、リソースの各要素に対応する画面を設定します。このボックスを選択しない場合、このリソースの要素の詳細ビューにアクセスできません。

1. **[!UICONTROL Create element]**&#x200B;をクリックします。
1. Select your linked resource and click **[!UICONTROL Add]**.

   Your new resource will then be available in the advanced menu by selecting **[!UICONTROL Client data]** &gt; **[!UICONTROL Purchase]**.

   ![](assets/custom_resource_link_to_profile_4.png)

1. Once your configuration is done, click **[!UICONTROL Confirm]**.

   これで、新しいリソースを公開できます。

By adding this link, a **Purchase** tab is added to the profiles detail screen from the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Profiles]** menu. Please note that this is specific to the **[!UICONTROL Profile]** resource.

![](assets/custom_resource_link_to_profile.png)

## Defining sending logs extension {#defining-sending-logs-extension}

送信ログ拡張により、次のことができます。

* to extend dynamic report capabilities by **adding profile custom fields**
* to extend the sending logs data with **segment code and profile data**

**セグメントコードを使用した拡張**

ユーザーは、ワークフローエンジンからのセグメントコードを使用してログを拡張できます。

セグメントコードはワークフローに定義する必要があります。

To activate this extension, check the option **[!UICONTROL Add segment code]**.

![](assets/sendinglogsextension_1.png)

For more information on segment code, refer to the [Segmentation](../../automating/using/segmentation.md) section.

**プロファイルフィールドで拡張**

>[!NOTE]
>
>管理者はカスタムフィールドでプロファイルリソースを拡張している必要があります。

![](assets/sendinglogsextension_2.png)

Click **[!UICONTROL Add field]** and select any custom field from the profile resource.

In order to generate a new sub-dimension linked to the Profile dimension, check the **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** option.

![](assets/sendinglogsextension_3.png)

動的レポートから、カスタムフィールドディメンションをフリーフォームテーブルにドラッグ&amp;ドロップできます。

For more information on Dynamic Reporting, refer to the [List of components](../../reporting/using/list-of-components-.md).

>[!CAUTION]
>
>動的レポートに送信されるフィールドの数は20個に制限されています。

## Editing resource properties {#editing-resource-properties}

In the custom resource screen, the **[!UICONTROL Summary]** pane indicates the status of the newly created resource. アクセスおよびその全般的なプロパティを管理できます。

![](assets/schema_extension_3.png)

1. Click the **[!UICONTROL Edit properties]** button to add a description.

   ![](assets/schema_extension_30.png)

1. 必要に応じて、リソースのラベルとIDを変更します。

   >[!NOTE]
   >
   >最大30文字を使用することをお勧めします。

1. このリソースへのアクセスを特定の組織単位に制限する必要がある場合は、ここで指定します。アプリケーションでこのリソースを使用できるのは、許可されている数量のユーザーのみです。
1. 変更を保存します。

変更が保存されます。リソースを適用するには、リソースを再度公開する必要があります。

## Generating a unique ID for profiles and custom resources {#generating-a-unique-id-for-profiles-and-custom-resources}

デフォルトでは、プロファイルおよびカスタムリソースには、作成時にビジネスIDがありません。要素の作成時に一意のIDを生成するオプションを有効にすることができます。このIDは次の目的に使用できます。

* 書き出されたレコードを外部ツールで簡単に識別できます。
* 別のアプリケーションで処理された更新データをインポートするときに、レコードを調整します。

プロファイルおよびカスタムリソースのみで有効にできます。

1. プロファイルリソースに拡張子を作成するか、新しいリソースを作成します。
1. In the data structure definition, check the **[!UICONTROL Add automatic ID field]** option, under the **[!UICONTROL Fields]** section.
1. リソースに加えた変更を保存して発行します。API経由で作成した要素にこのメカニズムを適用するには、APIを拡張するオプションを選択します。

**[!UICONTROL ACS ID]** 新しい要素が手動で作成されたとき、APIから新しい要素が作成されたとき、またはインポートワークフローから挿入されたときに、フィールドが自動的に設定されます。ACS IDフィールドはUUIDフィールドで、インデックス化されています。

When exporting profiles or custom resources, you can now add the **[!UICONTROL ACS ID]** column if it has been enabled for that resource. 外部ツールでこのIDを再利用して、レコードを識別できます。

![](assets/export_id_field.png)

別のアプリケーション（CRMなど）で処理または更新されたデータを再度インポートする場合、この一意のIDと簡単に調整できます。

>[!NOTE]
>
>**[!UICONTROL ACS ID]** このフィールドは、オプションをアクティブ化する前に作成されたプロファイルまたは要素に対しては更新されません。新しいレコードのみがACS IDを持ちます。このフィールドは読み取り専用モードです。変更することはできません。

