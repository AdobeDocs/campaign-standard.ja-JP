---
title: Adobe Campaign Standardでの配信品質の問題のトラブルシューティング
description: Adobe Campaign Standardで配信品質の問題が発生した場合の対処方法を説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 59%

---

# トラブルシューティング{#troubleshooting}

配信品質で問題が発生した場合は、以下のソリューションを参照してください。

## ISP に対する同じエラーメッセージ {#same-error-for-an-isp}

**特定の ISP でいつも同じエラーメッセージが表示されるのはなぜですか。**

ある ISP でいつも同じエラーメッセージが表示される場合、E メールまたは IP が ISP で誤って検出されている可能性があります。次の推奨事項を実行します。
* 受け取っているエラーの多くが、存在しない E メールアドレス（**不明なユーザー**&#x200B;エラー）に関連するものかどうかを確認します。
* 入力したドメイン名のエラーを検出するために、購読フォームを更新します（例：gmaul.com または yaho.com）。
* メッセージがスパムであることを宣言していることを示すエラーの場合、または、メッセージが常にブロックされていることを示すエラーの場合、過去 12 ヶ月間にメッセージを開封またはクリックしていない受信者をターゲットから除外してみます。

問題が解決されない場合は、商用または配信品質サービス、あるいは Adobe Campaign サポートにお問い合わせください。

## ブロックリストと強制隔離の比較 {#denylist-versus-quarantine}

* **上の E メールアドレスと強制隔離 E メールアドレブロックリストに加えるスの違いについて教えてください。**

   * ステータス **[!UICONTROL On denylist]** は、 [フィードバックループ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ja#feedback-loops) （人がメッセージをスパムとしてレポートする場合）。

   * ステータス **[!UICONTROL Quarantined]** は、ソフトバウンスまたはハードバウンスの結果です。

  詳しくは、[こちらの節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)を参照してください。

* **様々な強制隔離エラーの原因は何を意味しますか。**

  次の 10 個の原因が考えられます。未定義、不明なユーザー、無効なドメイン、上のアドレス、拒否、無視されたエラー、未到達、無効なアカウント、メールボックス容量超過、未接続。

  詳しくは、[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)を参照してください。

## ブロックリストからの削除 {#removing-from-denylist}

* **受信者の 1 人が誤ってに追ブロックリストに加える加されました。 メッセージの送信を再開できるようブロックリストに加えるに、メッセージから削除する方法を教えてください。**

   * 移動 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * 対応するレコードの詳細で、 **[!UICONTROL Status]** ～に向かって **[!UICONTROL Valid]**.
   * レコードを保存します。

* **IP の 1 つが中かどうかを確認するにはどうすればよいでブロックリストに加えるすか。 IP をブロックリストから削除する方法を教えてください。**

  IP アドレスが上にあるかどうかを確認するにブロックリストに加えるは、次のような様々な Web サイトを使用して検証できます。
   * [MX Toolbox](https://mxtoolbox.com/)
   * [What is my IP address](https://whatismyipaddress.com)

  通常、IP アドレスチェックの結果は、の詳細と IP アドレスをブロックした Web サイトの名前を含むリストで返されまブロックリストに加えるす。

  対応するリンクをクリックすると、Web サイトの詳細にアクセスできます。

  次に、IP アドレスがブロックリストに登録された Web サイトのリストから Web サイトを削除するようリクエストできます。

  >[!NOTE]
  >
  >リストからの削除のプロセスは、Web サイトによって異なります。サイトによって、アカウントの作成が必要な場合や、IP アドレスを指定するだけの場合があります。
