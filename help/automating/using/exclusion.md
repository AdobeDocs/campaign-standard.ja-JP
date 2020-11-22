---
solution: Campaign Standard
product: campaign
title: 除外
description: 「除外」アクティビティでは、特定の条件に従って、ある母集団から要素を除外することができます。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: exclusion,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 100%

---


# 除外{#exclusion}

## 説明 {#description}

![](assets/exclusion.png)

［**[!UICONTROL Exclusion]**］アクティビティでは、特定の条件に従って、ある母集団から要素を除外することができます。

## 使用状況 {#context-of-use}

「**[!UICONTROL Exclusion]**」アクティビティは基本的に、インバウンドトランジションの母集団に対して追加のフィルタリングを適用する場合に使用します。

プライマリセットは、インバウンドトランジションの中から定義します。これ以外のインバウンドトランジションのメンバーは、プライマリセットから除外されます。「除外」アクティビティのアウトバウンドトランジションには、他のインバウンドトランジションで検出されなかったプライマリセットのメンバーのみが含まれます。

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Exclusion]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. インバウンドトランジションから&#x200B;**[!UICONTROL Primary set]**&#x200B;を選択します。これは、要素の除外元のセットです。これ以外のセットは、プライマリセットから除外する前の要素に一致します。

   >[!NOTE]
   >
   >インバウンドトランジションには、母集団と同じタイプの要素が存在しなければなりません。例えば、プライマリセットにテストプロファイルが含まれている場合、これ以外のトランジションにもテストプロファイルが含まれていなければなりません。

1. 必要に応じて、アクティビティの[トランジション](../../automating/using/activity-properties.md)を管理して、アウトバウンド母集団の詳細設定オプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

年齢が 18～27 歳で無効な E メールアドレスを持っているプロファイルを Adobe Campaign データベースからフィルターするように設定した 2 つのクエリアクティビティの例を以下に示します。以降、E メールアドレスが無効なプロファイルが、最初のセットから除外されます。これにより、E メールの送信といった操作ができるようになります。

![](assets/wkf_exclusion_example.png)

