---
title: 複合識別キーを使用したリソースの呼び出し
seo-title: 複合識別キーを使用したリソースの呼び出し
description: 複合識別キーを使用したリソースの呼び出し
seo-description: 複合識別キーを使用してリソースを呼び出す方法
translation-type: tm+mt
source-git-commit: ff9861a2b8a59843cc668cec9f89b9ea76822d66

---


# 複合識別キーを使用したリソースの呼び出し

場合によっては、2つのフィールドで構成される識別キーをリソースに定義する必要があります。識別キーを構成したら、"Campaign Standard"インターフェイスまたは"API"から、この識別キーでリソースを呼び出すために、フィルタ定義を構成する必要があります。

このユースケースでは **、プロファイル** リソースはカスタムの **"CRM ID»フィールド?と«?カテゴリ******&#x200B;この2つのフィールドで構成されるプロファイルリソースのIDキーを作成します。次に、識別キーを使用してプロファイルリソースにアクセスできるように、フィルター定義を構成します。

このユースケースの主な手順は次のとおりです。

1. 2つのフィールドに基づいて、プロファイルリソースの識別キーを構成します。
1. フィルター定義を構成し、そのIDキーを使用してプロファイルリソースを呼び出すことができるようにします。
1. インターフェイスまたはAPIからプロファイルリソースを呼び出します。

関連トピック:

* [リソースの作成または拡張](../../developing/using/creating-or-extending-the-resource.md)
* [識別キーの定義](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [キャンペーン標準REST API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## ステップ1:識別キーの設定

>[!NOTE]
> 識別キーを構成する際のグローバルな概念については、このセクションで [詳しく](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)説明します。

1. 識別キーを構成する前に、リソースが必要なフィールドで拡張され、発行されたことを確認します。For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. / **[!UICONTROL Administration]****[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** メニューに移動し、 **[!UICONTROL Profile]** リソースを開きます。

   ![](assets/uc_idkey1.png)

1. **[!UICONTROL Identification keys]** セクションで、 **[!UICONTROL Create element]** ボタンをクリックします。

   ![](assets/uc_idkey2.png)

1. 2つのカスタム"CRM ID"フィールドと"Category"フィールドを追加し、をクリック **[!UICONTROL Confirm]**&#x200B;します。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > プロファイルのインターフェイスに2つのカスタムフィールドを表示する場合は、 **[!UICONTROL Screen definition]** タブを構成します。For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. これで、識別キーを使用してリソースを呼び出すことができるようにフィルタ定義を構成できるようになりました。

## ステップ2:フィルター定義の構成

>[!NOTE]
> フィルター定義を構成するときのグローバル概念については、このセクションで [詳しく](../../developing/using/configuring-filter-definition.md)説明します。

1. **[!UICONTROL Filter definition]** タブで、をクリック **[!UICONTROL Add an element]**&#x200B;し、フィルタ定義のラベルとIDを入力します。

1. フィルター定義のプロパティを編集して、その規則を構成します。

   ![](assets/uc_idkey4.png)

1. 識別キーで使用されるフィールドを含むテーブルをワークスペースにドラッグアンドドロップします。

   ![](assets/uc_idkey5.png)

1. 識別キー（"CRM ID"）で使用する最初のフィールドを選択し、オプション **[!UICONTROL Switch to parameters]** を有効にします。

   ![](assets/uc_idkey6.png)

1. **[!UICONTROL Filter conditions]** セクションで **[!UICONTROL Equal]** 、演算子を保持し、パラメータの名前を定義してプラス記号をクリックして作成します。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > プラスボタンをクリックすると、パラメータの名前が自動的に生成されます。この情報は、APIのフィルタを使用するために必要です。

1. 識別キー（「カテゴリ」）を構成するすべてのフィールドで上記の手順を繰り返し、変更を保存します。

   ![](assets/uc_idkey8.png)

1. フィルター定義が構成されました。フィルタを使用できるようにリソースを発行できます。

## ステップ3:識別キーに基づいてリソースを呼び出します

識別キーとそのフィルタ定義を構成したら、それらを使用して、Campaign標準インターフェイスまたはREST APIからリソースを呼び出すことができます。

インターフェイスのフィルター定義を使用するには、ワークフローの **[!UICONTROL Query]** アクティビティを使用します（この [セクション](../../automating/using/query.md)を参照）。その後、左側のペインでフィルターを使用できます。

![](assets/uc_idkey9.png)

Campaign Standard REST APIのフィルタ定義を使用するには、次の構文を使用します。

```
GET /profileAndServicesExt/<resourceName><filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

この場合、「スプリング」カテゴリからプロファイルを取得する構文と"123456" CRM IDは次のようになります。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

詳細については [、Campaign Standard REST APIのドキュメント](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering)を参照してください。