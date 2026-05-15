---
title: 待機
description: 「Wait」アクティビティは、ワークフローの一部の実行を一時的に中断します。
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: wait,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2ddc1b2b-0df5-4c91-a381-451cc094f2eb
TQID: https://experienceleague.adobe.com/PnbExucfP9-JLJA-0krFYAkYXJYExhHxEl7TRu5efec
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 98%

---

# 待機{#wait}

## 説明 {#description}

![](assets/wait.png)

「**[!UICONTROL Wait]**」アクティビティは、ワークフローの一部の実行を一時的に中断します。 数秒から数ヶ月の遅延の後に、アウトバウンドトランジションがアクティブになり、その後、指定されたアクティビティが実行されます。

## Context of use {#context-of-use}

「**[!UICONTROL Wait]**」アクティビティは、実行する 2 つのアクティビティ間に一定の時間間隔を設定するために使用します。 例えば、メール配信アクティビティを実行したあと数日間待機し、この期間中に発生した開封数とクリック数を分析してから、フォローアップ操作（リマインダーメール、オーディエンスの作成など）を実行します。

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Wait]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. アクティビティのインバウンドトランジションからアウトバウンドトランジションがアクティブ化されるまでの待機時間（**[!UICONTROL Duration]**）を指定します。

   この期間は手動で入力するか、フィールド内のセレクターを使用して入力できます。

   ![](assets/wait_duration.png)

1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

以下に、「**[!UICONTROL Wait]**」アクティビティの一般的なユースケースを示します。 イベントへの招待メールを送信します。 送信後 24 時間が経過すると、メール配信ログが分析され、最初のメールを受信したものの登録しなかった人に対してリマインダーメールが送信されます。

ワークフローは次のとおりです。

![](assets/wait_example_workflow.png)

* 最初の「**[!UICONTROL Query]**」アクティビティでは、招待メールを送信するプロファイルをターゲットにします。
* 「**[!UICONTROL Email delivery]**」では、選択したプロファイルに対して最初の招待メールを送信します。
* 24 時間の「**[!UICONTROL Wait]**」アクティビティにより、招待メールが送信された後、その他のワークフローを実行するまで一定の時間を空けます。
* 2 つ目の「**[!UICONTROL Query]**」では、最初のメールを受信したものの記載されているサブスクリプションリンクをクリックしなかったプロファイルをターゲットに指定します。
* 2 つ目の「**[!UICONTROL Email delivery]**」では、選択したオーディエンスにリマインダー E メールを送信します。
