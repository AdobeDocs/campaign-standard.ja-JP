---
solution: Campaign Standard
product: campaign
title: 年齢層別のセグメント化
description: このページでは、データベースプロファイルの年齢グループに基づくセグメント化を示します。 このワークフローの目的は、各年齢グループに対して特定の E メールを送信することです。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: ワークフロー
role: Data Architect
level: 中級
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 66%

---


# 年齢層別のセグメント化 {#segmentation-age-groups}

次の例は、年齢グループに基づくデータベースプロファイルのセグメント化を示しています。

このワークフローの目的は、各年齢グループに対して特定の E メールを送信することです。このワークフローがテストキャンペーンの一部であることを考慮し、各セグメントには、制限された代表的なオーディエンスを同時に使用するためにランダムに選択された最大 100 人のプロファイルのみを含めることができます。

![](assets/wkf_segment_example_4.png)

ワークフローは、次の要素で構成されています。

* ワークフローの実行日を指定する[スケジューラーアクティビティ](../../automating/using/segmentation.md)。
* 誕生日と電子メールアドレスが入力された人のターゲットプロファイルに対する[クエリ](../../automating/using/query.md)アクティビティ。
* [セグメント化](../../automating/using/segmentation.md)アクティビティを使用して、異なるアウトバウンドトランジションに分割された3つのセグメントを作成します。18-25歳、26-32歳、32歳以上のプロファイル。 セグメントは、次のパラメーターに従って定義されます。

   ![](assets/wkf_segment_example_3.png)

   * セグメントの年齢グループを定義する年齢に関するフィルター

      ![](assets/wkf_segment_new_segment.png)

   * **[!UICONTROL Maximum size]** の上限（100）にリンクされた **[!UICONTROL Random sampling]** タイプ制限

      ![](assets/wkf_segment_example_1.png)

* セグメントごとの[電子メール配信](../../automating/using/email-delivery.md)アクティビティ。
