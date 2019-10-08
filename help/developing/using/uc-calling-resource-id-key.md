---
title: 複合IDキーを使用したリソースの呼び出し
seo-title: 複合IDキーを使用したリソースの呼び出し
description: 複合IDキーを使用したリソースの呼び出し
seo-description: 複合IDキーを使用してリソースを呼び出す方法を説明します。
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# 複合IDキーを使用したリソースの呼び出し{#calling-a-resource-using-a-composite-identification-key}

場合によっては、2つのフィールドで構成される識別キーをリソースに対して定義する必要があります。 IDキーを設定したら、Campaign StandardインターフェイスまたはAPIからこのIDキーを使用してリソースを呼び出せるように、フィルター定義を設定する必要があります。

この使用例では、 **Profile** リソースがカスタムの「CRM ID **」と「category** 」フ **ィールドで拡張されました** 。 この2つのフィールドで構成されるプロファイルリソースのIDキーを作成します。 次に、IDキーを使用してプロファイルリソースにアクセスできるように、フィルター定義を設定します。

この使用例の主な手順は次のとおりです。

1. 2つのフィールドに基づいて、プロファイルリソースのIDキーを設定します。
1. 識別キーを使用してプロファイルリソースを呼び出せるように、フィルター定義を設定します。
1. インターフェイスまたはAPisからプロファイルリソースを呼び出します。

関連トピック：

* [リソースの作成または拡張](../../developing/using/creating-or-extending-the-resource.md)
* [識別キーの定義](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [キャンペーン標準REST API](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## 手順1:IDキーの設定{#step-1-configure-the-identification-key}

>[!NOTE]
> IDキーを設定する際のグローバルな概念については、この節で [詳しく説明しま](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)す。

1. IDキーを設定する前に、リソースが目的のフィールドで拡張され、発行されていることを確認します。 詳しくは、[この節](../../developing/using/creating-or-extending-the-resource.md)を参照してください。

1. / **[!UICONTROL Administration]** /メニューに移 **[!UICONTROL Developement]** 動し **[!UICONTROL Custom resources]** 、リソースを開き **[!UICONTROL Profile]** ます。

   ![](assets/uc_idkey1.png)

1. セクション **[!UICONTROL Identification keys]** で、ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/uc_idkey2.png)

1. 2つのカスタム「CRM ID」フィールドと「カテゴリ」フィールドを追加し、をクリックしま **[!UICONTROL Confirm]**&#x200B;す。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > プロファイルのインターフェイスに2つのカスタムフィールドを表示する場合は、タブを設定し **[!UICONTROL Screen definition]** ます。 詳しくは、[この節](../../developing/using/configuring-the-screen-definition.md)を参照してください。

1. これで、フィルター定義のIDキーを使用してリソースを呼び出せるように設定できます。

## 手順2:フィルター定義の設定{#step-2-configure-the-filter-definition}

>[!NOTE]
> フィルター定義を設定する際のグローバル概念については、この節 [で詳しく説明しま](../../developing/using/configuring-filter-definition.md)す。

1. タブでを **[!UICONTROL Filter definition]** クリックし、 **[!UICONTROL Add an element]**&#x200B;フィルター定義のラベルとIDを入力します。

1. フィルター定義のプロパティを編集して、ルールを設定します。

   ![](assets/uc_idkey4.png)

1. IDキーで使用されるフィールドを含むテーブルをワークスペースにドラッグ&amp;ドロップします。

   ![](assets/uc_idkey5.png)

1. IDキーで使用される最初のフィールド(「CRM ID」)を選択し、このオプションをアクティブにし **[!UICONTROL Switch to parameters]** ます。

   ![](assets/uc_idkey6.png)

1. セクション **[!UICONTROL Filter conditions]** で、演算子を残し、 **[!UICONTROL Equal]** パラメーターの名前を定義し、プラス記号をクリックして作成します。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > プラスボタンをクリックすると、パラメーターの名前が自動的に生成されます。 この情報は、APIのフィルターを使用する必要があるので、注意してください。

1. IDキー(「category」)を構成するすべてのフィールドで上記の手順を繰り返し、変更を保存します。

   ![](assets/uc_idkey8.png)

1. これで、フィルター定義が設定されました。 リソースを公開して、フィルターを使用できるようにします。

## 手順3:識別キーに基づいてリソースを呼び出す{#step-3-call-the-resource-based-on-its-identification-key}

IDキーとそのフィルター定義を設定したら、それらを使用して、Campaign標準インターフェイスまたはREST APIからリソースを呼び出すことができます。

インターフェイスのフィルター定義を使用するには、ワークフローでア **[!UICONTROL Query]** クティビティを使用します(こ [の節を参照](../../automating/using/query.md))。 その後、左側のパネルでフィルターを使用できます。

![](assets/uc_idkey9.png)

キャンペーン標準REST APIのフィルター定義を使用するには、次の構文を使用します。

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>顧客フィルターを呼び出すには、手順2でフィルター定義を設定する際に、「by」プレフィックスに続けて定義したフィルター名を [使用しま](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition)す。

この例では、「123456」CRM IDを持つ「spring」カテゴリからプロファイルを取得する構文は、次のようになります。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

詳しくは、キャンペーン標準REST APIに関 [するドキュメントを参照してください](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering)。