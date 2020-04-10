---
title: Campaign Standardリリース計画
description: このページでは、リスト標準の今後のリリースをAdobe Campaignします。
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
source-git-commit: a71af00e606d78c4ff8b39da1b9f032c0dcf0fc6

---


# リリース計画 {#release-planning}

アドビは、新しい機能、機能強化および修正を追加することで、ソリューションを引き続き強化しています。

すべてのAdobe Campaign標準インスタンスは、新しいリリースのたびにアップグレードされます。 アップグレードの際には、何も行う必要はありません。

アップグレードは2段階で導入されます。 まず、Stageインスタンスがアップグレードされ、お客様が新しい機能をテストし、必要に応じて設定を適応できるようになります。 その後、実稼働インスタンスがアップグレードされます。

すべてのリリース日は変更される可能性があります。このページを定期的に訪問して、更新を確認することをお勧めします。

**新機能！** 今後のリリー [スの詳細を受信トレイで](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) 、Campaign Standardのリリース通知を購読して取得します。

## リリース20.3.1 - 5月のリリース {#release-20-3-may-release}

環境の更新は、ウェーブで、以下に示す時間枠内に発生します。 このリリースに関する詳細は、リリースノートを参照 [してください](../../rn/using/release-notes.md)。 その他のご質問は、 [Adobe ClientCareにお問い合わせください](https://support.neolane.net/webApp/extranetLogin)。

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
   <td> April 27 - 28, 2020<br /> </td> 
  </tr> 
  <tr> 
   <td> Production（本番）<br /> </td> 
   <td> 2020年5月4日～11日<br /> </td> 
  </tr> 
 </tbody> 
</table>



## 質問と回答 {#questions-and-answers}

**質問：影響は？**

A:変更点は、関連ドキュメン [トへのリンクを含め](../../rn/using/release-notes.md)、リリースノートに記載されています。 また、廃止および削除された機能のペ [ージを参照することをお勧めします](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)。 これらのページは、Stage環境のアップグレード日に公開されます。

**質問：検証プロセスとは**

A:ステージングインスタンスがアップグレードされると、アドビでは、プロセスと使用事例がこの新しいバージョンで適切に機能していることを検証し、問題が発生した場合は [Adobe ClientCareに報告することを推奨します](https://support.neolane.net/webApp/extranetLogin)。

**質問：アップグレードプロセス中にインスタンスにアクセスできますか。**

A:いいえ。 インスタンスのアップグレード中、数分間はデータベースにアクセスできない場合があります。 すべてのプロセスが自動的に再起動します。

**質問：メッセージは引き続き送信されますか？**

A:いいえ。 数分間はメッセージは送信されません。 アップグレードが完了すると、プロセスが自動的に再起動されます。

**質問：ワークフローは引き続き実行され、配信を送信しますか？**

A:いいえ。 ビルドのアップグレード中に、ワークフローサーバーとMTAの両方が停止します。 つまり、ワークフローは実行されず、配信は数分間送信されません。 必要なアクションはありません。ワークフローは、インスタンスがアップグレードされるとすぐに開始し直します。

**質問：アップグレード中も、メッセージ内のリンクの追跡は引き続き機能しますか。**

A:はい、彼らは働きます。 アップグレードの間、新しい E メールは送信できませんが、既に送信されている E メールに含まれるトラッキングリンクは機能します。

**質問：アップグレードが完了したことを確認する方法を教えてください。**

A:キャンペーンにログオンすると、リリース通知ポップアップが最新バージョンと共に表示されます。

その他のご質問は、 [Adobe ClientCareにお問い合わせください](https://support.neolane.net/webApp/extranetLogin)。