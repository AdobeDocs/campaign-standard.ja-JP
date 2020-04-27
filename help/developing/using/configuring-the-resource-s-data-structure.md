---
title: リソースのデータ構造の設定
description: データ構造を設定する方法を説明します。
page-status-flag: never-activated
uuid: 60fe80c0-9df6-4808-a432-60a1977216ea
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 4f22ee35-1d5f-4c75-95b4-3e38b85de26e
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6cf00f9b9bafdd54d8424a353b33dc689c0f59aa

---


# リソースのデータ構造の設定{#configuring-the-resource-s-data-structure}

新しいカスタムリソースを作成した後、データ構造を設定する必要があります。

リソースを編集する際に、タブ **[!UICONTROL Data structure]** で次を追加できます。

* [フィールド](#adding-fields-to-a-resource)
* [識別キー](#defining-identification-keys)
* [インデックス](#defining-indexes)
* [リンク](#defining-links-with-other-resources)
* [ログの送信](#defining-sending-logs-extension)

## リソースへのフィールドの追加 {#adding-fields-to-a-resource}

リソースに新しいフィールドを追加して、既製のデータモデルに含まれていないデータを保存できます。

1. ボタンを使用 **[!UICONTROL Create element]** して、フィールドを作成します。
1. ラベル、ID、フィールドタイプを指定し、このフィールドに対して許可される最大長を定義します。

   このフィ **[!UICONTROL ID]** ールドは必須で、追加する各フィールドに対して一意である必要があります。

   >[!NOTE]
   >
   >最大30文字を使用します。

   ![](assets/schema_extension_4.png)

1. いずれかのフィールドを変更するには、ボタンをチェック **[!UICONTROL Edit Properties]** します。

   ![](assets/schema_extension_24.png)

1. 画面で **[!UICONTROL Field definition]** は、オーディエンスとターゲットに使用するカテゴリを定義したり、説明を追加したりできます。

   ![](assets/schema_extension_5.png)

1. ユーザー **[!UICONTROL Specify a list of authorized values]** に提供する値（ユーザー値）を定義する必要がある場合は、このオプションを定義済みリストします。

   次に、をクリッ **[!UICONTROL Create element]** クし、とを指 **[!UICONTROL Label]** 定しま **[!UICONTROL Value]**&#x200B;す。 必追加要な数の値。

1. フィールドを追加したら、作成日、リソースを作成したユーザ、 **[!UICONTROL Add audit fields]** 日付、最後の変更の作成者の詳細を示すフィールドを含めるチェックボックスをオンにします。
1. 特定のリソース **[!UICONTROL Add access authorization management fields]** に対するアクセス権を持つフィールドを含める場合は、このチェックボックスをオンにします。

   これらのフィールドは、データベースの更新が完了すると表示されるデータとメタデータに表示されます。 For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

1. IDを自動的に生成 **[!UICONTROL Add automatic ID]** するには、フィールドをチェックします。 既存のエンティティは空のままになります。 詳しくは、「リソースとカスタムリソ [ースの一意のIDの生成」を参照してプロファイルします](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)。
1. リソース要素の名前がリソースおよび作成手順で表示される方法を変更するには、リストのチェックボックスをオンに **[!UICONTROL Customize the title of the resource elements]** します。 このリソース用に作成したフィールドを選択します。

   ![](assets/schema_extension_18.png)

   >[!NOTE]
   >
   >このオプションを選択しない場合、このテーブルのすべてのエンティティをリストする際に、自動主キー（エンティティがテーブルに追加されるたびに自動的に作成される）が使用されます。

これで、リソースのフィールドが定義されました。

## 識別キーの定義 {#defining-identification-keys}

各リソースには、少なくとも1つの一意のキーが必要です。 例えば、2つの製品が1つの購入テーブルで同じIDを持つことができないように、キーを指定できます。

1. テクニカルキーを自 **[!UICONTROL Automatic primary key]** 動的に増分的に生成する場合は、ストレージのサイズをセクションで指定します。

   ![](assets/schema_extension_6.png)

1. ボタンを使 **[!UICONTROL Create element]** 用してキーを作成します。

   とのフ **[!UICONTROL Label]** ィール **[!UICONTROL ID]** ドはデフォルトで入力されますが、編集することができます。

   >[!NOTE]
   >
   >最大30文字を使用します。

1. このキーを構成する要素を定義するには、をクリックし **[!UICONTROL Create element]** て、このリソース用に作成したフィールドを選択します。

   ![](assets/schema_extension_7.png)

   作成されたキーがセクションに表示さ **[!UICONTROL Custom keys]** れます。

これで、リソースのIDキーが作成されます。

>[!NOTE]
>
>IDキーを作成する際のベストプラクティスについては、この節を参照して [くださ](../../developing/using/data-model-best-practices.md#keys)い。

## インデックスの定義 {#defining-indexes}

インデックスは、1つまたは複数のリソースフィールドを参照できます。 インデックスを使用すると、データベースでレコードをより簡単にリカバリできるようにレコードを並べ替えることができます。 SQLのパフォーマンスを最適化するクエリ。

インデックスの定義は推奨されますが、必須ではありません。

1. 索引を作成す **[!UICONTROL Create element]** るには、ボタンを使用します。

   ![](assets/schema_extension_26.png)

1. とのフ **[!UICONTROL Label]** ィール **[!UICONTROL ID]** ドはデフォルトで入力されますが、編集することもできます。

   >[!NOTE]
   >
   >最大30文字を使用します。

1. このインデックスを構成する要素を定義するには、このリソース用に作成したフィールドからフィールドを選択します。

   ![](assets/schema_extension_27.png)

1. クリック **[!UICONTROL Confirm]** .

作成されたインデックスは、セクションのリストに表示さ **[!UICONTROL Index]** れます。

>[!NOTE]
>
>インデックスを作成する際のベストプラクティスについては、この節を参照して [くださ](../../developing/using/data-model-best-practices.md#indexes)い。

## 他のリソースとのリンクの定義 {#defining-links-with-other-resources}

リンクは、あるテーブルと他のテーブルとの関連付けの詳細を示します。

1. ボタンを使 **[!UICONTROL Create element]** 用して、リソースへのリンクを作成します。ターゲット
1. クリック **[!UICONTROL Select a target resource]** .

   ![](assets/schema_extension_28.png)

1. リソースはアルファベット順に表示され、名前でフィルタリングできます。 技術名は角括弧で囲まれて表示されます。

   要素から要素を選択し、リストをクリックしま **[!UICONTROL Confirm]**&#x200B;す。

   ![](assets/schema_extension_9.png)

1. 基数に従っ **[!UICONTROL Link type]** てを選択します。 選択した基数のタイプによって、レコードが削除されたり複製されたりする場合の動作が異なる場合があります。

   次に、様々なリンクタイプを示します。

   * **[!UICONTROL 1 cardinality simple link]**:ソーステーブルの1つのオカレンスは、対応する1つのオカレンスのターゲットテーブルです。
   * **[!UICONTROL N cardinality collection link]**:ソーステーブルの1つのオカレンスは、対応する複数のターゲットテーブルのオカレンスを持つことができますが、ターゲットテーブルの1つのオカレンスは、ソーステーブルの対応するオカレンスを1つだけ持つことができます。
   * **[!UICONTROL 0 or 1 cardinality simple link]**:ソーステーブルの1つのオカレンスは、対応する1つのオカレンスのターゲットテーブルです。 この種の場合、パフォーマンスの問題 **[!UICONTROL Link type]** が発生する可能性があります。
   ![](assets/schema_extension_29.png)

1. 画面では、 **[!UICONTROL New link]** とのフィー **[!UICONTROL Label]** ルドはデ **[!UICONTROL ID]** フォルトで入力されていますが、編集することもできます。

   >[!NOTE]
   >
   >最大30文字を使用します。

   >[!IMPORTANT]
   >
   >リンクの作成後にリンク名を変更することはできません。 リンクの名前を変更するには、リンクを削除して、再度作成する必要があります。

1. この **[!UICONTROL Category for the audience and targeting]** リストを使用すると、このリンクをカテゴリに割り当て、クエリエディタツールで表示しやすくできます。
1. 必要に応じて、このセ **[!UICONTROL Reverse link definition]** クションでは、対象のリソース内のリソースのラベルとIDを表示できます。
1. セクション内のリンクで参照されるレコードの動作を定義し **[!UICONTROL Behavior if deleted/duplicated]** ます。

   デフォルトでは、ターゲットレコードはリンクで参照されなくなると削除されます。

   ![](assets/schema_extension_16.png)

1. セクションで **[!UICONTROL Join definition]** は、デフォルトのオ **[!UICONTROL Use the primary keys to make the join]** プションが選択されていますが、次の2つのオプションから選択できます。

   * **[!UICONTROL Use the primary key to make the join]**:この結合定義を使用すると、プロファイルの主キーを使用して購入の主キーと調整できます。
   * **[!UICONTROL Define specific join conditions]**:この結合定義を使用すると、両方のリソースを結合するフィールドを手動で選択できます。 データが正しく設定されていない場合は、購入レコ **ードは** 表示されません。
   ![](assets/schema_extension_17.png)

作成されたリンクがセクションのリストに表示さ **[!UICONTROL Links]** れます。

>[!NOTE]
>
>インデックスを作成する際のベストプラクティスについては、この節を参照して [くださ](../../developing/using/data-model-best-practices.md#links)い。

**例：作成したリソースを&#39;プロファイル&#39;リソースにリンク**

この例では、新しいリソース **Purchaseを** プロファイル **・カスタム・リソースとリ** ンクします。

1. 新しい購入リソース **を作成** します。
1. これを **プロファイル** ・カスタム・リソースとリンクするには、タ **[!UICONTROL Links]** ブのセクションを **[!UICONTROL Data structure]** 展開し、をクリ **[!UICONTROL Create element]**&#x200B;ックします。
1. ここで、ターゲットリソースを選択しま **[!UICONTROL Profiles (profile)]**&#x200B;す。
1. この例では、デフォルトのリンクタイプを選 **[!UICONTROL 1 cardinality simple link]** 択したままにします。

   ![](assets/custom_resource_link_to_profile_2.png)

1. 結合定義を選択します。ここではデフォルトのままにしま **[!UICONTROL Use the primary key to make the join]**&#x200B;す。

   ![](assets/custom_resource_link_to_profile_3.png)

1. 必要に応じて、購入を編集してプロファイルにリンクする詳細画面を **定義できます** 。

   セクション **[!UICONTROL Detail screen configuration]** を展開し、リソー **[!UICONTROL Define a detail screen]** スの各要素に対応する画面を設定します。 このチェックボックスをオフにすると、このリソースの要素の詳細表示にアクセスできなくなります。

1. クリック **[!UICONTROL Create element]** .
1. リンクされたリソースを選択し、をクリックしま **[!UICONTROL Add]**&#x200B;す。

   その後、>を選択して、新しいリソースをアドバンスメニューで使 **[!UICONTROL Client data]** 用できま **[!UICONTROL Purchase]**&#x200B;す。

   ![](assets/custom_resource_link_to_profile_4.png)

1. 設定が完了したら、をクリックしま **[!UICONTROL Confirm]**&#x200B;す。

   これで、新しいリソースを公開できます。

このリンクを追加すると、「購入 **」タブが/メニューからプロファイルの詳細画面に** 追加され **[!UICONTROL Profiles & audiences]****[!UICONTROL Profiles]** ます。 これはリソースに固有のものであることに注意してく **[!UICONTROL Profile]** ださい。

![](assets/custom_resource_link_to_profile.png)

## 送信ログの拡張の定義 {#defining-sending-logs-extension}

送信ログの拡張機能を使用すると、次のことができます。

* 動的レポート機能を拡張するには、カスタムフィールド **プロファイルを追加します。**
* 送信ログデータを **セグメントコードとプロファイル**

**拡張とセグメントコード**

ユーザーは、ログを拡張する際に、そのセグメントコードのログを使用できます。

このセグメントコードは、ワークフロー内に定義する必要があります。

この拡張機能をアクティブにするには、オプションをオンにしま **[!UICONTROL Add segment code]**&#x200B;す。

![](assets/sendinglogsextension_1.png)

セグメントコードの詳細については、「セグメント化 [](../../automating/using/segmentation.md) 」の節を参照してください。

**拡張フィールドをプロファイル**

>[!NOTE]
>
>管理者は、カスタムフィールドを使用してプロファイルリソースを拡張している必要があります。

![](assets/sendinglogsextension_2.png)

をクリック **[!UICONTROL Add field]** し、任意のカスタムフィールドをプロファイルします。

プロファイルディメンションにリンクされた新しいサブディメンションを生成するには、このオプションをオンに **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** します。

![](assets/sendinglogsextension_3.png)

動的レポートから、カスタムフィールドディメンションをフリーフォームテーブルにドラッグ&amp;ドロップできます。

ダイナミックレポートについて詳しくは、コンポーネントの [リストを参照してくださ](../../reporting/using/list-of-components-.md)い。

>[!IMPORTANT]
>
>ダイナミックレポートに送信されるフィールドの数は20個に制限されます。

## リソースプロパティの編集 {#editing-resource-properties}

カスタムリソース画面のウィンドウに、新 **[!UICONTROL Summary]** しく作成されたリソースのステータスが表示されます。 アクセスとその一般的なプロパティを管理できます。

![](assets/schema_extension_3.png)

1. 説明を追加する **[!UICONTROL Edit properties]** には、ボタンをクリックします。

   ![](assets/schema_extension_30.png)

1. 必要に応じて、リソースのラベルとIDを変更します。

   >[!NOTE]
   >
   >最大30文字を使用します。

1. このリソースへのアクセスを特定の組織単位に制限する必要がある場合は、ここで指定します。 許可された単位のユーザーのみが、アプリケーションでこのリソースを使用できます。
1. 変更を保存します。

変更が保存されます。 リソースを適用するには、再度リソースを発行する必要があります。

## リソースおよびカスタムプロファイルの一意のIDの生成 {#generating-a-unique-id-for-profiles-and-custom-resources}

デフォルトでは、プロファイルとカスタムリソースの作成時にビジネスIDは持ちません。 要素の作成時に一意のIDを自動的に生成するオプションを有効にできます。 このIDは、次の目的で使用できます。

* 外部ツールでエクスポートされたレコードを簡単に識別できます。
* 別のアプリケーションで処理された更新済みデータをインポートする際に、レコードを調整します。

有効にできるのは、リソースとカスタムプロファイルのみです。

1. リソースリソースの拡張子を作成するか、プロファイルを新しく作成します。
1. データ構造の定義で、セクションの下の **[!UICONTROL Add automatic ID field]** オプションをチェックし **[!UICONTROL Fields]** ます。

   ![](assets/option_id_field.png)

   >[!NOTE]
   >
   >新しいレコードのみがACS IDを持ちます。 このオプシ **[!UICONTROL ACS ID]** ョンを有効にする前に作成されたプロファイルまたは要素のフィールドは空のままです。

1. リソースに対して行った変更を保存し、公開します。 このメカニズムをAPIを介して作成された要素に適用する場合は、APIを拡張するオプションを選択します。

新しい **[!UICONTROL ACS ID]** 要素が手動、APIから、または読み込みワークフローから挿入されたときに、このフィールドが使用可能になり、自動的に設定されるようになりました。 ACS IDフィールドはUUIDフィールドで、インデックスが作成されます。

プロファイルまたはカスタムリソースを書き出す際に、そのリソースが有効になっ **[!UICONTROL ACS ID]** ている場合に列を追加できるようになりました。 このIDを外部ツールで再利用して、レコードを識別できます。

![](assets/export_id_field.png)

別のアプリケーション（CRMなど）で処理または更新されたデータを再インポートする場合、この一意のIDと簡単に調整できます。

>[!NOTE]
>
>オプション **[!UICONTROL ACS ID]** を有効にする前に作成されたプロファイルまたは要素のフィールドは更新されません。 新しいレコードのみがACS IDを持ちます。
>
>このフィールドは読み取り専用モードです。 変更はできません。
