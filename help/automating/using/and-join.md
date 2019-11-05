---
title: AND 結合
description: AND結合アクティビティを使用すると、ワークフローの複数の実行ブランチを同期できます。
page-status-flag: 非活性化の
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59b383ca
context-tags: andjoin,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# AND 結合{#and-join}

## 説明 {#description}

![](assets/and_join.png)

アクティビティ **[!UICONTROL AND-join]** を使用すると、ワークフローの複数の実行ブランチを同期できます。

## 使用状況 {#context-of-use}

アクティビティ **[!UICONTROL AND-join]** は、すべてのインバウンドトランジションがアクティブ化される（つまり、前のアクティビティがすべて完了する）と、アウトバウンドトランジションをトリガーするだけです。

## 設定 {#configuration}

1. クエリーなどの複数のアクティビティをワークフローにドロップし、少なくとも2つの異なる実行ブランチを形成します。
1. アクティビティをワークフロー **[!UICONTROL AND-join]** にドラッグ&amp;ドロップします。
1. 同期する2つの異なるブランチの後に接続します。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. アウトバウンドトランジションに保持するメインセットを選択します。 セットを選択しない場合、アクティビティからランダムな母集団が送信されます。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、アクティビティに結合される前の2つのワークフローブランチを示し **[!UICONTROL AND-join]** ています。 ファイルの抽出は、アクティビティの3つの受信遷移が有効な場合にのみ **[!UICONTROL AND-join]** 行われます。

![](assets/wkf_and-join_example.png)

