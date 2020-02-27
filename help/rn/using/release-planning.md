---
title: キャンペーン標準リリース計画
description: このページには、Adobe Campaign Standardの今後のリリースの一覧が表示されます。
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6ffbf03a7eb4fc1b5bfbd523c0c5342d41cfd211

---


# キャンペーン標準リリース計画 {#release-planning}

アドビは、新しい機能、拡張機能および修正を追加して、ソリューションを継続的に強化しています。

すべてのAdobe Campaign Standardインスタンスは、新しいリリースのたびにアップグレードされます。 アップグレードに対する対応は不要です。

アップグレードは2段階で導入されます。 まず、Stageインスタンスがアップグレードされ、お客様が新しい機能をテストし、必要に応じて設定を適応できるようになります。 その後、実稼働インスタンスがアップグレードされます。

すべてのリリース日は変更される可能性があります。このページを定期的に訪問して、更新を確認することをお勧めします。

Adobe Experience cloudの最新リリ [ースの詳細を受信トレイに直接入手するには](https://www.adobe.com/subscription/priority-product-update.html) 、リリース通知を受信するように登録してください。

## リリース20.1.3 - 2月のリリースアップデート {#release-20-1-3---february-release-update}

環境の更新は、次に示す時間枠内で波状に発生します。 このリリースに関する詳細は、リリースノートを参照 [してください](../../rn/using/release-notes.md)。 その他のご質問は、 [Adobe ClientCareにお問い合わせください](https://support.neolane.net/webApp/extranetLogin)。

<table> 
 <thead> 
  <tr> 
   <th> 環境<br /> </th> 
   <th> 日付<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ステージ<br /> </td> 
   <td> 2020年2月17日～18日<br /> </td> 
  </tr> 
  <tr> 
   <td> Production（本番）<br /> </td> 
   <td> 2020年2月20日～3月5日<br /> </td> 
  </tr> 
 </tbody> 
</table>



## 質問と回答 {#questions-and-answers}

**質問：影響は？**

A:変更点は、関連ドキュメントへ [のリンクを含め](../../rn/using/release-notes.md)、リリースノートに記載されています。 また、廃止および削除された機能のペ [ージを参照することをお勧めします](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。 これらのページは、Stage環境のアップグレード日に新しいリリースで利用できます。

**質問：検証プロセスとは**

A:ステージングインスタンスがアップグレードされると、アドビでは、プロセスと使用事例がこの新しいバージョンで正しく機能していることを検証し、問題が発生した場合は [Adobe ClientCareに報告することをお勧めします](https://support.neolane.net/webApp/extranetLogin)。

**質問：アップグレードプロセス中にインスタンスにアクセスできますか。**

A:いいえ。 インスタンスのアップグレード中、数分間はデータベースにアクセスできない場合があります。 すべてのプロセスが自動的に再起動します。

**質問：メッセージは引き続き送信されますか。**

A:いいえ。 数分間はメッセージは送信されません。 アップグレードが完了すると、プロセスが自動的に再起動されます。

**質問：ワークフローは引き続き実行され、配信が送信されますか。**

A:いいえ。 ビルドのアップグレード中に、ワークフローサーバーとMTAの両方が停止します。 つまり、ワークフローは実行されず、数分間配信も送信されません。 必要なアクションはありません。ワークフローは、インスタンスがアップグレードされるとすぐに再開されます。

**質問：アップグレード中も、メッセージ内のリンクの追跡は引き続き機能しますか。**

A:はい、彼らは働きます。 アップグレードの間、新しい E メールは送信できませんが、既に送信されている E メールに含まれるトラッキングリンクは機能します。

**質問：アップグレードが完了したことを確認する方法**

A:Campaignにログオンすると、最新バージョンのリリース通知ポップアップが表示されます。

その他のご質問は、 [Adobe ClientCareにお問い合わせください](https://support.neolane.net/webApp/extranetLogin)。