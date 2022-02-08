---
title: アップデートとメンテナンス操作
description: Adobe Campaignサーバーの更新およびメンテナンス操作に関する情報です。
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 43%

---

# アップデートとメンテナンス操作{#updates-and-maintenance-operations}

メンテナンスのために、Adobe Campaignサーバーは毎日午前 6 時（サーバータイムゾーン）に再起動されます。 Adobeに問い合わせて、サーバーの時刻を知らせます。 この操作は自動で透過的です。 ただし、再起動直前にデータ処理を実行しないことをお勧めします。 例えば、再起動前にワークフローを開始しないようにし、1 分後にワークフローを開始するようにスケジュールを設定します。

アドビでは、新しい機能、機能強化および修正を加えてソリューションを継続的に改善しています。すべての Adobe Campaign Standard インスタンスは、新しいリリースのたびにアップグレードされます。アップグレードに必要なアクションはありません。アップグレードは 2 段階でデプロイされます。まず、ステージング用インスタンスがアップグレードされて、お客様が新しい機能をテストしたり、必要に応じて設定を調整したりできるようになります。その後、本番用インスタンスがアップグレードされます。詳しくは、 [リリース計画](https://helpx.adobe.com/jp/campaign/kb/acs-release-planning.html) をクリックして、次のリリースがいつおこなわれるかを確認します。 また、 [廃止および削除された機能](../../rn/using/deprecated-features.md).
