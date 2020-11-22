---
solution: Campaign Standard
product: campaign
title: 複合 ID キーを使用したリソースの呼び出し
description: 複合IDキーを使用してリソースを呼び出す方法を学習します。
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---


# 複合 ID キーを使用したリソースの呼び出し{#calling-a-resource-using-a-composite-identification-key}

場合によっては、2つのフィールドで構成される識別キーをリソースに対して定義する必要があります。 IDキーを設定したら、Campaign StandardインターフェイスまたはAPIからこのIDキーを使用してリソースを呼び出せるように、フィルター定義を設定する必要があります。

この使用例では、 **プロファイル** リソースがカスタムの「CRM ID **」フィールドと「** カテゴリ」 **** フィールドを使用して拡張されています。 この2つのフィールドで構成されるプロファイルリソースのIDキーを作成します。 次に、IDキーを使用してプロファイルリソースにアクセスできるように、フィルター定義を設定します。

この使用例の主な手順は次のとおりです。

1. 2つのフィールドに基づいて、プロファイルリソースのIDキーを設定します。
1. IDキーを使用してプロファイルリソースを呼び出せるように、フィルター定義を設定します。
1. プロファイルリソースをインターフェイスまたはAPから呼び出します。

関連トピック ： 

* [リソースの作成または拡張](../../developing/using/creating-or-extending-the-resource.md)
* [識別キーの定義](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign StandardREST API](../../api/using/get-started-apis.md)

## 手順1:IDキーの設定{#step-1-configure-the-identification-key}

>[!NOTE]
> IDキーを設定する際のグローバルな概念について詳し [くは、この節](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

1. IDキーを設定する前に、目的のフィールドでリソースが拡張され、発行されていることを確認します。 詳しくは、[この節](../../developing/using/creating-or-extending-the-resource.md)を参照してください。

1. 「 **[!UICONTROL Administration]** / **[!UICONTROL Developement]** /」 **[!UICONTROL Custom resources]** メニューに移動し、 **[!UICONTROL Profile]** リソースを開きます。

   ![](assets/uc_idkey1.png)

1. In the **[!UICONTROL Identification keys]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/uc_idkey2.png)

1. 2つ追加のカスタム「CRM ID」と「カテゴリ」フィールドで、をクリックし **[!UICONTROL Confirm]**&#x200B;ます。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > プロファイルのインターフェイスに2つのカスタムフィールドを表示する場合は、 **[!UICONTROL Screen definition]** タブを設定します。 詳しくは、[この節](../../developing/using/configuring-the-screen-definition.md)を参照してください。

1. これで、フィルター定義のIDキーを使用してリソースを呼び出せるようにフィルター定義を設定できます。

## 手順2:フィルター定義の設定{#step-2-configure-the-filter-definition}

>[!NOTE]
> フィルター定義を設定する際のグローバル概念について詳し [くは、この節](../../developing/using/configuring-filter-definition.md)。

1. タブでをクリック **[!UICONTROL Filter definition]****[!UICONTROL Add an element]**&#x200B;し、フィルタ定義のラベルとIDを入力します。

1. フィルター定義のプロパティを編集して、ルールを設定します。

   ![](assets/uc_idkey4.png)

1. IDキーで使用されるフィールドを含むテーブルをワークスペースにドラッグ&amp;ドロップします。

   ![](assets/uc_idkey5.png)

1. IDキーで使用される最初のフィールド(「CRM ID」)を選択し、この **[!UICONTROL Switch to parameters]** オプションをアクティブ化します。

   ![](assets/uc_idkey6.png)

1. このセクションでは、 **[!UICONTROL Filter conditions]****[!UICONTROL Equal]** 演算子をそのまま使用し、パラメーターの名前を定義し、プラス記号をクリックして作成します。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > 「 **+」** ボタンをクリックすると、パラメーター名が自動的に生成されます。 この情報は、APIのフィルタを使用する必要があるので、注意してください。

1. IDキー(「カテゴリ」)を構成するすべてのフィールドに対して上記の手順を繰り返し、変更を保存します。

   ![](assets/uc_idkey8.png)

1. これで、フィルター定義が設定されます。 リソースを公開して、フィルターを使用できます。

## 手順3:識別キーに基づいてリソースを呼び出す{#step-3-call-the-resource-based-on-its-identification-key}

IDキーとそのフィルター定義が設定されたら、それらを使用して、キャンペーン標準インターフェイスまたはREST APIからリソースを呼び出すことができます。

インターフェイスのフィルタ定義を使用するには、ワークフローで **[!UICONTROL Query]** アクティビティを使用します( [この節を参照](../../automating/using/query.md))。 その後、左側のペインでフィルターを使用できます。

![](assets/uc_idkey9.png)

Campaign StandardREST APIのフィルター定義を使用するには、次の構文を使用します。

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>カスタムフィルターを呼び出すには、 [手順2でフィルター定義を設定する際に定義したフィルター名の後に、「by」プレフィックスを使用し](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition)ます。

この例では、「123456」CRM IDを持つ「spring」カテゴリからプロファイルを取得する構文は次のようになります。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

詳しくは、 [Campaign StandardREST APIのドキュメントを参照してください](../../api/using/filtering.md)。