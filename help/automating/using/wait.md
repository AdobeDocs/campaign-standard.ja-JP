---
title: 待機
description: 待機アクティビティは、ワークフローの一部の実行を一時的に中断します。
page-status-flag: 非活性化の
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 自動化
content-type: 参照
topic-tags: 実行活動
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# 待機{#wait}

## 説明 {#description}

![](assets/wait.png)

アクティビティ **[!UICONTROL Wait]** は、ワークフローの一部を実行するのを一時的に中断します。 数秒から数か月の遅延の後にアウトバウンドトランジションをアクティブにし、その後に配置されたアクティビティを実行します。

## 使用状況 {#context-of-use}

アクティビテ **[!UICONTROL Wait]** ィは、実行中の2つのアクティビティの間で一定の時間を経過させるために使用されます。 例えば、電子メール配信アクティビティの数日後に待機する場合は、この期間に生成された開封数とクリック数を分析してから、フォローアップ操作（リマインダー電子メール、オーディエンスの作成など）を実行します。

## 設定 {#configuration}

1. アクティビティをワークフロー **[!UICONTROL Wait]** にドラッグ&amp;ドロップします。
1. アクティビティを選択し、表示されるクイックアクシ ![](assets/edit_darkgrey-24px.png) ョンのボタンを使用して開きます。
1. アクティビテ **[!UICONTROL Duration]** ィの受信遷移と送信遷移がアクティブ化されるまでの待機の時間を指定します。

   期間は手動で入力するか、フィールドで使用可能なセレクターを使用して選択できます。

   ![](assets/wait_duration.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 ：{#example}

次の例は、一般的な使用例 **[!UICONTROL Wait]** でのアクティビティを示しています。 イベントへの招待メールが送信されます。 送信後24時間後に、電子メール配信ログが分析され、最初の電子メールを受信したがサインアップしなかった人にリマインダー電子メールが送信されます。

ワークフローは次のとおりです。

![](assets/wait_example_workflow.png)

* 最初のターゲ **[!UICONTROL Query]** ットは、電子メールの招待状を送信するプロファイルです。
* が、選 **[!UICONTROL Email delivery]** 択したプロファイルに初めて招待を送信します。
* 24hの **[!UICONTROL Wait]** アクティビティは、招待が送信された時点とワークフローの残りの部分との間に一時停止を配置します。
* もう1つは、最初 **[!UICONTROL Query]** の電子メールを受信したが、内部の購読リンクをクリックしなかったプロファイルをターゲットにします。
* 別のメッセージ **[!UICONTROL Email delivery]** が、選択したユーザーに招待のリマインダーを送信します。

