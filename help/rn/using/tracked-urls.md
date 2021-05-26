---
solution: Campaign Standard
product: campaign
title: トラッキングする URL の署名に関する問題
description: トラッキングする URL の署名に関する問題
hidefromtoc: true
hide: true
source-git-commit: 65c81f2f9e4fc80e7b2f7c0bdc0302e90f068b1e
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 100%

---


# トラッキングする URL の署名に関する問題 {#tracked-urls}

直近の変更が行われた後、Adobe Campaign から送信されたトラッキング対象 URL が機能しない可能性があります。一部の企業で使用されている特定のセキュリティツールは、リンクに影響を与え、URL 署名メカニズムを変更する可能性があるので、一部のメールボックスは他のメールボックスよりも大きな影響を受ける可能性があります。

そのため、トラッキングリンクの署名メカニズムを無効にすることになりました。 この手順では、すべてのトラッキングリンクを修正します。

購読解除リンクは他のリンクと同様に失敗する可能性があります。その頻度はホストにより異なりますが、1％未満です。

**影響の有無**

電子メール内のトラッキングリンクの署名メカニズムが [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020)（2020 年 10 月）で導入され、すべての顧客に対してデフォルトで有効になっているので、一部の Campaign Standard ユーザーは影響を受けます。

**更新方法**

アドビでは、近日中にお客様と協力して設定を更新いたします。アップグレードスケジュールを記載した E メール通知が届く予定です。

**どのような影響がありますか？**

メンテナンスには最大 25 分のダウンタイムが必要で、この間はすべての配信、トラッキングリンクおよび API 呼び出しが機能しません。

更新が完了すると、すべてのリンクが想定通りに動作します。

>[!NOTE]
>
>これらの変更点に関するご質問は、[アドビのサポート](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)にお問い合わせください。

