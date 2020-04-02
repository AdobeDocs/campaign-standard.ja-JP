---
title: マッピング定義
description: エクスペリエンスデータモデル(XDM)フィールドを使用してCampaign Standardフィールドをマッピングする方法について説明します。
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
source-git-commit: 327d0e4f862b39c60fb3943d1128f4f42828bc0d

---


# マッピング定義 {#mapping-definition}

>[!IMPORTANT]
>
>Campaign Standardデータサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米の場合のみベータ版）。 ご利用になりたい場合は、アドビカスタマーケアにお問い合わせください。

この節では、エクスペリエンスデータモデル(XDM)フィールドを使用してCampaign Standardフィールドをマッピングする方法を見つけます。

このタスクを実行するには、前提条件を次に示します。

* インターフェイスを介したXDMスキーマ定義、またはXDMに関連付けられたREST APIを使用したXDM定義
* XDMデータセット定義に基づくスキーマ作成

1. //に移 **[!UICONTROL Administration]** 動し **[!UICONTROL Development]** 、エ **[!UICONTROL Platform]** ントリを選択し **[!UICONTROL Data mappings]** ます。

1. 新しいXDMマッピ **[!UICONTROL Create]** ングを開始するには、をクリックします。

   ![](assets/aep_createmapping.png)

1. 必須フィールドに入力し、次を選択します。

   * a **ターゲティングディメンション**:これは、マッピングするCampaign Standardスキーマです
   * データ **セット**:これは、Adobe Experience PlatformのXDMデータパッケージに関連付けられたスキーマです。

>[!NOTE]
>
>バッチをReal-time Customer CommentまたはIDサービスに取り込むには、データセットをReal-time Customer Commendationで有効に [する必要があります](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)。
>
>選択したデータセットが既に既存のデータマッピングで使用されている場合は、Adobe Experience Platformでデータが上書きされる可能性があることを示す警告が表示されます。 これは、同じデータセットを使用するDataMappingに一般的な受信者がある場合に発生する可能性があります。

次の画面に、Campaign Standardスキーマの各フ **[!UICONTROL Field mappings]** ィールドに対して新しいマッピングを作成できるセクションを示します。

![](assets/aep_fieldmappings.png)

このボ **[!UICONTROL Create new field mapping]** タンを使用すると、XDMCampaign Standard内の式フィールドと対応するフィールドパススキーマを選択できます。

検索フィールドが見つからない場合は、Campaign Standardフィールドを使用して検索できます。 現在、検索は、階層で開いているフィールドに対してのみ機能します。

![](assets/aep_mapfield.png)

Campaign Standardで定義された拡張リソースは、すべてのネイティブフィールドに対して「いいね！」が付けられます。 XDMの_customer/default拡張子に定義されます。

![](assets/aep_fieldscusmapping.png)

APIを使用してXDM拡張をカスタマイズし、独自の拡張を定義すると、マッピングをより細かく制御できます。

XDM APIについ [て詳しくは](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html) 、スキーマレジストリAPIチュートリアルを参照してください。

定義済みリストフィールドをマップするには、式エディターを使用して、XDM値に対応する各定義済みリスト値を定義する必要があります。 例えば、postalAdressfieldを次のように定義する必要があります。

![](assets/aep_enummapping.png)

XDM値がXDMスキーマの定義済みリストとして定義されている場合は、lif構文を自動的に置き換えるネイティブEXDM関数を使用で **きます** 。

![](assets/aep_enummappingexdm.png)

XDMマッピングを編集するには、XDMマッピングを開き、必要な情報を変更して保存します。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>現時点では、セクションの値を編集し、フィールドの外側をク **[!UICONTROL Field mappings]** リックした場合、ボタンをクリックするまで変更はインターフェイスに表示され **[!UICONTROL Save]** ません。 この動作は、ページ上の最初の編集時に1 **[!UICONTROL Field Mappings]** 回だけ発生します。
