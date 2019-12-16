---
title: Adobe Campaign Standardでの配信品質の問題のトラブルシューティング
description: Adobe Campaign Standardで配信品質の問題が発生した場合の対処方法を説明します。
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
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# トラブルシューティング{#troubleshooting}

配信品質で問題が発生した場合は、以下の解決策を参照してください。

**特定の ISP でいつも同じエラーメッセージが表示されるのはなぜですか。**

ある ISP でいつも同じエラーメッセージが表示される場合、E メールまたは IP が ISP で誤って検出されている可能性があります。次の推奨事項を実行します。
* 受け取っているエラーの多くが、存在しない E メールアドレス（**不明なユーザー**&#x200B;エラー）に関連するものかどうかを確認します。
* 入力したドメイン名のエラーを検出するために、購読フォームを更新します（例：gmaul.com または yaho.com）。
* メッセージがスパムであることを宣言していることを示すエラーの場合、または、メッセージが常にブロックされていることを示すエラーの場合、過去 12 ヶ月間にメッセージを開封またはクリックしていない受信者をターゲットから除外してみます。

問題が解決されない場合は、商用または配信品質サービス、あるいは Adobe Campaign サポートにお問い合わせください。

**ブラックリストに登録された E メールアドレスと強制隔離 E メールアドレスの違いについて教えてください。**

The status **[!UICONTROL Blacklisted]** is a result of a feedback loop (when a person reports a message as spam).

The status **[!UICONTROL Quarantined]** is a result of a soft or hard bounce.

**様々な強制隔離エラーの原因は何を意味しますか。**

次の 10 個の原因が考えられます。未定義、不明なユーザー、無効なドメイン、ブラックリストに登録されたアドレス、拒否、無視されたエラー、未到達、無効なアカウント、メールボックス容量超過、未接続。

詳しくは、「検疫管理につ [いて」を参照してください](../../sending/using/understanding-quarantine-management.md)。

**受信者の 1 人が誤ってブラックリストに登録されました。メッセージの送信を再開できるように、ブラックリスト登録を解除するにはどうすればよいですか。**

* 移動 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
* In the details of the corresponding record, set the value of the **[!UICONTROL Status]** field to **[!UICONTROL Valid]**.
* レコードを保存します。

**IP のいずれかがブラックリストに登録されているかどうかを確認するにはどうすればよいですか。IP のブラックリスト登録を解除するにはどうすればよいですか。**

IP アドレスがブラックリストに登録されているかどうかを確認するには、以下のような様々な Web サイトを使用して検証できます。
* https://mxtoolbox.com/
* https://whatismyipaddress.com/blacklist-check
* http://www.blacklistalert.org/

一般に、IPアドレスのチェックの結果は、ブラックリストの詳細と、そのIPアドレスをブラックリストに記載したWebサイトの名前を含むリストを返します。

リンクをクリックすると、Webサイトの詳細にアクセスできます。

次に、IP アドレスがブラックリストに登録された Web サイトのリストから Web サイトを削除するようリクエストできます。

リストからの削除のプロセスは、Web サイトによって異なります。サイトによって、アカウントの作成が必要な場合や、IP アドレスを指定するだけの場合があります。
