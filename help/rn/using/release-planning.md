---
solution: Campaign Standard
product: campaign
title: Campaign Standard のリリース計画
description: このページでは、Adobe Campaign Standard の今後のリリースを紹介します。
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
translation-type: tm+mt
source-git-commit: 505e2292639f617cbcedd8c7227529bf76d54508
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 96%

---


# リリース計画 {#release-planning}

アドビでは、新しい機能、機能強化および修正を加えてソリューションを継続的に改善しています。

すべての Adobe Campaign Standard インスタンスは、新しいリリースのたびにアップグレードされます。アップグレードに必要なアクションはありません。

アップグレードは 2 段階でデプロイされます。まず、ステージング用インスタンスがアップグレードされて、お客様が新しい機能をテストしたり、必要に応じて設定を調整したりできるようになります。その後、本番用インスタンスがアップグレードされます。

すべてのリリース日は変更される可能性があります。このページに定期的にアクセスして、アップデートを確認することをお勧めします。

**新規：**[Campaign Standard のリリース通知](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU)をご購読いただくと、今後のリリースの詳細が E メールで通知されます。

## リリース 21.1 - 2 月リリース {#release-21-1-release}

環境のアップデートは、以下に示す期間に順次おこなわれます。このリリースに関する詳細は、Stage環境の開始がアップグレードされた場合のリリースノート[](../../rn/using/release-notes.md)を参照してください。 その他のご質問については、[アドビクライアントケア](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。

<table>
 <thead>
  <tr>
   <th> 環境<br /> </th>
   <th> 日付<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>ステージング<br /> </td>
   <td>2021 年 1 月 25 日～27 日 <br /> </td>
  </tr>
  <tr>
   <td> 本番<br /> </td>
   <td>2021 年 2 月 1 日～8 日<br /> </td>
  </tr>
 </tbody>
</table>

## 質問と回答 {#questions-and-answers}

**Q：どのような影響がありますか？**

A：変更点は[リリースノート](../../rn/using/release-notes.md)に記載されています。リリースには、関連ドキュメントへのリンクも含まれています。また、[廃止および削除された機能](../../rn/using/deprecated-features.md)のページを参照することもお勧めします。新しいリリースについてのこれらのページは、ステージング環境のアップグレード日に利用可能になります。

**Q：検証プロセスとは何ですか？**

A：ステージング用インスタンスがアップグレードされたら、お客様のプロセスとユースケースがこの新しいバージョンで正しく動作することを検証し、問題があれば[アドビクライアントケア](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)に報告することをお勧めします。

**Q：アップグレード中にインスタンスにアクセスできますか？**

A：いいえ。インスタンスのアップグレード中は、数分間データベースにアクセスできない可能性があります。すべてのプロセスが自動的に再起動します。

**Q：メッセージは引き続き送信されますか？**

A：いいえ。メッセージは、数分間送信されません。アップグレードが完了するとすぐに、プロセスは自動的に再起動されます。

**Q：ワークフローは引き続き実行され、配信を送信しますか？**

A：いいえ。ビルドのアップグレード中は、ワークフローサーバーと MTA の両方が停止します。つまり、数分間、ワークフローは実行されず、配信は送信されません。ユーザー側で必要なアクションはありません。ワークフローは、インスタンスがアップグレードされるとすぐに再開します。

**Q：アップグレード中も、メッセージ内のトラッキングリンクは機能しますか？**

A：はい。アップグレード中に新しい E メールは送信できませんが、既に送信されている E メールに含まれるトラッキングリンクは機能します。

**Q：アップグレードが完了したことを確認する方法がありますか？**

A：Campaign にログオンすると、リリース通知ポップアップが表示され、最新バージョンが表示されます。

その他のご質問については、[アドビクライアントケア](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
