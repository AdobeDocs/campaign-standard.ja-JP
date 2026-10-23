---
title: 年齢層によるセグメント化
description: このページでは、年齢グループに応じたデータベースプロファイルのセグメント化を示します。 このワークフローの目的は、各年齢グループに対して特定のメールを送信することです。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
TQID: 'https://experienceleague.adobe.com/LkH1qmElMwEn6JGmUaWj7Qpv7arSvLAZixbfJYTi2NQ'
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
source-wordcount: '206'
ht-degree: 58%
---
# 年齢層によるセグメント化 {#segmentation-age-groups}

次の例は、年齢グループに応じたデータベースプロファイルのセグメント化を示しています。

このワークフローの目的は、各年齢グループに対して特定のメールを送信することです。 このワークフローがテストキャンペーンの一部であることを考慮し、各セグメントには、制限された代表的なオーディエンスを同時に使用するためにランダムに選択された最大 100 人のプロファイルのみを含めることができます。

![](assets/wkf_segment_example_4.png)

ワークフローは、次の要素で構成されています。

* ワークフローの実行日を指定する[&#x200B; スケジューラーアクティビティ &#x200B;](../../automating/using/segmentation.md)。
* 誕生日と電子メールアドレスが入力されたユーザーのプロファイルをターゲットにする[&#x200B; クエリ &#x200B;](../../automating/using/query.md) アクティビティ。
* 異なるアウトバウンドトランジションに分けられた3つのセグメントを作成する[&#x200B; セグメント &#x200B;](../../automating/using/segmentation.md) アクティビティ（18～25歳、26～32歳、32歳以上のプロファイル）。 セグメントは、次のパラメーターに従って定義されます。

  ![](assets/wkf_segment_example_3.png)

  * セグメントの年齢グループを定義する年齢に関するフィルター

    ![](assets/wkf_segment_new_segment.png)

  * **[!UICONTROL Maximum size]** の上限（100）にリンクされた **[!UICONTROL Random sampling]** タイプ制限

    ![](assets/wkf_segment_example_1.png)

* セグメントごとの[&#x200B; メール配信](../../automating/using/email-delivery.md) アクティビティ。
