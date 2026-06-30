---
title: トラッキングする URL の署名に関する問題
description: トラッキングする URL の署名に関する問題
hide: true
exl-id: 8c2725a8-2c3a-448a-8c04-c0c2a5950574
TQID: https://experienceleague.adobe.com/6R8s1OkdU0TWD2Qo1DnI33T-FsiV4kVNkn942k0o5-Q
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 77a1b72042c178fd56fefb639aba2674d85c9caa
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 100%

---

# トラッキングする URL の署名に関する問題 {#tracked-urls}

直近の変更が行われた後、Adobe Campaign から送信されたトラッキング対象 URL が機能しない可能性があります。 一部の企業で使用されている特定のセキュリティツールは、リンクに影響を与え、URL 署名メカニズムを変更する可能性があるので、一部のメールボックスは他のメールボックスよりも大きな影響を受ける可能性があります。

そのため、トラッキングリンクの署名メカニズムを無効にすることになりました。 この手順では、すべてのトラッキングリンクを修正します。

購読解除リンクは他のリンクと同様に失敗する可能性があります。その頻度はホストにより異なりますが、1％未満です。

**影響の有無**

電子メール内のトラッキングリンクの署名メカニズムが [Campaign Standard 20.4](release-notes-2020.md#release-20-4-october-2020)（2020 年 10 月）で導入され、すべての顧客に対してデフォルトで有効になっているので、一部の Campaign Standard ユーザーは影響を受けます。

**更新方法**

アドビでは、近日中にお客様と協力して設定を更新いたします。 アップグレードタイムラインを記載したメール通知が届く予定です。

**どのような影響がありますか？**

メンテナンスには最大 25 分のダウンタイムが必要で、この間はすべての配信、トラッキングリンクおよび API 呼び出しが機能しません。

更新が完了すると、すべてのリンクが想定通りに動作します。

>[!NOTE]
>
>これらの変更点に関するご質問は、[アドビのサポート](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)にお問い合わせください。
>


