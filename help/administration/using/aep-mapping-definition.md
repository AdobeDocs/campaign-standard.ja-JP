---
title: マッピング定義
description: 「キャンペーン標準」フィールドをエクスペリエンスデータモデル(XDM)フィールドにマッピングする方法について説明します。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 74e2e1e6cc9c045203f4cfbe37cab673b6761b89

---


# マッピング定義 {#mapping-definition}

>[!IMPORTANT]
>
>キャンペーン標準データサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

この節では、「キャンペーン標準」フィールドと「エクスペリエンスデータモデル(XDM)」フィールドをマッピングする方法について説明します。

>[!NOTE]
>
>このタスクを実行するための前提条件は次のとおりです。
>
> * インターフェイスを介した、またはXDMに関連付けられたREST APIを使用したXDMスキーマ定義
> * xdmスキーマ定義に基づくデータセットの作成


1. //に移 **[!UICONTROL Administration]**動し**[!UICONTROL Development]** 、エ **[!UICONTROL Platform]**ントリを選択し**[!UICONTROL Data mappings]** ます。

1. をクリックし **[!UICONTROL Create]**て、新しいXDMマッピングを開始します。

   ![](assets/aep_createmapping.png)

1. 必須フィールドに入力し、次を選択します。

   * ターゲット **ディメンション**:これは、マッピングするキャンペーン標準スキーマです
   * データ **セット**:これは、Adobe Experience PlatformのXDMスキーマに関連付けられたデータパッケージです。

>[!NOTE]
>
>バッチをReal-time Customer ProfileまたはIDサービスに取り込むには、データセットでReal-time Customer Profileを有効にす [る必要があります](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/data_ingestion_tutorial/data_ingestion_tutorial.md)。
>
>選択したデータセットが既に既存のデータマッピングで使用されている場合は、Adobe Experience Platformでデータが上書きされる可能性があることを知らせる警告が表示されます。 これは、同じデータセットを使用するDataMappingの受信者がいくつかいる場合に発生する可能性があります。

次の画面に、キャンペーン **[!UICONTROL Field mappings]**標準スキーマの各フィールドに対して新しいマッピングを作成できるセクションを示します。

![](assets/aep_fieldmappings.png)

このボ **[!UICONTROL Create new field mapping]**タンを使用すると、「Campaign Standard」フィールドと、XDMスキーマ内の対応するフィールドパス式を選択できます。

「キャンペーン標準」フィールドが見つからない場合は、検索フィールドを使用してフィールドを検索できます。 現在、検索は階層で開いているフィールドに対してのみ機能します。

![](assets/aep_mapfield.png)

Campaign Standardで定義された拡張リソースは、すべてのネイティブフィールドに「いいね！」されてマッピングされます。 XDMの_customer/default拡張子に定義されます。

![](assets/aep_fieldscusmapping.png)

APIを使用してXDM拡張機能をカスタマイズし、独自の拡張機能を定義すると、マッピングをより細かく制御できます。

XDM APIにつ [いて詳しくは](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/tutorials/schema_registry_api_tutorial/schema_registry_api_tutorial.md) 、「Schema Registry API tutorial」を参照してください。

列挙フィールドをマッピングするには、式エディターを使用して、XDM値に対応する各列挙値を定義する必要があります。 例えば、postalAdressフィールドを次のように定義する必要があります。

![](assets/aep_enummapping.png)

XDM値がXDMスキーマの列挙として定義されている場合は、lif構文を自動的に置き換えるネイティブEXDM関数を使用で **きます** 。

![](assets/aep_enummappingexdm.png)

XDMマッピングを編集するには、XDMマッピングを開き、必要な情報を変更して保存します。

>[!IMPORTANT]
>
>ここでは、セクションの値を編集し、フィールドの外側をクリ **[!UICONTROL Field mappings]**ックした場合、ボタンをクリックするまで変更はインターフェイスに表示され**[!UICONTROL Save]** ません。 この動作は、ページ上での編集が最初の編集で **[!UICONTROL Field Mappings]**ある場合に1回だけ発生します。

![](assets/aep_editmapping.png)
