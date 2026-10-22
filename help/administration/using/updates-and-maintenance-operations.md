---
title: アップデートとメンテナンス操作
description: Adobe Campaign サーバーの更新およびメンテナンス操作に関する情報。
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
TQID: 'https://experienceleague.adobe.com/aWpRR9r5jK3vVHxO9-xFPrVSyTI9Cg2rIBJ6AzvEONQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: 7f0a1ee5-eeb8-5478-a9cd-b1896f033118
    internal-label: Instance Settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 33%
---
# アップデートとメンテナンス操作{#updates-and-maintenance-operations}

メンテナンスの目的で、Adobe Campaign サーバーは毎日午前6時（サーバーのタイムゾーン）に再起動されます。 サーバー時間については、Adobeにお問い合わせください。 この操作は自動で透明です。 ただし、再起動前にデータ処理操作を実行しないことをお勧めします。 例えば、再起動前にワークフローを開始しないようにし、1分後に開始するようにスケジュールします。

Adobeでは、新しい機能の追加、機能強化、修正により、ソリューションを継続的に改善しています。 すべての Adobe Campaign Standard インスタンスは、新しいリリースのたびにアップグレードされます。 アップグレードに必要なアクションはありません。 アップグレードは 2 段階でデプロイされます。 まず、ステージング用インスタンスがアップグレードされて、お客様が新しい機能をテストしたり、必要に応じて設定を調整したりできるようになります。 その後、実稼動インスタンスがアップグレードされます。 次のリリースがいつ発生するかを確認するには、[ リリース計画](https://helpx.adobe.com/jp/campaign/kb/acs-release-planning.html)を参照してください。 また、[非推奨の機能と削除された機能](../../rn/using/deprecated-features.md)の一覧も参照してください。
