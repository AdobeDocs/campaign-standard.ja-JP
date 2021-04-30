---
solution: Campaign Standard
product: campaign
title: トラッキングされる URL の署名の問題
description: トラッキングされる URL の署名の問題
translation-type: tm+mt
source-git-commit: 830c003e36cec41e5cf480f66812900312609e9f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 59%

---


# トラッキングされる URL の署名の問題 {#tracked-urls}

最近の変更に続いて、キャンペーンが送信した追跡対象URLが失敗する場合があります。 一部の会社が使用している特定のセキュリティツールでは、リンクに影響を与え、URL 署名のメカニズムを変更する可能性があるため、一部のメールボックスは他のメールボックスよりも影響を受ける可能性が高くなります。

その結果、Adobeはリンクの追跡に使用する署名のメカニズムを無効にすることにしました。 この手順では、すべてのトラッキングリンクを修正します。

購読解除リンクは他のリンクと同様に失敗する可能性があります。その頻度はホストにより異なりますが、1％未満です。

**影響の有無**

電子メールのリンクを追跡する際の署名メカニズムとして、Campaign Standardユーザーの中には、[Campaign Standard20.4](release-notes-2020.md#release-20-4---october-2020) - 2020年10月に導入された署名メカニズムの影響を受けるものもあります。この機能は、すべての顧客に対してデフォルトで有効です。

**更新方法**

近日中に設定を更新するため、Adobeがご協力いたします。 アップグレードのタイムラインに関する電子メール通知が届きます。

**どのような影響がありますか？**

メンテナンスには最大 25 分のダウンタイムが必要で、この間はすべての配信、トラッキングリンクおよび API 呼び出しが機能しません。

更新が完了すると、すべてのリンクが想定通りに動作します。

>[!NOTE]
>
>これらの変更点に関するご質問は、[アドビのサポート](https://helpx.adobe.com/jp/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html)にお問い合わせください。

