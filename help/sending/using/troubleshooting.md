---
title: Adobe Campaign Standardでの配信品質の問題のトラブルシューティング
description: Adobe Campaign Standardの配信品質の問題が発生した場合の対処方法について説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 55%

---

# トラブルシューティング{#troubleshooting}

配信品質で問題が発生した場合は、以下のソリューションを参照してください。

## ISP に対する同じエラーメッセージ {#same-error-for-an-isp}

**特定の ISP でいつも同じエラーメッセージが表示されるのはなぜですか。**

ある ISP でいつも同じエラーメッセージが表示される場合、メールまたは IP が ISP で誤って検出されている可能性があります。次のレコメンデーションを実行します。

* 受け取っているエラーの多くが、存在しないメールアドレス（**不明なユーザー**&#x200B;エラー）に関連するものかどうかを確認します。
* 入力したドメイン名のエラーを検出するために、購読フォームを更新します（例：gmaul.com または yaho.com）。
* メッセージがスパムであることを宣言していることを示すエラーの場合、または、メッセージが常にブロックされていることを示すエラーの場合、過去 12 ヶ月間にメッセージを開封またはクリックしていない受信者をターゲットから除外してみます。

問題が解決されない場合は、商用または配信品質サービス、あるいは Adobe Campaign サポートにお問い合わせください。

## ブロックリストと強制隔離の比較 {#denylist-versus-quarantine}

* **ブロックリストのメールアドレスと強制隔離されたメールアドレスの違いは何ですか？**

   * ステータス **[!UICONTROL On denylist]** は [ フィードバックループ ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ja#feedback-loops) の結果（メッセージがスパムとして報告された場合）です。

   * ステータス **[!UICONTROL Quarantined]** は、ソフトバウンスまたはハードバウンスの結果です。

  詳しくは、[こちらの節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)を参照してください。

* **様々な強制隔離エラーの原因は何を意味しますか。**

  考えられる理由は次の 10 つです。定義されていない、不明なユーザー、無効なドメイン、アドレスがブロックリスト、拒否、無視されたエラー、到達できない、無効なアカウント、メールボックスがいっぱいである、接続されていない。

  詳しくは、[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)を参照してください。

## ブロックリストからの削除 {#removing-from-denylist}

* **誤って 1 人の受信者がブロックリストに追加されました。 ブロックリストに加える メッセージを送信し直すにはどうすればよいですか**

   * **[!UICONTROL Administration > Channels > Quarantines > Addresses]** に移動します。
   * 対応するレコードの詳細で、**[!UICONTROL Status]** フィールドの値を **[!UICONTROL Valid]** に設定します。
   * レコードを保存します。

* ブロックリストに加える **自分の IP がオンになっているかどうかを調べるにはどうすればよいですか？ IP をブロックリストから削除する方法を教えてください。**

  IP アドレスがブロックリストに登録されているかどうかを確認するには、次のような様々な Web サイトを使用して確認できます。
   * [MX Toolbox](https://mxtoolbox.com/)
   * [What is my IP address](https://whatismyipaddress.com)

  通常、IP アドレスのチェックの結果は、ブロックリストの詳細と、IP アドレスをブロックした web サイトの名前を含むリストを返します。

  対応するリンクをクリックすると、web サイトの詳細にアクセスできます。

  次に、IP アドレスがブロックリストに登録された Web サイトのリストから Web サイトを削除するようリクエストできます。

  >[!NOTE]
  >
  >リストからの削除のプロセスは、Web サイトによって異なります。サイトによって、アカウントの作成が必要な場合や、IP アドレスを指定するだけの場合があります。
