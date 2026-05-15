---
title: Adobe Campaign Standardでの配信品質の問題のトラブルシューティング
description: Adobe Campaign Standardで配信品質の問題が発生した場合の対処方法について説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
TQID: https://experienceleague.adobe.com/UyKD0H4ffjVDfJRubitjN0pJs2DQbswTlOPNzvU6zLo
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: a39dbcf0-89cb-4765-9bcb-cf9dfbe2875f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 475
ht-degree: 57%

---

# トラブルシューティング{#troubleshooting}

配信品質で問題が発生した場合は、 以下のソリューションを参照してください。

## ISP に対する同じエラーメッセージ {#same-error-for-an-isp}

**特定の ISP でいつも同じエラーメッセージが表示されるのはなぜですか。**

ある ISP でいつも同じエラーメッセージが表示される場合、メールまたは IP が ISP で誤って検出されている可能性があります。 次のレコメンデーションを実行します。

* 受け取っているエラーの多くが、存在しないメールアドレス（**不明なユーザー**&#x200B;エラー）に関連するものかどうかを確認します。
* 入力したドメイン名のエラーを検出するために、購読フォームを更新します（例：gmaul.com または yaho.com）。
* メッセージがスパムであることを宣言していることを示すエラーの場合、または、メッセージが常にブロックされていることを示すエラーの場合、過去 12 ヶ月間にメッセージを開封またはクリックしていない受信者をターゲットから除外してみます。

問題が解決されない場合は、商用または配信品質サービス、あるいは Adobe Campaign サポートにお問い合わせください。

## ブロックリストと強制隔離の比較 {#denylist-versus-quarantine}

* **メール アドレスと強制隔離されたメール アドレスの違いは何ですか？**

   * ステータス **[!UICONTROL On denylist]**&#x200B;は、[ フィードバックループ ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ja#feedback-loops)の結果です（ユーザーがメッセージをスパムとして報告した場合）。

   * ステータス **[!UICONTROL Quarantined]**&#x200B;は、ソフトバウンスまたはハードバウンスの結果です。

  詳しくは、[こちらの節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)を参照してください。

* **様々な強制隔離エラーの原因は何を意味しますか。**

  考えられる10の理由は次のとおりです。未定義、ユーザー不明、無効なドメイン、アドレス、拒否、エラー無視、到達不能、アカウントが無効、メールボックスがいっぱいで、接続されていません。

  詳しくは、[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)を参照してください。

## ブロックリストからの削除 {#removing-from-denylist}

* **受信者の1人が誤ってメールブロックリストに追加されました。 メッセージの送信を再開できるように、メールをメールブロックリストから削除する方法を教えてください。**

   * **[!UICONTROL Administration > Channels > Quarantines > Addresses]**&#x200B;に移動します。
   * 対応するレコードの詳細で、**[!UICONTROL Status]** フィールドの値を&#x200B;**[!UICONTROL Valid]**&#x200B;に設定します。
   * レコードを保存します。

* **自分のIP アドレスがオンラインかどうかを確認するにはどうすればよいですか？ IP をブロックリストから削除する方法を教えてください。**

  IP アドレスがブロックリスト上にあるかどうかを確認するには、さまざまなweb サイトを使用して次のように確認できます。
   * [MX ツールボックス](https://mxtoolbox.com/)
   * [IP アドレスを教えてください](https://whatismyipaddress.com)

  一般に、IP アドレスチェックの結果は、IP アドレスをブロックしたWeb サイトの名前と共に、ブロックリストの詳細を含むリストを返します。

  対応するリンクをクリックすると、Web サイトの詳細にアクセスできます。

  次に、IP アドレスがブロックリストに登録された Web サイトのリストから Web サイトを削除するようリクエストできます。

  >[!NOTE]
  >
  >リストからの削除のプロセスは、Web サイトによって異なります。 サイトによって、アカウントの作成が必要な場合や、IP アドレスを指定するだけの場合があります。
