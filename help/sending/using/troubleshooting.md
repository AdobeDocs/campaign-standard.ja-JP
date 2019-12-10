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
source-git-commit: b2df5ca4d38e35f57815924ffbe0313dc1a22b29

---


# トラブルシューティング{#troubleshooting}

配信品質に問題が発生しているか。 解決策はここで見つかるかもしれません…

**特定のISPに対して、常に同じエラーメッセージが表示されるのはなぜですか。**

ISPに対して常に同じエラーメッセージが表示される場合は、ISPによって電子メールまたはIPが障害として検出された可能性があります。 次の推奨事項を実行します。
* 存在しない電子メールアドレスにリンクされたエラーの大きな割合を受け取ったかどうかを確認します(**ユーザ不明** 、エラー)。
* 入力したドメイン名のエラーを検出するには、購読フォームを更新します(例：gmaul.comまたはyaho.com)。
* メッセージがスパムとして宣言されている、またはメッセージが常にブロックされているというエラーが発生した場合は、ターゲットから12か月間にメッセージの1つを開いていない、またはクリックしていない受信者を除外してみてください。

問題が解決しない場合は、商用または配信品質サービス、またはAdobe Campaignサポートにお問い合わせください。

**ブラックリストに記載された電子メールアドレスと検疫済みの電子メールアドレスの違いは何ですか。**

ステータス **[!UICONTROL Blacklisted]** は、フィードバックループ（ユーザーがメッセージをスパムとして報告した場合）の結果です。

ステータス **[!UICONTROL Quarantined]** は、ソフトバウンスまたはハードバウンスの結果です。

**異なる検疫エラーの理由は何を意味していますか？**

考えられる理由は次の10つです。未定義、ユーザー不明、無効なドメイン、ブラックリストに記載されたアドレス、拒否、エラー無視、到達不能、アカウント無効、メールボックスがいっぱい、接続されていません。

詳しくは、「検疫管理につ [いて」を参照してください](../../sending/using/understanding-quarantine-management.md)。

**私の受信者の1人が誤ってブラックリストに載っていました。 再度メッセージを送信できるように、ブラックリストを解除する方法を教えてください。**

* 移動 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
* 対応するレコードの詳細で、フィールドの値をに設 **[!UICONTROL Status]** 定します **[!UICONTROL Valid]**。
* レコードを保存します。

**IPの1つがブラックリストに記載されているかどうかを調べるにはどうしたらよいですか。 IPをブラックリストから削除する方法を教えてください。**

IPアドレスがブラックリストに記載されているかどうかを確認するには、様々なWebサイトを使用して確認します。
* http://mxtoolbox.com/
* http://whatismyipaddress.com/blacklist-check
* http://www.blacklistalert.org/

一般に、IPアドレスのチェックの結果は、ブラックリストの詳細と、そのIPアドレスをブラックリストに記載したWebサイトの名前を含むリストを返します。

リンクをクリックすると、Webサイトの詳細にアクセスできます。

その後、IPアドレスをブラックリストに記載したWebサイトのリストからWebサイトのリストを削除するように要求できます。

配信プロセスはWebサイトによって異なる場合があります。 一部のサイトではアカウントの作成が必要ですが、IPアドレスの入力が必要なサイトもあります。
