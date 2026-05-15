---
title: データモデルの変更の監視
description: Adobe Campaign データモデルの診断方法について説明します。
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
TQID: https://experienceleague.adobe.com/XWMP0LlTRgqEJujGETPzVXOCUvkm-Q9OXC-RvaWd-58
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 202
ht-degree: 8%

---

# データモデルの変更の監視{#monitoring-data-model-changes}

**[!UICONTROL Diagnosis]** メニューから、アプリケーションによって生成されたテクニカル オブジェクトを分析するために表示できます。

>[!NOTE]
>
>このメニューの画面は読み取り専用です。

![](assets/diagnostic.png)

次の種類のオブジェクトを表示できます。

* データスキーマ
* Web ページ
* フィルター
* ナビゲーション
* コンポーネント
* バッチジョブ

リスト設定を変更できます。

* 列を追加したり削除したりできます。
* 列名を定義することもできます。
* リスト内の列の表示順序を定義できます。
* リスト内の値の並べ替え順序を選択できます。

リストをフィルタリングできます。

* ネイティブデータスキーマ、web ページ、フィルター、ナビゲーションオブジェクトを含めることも除外することもできます。
* 名前でオブジェクトを検索できます。
* ステータス、開始日、終了日でバッチジョブをフィルタリングできます。

コンマ区切りの値を含むTXT形式のファイルに表示されたリストをダウンロードできます。

選択したオブジェクトの詳細を表示できます。

例えば、この機能を使用して、標準のフィルターのフィルター条件を表示できます。 次の例は、標準フィルターのフィルター条件に表示されるコードを示しています。

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)