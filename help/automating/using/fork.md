---
title: 分岐
description: Forkアクティビティを使用すると、複数のアクティビティを同時に開始するアウトバウンド遷移を作成できます。
page-status-flag: 非活性化の
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: fork,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 分岐{#fork}

## 説明 {#description}

![](assets/fork.png)

アクテ **[!UICONTROL Fork]** ィビティを使用すると、複数のアクティビティを同時に開始するアウトバウンド遷移を作成できます。

## 使用状況 {#context-of-use}

アクティビテ **[!UICONTROL Fork]** ィを使用すると、同じワークフロー内で個別に複数の異なるアクティビティを実行できます。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Fork]** にドラッグ&amp;ドロップします。
1. クエリーなど、その前の他のアクティビティに接続します。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. アウトバウンド遷移の数を作成、削除または複製して指定します。 また、名前とラベルを属性に付けることもできます。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、Adobe Campaignデータベースからのプロファイルをターゲットにする2つのクエリアクティビティの共通部分を示しています。この場合、パリ在住の女性です。 したがって、フォークアクティビティでは、複数のアクティビティを同時に使用できます。1つはオーディエンスを保存して計算された訪問者を記憶し、もう1つは訪問者をセグメント化して各セグメントに対してターゲットコンテンツを含む2つの異なる電子メールを送信する方法です。 最初のメールは18歳から40歳のパリの女性と40歳以上のパリの女性を対象に送られます。

![](assets/wkf_fork_example.png)

