---
title: 複合識別キーを使用したリソースの呼び出し
seo-title: 複合識別キーを使用したリソースの呼び出し
description: 複合識別キーを使用したリソースの呼び出し
seo-description: 複合識別キーを使用してリソースを呼び出す方法について説明します
translation-type: tm+mt
source-git-commit: b9bc9163cc02efea8549a21fa947956dc9d3824a

---


# 複合識別キーを使用したリソースの呼び出し

場合によっては、2つのフィールドで構成されるIDキーをリソースに定義することが必要な場合があります。IDキーが設定されたら、キャンペーンStandardインターフェイスまたはAPIからこのIDキーでリソースを呼び出せるように、フィルター定義を設定する必要があります。

In this use case, the **Profile** resource has been extended with custom **"CRM ID"** and **"category"** field. これら2つのフィールドで構成されるプロファイルリソースのIDキーを作成します。次に、IDキーを使用してプロファイルリソースにアクセスできるように、フィルター定義を設定します。

この使用例の主な手順を次に示します。

1. 2つのフィールドに基づいてプロファイルリソースのIDキーを設定します。
1. IDキーを使用してプロファイルリソースを呼び出せるように、フィルター定義を設定します。
1. インターフェイスまたはAPIからプロファイルリソースを呼び出します。

関連トピック:

* [リソースの作成または拡張](../../developing/using/creating-or-extending-the-resource.md)
* [IDキーの定義](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Campaign Standard REST API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## 手順1:IDキーの設定

>[!NOTE]
> Global concepts when configuring identification keys are detailed in [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. IDキーを設定する前に、目的のフィールドとそれが発行されていることを確認してください。For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** メニューに移動し、リソースを **[!UICONTROL Profile]** 開きます。

   ![](assets/uc_idkey1.png)

1. **[!UICONTROL Identification keys]** セクションで、ボタンを **[!UICONTROL Create element]** クリックします。

   ![](assets/uc_idkey2.png)

1. Add the two custom "CRM ID" and "Category" fields, then click **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > If you want to display the two custom fields in the profile's interface, configure the **[!UICONTROL Screen definition]** tab. For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. IDキーを使用してリソースを呼び出せるように、フィルター定義を設定できるようになりました。

## 手順2:フィルター定義の設定

>[!NOTE]
> Global concepts when configuring filter definitions are detailed in [this section](../../developing/using/configuring-filter-definition.md).

1. **[!UICONTROL Filter definition]** タブでをクリック **[!UICONTROL Add an element]**&#x200B;し、フィルター定義のラベルとIDを入力します。

1. フィルター定義のプロパティを編集して、ルールを設定します。

   ![](assets/uc_idkey4.png)

1. IDキーで使用されているフィールドを含むテーブルをワークスペースにドラッグ&amp;ドロップします。

   ![](assets/uc_idkey5.png)

1. Select the first field used in the identification key ("CRM ID"), then activate the **[!UICONTROL Switch to parameters]** option.

   ![](assets/uc_idkey6.png)

1. **[!UICONTROL Filter conditions]** セクションで **[!UICONTROL Equal]** 、演算子を保持し、パラメーターの名前を定義して、プラス記号をクリックして作成します。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > プラスボタンをクリックすると、パラメーターの名前が自動的に生成されます。APIからフィルターを使用する必要があるので、この情報に注意してください。

1. 上記の手順を繰り返して、IDキー（"category"）を構成するすべてのフィールドを選択し、変更を保存します。

   ![](assets/uc_idkey8.png)

1. フィルター定義が設定されるようになりました。フィルターを使用できるようにリソースを公開できます。

## 手順3:IDキーに基づいてリソースを呼び出します

IDキーとフィルター定義が設定されたら、キャンペーン標準インターフェイスまたはREST APIからリソースを呼び出すことができます。

To use the filter definition from the interface, use a **[!UICONTROL Query]** activity in a workflow (see [this section](../../automating/using/query.md)). その後、左側のパネルでフィルターを使用できます。

![](assets/uc_idkey9.png)

キャンペーン標準REST APIからフィルター定義を使用するには、以下の構文を使用します。

```
GET /profileAndServicesExt/<resourceName><filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

この場合、"Spring"カテゴリからプロファイルを取得する構文と"123456" CRM IDは次のようになります。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

For more details, refer to [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).