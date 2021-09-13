---
title: セグメントビルダーの使用
description: セグメントビルダーを使用してオーディエンスを作成する方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 9a6c542e-10ed-4e77-abb3-36324e1cb38f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 3%

---

# セグメントビルダーの使用 {#using-the-segment-builder}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

セグメントビルダーを使用すると、[リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)からのデータに基づいてルールを定義することで、オーディエンスを構築できます。

この節では、セグメントを作成する際のグローバルな概念について説明します。 セグメントビルダー自体について詳しくは、『[セグメントビルダーユーザガイド](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)』を参照してください。

セグメントビルダーのインターフェイスは、次のように構成されています。

* 左側のパネルには、目的のフィールドをセグメントビルダーのワークスペースにドラッグ&amp;ドロップすることで、セグメントの作成に使用できるすべての属性、イベントおよびオーディエンスが表示されます。
* 中央の領域には、使用可能なフィールドからルールを定義および組み合わせて、セグメントを作成するためのワークスペースが表示されます。
* ヘッダーと右側のパネルには、セグメントのプロパティ（名前、説明、セグメントの推定修飾プロファイル）が表示されます。

![](assets/aep_audiences_interface.png)

## セグメントの作成

セグメントを作成するには、次の手順に従います。

セグメントビルダーがワークスペースに表示されます。 これにより、Adobe Experience Platformのデータを使用してセグメントを構築し、最終的にオーディエンスの作成に使用できます。

1. セグメントに名前を付けて、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 設定パネルで目的の結合ポリシーが選択されていることを確認します。

   結合ポリシーの詳細については、『[セグメントビルダーユーザガイド](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)』の該当する節を参照してください。

   ![](assets/aep_audiences_mergepolicy.png)

1. 左側のパネルで目的のフィールドを探し、中央のワークスペースにドラッグします。

   ![](assets/aep_audiences_dragfield.png)

1. ドラッグしたフィールドに対応するルールを設定します。

   ![](assets/aep_audiences_configure_rules.png)

1. 「**[!UICONTROL Create segment]**」ボタンをクリックします。

## セグメントに適したフィールドの検索

左側のパネルには、ルールの作成に使用できるすべての属性、イベント、オーディエンスが一覧表示されます。

リストされるフィールドは、会社でキャプチャされた属性で、[エクスペリエンスデータモデル(XDM)システム](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html)を通じて使用できるようになっています。

フィールドはタブに整理されています。

* **[!UICONTROL Attributes]**:Adobe CampaignデータベースやAdobe Experience Platformから作成できる既存のプロファイル属性。プロファイルに添付される静的情報（例：Eメールアドレス、居住国、ロイヤルティプログラムステータスなど）を参照します。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:「2週間に2回注文した人」など、会社の顧客タッチポイントと何らかのインタラクションを持つ顧客を識別するアクティビティ。これは、Adobe Analyticsからストリーミングしたり、サードパーティのETLツールを使用してAdobe Experience Platformに直接取り込んだりできます。

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**複数エンティティのセ** グメント化を使用すると、製品、店舗、またはその他のプロファイル以外のクラスに基づいて、プロファイルデータを追加データで拡張できます。接続すると、追加のクラスのデータが、プロファイルスキーマ本来の方法と同じように使用可能になります。
>
>詳しくは、[該当するドキュメント](https://experienceleague.adobe.com/docs/experience-platform/segmentation/multi-entity-segmentation.html)を参照してください。

デフォルトでは、セグメントビルダーには、既にデータが存在するフィールドが表示されます。 データが存在しないフィールドを含む完全なスキーマを表示するには、設定で&#x200B;**[!UICONTROL Show full XDM schema]**&#x200B;オプションを有効にします。

![](assets/aep_audiences_populatedfields.png)

各フィールドの最後の記号は、属性とその使用方法に関する追加情報を提供します。

![](assets/aep_audiences_isymbol.png)

## セグメントのルールの定義

>[!NOTE]
>
>以下の節では、ルール定義に関する全体的な情報を示します。 詳しくは、『[セグメントビルダーユーザガイド](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html)』を参照してください。

ルールを作成するには、次の手順に従います。

1. ルールの基となる属性やイベントを反映するフィールドを左側のペインから探します。

1. フィールドを中央のワークスペースにドラッグし、目的のセグメント定義に従って設定します。 これをおこなうには、いくつかの文字列関数と日付/時間関数を使用できます。

   次の例では、ルールは、性別が「男性」に等しいすべてのプロファイルをターゲットにします。

   ![](assets/aep_audiences_malegender.png)

   セグメントに対応する推定母集団は、 **[!UICONTROL Segment Properties]**&#x200B;セクションで自動的に再計算されます。

1. 「**[!UICONTROL View Profiles]**」ボタンをクリックすると、ルールに対応する最初の20件のレコードのプレビューが表示され、セグメントをすばやく検証できます。

   ![](assets/aep_audiences_samplepreview.png)

   適切なプロファイルをターゲットにするために、必要な数のルールを追加できます。

   ルールをコンテナに追加する場合、AND論理演算子を使用する既存のルールに追加されます。 必要に応じて、論理演算子をクリックして変更します。

   ![](assets/aep_audiences_andoperator.png)

2つのルールをリンクすると、1つのコンテナが形成されます。

## フィールドの比較

セグメントビルダーを使用すると、2つのフィールドを比較して1つのルールを定義できます。 例えば、自宅住所が勤務先住所とは異なる郵便番号の女性。

次の手順に従います。

1. 比較する最初のフィールド（自宅住所の郵便番号など）を中央のワークスペースにドラッグします。

   ![](assets/aep_audiences_comparing_1.png)

1. 最初のフィールドと比較する2番目のフィールド（勤務先住所の郵便番号など）を選択します。

   中央のワークスペースの、最初のフィールドと同じコンテナ内の&#x200B;**[!UICONTROL Drop here to compare operands]**&#x200B;ボックスにドラッグします。

   ![](assets/aep_audiences_comparing_2.png)

1. 必要に応じて、2つのフィールド間の演算子を設定します。 この例では、セグメントで、勤務先住所とは異なる自宅住所を持つプロファイルをターゲティングします。

   ![](assets/aep_audiences_comparing_3.png)

これで、ルールが設定され、オーディエンスとしてアクティブ化できる状態になりました。
