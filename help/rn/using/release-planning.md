---
title: Campaign Standardリリースの計画
description: このページでは、Adobe Campaign標準の今後のリリースリストを紹介します。
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
source-git-commit: 292f4f65f2e0597ff4dc36ab3222551ab40cbafb
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 9%

---


# リリース計画 {#release-planning}

アドビは、新しい機能、拡張機能および修正を追加することで、ソリューションを継続的に強化しています。

すべてのAdobe Campaign標準インスタンスは、新しいリリースのたびにアップグレードされます。 アップグレードに対するアクションは必要ありません。

アップグレードは2段階で導入されます。 最初に、Stageインスタンスがアップグレードされ、お客様が新しい機能をテストし、必要に応じて設定を調整できるようになりました。 その後、実稼働インスタンスがアップグレードされます。

すべてのリリース日は変更される可能性があります。 このページを定期的に訪問して、更新を確認することをお勧めします。

**新規！** Campaign Standardのリリース通知を購読する [](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) 、今後のリリースに関する詳細を受信トレイに直接表示できます。

## リリース20.3.1 - 5月のリリース {#release-20-3-may-release}

環境の更新は、以下に示す時間枠内にウェーブで発生します。 このリリースに関する詳細は、 [リリースノートを参照してください](../../rn/using/release-notes.md)。 その他のご質問は、 [Adobe Client Careにお問い合わせください](https://support.neolane.net/webApp/extranetLogin)。

<table>
 <thead>
  <tr>
   <th> 環境<br /> </th>
   <th> 日付<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>ステージ<br /> </td>
   <td>2020年5月25日～26日<br /> </td>
  </tr>
  <tr>
   <td> Production（本番）<br /> </td>
   <td>2020年5月28日～6月1日<br /> </td>
  </tr>
 </tbody>
</table>



## 質問と回答 {#questions-and-answers}

**Q: 影響は？**

A: 変更点は [リリースノートに記載されており](../../rn/using/release-notes.md)、関連ドキュメントへのリンクも含まれています。 また、 [廃止/削除された機能のページを参照することをお勧めします](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)。 これらのページは、Stage環境のアップグレード日に、新しいリリースで利用できます。

**Q: 検証プロセスとは**

A: ステージングインスタンスがアップグレードされると、アドビでは、プロセスおよび使用例がこの新しいバージョンで正しく動作していることを検証し、問題があれば [Adobe Client Careに報告することをお勧めします](https://support.neolane.net/webApp/extranetLogin)。

**Q: アップグレードプロセス中に、インスタンスにアクセスできますか。**

A: いいえ。 インスタンスのアップグレード中、数分間はデータベースにアクセスできない場合があります。 すべてのプロセスが自動的に再起動します。

**Q: メッセージは引き続き送信されますか？**

A: いいえ。 数分間はメッセージは送信されません。 アップグレードが完了すると、プロセスは自動的に再起動されます。

**Q: ワークフローは引き続き実行され、配信を送信しますか？**

A: いいえ。 ビルドのアップグレード中に、ワークフローサーバーとMTAの両方が停止します。 つまり、ワークフローは実行されず、数分間は配信は送信されません。 必要なアクションはありません。 ワークフローは、インスタンスがアップグレードされるとすぐに再び開始します。

**Q: アップグレード中も、メッセージ内のリンクの追跡は引き続き機能しますか。**

A: はい、彼らは働きます。 アップグレードの間、新しい E メールは送信できませんが、既に送信されている E メールに含まれるトラッキングリンクは機能します。

**Q: アップグレードが完了したことを確認する方法**

A: キャンペーンにログオンすると、リリース通知ポップアップが表示され、最新バージョンが表示されます。

その他のご質問は、 [Adobe Client Careにお問い合わせください](https://support.neolane.net/webApp/extranetLogin)。
