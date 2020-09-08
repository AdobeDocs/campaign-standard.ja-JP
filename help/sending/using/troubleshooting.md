---
title: Adobe Campaign Standardでの配信品質の問題のトラブルシューティング
description: 配信品質の問題がAdobe Campaign Standardで発生した場合の対処方法を説明します。
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
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 48%

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

* **電子メールアドレスと隔離されたブロックリストに加える電子メールアドレスの違いを教えてください。**

   * The status **[!UICONTROL Denylisted]** is a result of a feedback loop (when a person reports a message as spam).

   * The status **[!UICONTROL Quarantined]** is a result of a soft or hard bounce.
   詳しくは、[こちらの節](../../sending/using/understanding-quarantine-management.md#quarantine-vs-block-list)を参照してください。

* **様々な強制隔離エラーの原因は何を意味しますか。**

   考えられる理由は10つあります。未定義、ユーザー不明、無効なドメイン、ブロックリストに加えるアドレス、拒否、エラー無視、未到達、アカウント無効、メールボックスフル、接続なし

   詳しくは、[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)を参照してください。

## ブロックリストからの削除 {#removing-from-denylist}

* **私の受信者の一つはブロックリストに加える間違っていた。 How do I remove them from the denylist so that I can start sending them messages again?**

   * 移動 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * In the details of the corresponding record, set the value of the **[!UICONTROL Status]** field to **[!UICONTROL Valid]**.
   * レコードを保存します。

* **IPの1つが存在するかどうかを調べるにはどうブロックリストに加えるしますか。 IPをから削除する方法を教えてブロックリストください。**

   IPアドレスがブロックリストに加える確認するには、次のような様々なWebサイトを使用して確認します。
   * [MX Toolbox](https://mxtoolbox.com/)
   * [IPアドレスは何か](https://whatismyipaddress.com)

   通常、IPアドレスの確認の結果、リストの詳細と、IPアドレスをブロックしブロックリストたWebサイトの名前を含むが返されます。

   対応するリンクをクリックすると、Web サイトの詳細にアクセスできます。

   その後、IPアドレスを追加したWebサイトのリストからWebサイトを削除するように要求ブロックリストできます。

   >[!NOTE]
   >
   >リストからの削除のプロセスは、Web サイトによって異なります。サイトによって、アカウントの作成が必要な場合や、IP アドレスを指定するだけの場合があります。
