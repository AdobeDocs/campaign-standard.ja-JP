---
title: 重複排除
description: 重複排除 - 重複アクティビティでは、受信アクティビティの結果の重複を削除できます。
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 4%

---


# 重複排除{#deduplication}

## 説明 {#description}

![](assets/deduplication.png)

この **[!UICONTROL Deduplication]** アクティビティでは、受信アクティビティの結果の重複を削除できます。

## 使用状況 {#context-of-use}

この **[!UICONTROL Deduplication]** アクティビティは、通常、ターゲット設定アクティビティに従って、またはファイルを読み込んだ後、またはターゲット設定されたデータを使用できるアクティビティの前に使用されます。

重複排除 - 重複中、受信トランジションは別々に処理されます。 例えば、プロファイル1の結果にクエリAが存在し、クエリ2の結果にもAが存在する場合、重複は除外されません。

したがって、重複排除 - 重複が受信トランジションを1つだけ持つようにお勧めします。 これを行うには、和集合アクティビティ、交差点アクティビティなど、ターゲット設定のニーズに対応したアクティビティを使用して、様々なクエリを組み合わせます。 次に例を示します。

![](assets/dedup_bonnepratique.png)

**関連トピック**

* [使用例： 配信前の重複の識別](../../automating/using/identifying-duplicated-before-delivery.md)
* [使用例： 読み込んだファイルからのデータの重複を除外する](../../automating/using/deduplicating-data-imported-file.md)

## 設定 {#configuration}

重複排除 - 重複アクティビティを設定するには、ラベル、メソッド、重複排除 - 重複条件、および結果に関連するオプションを入力する必要があります。

1. ワークフローに **[!UICONTROL Deduplication]** アクティビティをドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。

   ![](assets/deduplication_1.png)

1. 重複排除 - 重複 **[!UICONTROL Resource type]** を実行する対象を選択します。

   * **[!UICONTROL Database resource]** データベースに既に存在するデータに対して重複排除 - 重複が実行される場合。 重複除外するデータ **[!UICONTROL Filtering dimension]** に応じて、と **[!UICONTROL Targeting dimension]**&#x200B;を選択します。 デフォルトでは、 **プロファイルで重複排除 - 重複が実行されます**。
   * **[!UICONTROL Temporary resource]** 重複排除 - 重複がワークフローの一時データで実行される場合： 重複除外するデータ **[!UICONTROL Targeted set]** を含むデータを選択します。 この使用例は、ファイルのインポート後、またはデータベース内のデータがリンチされた(例えば、セグメントコードで)場合に発生します。

1. を選択し **[!UICONTROL Number of unique records to keep]**&#x200B;ます。 このフィールドのデフォルト値は1です。 値0を指定すると、すべての重複を保持できます。

   例えば、レコードAとBがレコードYの重複と見なされ、レコードCがレコードZの重複と見なされる場合、次のように指定します。

   * フィールドの値が1の場合： YとZのレコードのみが保持されます。
   * フィールドの値が0の場合： すべてのレコードが保持されます。
   * フィールドの値が2の場合： A、B、Yのレコードは、C、Zのレコードを記録し、偶然、又はその後選択した重複排除 - 重複法に応じて2レコード保持する。

1. 指定したリストに条件を追加して、 **[!UICONTROL Duplicate identification]** 条件を定義します。 同じ値を使用して重複を識別できるフィールドや式を指定します。 電子メールアドレス、名、姓など 条件の順序によって、最初に処理する条件を指定できます。
1. ドロップダウンリストで、使用するアイテム **[!UICONTROL Deduplication method]** を選択します。

   * **[!UICONTROL Choose for me]**: 重複に含めないレコードをランダムに選択します。
   * **[!UICONTROL Following a list of values]**: 1つ以上のフィールドに値の優先度を定義できます。 優先度の値を定義するには、フィールドを選択するか式を作成し、適切なフィールドに値を追加します。To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: これにより、選択した式の値が空でないレコードを優先度として保持できます。

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: これにより、入力した式の値が最も小さいか大きいレコードを保持できます。

      ![](assets/deduplication_4.png)

1. 必要に応じて、アクティビティの [トランジションを管理し](../../automating/using/activity-properties.md) 、アウトバウンド母集団のアドバンスオプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。
