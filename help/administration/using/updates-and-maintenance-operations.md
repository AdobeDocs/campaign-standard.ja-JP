---
title: アップデートとメンテナンス操作
description: Adobe Campaign サーバーの更新およびメンテナンス操作に関する情報です。
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 27%

---

# アップデートとメンテナンス操作{#updates-and-maintenance-operations}

メンテナンスのため、Adobe Campaign サーバーは毎日午前 6 時（サーバーのタイムゾーン）に再起動されます。 Adobeに問い合わせて、サーバー時刻を確認します。 この操作は自動的かつ透過的です。 ただし、再起動の直前にデータ処理操作を実行しないことをお勧めします。 例えば、再起動の前にワークフローを開始しないようにして、1 分後に開始するようにスケジュールします。

Adobeは、新しい機能の追加、機能強化および修正を加えることで、ソリューションを継続的に改善しています。 すべての Adobe Campaign Standard インスタンスは、新しいリリースのたびにアップグレードされます。アップグレードに必要なアクションはありません。 アップグレードは 2 段階でデプロイされます。まず、ステージング用インスタンスがアップグレードされて、お客様が新しい機能をテストしたり、必要に応じて設定を調整したりできるようになります。その後、実稼動インスタンスがアップグレードされます。 次のリリースがいつ行われるかを確認するには、[&#x200B; リリース計画 &#x200B;](https://helpx.adobe.com/jp/campaign/kb/acs-release-planning.html) を参照してください。 また、[&#x200B; 廃止される機能および削除された機能 &#x200B;](../../rn/using/deprecated-features.md) のリストも参照してください。
