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
source-git-commit: 888cf4cd7bfa7f82bfe70c408f8c2785c51c36e2

---


# リソースのデータ構造の設定{#configuring-the-resource-s-data-structure}

新しいカスタムリソースを作成したら、データ構造を設定する必要があります。

リソースを編集する際、タブで **[!UICONTROL Data structure]** 追加できます。

* [フィールド](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)
* [識別キー](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [インデックス](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)
* [リンク](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)
* [ログの送信](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

## リソースへのフィールドの追加 {#adding-fields-to-a-resource}

リソースに新しいフィールドを追加して、デフォルトのデータモデルに含まれていないデータを保存することができます。

1. ボタンを **[!UICONTROL Create element]** 使用してフィールドを作成します。
1. ラベル、ID、フィールドタイプを指定し、このフィールドに対して許可されている最大長を定義します。

   **[!UICONTROL ID]** フィールドは必須で、追加されるフィールドごとに一意である必要があります。

   >[!NOTE]
   >
   >フィールドを **[!UICONTROL Label]** 空のままにすると、IDから自動的に完了します。
   >最大30文字を使用することをお勧めします。

   ![](assets/schema_extension_4.png)

1. いずれかのフィールドを変更するには、ボタンを **[!UICONTROL Edit Properties]** チェックします。

   ![](assets/schema_extension_24.png)

1. **[!UICONTROL Field definition]** 画面で、オーディエンスとターゲット設定に使用するカテゴリを定義することも、説明を追加することもできます。

   ![](assets/schema_extension_5.png)

1. ユーザーに提供する値（列挙値）を定義する必要がある場合は **[!UICONTROL Specify a list of authorized values]** 、このオプションを選択します。

   次に、をクリック **[!UICONTROL Create element]** して、 **[!UICONTROL Label]** および **[!UICONTROL Value]**&#x200B;を指定します。必要な数だけ値を追加します。

1. フィールドを追加したら **[!UICONTROL Add audit fields]** 、チェックボックスをオンにして、作成日の詳細、リソースを作成したユーザー、日付および最終変更者を含めます。
1. **[!UICONTROL Add access authorization management fields]** このチェックボックスをオンにして、特定のリソースへのアクセス権を持つユーザーを含めます。

   これらのフィールドは、データベースの更新が実行された後に表示できるデータおよびメタデータに表示されます。これについて詳しくは、「データベース構造の [更新」](../../developing/using/updating-the-database-structure.md) を参照してください。

1. フィールドを **[!UICONTROL Add automatic ID]** チェックしてIDを自動的に生成します。既存のエンティティは空のままです。
1. リソース要素の名前をリストと作成手順に表示する方法を変更するには、ボックスを **[!UICONTROL Personalize the resource title]** チェックします。このリソース用に作成したフィールドを選択します。

   ![](assets/schema_extension_18.png)

リソースのフィールドが定義されるようになりました。

## IDキーの定義 {#defining-identification-keys}

各リソースには、少なくとも1つの一意のキーが必要です。例えば、2つの製品が購入テーブルに同じIDを持つことができないようにキーを指定できます。

1. 技術的なキーを自動的かつインクリメンタルに生成する場合は、ストレージのサイズの **[!UICONTROL Automatic primary key]** セクションで指定します。

   ![](assets/schema_extension_6.png)

1. ボタンを **[!UICONTROL Create element]** 使用してキーを作成します。

   デフォルトでは、フィールド **[!UICONTROL Label]** は **[!UICONTROL ID]** 完了しますが、編集することもできます。

   >[!NOTE]
   >
   >最大30文字を使用することをお勧めします。

1. このキーを構成する要素を定義するには、このリソース用に作成したフィールドをクリック **[!UICONTROL Create element]** して選択します。

   ![](assets/schema_extension_7.png)

   作成したキーが **[!UICONTROL Custom keys]** セクションに表示されます。

リソースのIDキーが作成されるようになりました。

## インデックスの定義 {#defining-indexes}

インデックスは、1つまたは複数のリソースフィールドを参照できます。インデックスを使用すると、データベースはレコードをソートして、より簡単に復元できます。SQLクエリーのパフォーマンスを最適化します。

インデックスの定義は推奨されますが、必須ではありません。

1. インデックスを作成するには **[!UICONTROL Create element]** 、このボタンを使用します。

   ![](assets/schema_extension_26.png)

1. デフォルトでは、フィールド **[!UICONTROL Label]** は **[!UICONTROL ID]** 完了しますが、編集することもできます。

   >[!NOTE]
   >
   >最大30文字を使用することをお勧めします。

1. このインデックスを構成する要素を定義するには、このリソース用に作成したフィールドを選択します。

   ![](assets/schema_extension_27.png)

1. **[!UICONTROL Confirm]**&#x200B;をクリックします。

作成されたインデックスは **[!UICONTROL Index]** 、セクション内のリストに表示されます。

## 他のリソースによるリンクの定義 {#defining-links-with-other-resources}

リンクは、1つのテーブルに他のテーブルとの関連付けを詳細に詳細に示します。

1. ターゲットリソースへのリンクを作成するには **[!UICONTROL Create element]** 、このボタンを使用します。
1. **[!UICONTROL Select a target resource]**&#x200B;をクリックします。

   ![](assets/schema_extension_28.png)

1. リソースはアルファベット順に表示され、名前でフィルターできます。技術的な名前は括弧で囲まれて表示されます。

   リストから要素を選択し、をクリック **[!UICONTROL Confirm]**&#x200B;します。

   ![](assets/schema_extension_9.png)

1. 基数に **[!UICONTROL Link type]** 従って選択します。選択した基数タイプに応じて、レコードが削除または複製された場合に動作が異なる可能性があります。

   様々なリンクタイプを次に示します。

   * **[!UICONTROL 1 cardinality simple link]**:ソーステーブルの1回のオカレンスには、ターゲットテーブルの対応するオカレンスを1つずつ含めることができます。
   * **[!UICONTROL N cardinality collection link]**:ソーステーブルの1回のオカレンスは、ターゲットテーブルの複数の対応するオカレンスを持つことができますが、ターゲットテーブルの1つのオカレンスには、ソーステーブルの対応するオカレンスを1つずつ含めることができます。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:ソーステーブルの1回のオカレンスには、ターゲットテーブルの対応するオカレンスを1つだけ含めることも、なしにすることもできます。これに **[!UICONTROL Link type]** より、パフォーマンスの問題が発生する可能性があります。
   ![](assets/schema_extension_29.png)

1. **[!UICONTROL New link]** 画面では、デフォルトでは **[!UICONTROL Label]****[!UICONTROL ID]** フィールドが完了しますが、編集することもできます。

   >[!NOTE]
   >
   >最大30文字を使用することをお勧めします。

   >[!CAUTION]
   >
   >作成後にリンクの名前を変更することはできません。リンクの名前を変更するには、リンクを削除してから再度作成する必要があります。

1. **[!UICONTROL Category for the audience and targeting]** このリストを使用すると、このリンクをカテゴリに割り当てて、クエリエディターツールにより多くの表示を表示できます。
1. 必要に応じて **[!UICONTROL Reverse link definition]** 、対象のリソースにリソースのラベルとIDを表示することができます。
1. **[!UICONTROL Behavior if deleted/duplicated]** セクション内のリンクによって参照されるレコードの動作を定義します。

   デフォルトでは、ターゲットレコードはリンクによって参照されなくなります。

   ![](assets/schema_extension_16.png)

1. **[!UICONTROL Join definition]** セクションでは、デフォルト **[!UICONTROL Use the primary keys to make the join]** のオプションが選択されていますが、次の2つのオプションを選択できます。

   * **[!UICONTROL Use the primary key to make the join]**:この結合定義を使用すると、プライマリキーを使用して購入のプライマリキーと調整できます。
   * **[!UICONTROL Define specific join conditions]**:この結合定義を使用すると、両方のリソースに結合するフィールドを手動で選択できます。データが正しく設定されていない場合、 **購入** レコードは表示されません。
   ![](assets/schema_extension_17.png)

作成されたリンクは **[!UICONTROL Links]** セクション内のリストに表示されます。

**例:作成したリソースを「プロファイル」リソースとリンク**

この例では、新しいリソース **購入** を **プロファイル** カスタムリソースとリンクします。

1. **新しい購入** リソースを作成します。
1. **プロファイル** カスタムリソースにリンクするには、タブの **[!UICONTROL Links]****[!UICONTROL Data structure]** セクションを展開して、をクリック **[!UICONTROL Create element]**&#x200B;します。
1. ターゲットリソースを選択 **[!UICONTROL Profiles (profile)]**&#x200B;します。
1. この例では、デフォルト **[!UICONTROL 1 cardinality simple link]** のリンクタイプを選択したままにします。

   ![](assets/custom_resource_link_to_profile_2.png)

1. 結合定義を選択し、デフォルトを維持 **[!UICONTROL Use the primary key to make the join]**&#x200B;します。

   ![](assets/custom_resource_link_to_profile_3.png)

1. 必要に応じて、購入を編集 **** してプロファイルにリンクするための詳細画面を定義できます。

   **[!UICONTROL Detail screen configuration]** セクションを展開して **[!UICONTROL Define a detail screen]** 、リソースの各要素に対応する画面を設定します。このボックスを選択しない場合、このリソースの要素の詳細ビューにアクセスできません。

1. **[!UICONTROL Create element]**&#x200B;をクリックします。
1. リンクされているリソースを選択し、をクリック **[!UICONTROL Add]**&#x200B;します。

   新しいリソースは **[!UICONTROL Client data]** 、/ **[!UICONTROL Purchase]**&#x200B;を選択して詳細メニューで使用できます。

   ![](assets/custom_resource_link_to_profile_4.png)

1. 設定が完了したら、をクリック **[!UICONTROL Confirm]**&#x200B;します。

   これで、新しいリソースを公開できます。

このリンクを追加すると、/メニューからプロファイルの詳細画面に **「購入」** タブが追加 **[!UICONTROL Profiles & audiences]****[!UICONTROL Profiles]** されます。これは **[!UICONTROL Profile]** リソースに固有のものであることに注意してください。

![](assets/custom_resource_link_to_profile.png)

## ログ拡張の送信の定義 {#defining-sending-logs-extension}

送信ログ拡張により、次のことができます。

* プロファイルカスタムフィールドを追加して **動的レポート機能を拡張するには**
* を拡張すると、セグメントコードとプロファイルデータを含む **データを送信します**

**セグメントコードを使用した拡張**

ユーザーは、ワークフローエンジンからのセグメントコードを使用してログを拡張できます。

セグメントコードはワークフローに定義する必要があります。

この拡張機能をアクティブにするには、このオプションを選択 **[!UICONTROL Add segment code]**&#x200B;します。

![](assets/sendinglogsextension_1.png)

セグメントコードについて詳しくは [、「セグメント化](../../automating/using/segmentation.md) 」セクションを参照してください。

**プロファイルフィールドで拡張**

>[!NOTE]
>
>管理者はカスタムフィールドでプロファイルリソースを拡張している必要があります。

![](assets/sendinglogsextension_2.png)

プロファイルリソースから任意のカスタムフィールドをクリック **[!UICONTROL Add field]** して選択します。

プロファイルディメンションにリンクされた新しいサブディメンションを生成するには、オプションを **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** チェックします。

![](assets/sendinglogsextension_3.png)

動的レポートから、カスタムフィールドディメンションをフリーフォームテーブルにドラッグ&amp;ドロップできます。

動的レポートについて詳しくは、コンポーネントの [リスト](../../reporting/using/list-of-components-.md)を参照してください。

>[!CAUTION]
>
>動的レポートに送信されるフィールドの数は20個に制限されています。

## リソースプロパティの編集 {#editing-resource-properties}

カスタムリソース画面で、ペインは **[!UICONTROL Summary]** 新しく作成されたリソースのステータスを示します。アクセスおよびその全般的なプロパティを管理できます。

![](assets/schema_extension_3.png)

1. ボタンを **[!UICONTROL Edit properties]** クリックして説明を追加します。

   ![](assets/schema_extension_30.png)

1. 必要に応じて、リソースのラベルとIDを変更します。

   >[!NOTE]
   >
   >最大30文字を使用することをお勧めします。

1. このリソースへのアクセスを特定の組織単位に制限する必要がある場合は、ここで指定します。アプリケーションでこのリソースを使用できるのは、許可されている数量のユーザーのみです。
1. 変更を保存します。

変更が保存されます。リソースを適用するには、リソースを再度公開する必要があります。

## プロファイルとカスタムリソースの一意のIDの生成 {#generating-a-unique-id-for-profiles-and-custom-resources}

デフォルトでは、プロファイルおよびカスタムリソースには、作成時にビジネスIDがありません。要素の作成時に一意のIDを生成するオプションを有効にすることができます。このIDは次の目的に使用できます。

* 書き出されたレコードを外部ツールで簡単に識別できます。
* 別のアプリケーションで処理された更新データをインポートするときに、レコードを調整します。

プロファイルおよびカスタムリソースのみで有効にできます。

1. プロファイルリソースに拡張子を作成するか、新しいリソースを作成します。
1. データ構造定義で、セクションの下の **[!UICONTROL Add automatic ID field]** オプションをチェック **[!UICONTROL Fields]** します。
1. リソースに加えた変更を保存して発行します。API経由で作成した要素にこのメカニズムを適用するには、APIを拡張するオプションを選択します。

**[!UICONTROL ACS ID]** 新しい要素が手動で作成されたとき、APIから新しい要素が作成されたとき、またはインポートワークフローから挿入されたときに、フィールドが自動的に設定されます。ACS IDフィールドはUUIDフィールドで、インデックス化されています。

プロファイルまたはカスタムリソースを書き出すときに、そのリソースに対して有効になっている場合は **[!UICONTROL ACS ID]** 、列を追加できるようになりました。外部ツールでこのIDを再利用して、レコードを識別できます。

![](assets/export_id_field.png)

別のアプリケーション（CRMなど）で処理または更新されたデータを再度インポートする場合、この一意のIDと簡単に調整できます。

>[!NOTE]
>
>**[!UICONTROL ACS ID]** このフィールドは、オプションをアクティブ化する前に作成されたプロファイルまたは要素に対しては更新されません。新しいレコードのみがACS IDを持ちます。このフィールドは読み取り専用モードです。変更することはできません。

