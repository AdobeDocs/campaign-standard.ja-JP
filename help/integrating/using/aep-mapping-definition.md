---
title: マッピングの定義
description: エクスペリエンスデータモデル(XDM)フィールドにCampaign Standardフィールドをマッピングする方法について説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# マッピングの定義 {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは現在ベータ版です。通知なしに頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

この節では、エクスペリエンスデータモデル(XDM)フィールドにCampaign Standardフィールドをマッピングする方法を説明します。

このタスクを実行するための前提条件は次のとおりです。

* インターフェイスを介した、またはXDMに関連付けられたREST APIを使用したXDMスキーマ定義
* XDMスキーマ定義に基づくデータセットの作成

1. **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]**&#x200B;に移動し、**[!UICONTROL Data mappings]**&#x200B;エントリを選択します。

1. **[!UICONTROL Create]**&#x200B;をクリックして、新しいXDMマッピングを開始します。

   ![](assets/aep_createmapping.png)

1. 必須フィールドに入力し、次を選択します。

   * **ターゲティングディメンション**:これは、マッピングするCampaign Standardスキーマです。
   * **dataset**:これは、Adobe Experience PlatformのXDMスキーマに関連付けられたデータパッケージです。

>[!NOTE]
>
>バッチをリアルタイム顧客プロファイルまたはIDサービスに取り込むには、データセットをリアルタイム顧客プロファイルに対して[有効](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html)にする必要があります。
>
>選択したデータセットが既存のデータマッピングで既に使用されている場合は、Adobe Experience Platformでデータが上書きされる可能性があることを示す警告が表示されます。 この問題は、同じデータセットを使用するデータマッピングに、一部の一般的な受信者が存在する場合に発生する可能性があります。

次の画面に、Campaign Standardスキーマ内の各フィールドに対して新しいマッピングを作成できる&#x200B;**[!UICONTROL Field mappings]**&#x200B;セクションを示します。

![](assets/aep_fieldmappings.png)

「**[!UICONTROL Create new field mapping]**」ボタンを使用すると、Campaign Standardフィールドと、XDMスキーマ内の対応するフィールドパス式を選択できます。

Adobe Campaign Standardフィールドが見つからない場合は、検索フィールドを使用してフィールドを検索できます。 現在、検索は階層で開いているフィールドに対してのみ機能します。

![](assets/aep_mapfield.png)

「Campaign Standard」で定義された拡張リソースは、すべてのネイティブフィールドに「いいね！」されます。 これらはXDMの_customer/default拡張で定義されます。

![](assets/aep_fieldscusmapping.png)

APIを使用してXDM拡張機能をカスタマイズし、独自の拡張機能を定義すると、マッピングをより適切に制御できます。

XDM APIについて詳しくは、[スキーマレジストリAPIのチュートリアル](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html)を参照してください。

列挙フィールドをマッピングするには、式エディターを使用して、XDM値に対応する各列挙値を定義する必要があります。 例えば、postalAdressfieldを次のように定義する必要があります。

![](assets/aep_enummapping.png)

XDM値がXDMスキーマの列挙として定義されている場合は、ネイティブのEXDM関数を使用して、**lif**&#x200B;構文を自動的に置き換えることができます。

![](assets/aep_enummappingexdm.png)

XDMマッピングを編集するには、XDMマッピングを開き、必要な情報を変更して保存します。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>現時点では、**[!UICONTROL Field mappings]**&#x200B;セクションの値を編集し、フィールドの外側をクリックした場合、**[!UICONTROL Save]**&#x200B;ボタンをクリックするまで変更はインターフェイスに表示されません。 この動作は、**[!UICONTROL Field Mappings]**&#x200B;の編集がページの最初の編集である場合に1回だけ発生します。
