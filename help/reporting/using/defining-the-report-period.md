---
title: レポート期間の定義
description: レポートの期間を使用すると、選択した日付に応じてデータをフィルターできます。
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 1fa05187-0488-4649-b903-079bfa4628f1
TQID: 'https://experienceleague.adobe.com/1ubxoguqhz9JzUE2T-H1wXGLDOCnSVaU1Tfo4dzex9w'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 95%
---
# レポート期間の定義{#defining-the-report-period}

>[!NOTE]
>
>データレポートは、過去3年間のみ利用できます。 データ保持期間について詳しくは、アドビコンサルタントまたは技術管理者にお問い合わせください。

レポートを開始またはレポートにアクセスする前に、期間を適用する必要があります。 指定された期間はレポートの右上に表示されます。

デフォルトでは、キャンペーンまたはプログラムの場合、フィルター期間はプログラムまたはキャンペーンの開始日と終了日に設定されます。 配信の場合、開始日は送信日に、終了日は送信日に 7日を加えた日付になります。

フィルターを変更するには、開始日と期間を選択するか、または事前に設定された期間（先週、2 か月前など）を使用します。

フィルターを適用または変更すると、レポートが自動的に更新されます。 選択したレポート期間によって管理されるのは、その期間内に作成された配信のデータセット全体ではなく、その期間内に発生したイベントです。例えば、配信が 1月1日から 5日まで行われ、レポート期間が 1月1日から 2日までの場合、部分的なデータが表示されることがあります。 開封やクリックは、配信から 1 か月後でも発生する可能性があるため、選択した期間が開封／クリックの数に影響を与える可能性があります。

![](assets/campaign_reports_5.png)
