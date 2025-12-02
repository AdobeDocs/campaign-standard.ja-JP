---
title: マッピングの定義
description: Campaign Standard フィールドをエクスペリエンスデータモデル（XDM）フィールドにマッピングする方法について説明します。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# マッピングの定義 {#mapping-definition}

>[!IMPORTANT]
>
>現在、Adobe Experience Platform Data Connector はベータ版です。予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様を Azure でホストする必要があります（現在は北米向けのベータ版のみ）。 へのアクセスを希望する場合は、Adobe カスタマーケアにお問い合わせください。

この節では、Campaign Standard フィールドをエクスペリエンスデータモデル（XDM）フィールドにマッピングする方法について説明します。

このタスクを実行するには、次の前提条件があります。

* インターフェイスを介して、または XDM に関連付けられた REST API を使用して XDM スキーマを定義します
* XDM スキーマ定義に基づくデータセットの作成

1. **[!UICONTROL Administration]**/**[!UICONTROL Development]**/**[!UICONTROL Platform]** に移動し、**[!UICONTROL Data mappings]** エントリを選択します。

1. 「**[!UICONTROL Create]**」をクリックして、新しい XDM マッピングを開始します。

   ![](assets/aep_createmapping.png)

1. 必須フィールドに入力し、以下を選択します。

   * **ターゲティングディメンション**：これは、マッピングするCampaign Standard スキーマです
   * **データセット**：これは、Adobe Experience Platformの XDM スキーマに関連付けられたデータパッケージです。

>[!NOTE]
>
>バッチをリアルタイム顧客プロファイルまたは ID サービスに取り込むには、データセットを [&#x200B; リアルタイム顧客プロファイルに対して有効にする &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html) 必要があります。
>
>選択したデータセットが既存のデータマッピングで既に使用されている場合は、Adobe Experience Platformでデータが上書きされる可能性があることを知らせる警告が表示されます。 これは、同じデータセットを使用したデータマッピングに一般的な受信者が複数ある場合に発生する可能性があります。

次の画面では、Campaign Standard スキーマの各フィールドに対して新しいマッピングを作成できる、**[!UICONTROL Field mappings]** の節を示します。

![](assets/aep_fieldmappings.png)

「**[!UICONTROL Create new field mapping]**」ボタンを使用すると、Campaign Standard フィールドと、XDM スキーマ内の対応するフィールドパス式を選択できます。

Adobe Campaign Standard フィールドが見つからない場合は、検索フィールドを使用してフィールドを検索できます。 現在、検索は階層で開かれているフィールドに対してのみ機能します。

![](assets/aep_mapfield.png)

Campaign Standardで定義された拡張リソースは、すべてのネイティブフィールドと同様にマッピングされます。 これらは、XDM の_customer/default 拡張機能に定義されます。

![](assets/aep_fieldscusmapping.png)

API を介して XDM 拡張機能をカスタマイズし、独自の拡張機能を定義すると、マッピングをより詳細に制御できます。

XDM API について詳しくは、[&#x200B; スキーマレジストリ API チュートリアル &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) を参照してください。

列挙フィールドをマッピングするには、式エディターを使用して、XDM 値に対応する各列挙値を定義する必要があります。 例えば、postaladdressfield は、次のように定義する必要があります。

![](assets/aep_enummapping.png)

XDM 値が XDM スキーマの列挙として定義されている場合は、**lif** 構文を自動的に置き換えるネイティブの EXDM 関数を使用できます。

![](assets/aep_enummappingexdm.png)

XDM マッピングを編集するには、マッピングを開き、目的の情報を変更して保存します。

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>現時点では、「**[!UICONTROL Field mappings]**」セクションの値を編集してフィールドの外側をクリックしても、「**[!UICONTROL Save]**」ボタンをクリックするまで変更内容はインターフェイスに表示されません。 この動作は、ページ上で **[!UICONTROL Field Mappings]** の編集が最初の編集である場合に 1 回だけ発生します。
