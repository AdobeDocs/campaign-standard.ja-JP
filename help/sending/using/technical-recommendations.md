---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard向けの配信品質に関する技術推奨事項
description: Adobe Campaign Standardでの配信品質を向上させるための技術的な推奨事項をご覧ください。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 技術的な推奨事項{#technical-recommendations}

配信品質を向上させるために使用できるテクニック、設定、ツールのいくつかを以下に示します。次に、主な技術用語の定義をいくつか示します。

**リバース DNS**：Adobe Campaign は、IP アドレスにリバース DNS が指定されているかどうか、およびこれが IP を正しく指しているかどうかを確認します。

**MX ルール**&#x200B;は、Campaign MTA（メール転送エージェント）が E メールを個々の E メールドメインまたは ISP（例：hotmail.com、comcast.net）に送信する速度を制御するために使用されます。これらのルールは、通常、ISP によって公開された制限（例：各 SMTP 接続あたり 20 を超えるメッセージを含めない）に基づいています。

**TLS**（トランスポート層セキュリティ）は、暗号化プロトコルで、2 つの E メールサーバー間の接続を保護したり、E メールのコンテンツを保護して意図された受信者以外によって読まれないようにするために使用できます。

**SPF**（Sender Policy Framework）は、E メール認証標準で、ドメインの所有者がドメインの代わりに E メールを送信できる E メールサーバーを指定できます。この標準は、E メールの「Return-Path」ヘッダー（「Envelope From」アドレスとも呼ばれる）のドメインを使用します。

**DKIM**（Domain Keys Identified Mail）認証は、SPF の後継で、公開鍵暗号化を使用します。受信 E メールサーバーは、送信したと主張する個人または法人によってメッセージが実際に送信されたか、およびメッセージコンテンツが最初に送信された（および DKIM が「署名された」）ときと受信時で変更されているかどうかを検証できます。この標準は、通常、「From」または「Sender」ヘッダーのドメインを使用します。

**DMARC**（Domain-based Message Authentication, Reporting and Conformance）は、最新の E メール認証です。SPF と DKIM 認証の両方に基づいて E メールの合否を判定します。DMARC は以下の 2 つの点においてユニークで強力な認証方法です。
* 適合性 - 送信者は、認証に失敗したすべてのメッセージをどのように処理するか（「承諾しない」など）について ISP に指示できます。
* レポート - DMARC 認証に失敗したすべてのメッセージを、それぞれに使用された「From」ドメインおよび IP アドレスと共に詳細なレポートを送信者に提供します。これにより、認証に失敗し、ある種の「修正」（IP アドレスの SPF レコードへの追加など）が必要な正当な E メールを、その E メールドメインのフィッシング攻撃のソースおよび横行率と共に識別できます。

DMARC は、250ok が生成したレポートを活用できます。

**SMTP**（Simple Mail Transfer Protocol）は、E メール送信のインターネット標準です。

**専用IP**:Adobeは、評判を確立し、配信パフォーマンスを最適化するために、各顧客に専用のIP戦略を提供し、ランプアップIPを提供します。
