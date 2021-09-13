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

* **強制隔離Eメールアドレスとの違ブロックリストいは何ですか。**

   * ステータス&#x200B;**[!UICONTROL On denylist]**&#x200B;は、[フィードバックループ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=ja#feedback-loops)の結果です（人がメッセージをスパムとしてレポートする場合）。

   * **[!UICONTROL Quarantined]**&#x200B;というステータスは、ソフトバウンスまたはハードバウンスの結果です。
   詳しくは、[こちらの節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)を参照してください。

* **様々な強制隔離エラーの原因は何を意味しますか。**

   考えられる理由は次の10です。未定義、不明なユーザー、無効なドメイン、ブロックリストのアドレス、拒否、無視されたエラー、未到達、無効なアカウント、メールボックス容量超過、未接続

   詳しくは、[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)を参照してください。

## ブロックリストからの削除 {#removing-from-denylist}

* **受信者の1人が誤ってにブロックリスト追加されました。メッセージの送信を再開するにブロックリストは、どうすればから削除できますか？**

   * 移動 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * 対応するレコードの詳細で、**[!UICONTROL Status]**&#x200B;フィールドの値を&#x200B;**[!UICONTROL Valid]**&#x200B;に設定します。
   * レコードを保存します。

* **IPの1つが中かどうかはどうすればわかりまブロックリストすか。IP をブロックリストから削除する方法を教えてください。**

   IPアドレスがになっているかどうかを確認するにブロックリストは、次のような様々なWebサイトを使用して検証できます。
   * [MX Toolbox](https://mxtoolbox.com/)
   * [What is my IP address](https://whatismyipaddress.com)

   通常、IPアドレスチェックの結果は、の詳細ブロックリストと、IPアドレスをブロックしたWebサイトの名前を含むリストを返します。

   対応するリンクをクリックすると、Web サイトの詳細にアクセスできます。

   次に、IP アドレスがブロックリストに登録された Web サイトのリストから Web サイトを削除するようリクエストできます。

   >[!NOTE]
   >
   >リストからの削除のプロセスは、Web サイトによって異なります。サイトによって、アカウントの作成が必要な場合や、IP アドレスを指定するだけの場合があります。
