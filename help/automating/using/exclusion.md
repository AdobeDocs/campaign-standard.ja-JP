---
title: 除外
description: 「除外」アクティビティでは、特定の条件に従って、ある母集団から要素を除外することができます。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: exclusion,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: dccb9545-0d7e-4d40-9a8f-2915b4da99a7
TQID: 'https://experienceleague.adobe.com/46Q9UK-l1t1bBo9PZiasUxF2nqbLs7luEzqOJt7PU1k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 98%
---
# 除外{#exclusion}

## 説明 {#description}

![](assets/exclusion.png)

［**[!UICONTROL Exclusion]**］アクティビティでは、特定の条件に従って、ある母集団から要素を除外することができます。

## Context of use {#context-of-use}

「**[!UICONTROL Exclusion]**」アクティビティは基本的に、インバウンドトランジションの母集団に対して追加のフィルタリングを適用する場合に使用します。

プライマリセットは、インバウンドトランジションの中から定義します。 これ以外のインバウンドトランジションのメンバーは、プライマリセットから除外されます。 「除外」アクティビティのアウトバウンドトランジションには、他のインバウンドトランジションで検出されなかったプライマリセットのメンバーのみが含まれます。

## 設定 {#configuration}

1. ワークフローに「**[!UICONTROL Exclusion]**」アクティビティをドラッグ＆ドロップします。
1. アクティビティを選択し、表示されるクイックアクションの ![](assets/edit_darkgrey-24px.png) ボタンを使用して開きます。
1. インバウンドトランジションから&#x200B;**[!UICONTROL Primary set]**&#x200B;を選択します。 これは、要素の除外元のセットです。 これ以外のセットは、プライマリセットから除外する前の要素に一致します。

   >[!NOTE]
   >
   >インバウンドトランジションには、母集団と同じタイプの要素が存在しなければなりません。 例えば、プライマリセットにテストプロファイルが含まれている場合、これ以外のトランジションにもテストプロファイルが含まれていなければなりません。

1. 必要に応じて、アクティビティの[トランジション](../../automating/using/activity-properties.md)を管理して、アウトバウンド母集団の詳細設定オプションにアクセスします。
1. アクティビティの設定を確認し、ワークフローを保存します。

## 例 {#example}

年齢が 18～27 歳で無効なメールアドレスを持っているプロファイルを Adobe Campaign データベースからフィルターするように設定した 2 つのクエリアクティビティの例を以下に示します。 以降、メールアドレスが無効なプロファイルが、最初のセットから除外されます。 これにより、メールの送信といった操作ができるようになります。

![](assets/wkf_exclusion_example.png)
