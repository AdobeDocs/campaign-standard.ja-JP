---
title: マッピング定義
description: Experience Data Model(XDM)フィールドを使用してCampaign Standardフィールドをマッピングする方法について説明します。
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
source-git-commit: c2ed4b3c85ceef3b604a8f68d924c7e5d9fad900

---


# マッピング定義 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは、現在ベータ版です。この機能は、予告なく頻繁にアップデートされる場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 アドビカスタマーケアにお問い合わせの際は、アドビカスタマーケアにご連絡ください。

この節では、エクスペリエンスデータモデル(XDM)フィールドを使用してCampaign Standardフィールドをマッピングする方法を見つけ出します。

このタスクを実行するための前提条件は次のとおりです。

* インターフェイスを介した、またはXDMに関連付けられたREST APIを使用したXDMスキーマ定義
* XDMスキーマ定義に基づくデータセットの作成

1. / **[!UICONTROL Administration]** /に移動し、 **[!UICONTROL Development]** エントリ **[!UICONTROL Platform]****[!UICONTROL Data mappings]** を選択します。

1. 新しいXDMマッピング **[!UICONTROL Create]** を開始するには、をクリックします。

   ![](assets/aep_createmapping.png)

1. 必須フィールドに入力し、次を選択します。

   * a **ターゲティングディメンション**: これは、マッピングするCampaign Standardスキーマです
   * データ **セット**: これは、Adobe Experience PlatformのXDMスキーマに関連付けられたデータパッケージです。

>[!NOTE]
>
>バッチをリアルタイム顧客プロファイルまたはIDサービスに取り込むには、データセットをリアルタイム顧客プロファイル用に [有効にする必要があります](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)。
>
>選択したデータセットが既存のデータマッピングで既に使用されている場合は、Adobe Experience Platformでデータが上書きされる可能性があることを示す警告が表示されます。 これは、同じデータセットを使用するデータマッピングに一般的な受信者がある場合に発生する可能性があります。

次の画面に、Campaign Standardスキーマの各フィールドに対して新しいマッピングを作成できる **[!UICONTROL Field mappings]** 節を示します。

![](assets/aep_fieldmappings.png)

この **[!UICONTROL Create new field mapping]** ボタンを使用すると、XDMスキーマ内のCampaign Standardフィールドと対応するフィールドパス式を選択できます。

Campaign Standardフィールドが見つからない場合は、検索フィールドを使用してフィールドを検索できます。 現在、検索は、階層で開いているフィールドに対してのみ機能します。

![](assets/aep_mapfield.png)

Campaign Standardで定義された拡張リソースは、すべてのネイティブフィールドに「いいね！」されます。 XDMの_customer/default拡張子に定義されます。

![](assets/aep_fieldscusmapping.png)

APIを使用してXDM拡張機能をカスタマイズし、独自の拡張機能を定義すると、マッピングをより詳細に制御できます。

XDM APIについて詳しくは、 [スキーマレジストリAPIチュートリアル](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html) （英語）を参照してください。

定義済みリストフィールドをマッピングするには、式エディタを使用して、XDM値に対応する各定義済みリスト値を定義する必要があります。 例えば、postalAdressfieldを次のように定義する必要があります。

![](assets/aep_enummapping.png)

XDM値がXDMスキーマの定義済みリストとして定義されている場合は、lif **** 構文を自動的に置き換えるネイティブのEXDM関数を使用できます。

![](assets/aep_enummappingexdm.png)

XDMマッピングを編集するには、XDMマッピングを開き、必要な情報を変更して保存します。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>現時点では、セクション内の値を編集してからフィールドの外側をクリックすると、 **[!UICONTROL Field mappings]** ボタンをクリックするまで変更がインターフェイスに表示されません **[!UICONTROL Save]** 。 この動作は、ページ上の最初の編集が編集対象の場合 **[!UICONTROL Field Mappings]** に1回だけ発生します。
