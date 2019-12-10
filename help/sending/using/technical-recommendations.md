---
title: Adobe Campaign Standardの配信品質に関する技術的な推奨事項
description: Adobe Campaign Standardでの配信品質を向上させるための技術的な推奨事項をご覧ください。
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# 技術的な推奨事項{#technical-recommendations}

さらに、配信品質を向上させるために使用できる技術、設定、ツールのいくつかを以下に示します。

主な技術用語の定義を以下に示します。

**DNSの逆引き** Adobe Campaignは、IPアドレスに逆引きDNSが与えられているかどうか、およびIPを正しく指しているかどうかを確認します。

**MXルール** MXルールは、キャンペーンMTA(Message Transfer Agent)が個々の電子メールドメインまたはISP（例：hotmail.com、comcast.net）に電子メールを送信する速度を制御するために使用します。 これらの規則は、通常、ISPが発行する制限に基づいています（例えば、各SMTP接続につき20個を超えるメッセージを含めないでください）。

**TLS** TLS(Transport Layer Security)は、2つの電子メールサーバー間の接続を保護し、電子メールのコンテンツが意図した受信者以外の誰かに読まれないように保護するために使用できる暗号化プロトコルです。

**SPF** SPF(Sender Policy Framework)は、ドメインの所有者が、そのドメインに代わって電子メールを送信できる電子メールサーバを指定できる電子メール認証標準です。 この標準では、電子メールの「Return-Path」ヘッダー（「Envelope From」アドレスとも呼ばれる）内のドメインが使用されます。

**DKIM** DKIM(Domain Keys Identified Mail)認証はSPFの後継機能で、公開鍵暗号化を使用して、受信電子メールサーバーが、送信元であると主張する個人またはエンティティによってメッセージが実際に送信されたこと、および最初に送信された時刻（およびDKIM「署名済み」）から受信時刻までに変更された。 この標準では、通常、「送信者」ヘッダーまたは「送信者」ヘッダーにドメインが使用されます。

**DMARC** DMARC(Domain-based Message Authentication, Reporting and Conformance)は、最新の電子メール認証方式で、電子メールの受け渡しまたは失敗を判断する際に、SPFとDKIMの両方の認証を利用します。 DMARCは、非常に重要な2つの点でユニークで強力です。
* 準拠 — 送信者は、認証に失敗したメッセージに対して何を行うか（例えば、受け入れない）をISPに指示できます。
* レポート — DMARC認証に失敗したすべてのメッセージを示す詳細なレポートと、各メッセージに使用される「From」ドメインとIPアドレスが送信者に提供されます。 これにより、認証に失敗し、ある種の「修正」が必要な正規の電子メール（SPFレコードへのIPアドレスの追加など）や、電子メールドメインでのフィッシング詐欺の発生元と発生率を特定できます。

DMARCは、250 OKで生成されたレポートを活用できます。

**SMTP** SMTP (Simple mail transfer protocol)は、電子メール送信のインターネット標準です。

**専用IPアドビは**、評判を確立し、配信パフォーマンスを最適化するために、各顧客に専用のIP戦略を提供します。
