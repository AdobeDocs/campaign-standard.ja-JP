---
title: 統合セグメントビルダーの使用
description: 統合セグメントビルダーを使用してオーディエンスを作成する方法について説明します。
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
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# 統合セグメントビルダーの使用 {#using-the-unified-segment-builder}

>[!IMPORTANT]
>
>Audience Destinationsサービスは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

統合セグメントビルダーを使用すると、Unified Profile Serviceからのデータに基づいてルールを定義することで、オーディエンス [を構築できます](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)。

このセクションでは、セグメントを作成する際のグローバル概念について説明します。 統合セグメントビルダー自体の詳細については、『セグメントビルダーユーザーガ [イド』を参照してください](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

統合セグメントビルダーのインターフェイスは、次のように構成されます。

* 左側のパネルには、目的のフィールドをセグメントビルダーワークスペースにドラッグ&amp;ドロップして、セグメントを構築するために使用できるすべての属性、イベントおよびオーディエンスが表示されます。
* 中央の領域は、使用可能なフィールドからルールを定義し、組み合わせてセグメントを作成するワークスペースです。
* ヘッダーと右側のペインには、セグメントのプロパティ（セグメントの名前、説明、および見積もり修飾プロファイル）が表示されます。

![](assets/aep_audiences_interface.png)

## セグメントの作成

セグメントを作成するには、次の手順に従います。

これで、統合セグメントビルダーがワークスペースに表示されます。 これにより、最終的にオーディエンスの作成に使用されるAdobe Experience Platformのデータを使用してセグメントを作成できます。

1. セグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 設定ウィンドウで目的の結合ポリシーが選択されていることを確認します。

   結合ポリシーの詳細については、『セグメントビルダーユーザーガイド』の専用 [の節を参照してください](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

   ![](assets/aep_audiences_mergepolicy.png)

1. 左ペインで目的のフィールドを探し、中央のワークスペースにドラッグします。

   ![](assets/aep_audiences_dragfield.png)

1. ドラッグしたフィールドに対応するルールを設定します。

   ![](assets/aep_audiences_configure_rules.png)

1. ボタンをクリッ **[!UICONTROL Create segment]**クします。

## セグメントの適切なフィールドの検索

左側のペインには、ルールの作成に使用できるすべての属性、イベントおよびオーディエンスが表示されます。

表示されるフィールドは、会社によってキャプチャされた属性で、 [Experience Data Model(XDM)Systemを通じて使用できるようになっています](https://www.adobe.io/apis/experienceplatform/home/xdm.html)。

フィールドはタブに整理されます。

* **[!UICONTROL Attributes]**:Adobe CampaignデータベースまたはAdobe Experience Platform、あるいはその両方から派生する既存のプロファイル属性。 プロファイルに添付された静的な情報（例：電子メールアドレス、居住国、忠誠度プログラムのステータスなど）を参照します。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:「2週間に2回注文した顧客」など、会社の顧客タッチポイントと何らかのインタラクションを持つ顧客を識別するアクティビティ。 これは、Adobe Analyticsからストリーミングしたり、サードパーティのETLツールを使用してAdobe Experience Platformに直接取り込んだりできます。

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**複数エンティティのセグメント化により** 、製品、ストア、または他の非プロファイルクラスに基づく追加のデータを使用して、プロファイルデータを拡張できます。 接続すると、追加のクラスのデータは、プロファイルスキーマにネイティブであるかのように使用可能になります。
>
>For more on this, refer to the [dedicated documentation](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/tutorials/segmentation/multi_entity_segmentation.md).

デフォルトでは、統合セグメントビルダーには、データが存在するフィールドが表示されます。 データが存在しないフィールドを含む完全なスキーマを表示するには、設定からこのオプ **[!UICONTROL Show full XDM schema]**ションを有効にします。

![](assets/aep_audiences_populatedfields.png)

各フィールドの末尾の記号は、属性とその使用方法に関する追加情報を提供します。

![](assets/aep_audiences_isymbol.png)

## セグメントのルールの定義

>[!NOTE]
>
>以下の節では、ルールの定義に関するグローバル情報を示します。 詳しくは、『セグメントビルダーユーザガイド』 [を参照してください](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)。

ルールを作成するには、次の手順に従います。

1. ルールの基となる属性やイベントを反映したフィールドを左ペインから探します。

1. フィールドを中央のワークスペースにドラッグし、目的のセグメント定義に従って設定します。 これを行うには、複数の文字列関数と日付/時間関数を使用できます。

   次の例では、「男性」に等しい性別を持つすべてのプロファイルがルールのターゲットになります。

   ![](assets/aep_audiences_malegender.png)

   セグメントに対応する推定母集団は、セクション内で自動的に再計算さ **[!UICONTROL Segment Properties]**れます。

1. このボ **[!UICONTROL View Profiles]**タンを使用すると、ルールに対応する最初の20件のレコードをプレビューでき、セグメントを迅速に検証できます。

   ![](assets/aep_audiences_samplepreview.png)

   適切なプロファイルをターゲットにするために、必要な数だけルールを追加できます。

   コンテナにルールを追加する場合、AND演算子を使用して既存のルールに追加されます。 演算子をクリックして、ORに変更するオプションにアクセスします。

   ![](assets/aep_audiences_andoperator.png)

リンクが完了すると、2つのルールでコンテナが形成されます。

## フィールドの比較

統合セグメントビルダーを使用すると、2つのフィールドを比較して、ルールを定義できます。 例えば、自宅の住所が勤務先の住所とは異なる郵便番号の女性。

それには、次の手順に従います。

1. 比較する最初のフィールド（自宅住所の郵便番号など）を中央のワークスペースにドラッグします。

   ![](assets/aep_audiences_comparing_1.png)

1. 最初のフィールドと比較する2番目のフィールド（勤務先住所の郵便番号など）を選択します。

   ボックス内の最初のフィールドと同じコンテナ内の中央のワークスペースにドラッグ **[!UICONTROL Drop here to compare operands]**します。

   ![](assets/aep_audiences_comparing_2.png)

1. 必要に応じて、2つのフィールド間の演算子を設定します。 この例では、セグメントで勤務先とは異なる自宅住所を持つプロファイルをターゲットにします。

   ![](assets/aep_audiences_comparing_3.png)

これで、ルールが設定され、オーディエンスとしてアクティブ化できる状態になりました。
