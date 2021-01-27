---
solution: Campaign Standard
product: campaign
title: セグメントビルダーの使用
description: セグメントビルダーを使用してオーディエンスを作成する方法を説明します。
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 4%

---


# セグメントビルダーの使用 {#using-the-segment-builder}

>[!IMPORTANT]
>
>オーディエンス宛先サービスは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

セグメントビルダーを使用すると、[リアルタイム顧客プロファイル](https://docs.adobe.com/content/help/ja-JP/experience-platform/profile/home.html)からのデータに基づいてルールを定義することで、オーディエンスを作成できます。

このセクションでは、セグメントを作成する際のグローバルな概念について説明します。 セグメントビルダー自体の詳細については、『[セグメントビルダーユーザーガイド](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)』を参照してください。

セグメントビルダーのインターフェイスは、次のように構成されています。

* 左側のパネルには、必要なフィールドをセグメントビルダーワークスペースにドラッグ&amp;ドロップして、セグメントを作成するために使用できるすべての属性、イベントおよびオーディエンスが表示されます。
* 中央の領域は、使用可能なフィールドからルールを定義し、組み合わせてセグメントを作成するワークスペースです。
* ヘッダーと右側のペインには、セグメントのプロパティ(セグメントの名前、説明、および見積もり修飾プロファイルなど)が表示されます。

![](assets/aep_audiences_interface.png)

## セグメントの作成

セグメントを作成するには、次の手順に従います。

セグメントビルダーがワークスペースに表示されます。 これにより、最終的にオーディエンスの作成に使用されるAdobe Experience Platformのデータを使用してセグメントを作成できます。

1. セグメントに名前を付け、説明を入力します（オプション）。

   ![](assets/aep_audiences_creation_edit_name.png)

1. 設定ウィンドウで目的の結合ポリシーが選択されていることを確認します。

   結合ポリシーの詳細については、[セグメントビルダーユーザーガイド](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)の専用の節を参照してください。

   ![](assets/aep_audiences_mergepolicy.png)

1. 左側のペインで目的のフィールドを探し、中央のワークスペースにドラッグします。

   ![](assets/aep_audiences_dragfield.png)

1. ドラッグしたフィールドに対応するルールを設定します。

   ![](assets/aep_audiences_configure_rules.png)

1. 「**[!UICONTROL Create segment]**」ボタンをクリックします。

## セグメントに適したフィールドの検索

左側のペインには、ルールの作成に使用できるすべての属性、イベント、オーディエンスがリストされます。

表示されるフィールドは、会社によってキャプチャされた属性で、[エクスペリエンスデータモデル(XDM)システム](https://docs.adobe.com/content/help/ja-JP/experience-platform/xdm/home.html)を通じて利用できます。

フィールドは、次のタブに分類されます。

* **[!UICONTROL Attributes]**:Adobe CampaignデータベースまたはAdobe Experience Platform、あるいはその両方から作成できる既存のプロファイル属性。プロファイルに付属する静的な情報(電子メールアドレス、住所の国、忠誠度プログラムのステータスなど)を参照します。

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:「2週間に2回注文した顧客」など、会社の顧客のタッチポイントと何らかのインタラクションを持つ顧客を識別するアクティビティ。これは、Adobe Analyticsからストリーミングされたり、サードパーティのETLツールを使用して直接Adobe Experience Platformに取り込まれたりできます。

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**複数エンティティ** セグメント化により、プロファイル、店舗、または他のプロファイル以外のクラスに基づく追加のデータを使用して、製品データを拡張できます。接続すると、追加のクラスのデータは、プロファイルスキーマにネイティブであるかのように使用可能になります。
>
>詳しくは、[該当するドキュメント](https://docs.adobe.com/content/help/en/experience-platform/segmentation/multi-entity-segmentation.html)を参照してください。

デフォルトでは、セグメントビルダーには、既にデータが存在するフィールドが表示されます。 データが存在しないフィールドを含む完全なスキーマを表示するには、設定から&#x200B;**[!UICONTROL Show full XDM schema]**&#x200B;オプションを有効にします。

![](assets/aep_audiences_populatedfields.png)

各フィールドの末尾の記号は、属性とその使用方法に関する追加情報を提供します。

![](assets/aep_audiences_isymbol.png)

## セグメントのルールの定義

>[!NOTE]
>
>以下の節では、ルール定義に関するグローバル情報を示します。 詳しくは、[セグメントビルダーユーザーガイド](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)を参照してください。

ルールを作成するには、次の手順に従います。

1. ルールの基となる属性やイベントを反映した左側のペインのフィールドを探します。

1. フィールドを中央のワークスペースにドラッグし、目的のセグメント定義に従って設定します。 これを行うには、文字列関数と日付/時間関数がいくつか使用できます。

   次の例では、ルールは性別が「男性」に等しいすべてのプロファイルをターゲットします。

   ![](assets/aep_audiences_malegender.png)

   セグメントに対応する推定母集団は、**[!UICONTROL Segment Properties]**&#x200B;セクションで自動的に再計算されます。

1. **[!UICONTROL View Profiles]**&#x200B;ボタンをクリックすると、ルールに対応する最初の20件のレコードのプレビューが表示され、セグメントをすばやく検証できます。

   ![](assets/aep_audiences_samplepreview.png)

   適切なプロファイルをターゲットするために、必要な数だけルールを追加できます。

   コンテナにルールを追加すると、AND論理演算子を持つ既存のルールに追加されます。 必要に応じて、論理演算子をクリックして変更します。

   ![](assets/aep_audiences_andoperator.png)

一度リンクすると、2つのルールがコンテナを形成します。

## フィールドの比較

セグメントビルダーを使用すると、2つのフィールドを比較して1つのルールを定義できます。 例えば、自宅の住所が職場の住所とは異なる郵便番号の女性など。

それをおこなうには、次の手順に従います。

1. 比較する最初のフィールド（自宅の住所の郵便番号など）を中央のワークスペースにドラッグします。

   ![](assets/aep_audiences_comparing_1.png)

1. 最初のフィールドと比較する2番目のフィールド（勤務先の住所の郵便番号など）を選択します。

   最初のフィールドと同じコンテナの中央のワークスペース（**[!UICONTROL Drop here to compare operands]**&#x200B;ボックス）にドラッグします。

   ![](assets/aep_audiences_comparing_2.png)

1. 必要に応じて、2つのフィールドの間に演算子を設定します。 この例では、勤務先住所とは異なる自宅住所を持つターゲットプロファイルにセグメントを提供します。

   ![](assets/aep_audiences_comparing_3.png)

これで、ルールが設定され、オーディエンスとしてアクティブ化できる状態になります。
