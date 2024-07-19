---
title: データモデルの変更の監視
description: Adobe Campaign データモデルの診断方法を説明します。
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 8%

---

# データモデルの変更の監視{#monitoring-data-model-changes}

**[!UICONTROL Diagnosis]** メニューから、アプリケーションで生成された技術的なオブジェクトを表示して分析できます。

>[!NOTE]
>
>このメニューの画面は読み取り専用です。

![](assets/diagnostic.png)

次のタイプのオブジェクトを表示できます。

* データスキーマ
* Web ページ
* フィルター
* ナビゲーション
* コンポーネント
* バッチジョブ

リスト設定は次のように変更できます。

* 列の追加と削除を行うことができます。
* 列名を定義できます。
* リスト内の列の表示順序を定義できます。
* リスト内の値の並べ替え順を選択できます。

リストをフィルタリングできます。

* ネイティブデータスキーマ、web ページ、フィルターおよびナビゲーションオブジェクトを含めたり、除外したりできます。
* オブジェクトを名前で検索できます。
* バッチジョブは、ステータス、開始日、終了日でフィルタリングできます。

表示されたリストを、コンマ区切り値を使用して TXT 形式でダウンロードできます。

選択したオブジェクトの詳細を表示できます。

例えば、この機能を使用して、標準のフィルターのフィルター条件を表示できます。 次の例は、標準のフィルターのフィルター条件に対して表示されるコードを示しています。

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)