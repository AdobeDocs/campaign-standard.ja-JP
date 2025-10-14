---
title: 複合 ID キーを使用したリソースの呼び出し
description: 複合識別キーを使用してリソースを呼び出す方法を説明します
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 6%

---

# 複合 ID キーを使用したリソースの呼び出し{#calling-a-resource-using-a-composite-identification-key}

場合によっては、リソースに、2 つのフィールドで構成される ID キーを定義する必要があります。 ID キーが設定されたら、この ID キーを使用してリソースをCampaign Standardインターフェイスまたは API から呼び出せるように、フィルター定義を設定する必要があります。

このユースケースでは、**プロファイル** リソースをカスタム **「CRM ID」および** 「カテゴリ **フィールドで拡張し** した。 これらの 2 つのフィールドで構成される、プロファイルリソースの識別キーを作成します。 次に、識別キーを使用してプロファイルリソースにアクセスできるように、フィルター定義を設定します。

このユースケースの主な手順は次のとおりです。

1. 2 つのフィールドに基づいて、プロファイルリソースの識別キーを設定します。
1. 識別キーを使用してプロファイルリソースを呼び出せるように、フィルター定義を設定します。
1. インターフェイスまたは API からプロファイルリソースを呼び出します。

関連トピック ： 

* [リソースの作成または拡張](../../developing/using/creating-or-extending-the-resource.md)
* [識別キーの定義](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [CAMPAIGN STANDARD REST API](../../api/using/get-started-apis.md)

## 手順 1：識別キーの設定{#step-1-configure-the-identification-key}

>[!NOTE]
> 識別キーを設定する際の全体的な概念については、[&#x200B; この節 &#x200B;](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys) を参照してください。

1. 識別キーを設定する前に、リソースが目的のフィールドを使用して拡張されていることと、リソースが公開されていることを確認してください。 詳しくは、[この節](../../developing/using/creating-or-extending-the-resource.md)を参照してください。

1. **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** メニューに移動し、**[!UICONTROL Profile]** リソースを開きます。

   ![](assets/uc_idkey1.png)

1. **[!UICONTROL Identification keys]** セクションで、「**[!UICONTROL Create element]**」ボタンをクリックします。

   ![](assets/uc_idkey2.png)

1. 2 つのカスタム「CRM ID」および「カテゴリ」フィールドを追加し、「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > プロファイルのインターフェイスに 2 つのカスタムフィールドを表示する場合は、「**[!UICONTROL Screen definition]**」タブを設定します。 詳しくは、[この節](../../developing/using/configuring-the-screen-definition.md)を参照してください。

1. 識別キーを使用してリソースを呼び出せるようにフィルター定義を設定できるようになりました。

## 手順 2：フィルター定義の設定{#step-2-configure-the-filter-definition}

>[!NOTE]
> フィルター定義を設定する際の全体的な概念については、[&#x200B; この節 &#x200B;](../../developing/using/configuring-filter-definition.md) を参照してください。

1. 「**[!UICONTROL Filter definition]**」タブで「**[!UICONTROL Add an element]**」をクリックし、フィルター定義のラベルと ID を入力します。

1. フィルター定義のプロパティを編集し、そのルールを設定します。

   ![](assets/uc_idkey4.png)

1. ID キーで使用されるフィールドを含むテーブルをワークスペースにドラッグ&amp;ドロップします。

   ![](assets/uc_idkey5.png)

1. 識別キー（「CRM ID」）で使用される最初のフィールドを選択し、「**[!UICONTROL Switch to parameters]**」オプションをアクティブ化します。

   ![](assets/uc_idkey6.png)

1. 「**[!UICONTROL Filter conditions]**」セクションで、**[!UICONTROL Equal]** 演算子を保持し、パラメーターの名前を定義した後、プラス記号をクリックしてパラメーターを作成します。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > **+** ボタンをクリックすると、パラメーターの名前が自動的に生成されます。 この情報は、API からフィルターを使用するために必要なので、注意してください。

1. 識別キー（「カテゴリ」）を構成するすべてのフィールドで上記の手順を繰り返し、変更を保存します。

   ![](assets/uc_idkey8.png)

1. これで、フィルター定義が設定されました。 リソースを公開すると、フィルターを使用できるようになります。

## 手順 3：識別キーに基づくリソースの呼び出し{#step-3-call-the-resource-based-on-its-identification-key}

識別キーとそのフィルター定義を設定したら、それらを使用して Campaign Standard インターフェイスまたは REST API からリソースを呼び出すことができます。

インターフェイスからフィルター定義を使用するには、ワークフローで **[!UICONTROL Query]** アクティビティを使用します（[&#x200B; この節 &#x200B;](../../automating/using/query.md) を参照）。 フィルターは左側のパネルで使用できます。

![](assets/uc_idkey9.png)

Campaign Standard REST API のフィルター定義を使用するには、次の構文を使用します。

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>カスタムフィルターを呼び出すには、「by」プレフィックスの後に、[&#x200B; 手順 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition) でフィルター定義を設定する際に定義したフィルター名を使用します。

この場合、「spring」カテゴリから CRM ID 「123456」を持つプロファイルを取得する構文は次のようになります。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

詳しくは、[Campaign Standard REST API ドキュメント &#x200B;](../../api/using/filtering.md) を参照してください。
