---
title: 複合 ID キーを使用したリソースの呼び出し
description: 複合 ID キーを使用したリソースの呼び出し方法を説明します
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---

# 複合 ID キーを使用したリソースの呼び出し{#calling-a-resource-using-a-composite-identification-key}

場合によっては、リソースに対して 2 つのフィールドで構成される識別キーを定義する必要があります。 識別キーを設定したら、Campaign Standardインターフェイスまたは API からこの識別キーを使用してリソースを呼び出せるように、フィルター定義を設定する必要があります。

この使用例では、 **プロファイル** リソースがカスタムで拡張されました **&quot;CRM ID&quot;** および **&quot;category&quot;** フィールド。 プロファイルリソースの識別キーを作成します。このキーは、これら 2 つのフィールドで構成されます。 次に、識別キーを使用してプロファイルリソースにアクセスできるように、フィルター定義を設定します。

この使用例の主な手順は次のとおりです。

1. 2 つのフィールドに基づいて、プロファイルリソースの識別キーを設定します。
1. フィルター定義を設定し、その識別キーを使用してプロファイルリソースを呼び出すことができるようにします。
1. インターフェイスまたは APis からプロファイルリソースを呼び出します。

関連トピック ： 

* [リソースの作成または拡張](../../developing/using/creating-or-extending-the-resource.md)
* [識別キーの定義](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign StandardREST API](../../api/using/get-started-apis.md)

## 手順 1:識別キーの設定{#step-1-configure-the-identification-key}

>[!NOTE]
> 識別キーを設定する際のグローバル概念について詳しくは、 [この節](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. 識別キーを設定する前に、目的のフィールドを使用してリソースが拡張され、公開されていることを確認します。 詳しくは、[この節](../../developing/using/creating-or-extending-the-resource.md)を参照してください。

1. 次に移動： **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** メニューを開き、 **[!UICONTROL Profile]** リソース。

   ![](assets/uc_idkey1.png)

1. 内 **[!UICONTROL Identification keys]** セクションで、 **[!UICONTROL Create element]** 」ボタンをクリックします。

   ![](assets/uc_idkey2.png)

1. 2 つのカスタム「CRM ID」フィールドと「カテゴリ」フィールドを追加し、 **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > プロファイルのインターフェイスに 2 つのカスタムフィールドを表示する場合は、 **[!UICONTROL Screen definition]** タブをクリックします。 詳しくは、[この節](../../developing/using/configuring-the-screen-definition.md)を参照してください。

1. これで、フィルター定義の識別キーを使用してリソースを呼び出せるように、フィルター定義を設定できます。

## 手順 2:フィルター定義の設定{#step-2-configure-the-filter-definition}

>[!NOTE]
> フィルター定義を設定する際のグローバル概念について詳しくは、 [この節](../../developing/using/configuring-filter-definition.md).

1. 内 **[!UICONTROL Filter definition]** タブ、クリック **[!UICONTROL Add an element]**&#x200B;次に、フィルター定義のラベルと ID を入力します。

1. フィルター定義のプロパティを編集して、ルールを設定します。

   ![](assets/uc_idkey4.png)

1. 識別キーで使用するフィールドを含むテーブルをワークスペースにドラッグ&amp;ドロップします。

   ![](assets/uc_idkey5.png)

1. 識別キーで使用する最初のフィールド (「CRM ID」) を選択し、 **[!UICONTROL Switch to parameters]** オプション。

   ![](assets/uc_idkey6.png)

1. 内 **[!UICONTROL Filter conditions]** セクション、 **[!UICONTROL Equal]** 演算子を使用して、パラメーターの名前を定義し、プラス記号をクリックして作成します。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 次に、 **+** 」ボタンをクリックすると、パラメーターの名前が自動的に生成されます。 API からフィルターを使用するにはこの情報が必要なので、この情報に注意してください。

1. 識別キー（「カテゴリ」）を構成するすべてのフィールドに対して上記の手順を繰り返し、変更を保存します。

   ![](assets/uc_idkey8.png)

1. これで、フィルター定義が設定されました。 フィルターを使用できるように、リソースを公開できます。

## 手順 3:識別キーに基づいてリソースを呼び出す{#step-3-call-the-resource-based-on-its-identification-key}

識別キーとそのフィルター定義を設定したら、それらを使用して、Campaign Standard インターフェイスまたは REST API からリソースを呼び出すことができます。

インターフェイスでフィルター定義を使用するには、 **[!UICONTROL Query]** ワークフローのアクティビティ ( [この節](../../automating/using/query.md)) をクリックします。 これで、左側のウィンドウでフィルターを使用できるようになります。

![](assets/uc_idkey9.png)

Campaign StandardREST API のフィルター定義を使用するには、次の構文を使用します。

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>カスタムフィルターを呼び出すには、「by」プレフィックスを使用し、その後に [手順 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

この例では、「123456」 CRM ID を使用して「spring」カテゴリからプロファイルを取得する構文は次のようになります。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

詳しくは、 [Campaign StandardREST API のドキュメント](../../api/using/filtering.md).
