---
title: 複合IDキーを使用したリソースの呼び出し
seo-title: 複合IDキーを使用したリソースの呼び出し
description: 複合IDキーを使用したリソースの呼び出し
seo-description: 複合IDキーを使用してリソースを呼び出す方法を説明します
translation-type: tm+mt
source-git-commit: 339dfbcc9b6443211079d116eb3e007db69c8b1a

---


# 複合IDキーを使用したリソースの呼び出し{#calling-a-resource-using-a-composite-identification-key}

場合によっては、2つのフィールドで構成される識別キーをリソースに定義する必要があります。 IDキーを設定したら、キャンペーン標準インターフェイスまたはAPIから、このIDキーを使用してリソースを呼び出せるように、フィルタ定義を構成する必要があります。

この使用例では、 **Profile** リソースがカスタムの「CRM ID **」および「category** 」フ **ィールドで拡張され** ました。 この2つのフィールドで構成されるプロファイルリソースのIDキーを作成します。 次に、識別キーを使用してプロファイルリソースにアクセスできるように、フィルタ定義を構成します。

この使用例の主な手順は次のとおりです。

1. 2つのフィールドに基づいて、プロファイルリソースの識別キーを構成します。
1. 識別キーを使用してプロファイルリソースを呼び出せるように、フィルタ定義を構成します。
1. インターフェイスまたはAPisからProfileリソースを呼び出します。

関連トピック：

* [リソースの作成または拡張](../../developing/using/creating-or-extending-the-resource.md)
* [識別キーの定義](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [キャンペーン標準REST API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## ステップ1:IDキーの構成{#step-1-configure-the-identification-key}

>[!NOTE]
> IDキーを設定する際のグローバルな概念については、この節で詳 [しく説明します](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)。

1. IDキーを設定する前に、リソースが目的のフィールドで拡張され、発行されていることを確認してください。 For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. / **[!UICONTROL Administration]** /メニューに **[!UICONTROL Developement]** 移動し **[!UICONTROL Custom resources]** 、リソースを開き **[!UICONTROL Profile]** ます。

   ![](assets/uc_idkey1.png)

1. セクションで、 **[!UICONTROL Identification keys]** ボタンをクリック **[!UICONTROL Create element]** します。

   ![](assets/uc_idkey2.png)

1. 2つのユーザー設定の[CRM ID]フィールドと[カテゴリ]フィールドを追加し、をクリックしま **[!UICONTROL Confirm]**&#x200B;す。

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > プロファイルのインタフェースに2つのカスタムフィールドを表示する場合は、タブを構成 **[!UICONTROL Screen definition]** します。 For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. IDキーを使用してリソースを呼び出せるように、フィルタ定義を構成できます。

## 手順2:フィルタ定義の構成{#step-2-configure-the-filter-definition}

>[!NOTE]
> フィルタ定義を設定する際のグローバルな概念については、このセクシ [ョンで詳しく説明しま](../../developing/using/configuring-filter-definition.md)す。

1. タブでを **[!UICONTROL Filter definition]** クリックし、 **[!UICONTROL Add an element]**&#x200B;フィルタ定義のラベルとIDを入力します。

1. フィルタ定義のプロパティを編集して、規則を構成します。

   ![](assets/uc_idkey4.png)

1. IDキーで使用するフィールドを含むテーブルをワークスペースにドラッグ&amp;ドロップします。

   ![](assets/uc_idkey5.png)

1. IDキーで最初に使用するフィールド("CRM ID")を選択し、オプションをアクティブに **[!UICONTROL Switch to parameters]** します。

   ![](assets/uc_idkey6.png)

1. セクション **[!UICONTROL Filter conditions]** で、演算子を残し **[!UICONTROL Equal]** 、パラメータの名前を定義し、プラス記号をクリックして作成します。

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > [+]ボタンをクリックすると、パラメータ名が自動的に生成されます。 この情報は、APIのフィルタを使用するために必要なので注意してください。

1. IDキー（「カテゴリ」）を構成するすべてのフィールドで上記の手順を繰り返し、変更を保存します。

   ![](assets/uc_idkey8.png)

1. これで、フィルタ定義が構成されました。 フィルタを使用できるように、リソースを発行できます。

## ステップ3:識別キーに基づいてリソースを呼び出す{#step-3-call-the-resource-based-on-its-identification-key}

識別キーとそのフィルタ定義が構成されたら、それらを使用して、キャンペーン標準インタフェースまたはREST APIからリソースを呼び出すことができます。

インタフェースのフィルタ定義を使用するには、ワークフローでア **[!UICONTROL Query]** クティビティを使用します(このセクシ [ョンを参照](../../automating/using/query.md))。 左側のペインでフィルタを使用できます。

![](assets/uc_idkey9.png)

キャンペーン標準REST APIのフィルタ定義を使用するには、次の構文を使用します。

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>顧客フィルタを呼び出すには、手順2でフィルタ定義を構成する際に定義されたフィルタ名の後に「by」接頭辞を付 [けます](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition)。

この場合、「123456」 CRM idを持つ「spring」カテゴリからプロファイルを取得する構文は次のとおりです。

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

詳細は、『キャンペーン標準REST APIs [』マニュアルを参照してください](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering)。