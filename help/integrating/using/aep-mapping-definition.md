---
title: マッピングの定義
description: エクスペリエンスデータモデル (XDM) フィールドを使用してCampaign Standardフィールドをマッピングする方法について説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# マッピングの定義 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector は現在ベータ版です。通知なしに頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure 上でホストされている必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

この節では、エクスペリエンスデータモデル (XDM) フィールドを使用してCampaign Standardフィールドをマッピングする方法について説明します。

このタスクを実行するための前提条件は次のとおりです。

* インターフェイスを介した、または XDM に関連付けられた REST API を使用した XDM スキーマ定義
* XDM スキーマ定義に基づくデータセットの作成

1. に移動します。 **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** を選択し、 **[!UICONTROL Data mappings]** エントリ。

1. クリック： **[!UICONTROL Create]** をクリックして、新しい XDM マッピングを開始します。

   ![](assets/aep_createmapping.png)

1. 必須フィールドに入力し、次を選択します。

   * a **ターゲティングディメンション**：マッピングするCampaign Standardスキーマです。
   * a **データセット**:Adobe Experience Platformの XDM スキーマに関連付けられたデータパッケージです。

>[!NOTE]
>
>バッチをリアルタイム顧客プロファイルまたは ID サービスに取り込むには、データセットを [リアルタイム顧客プロファイルに対して有効](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html).
>
>選択したデータセットが既存のデータマッピングで既に使用されている場合は、Adobe Experience Platformでデータが上書きされる可能性があることを知らせる警告が表示されます。 この問題は、同じデータセットを使用するデータマッピングに、一部の一般的な受信者がある場合に発生する可能性があります。

次の画面に、 **[!UICONTROL Field mappings]** 「 」セクションで、マッピングスキーマの各フィールドに対して新しいマッピングをCampaign Standardできます。

![](assets/aep_fieldmappings.png)

The **[!UICONTROL Create new field mapping]** ボタンを使用すると、「Campaign Standard」フィールドと、XDM スキーマ内の対応するフィールドパス式を選択できます。

Adobe Campaign Standardフィールドが見つからない場合は、検索フィールドを使用してフィールドを検索できます。 現在、階層で開いているフィールドに対してのみ検索が機能します。

![](assets/aep_mapfield.png)

「Campaign Standard」で定義された拡張リソースは、すべてのネイティブフィールドに「いいね！」されます。 これらは XDM の_customer/default 拡張に定義されます。

![](assets/aep_fieldscusmapping.png)

API を介して XDM 拡張機能をカスタマイズし、独自の拡張機能を定義して、マッピングをより適切に制御できます。

詳しくは、 [スキーマレジストリ API のチュートリアル](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) を参照してください。

列挙フィールドをマッピングするには、式エディターを使用して、XDM 値に対応する各列挙値を定義する必要があります。 例えば、postaladdress フィールドを次のように定義する必要があります。

![](assets/aep_enummapping.png)

XDM 値が XDM スキーマの列挙として定義されている場合、ネイティブの EXDM 関数を使用して、 **lif** 構文を使用します。

![](assets/aep_enummappingexdm.png)

XDM マッピングを編集するには、XDM マッピングを開き、必要な情報を変更して保存します。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>現時点では、 **[!UICONTROL Field mappings]** セクションで「 」をクリックしてから、「 」フィールドの外側をクリックすると、「 **[!UICONTROL Save]** 」ボタンをクリックします。 この動作は、編集時に 1 回だけ発生します。 **[!UICONTROL Field Mappings]** は、ページの最初の編集です。
