---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standardでの配信品質の問題のトラブルシューティング
description: 配信品質の問題がAdobe Campaign Standardで発生した場合の対処方法を説明します。
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: 配信品質
role: ビジネス従事者
level: 中級者
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 57%

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

## ブロックリスト対強制隔離 {#denylist-versus-quarantine}

* **上の電子メールアドレスと隔離された電子メールアドレスの違いについて教えてください。**

   * ステータス&#x200B;**[!UICONTROL On denylist]**&#x200B;は、[フィードバックループ](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)の結果です（メッセージがスパムとして報告された場合）。

   * ステータス&#x200B;**[!UICONTROL Quarantined]**&#x200B;は、ソフトバウンスまたはハードバウンスの結果です。
   詳しくは、[こちらの節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)を参照してください。

* **様々な強制隔離エラーの原因は何を意味しますか。**

   考えられる理由は10つあります。未定義、ユーザー不明、無効なドメイン、ブロックリスト上のアドレス、拒否、エラー無視、未到達、アカウント無効、メールボックスフル、未接続

   詳しくは、[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)を参照してください。

## ブロックリストからの削除 {#removing-from-denylist}

* **私の受信者の1つが誤ってブロックリストに追加された。メッセージを再度送信する際に開始ブロックリストを取り出すには、から削除する方法は？**

   * 移動 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * 対応するレコードの詳細で、**[!UICONTROL Status]**&#x200B;フィールドの値を&#x200B;**[!UICONTROL Valid]**&#x200B;に設定します。
   * レコードを保存します。

* **IPの1つがブロックリストにあるかどうかを調べるにはどうしますか。IP をブロックリストから削除する方法を教えてください。**

   IPアドレスがブロックリスト上にあるかどうかを確認するには、次のような様々なWebサイトを使用して確認します。
   * [MX Toolbox](https://mxtoolbox.com/)
   * [What is my IP address](https://whatismyipaddress.com)

   通常、IPアドレスの確認の結果、リストの詳細と、IPアドレスをブロックしブロックリストたWebサイトの名前を含むが返されます。

   対応するリンクをクリックすると、Web サイトの詳細にアクセスできます。

   次に、IP アドレスがブロックリストに登録された Web サイトのリストから Web サイトを削除するようリクエストできます。

   >[!NOTE]
   >
   >リストからの削除のプロセスは、Web サイトによって異なります。サイトによって、アカウントの作成が必要な場合や、IP アドレスを指定するだけの場合があります。
