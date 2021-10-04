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
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# マッピングの定義 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector は現在ベータ版です。予告なく頻繁に更新される可能性があります。 お客様は、これらの機能にアクセスするには、Azure でホストする必要があります（現在、北米ではベータ版のみ）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

この節では、エクスペリエンスデータモデル (XDM) フィールドにCampaign Standardフィールドをマッピングする方法を説明します。

このタスクを実行するための前提条件は次のとおりです。

* インターフェイスを介した、または XDM に関連付けられた REST API を使用した XDM スキーマ定義
* XDM スキーマ定義に基づくデータセットの作成

1. **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** に移動し、**[!UICONTROL Data mappings]** エントリを選択します。

1. **[!UICONTROL Create]** をクリックして、新しい XDM マッピングを開始します。

   ![](assets/aep_createmapping.png)

1. 必須フィールドに入力し、次を選択します。

   * **ターゲティングディメンション**:マッピングするCampaign Standardスキーマです。
   * **dataset**:これは、Adobe Experience Platformの XDM スキーマに関連付けられたデータパッケージです。

>[!NOTE]
>
>バッチをリアルタイム顧客プロファイルまたは ID サービスに取り込むには、データセットがリアルタイム顧客プロファイル ](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html) に対して有効になっている必要があります。[
>
>選択したデータセットが既存のデータマッピングで既に使用されている場合は、Adobe Experience Platformでデータが上書きされる可能性があることを知らせる警告が表示されます。 この問題は、同じデータセットを使用するデータマッピングに、一部の一般的な受信者が存在する場合に発生する可能性があります。

次の画面は、Campaign Standardスキーマ内の各フィールドに対して新しいマッピングを作成できる **[!UICONTROL Field mappings]** セクションを示しています。

![](assets/aep_fieldmappings.png)

「**[!UICONTROL Create new field mapping]**」ボタンを使用すると、Campaign Standardフィールドと、XDM スキーマ内の対応するフィールドパス式を選択できます。

Adobe Campaign Standardフィールドが見つからない場合は、検索フィールドを使用してフィールドを検索できます。 現在、検索は階層で開いているフィールドに対してのみ機能します。

![](assets/aep_mapfield.png)

「Campaign Standard」で定義された拡張リソースは、すべてのネイティブフィールドに「いいね！」されます。 これらは XDM の_customer/default 拡張で定義されます。

![](assets/aep_fieldscusmapping.png)

API を使用して XDM 拡張機能をカスタマイズし、独自の拡張機能を定義すると、マッピングをより適切に制御できます。

XDM API について詳しくは、[ スキーマレジストリ API のチュートリアル ](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) を参照してください。

列挙フィールドをマッピングするには、式エディターを使用して、XDM 値に対応する各列挙値を定義する必要があります。 例えば、 postaladdress フィールドは次のように定義する必要があります。

![](assets/aep_enummapping.png)

XDM 値が XDM スキーマの列挙として定義されている場合は、ネイティブの EXDM 関数を使用して、**lif** 構文を自動的に置き換えることができます。

![](assets/aep_enummappingexdm.png)

XDM マッピングを編集するには、マッピングを開き、必要な情報を変更して保存します。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>現時点では、**[!UICONTROL Field mappings]** セクションの値を編集し、フィールドの外側をクリックした場合、**[!UICONTROL Save]** ボタンをクリックするまで変更はインターフェイスに表示されません。 この動作は、**[!UICONTROL Field Mappings]** の編集がページの最初の編集である場合に 1 回だけ発生します。
