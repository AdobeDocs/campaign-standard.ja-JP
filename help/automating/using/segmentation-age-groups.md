---
title: 年齢層によるセグメント化
description: このページでは、データベース・プロファイルのセグメント化を年齢グループ別に示します。 ワークフローの目的は、年齢グループごとに特定のメールを送信することです。
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
source-wordcount: '204'
ht-degree: 51%

---

# 年齢層によるセグメント化 {#segmentation-age-groups}

次の例は、データベースプロファイルを年齢層に応じてセグメント化する方法を示しています。

このワークフローの目的は、各年齢グループに対して特定のメールを送信することです。このワークフローがテストキャンペーンの一部であることを考慮し、各セグメントには、制限された代表的なオーディエンスを同時に使用するためにランダムに選択された最大 100 人のプロファイルのみを含めることができます。

![](assets/wkf_segment_example_4.png)

ワークフローは、次の要素で構成されています。

* ワークフローの実行日を指定する [&#x200B; スケジューラーアクティビティ &#x200B;](../../automating/using/segmentation.md)。
* 誕生日とメールアドレスが入力された人物のプロファイルをターゲットにする [&#x200B; クエリ &#x200B;](../../automating/using/query.md) アクティビティ。
* 3 つのセグメントを作成する [&#x200B; セグメント化 &#x200B;](../../automating/using/segmentation.md) アクティビティ。18～25 歳、26～32 歳のアウトバウンドトランジション、32 歳以上のプロファイルに分かれています。 セグメントは、次のパラメーターに従って定義されます。

  ![](assets/wkf_segment_example_3.png)

   * セグメントの年齢グループを定義する年齢に関するフィルター

     ![](assets/wkf_segment_new_segment.png)

   * **[!UICONTROL Maximum size]** の上限（100）にリンクされた **[!UICONTROL Random sampling]** タイプ制限

     ![](assets/wkf_segment_example_1.png)

* セグメントごとの [&#x200B; メール配信 &#x200B;](../../automating/using/email-delivery.md) アクティビティ。
