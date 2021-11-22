---
title: 年齢層によるセグメント化
description: このページでは、年齢グループに応じたデータベースプロファイルのセグメント化について説明します。 このワークフローの目的は、各年齢グループに対して特定の E メールを送信することです。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---

# 年齢層によるセグメント化 {#segmentation-age-groups}

次の例は、年齢グループに基づくデータベースプロファイルのセグメント化を示しています。

このワークフローの目的は、各年齢グループに対して特定の E メールを送信することです。このワークフローがテストキャンペーンの一部であることを考慮し、各セグメントには、制限された代表的なオーディエンスを同時に使用するためにランダムに選択された最大 100 人のプロファイルのみを含めることができます。

![](assets/wkf_segment_example_4.png)

ワークフローは、次の要素で構成されています。

* A [スケジューラーアクティビティ](../../automating/using/segmentation.md) をクリックして、ワークフローの実行日を指定します。
* A [クエリ](../../automating/using/query.md) 「 」アクティビティを使用して、誕生日と E メールアドレスが入力されたユーザーのプロファイルをターゲット設定します。
* A [セグメント化](../../automating/using/segmentation.md) アクティビティを使用して、異なるアウトバウンドトランジションに分割された 3 つのセグメントを作成します。18-25-year歳、26-32-year歳、32 歳を超えるプロファイル。 セグメントは、次のパラメーターに従って定義されます。

   ![](assets/wkf_segment_example_3.png)

   * セグメントの年齢グループを定義する年齢に関するフィルター

      ![](assets/wkf_segment_new_segment.png)

   * **[!UICONTROL Maximum size]** の上限（100）にリンクされた **[!UICONTROL Random sampling]** タイプ制限

      ![](assets/wkf_segment_example_1.png)

* An [E メール配信](../../automating/using/email-delivery.md) セグメントごとのアクティビティ。
