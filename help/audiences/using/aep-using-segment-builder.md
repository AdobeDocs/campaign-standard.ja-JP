---
title: 統合セグメントビルダーの使用
description: 統合セグメントビルダーを使用してセグメントを作成する方法についてオーディエンスします。
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 573131986d52bb4415cca59600048fd7dc5ba0db

---


# 統合セグメントビルダーの使用 {#using-the-unified-segment-builder}

>[!IMPORTANT]
>
>オーディエンスの宛先サービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米の場合のみベータ版）。 ご利用になりたい場合は、アドビカスタマーケアにお問い合わせください。

統合セグメントビルダーを使用すると、 [Unified Segment Serviceからのデータに基づいてルールを定義することで、オーディエンスを作成で](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)きます。

このセクションでは、セグメントを作成する際のグローバルな概念について説明します。 統合セグメントビルダー自体の詳細については、『セグメントビルダーユーザーガイド』 [を参照してください](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)。

統合セグメントビルダーのインターフェイスは、次のように構成されます。

* 左側のペインには、必要なフィールドをセグメントビルダーのワークスペースにドラッグ&amp;ドロップして、セグメントの作成に使用できるすべての属性、イベントおよびオーディエンスが表示されます。
* 中央の領域は、使用可能なフィールドからルールを定義し、組み合わせてセグメントを作成するワークスペースです。
* ヘッダーと右ペインには、セグメントのプロパティ(セグメントの名前、説明、および推定修飾プロファイル)が表示されます。

![](assets/aep_audiences_interface.png)

## セグメントの作成

セグメントを作成するには、次の手順に従います。

これで、統合セグメントビルダーがワークスペースに表示されます。 Adobe Experience Platformのデータを使用してセグメントを作成し、最終的にこのデータを使用してセグメントを作成できます。このデータは、最終的にオーディエンスの作成に使用されます。

1. セグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 設定ウィンドウで目的の結合ポリシーが選択されていることを確認します。

   結合ポリシーの詳細については、『セグメントビルダーユーザガイド』の専用の [節を参照してください](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)。

   ![](assets/aep_audiences_mergepolicy.png)

1. 左ペインで目的のフィールドを探し、中央のワークスペースにドラッグします。

   ![](assets/aep_audiences_dragfield.png)

1. ドラッグしたフィールドに対応するルールを設定します。

   ![](assets/aep_audiences_configure_rules.png)

1. ボタンをクリッ **[!UICONTROL Create segment]** クします。

## セグメントの適切なフィールドの検索

左側のペインには、ルールの作成に使用できるすべての属性、イベント、オーディエンスがリストされます。

表示されるフィールドは、会社によってキャプチャされ、 [Experience Data Model(XDM)Systemを通じて使用できるようになった属性です](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html)。

フィールドはタブに整理されています。

* **[!UICONTROL Attributes]**:既存のプロファイル属性。Adobe CampaignデータベースまたはAdobe Experience Platform、あるいはその両方から作成できます。 プロファイルに付属する静的な情報(例：電子メールアドレス、居住国、忠誠度のプログラムステータスなど)を参照します。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:「2週間に2回注文した顧客」など、会社の顧客タッチポイントと何らかのインタラクションを持つ顧客を識別するアクティビティ。 これは、Adobe Analyticsからストリーミングするか、サードパーティのETLツールを使用してAdobe Experience Platformに直接取り込むことができます。

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**複数エンティティのセグメント化** により、プロファイルデータを、製品、店舗、または他の非エンティティクラスに基づく追加のデータと共に拡張できます。 接続すると、追加のクラスのデータは、そのクラスのネイティブデータと同じようにプロファイルスキーマになります。
>
>For more on this, refer to the [dedicated documentation](https://docs.adobe.com/content/help/en/experience-platform/segmentation/multi-entity-segmentation.html).

デフォルトでは、統合セグメントビルダーには、既にデータが存在するフィールドが表示されます。 データが存在しないスキーマを含め、フルデータを表示するには、設定からこのオプ **[!UICONTROL Show full XDM schema]** ションを有効にします。

![](assets/aep_audiences_populatedfields.png)

各フィールドの末尾の記号は、属性とその使用方法に関する追加情報を提供します。

![](assets/aep_audiences_isymbol.png)

## セグメントのルールの定義

>[!NOTE]
>
>以下の節では、ルールの定義に関するグローバル情報を示します。 詳しくは、セグメントビルダーのユーザーガ [イドを参照してください](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)。

ルールを作成するには、次の手順に従います。

1. ルールの基になる属性やイベントを反映したフィールドを左ペインから探します。

1. フィールドを中央のワークスペースにドラッグし、目的のセグメント定義に従って設定します。 これを行うには、複数の文字列関数と日付/時間関数を使用できます。

   次の例では、「男性」に等しい性別を持つすべてのプロファイルがターゲットされます。

   ![](assets/aep_audiences_malegender.png)

   セグメントに対応する推定母集団は、セクション内で自動的に再計算さ **[!UICONTROL Segment Properties]** れます。

1. このボ **[!UICONTROL View Profiles]** タンを使用すると、ルールに対応する最初の20件のレコードのプレビューが表示され、セグメントを迅速に検証できます。

   ![](assets/aep_audiences_samplepreview.png)

   必要な数のルールを追加して、適切なルールをターゲットできます。

   ルールをコンテナに追加すると、AND論理演算子を持つ既存のルールに追加されます。 必要に応じて、論理演算子をクリックして変更します。

   ![](assets/aep_audiences_andoperator.png)

一度リンクすると、2つのルールが1つのコンテナです。

## フィールドの比較

統合セグメントビルダーを使用すると、2つのフィールドを比較して、ルールを定義できます。 例えば、自宅の住所が勤務先の住所とは異なる郵便番号の女性。

それには、次の手順に従います。

1. 比較する最初のフィールド（住所の郵便番号など）を中央のワークスペースにドラッグします。

   ![](assets/aep_audiences_comparing_1.png)

1. 最初のフィールドと比較する2番目のフィールド（勤務先住所の郵便番号など）を選択します。

   ボックス内の最初のフィールドと同じコンテナで、中央のワークスペースにドラッグ **[!UICONTROL Drop here to compare operands]** します。

   ![](assets/aep_audiences_comparing_2.png)

1. 必要に応じて、2つのフィールド間の演算子を設定します。 この例では、セグメントを勤務先住所とは異なる自宅住所を持つターゲットプロファイルに対して設定します。

   ![](assets/aep_audiences_comparing_3.png)

これで、ルールが設定され、アクティブ化の準備が整いました。オーディエンス。
