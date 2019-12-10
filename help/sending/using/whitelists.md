---
title: Adobe Campaign Standardのホワイトリスト
description: Adobe Campaign Standardでホワイトリストを最適化する方法を説明します。
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


# ホワイトリスト{#whitelists}

メインのインターネットサービスプロバイダ(ISP)およびウェブメールプロバイダは、認識された電子メールメッセージ送信者からのホワイトリストを管理します。 Adobe Campaignは、最適なホワイトリストの認定を受けるプロセスを支援します。

電子メールホワイトリストは、電子メールブロッキングプログラムがメッセージの受信を許可する電子メールアドレスまたはドメイン名のリストです。

ホワイトリストには2種類あります。
* 非商用ホワイトリスト
* 商用ホワイトリスト

## 非商用ホワイトリスト {#non-commercial-whitelists}

これらのホワイトリストに受け入れるには、送信者は、インフラストラクチャまたはそのアクティビティ（配信頻度、ボリューム、苦情数）の技術検証（電子メールサーバーはオープンリレーではなく、静的IPが必要）に基づいて、一連のテストに合格する必要があります。

送信者がこれらのルールのいずれにも従わない場合は、ホワイトリストから削除できます。 Adobe Campaignの電子メ **ール配信品質パッケージでは** 、Adobe Campaignは、非商用ホワイトリストの認定プロセスに関する付随的なエキスパートコンサルティングサービスを提供します。

## 商用ホワイトリスト {#commercial-whitelists}

商用ホワイトリストは、送信者がスパム対策フィルターを完全に回避したり、システムに入る際に増分ポイントを割り当てることを可能にするシステムに基づいています。 これらの支払いホワイトリスト（CPTまたは年間ベース）は、リターンパス送信者スコアなどのシステムによって提供されます。

ISPはこれらのサービスを無料で使用でき、ISPの数はホワイトリストによって異なります。 したがって、送信者は、配信保証を持ってメッセージを送信する際に、より確信を持つことができます。 一部のホワイトリストでは、画像を開いてリンクをアクティブにすることもできます。

ホワイトリストに表示されるアセットは、電子メールキャンペーンでは削除できません。 Adobe Campaignの **Eメール配信品質パッケージでは** 、CSAやリターンパス送信者スコアなどの商用ホワイトリスト認定サービスが提供されています。