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
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 45%

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

## ブロックリストと強制隔離 {#block-list-versus-quarantine}

* **ブロックリスト上の電子メールアドレスと検疫済みの電子メールアドレスの違いは何ですか。**

   * The status **[!UICONTROL On block list]** is a result of a feedback loop (when a person reports a message as spam).

   * The status **[!UICONTROL Quarantined]** is a result of a soft or hard bounce.
   For more on this, see this [section](../../sending/using/understanding-quarantine-management.md#quarantine-vs-block-list).

* **様々な強制隔離エラーの原因は何を意味しますか。**

   考えられる理由は10つあります。 未定義、ユーザー不明、無効なドメイン、ブロックリスト上のアドレス、拒否、エラー無視、未到達、アカウント無効、メールボックスがいっぱい、未接続

   詳しくは、[強制隔離管理の理解](../../sending/using/understanding-quarantine-management.md)を参照してください。

## ブロックリストからの削除 {#removing-from-block-list}

* **私の受信者の1つが誤ってブロックリストに追加された。 メッセージを再度送信する際に開始を使用できるように、ブロックリストからメッセージを削除する方法を教えてください。**

   * 移動 **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * In the details of the corresponding record, set the value of the **[!UICONTROL Status]** field to **[!UICONTROL Valid]**.
   * レコードを保存します。

* **IPの1つがブロックリスト上にあるかどうかを調べるにはどうすればよいですか。 IPをブロックリストから削除する方法を教えてください。**

   IPアドレスがブロックリスト上にあるかどうかを確認するには、次のような様々なWebサイトを使用して確認します。
   * [MX Toolbox](https://mxtoolbox.com/)
   * [IPアドレスは何か](https://whatismyipaddress.com)
   通常、IPアドレスの確認の結果、ブロックリストの詳細と、IPアドレスをブロックしたWebサイトの名前を含むリストが返されます。

   対応するリンクをクリックすると、Web サイトの詳細にアクセスできます。

   その後、IPアドレスをブロックリストに追加したWebサイトのリストからWebサイトを削除するように要求できます。

   >[!NOTE]
   >
   >リストからの削除のプロセスは、Web サイトによって異なります。サイトによって、アカウントの作成が必要な場合や、IP アドレスを指定するだけの場合があります。
