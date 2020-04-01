---
title: Adobe Campaign Standardを使用した新しいプラットフォームの起動
description: Adobe Campaign StandardでドメインとIPアドレスの評判を維持しながら、新しいプラットフォームを設定する方法を説明します。
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
source-git-commit: f83cf866f1c9fa53687e6cee26306d33327bd822

---


# 新しいプラットフォームの開始{#starting-new-platform}

ドメインおよび IP アドレスのレピュテーションの維持は、必要不可欠です。新しいプラットフォームを設定する際のアドバイスを以下に示します。

新しいプラットフォームでの E メール送信の開始は、（この目的で IP の送信に使用されていない場合）プラットフォームに使用履歴がなく、レピュテーションがないので、繊細な手順になります。ISP は、当然ながら、E メールを送信するのに使用したことがなく、突然、大量の E メールトラフィックを送信し始める IP アドレスを疑います。実際には、スパム送信者は通常、「不明な」IP アドレス（つまり、ブラックリストに記載されていないアドレス）を使用して、検出前に可能な限り大量のメッセージを送信します。

本番フェーズの初期の出力では、運用速度に達することは期待できません。さらに、ISP によって送信アドレスがブロックされ、残りの開始フェーズに大きく影響することになるので、このままでメッセージを送信しようとしてはいけません。

プラットフォームの開始は、多くの場合、アドレスのリストを初めて使用するときや、アドレスが完全修飾でない可能性があるときに発生します。無効なアドレスまたはハニーポットアドレスに送信すると、プラットフォームのレピュテーション低下の一因となります。
* 無効なアドレスのリストがある場合は、最初に送信する前に強制隔離テーブル(> >**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]****[!UICONTROL Addresses]**)にインポートすることが最善の方法です。 For more on this, see this [section](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* 同様に、無効なアドレスを再評価する場合は、時間と共に不適切なアドレスの使用を減らすために、プラットフォームのレピュテーションが確立されたらおこない、少しずつ時間をかけて再評価することを強くお勧めします。

開始時に従うべき原則を以下にまとめます。
* **アドビから送信される電子メールキャンペーンに固有の** 、専用のサブドメインをアドビに委任します。
* **無効な/非アクティブなアドレスを強制隔離テーブルにインポートします** （この情報がある場合）。
* **配信のスループット** (技術的な設定：一致件数の制限を参照)。
* **送信するボリュームを順に増やす**:ターゲット全体を開始から送信するのではなく、送信のたびにリストの一部を追加します。 これにより、各手順でボリュームを増やし、無効なアドレスの全体的な割合を減らすことができます。
* **定期的にメッセージを送信**:小さな写真を散発的に送るよりも、定期的に送る方が、ある程度までは良いキャンペーンだ。
* **詳細な監視配信レポート**:エラーインジケーターが高い場合は、技術設定が正しく設定されていないことを示しています。
