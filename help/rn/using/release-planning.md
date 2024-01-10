---
title: Campaign Standard のリリース計画
description: このページでは、Adobe Campaign Standard の今後のリリースを紹介します。
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: 7678628193f025ae9bfe4c70afe0cb5f0bbc4a4d
workflow-type: ht
source-wordcount: '464'
ht-degree: 100%

---

# リリース計画 {#release-planning}

アドビは、新しい機能の追加、機能強化および修正を加えることにより、ソリューションを継続的に改善しています。

すべての Adobe Campaign Standard インスタンスは、新しいリリースのたびにアップグレードされます。アップグレードに必要なアクションはありません。

アップグレードは 2 段階でデプロイされます。まず、ステージインスタンスがアップグレードされて、新しい機能をテストしたり、必要に応じて設定を調整したりできるようになります。次に、実稼動インスタンスがアップグレードされます。

リリース日は変更される場合があります。定期的にこのページにアクセスして、最新情報を確認してください。環境のアップデートは、以下に示す期間に順次おこなわれます。正確な日付は、各顧客にメールで通知されます。

## リリース 24.1 - 2024年冬リリース {#release-24-1-release}

このリリースについて詳しくは、[初期のリリースノート](e-release-notes.md)を参照してください。

<table>
 <thead>
  <tr>
   <th> 環境 </th>
   <th> 日付 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>ステージ </td>
   <td>2024年1月16日～2月13日（PT） </td>
  </tr>
  <tr>
   <td>実稼動 </td>
   <td>2024年1月23日～2月20日（PT） </td>
  </tr>
 </tbody>
</table>


## リリース 23.2 - 2023年秋限定リリース {#release-23-2-release}


>[!AVAILABILITY]
>
>このリリースは、一連の組織のみが使用できます（限定提供）。詳しくは、アドビ担当者にお問い合わせください。

このリリースについて詳しくは、[リリースノート](release-notes.md)を参照してください。

<table>
 <thead>
  <tr>
   <th> 環境 </th>
   <th> 日付 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>ステージ </td>
   <td>2023年10月3日～9日（PT） </td>
  </tr>
  <tr>
   <td>実稼動 </td>
   <td>2023年10月12日～18日（PT） </td>
  </tr>
 </tbody>
</table>

その他の質問があれば、[Adobe Client Care](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html) にお問い合わせください。

## 質問と回答 {#questions-and-answers}

**Q：どのような影響がありますか？**

A：変更点は[リリースノート](../../rn/using/release-notes.md)に記載されています。リリースには、関連ドキュメントへのリンクも含まれています。また、[廃止および削除された機能](../../rn/using/deprecated-features.md)のページを参照することもお勧めします。新しいリリースについてのこれらのページは、ステージング環境のアップグレード日に利用可能になります。

**Q：検証プロセスとは何ですか？**

A：ステージング用インスタンスがアップグレードされたら、お客様のプロセスとユースケースがこの新しいバージョンで正しく動作することを検証し、問題があれば[アドビクライアントケア](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)に報告することをお勧めします。

**Q：アップグレード中にインスタンスにアクセスできますか？**

A：いいえ。インスタンスのアップグレード中は、数分間データベースにアクセスできない可能性があります。すべてのプロセスが自動的に再起動します。

**Q：メッセージは引き続き送信されますか？**

A：いいえ。メッセージは、数分間送信されません。アップグレードが完了すると、プロセスが自動的に再起動します。

**Q：ワークフローは引き続き実行され、配信を送信しますか？**

A：いいえ。ビルドのアップグレード中は、ワークフローサーバーと MTA の両方が停止します。その結果、ワークフローは実行されず、配信は数分間送信されません。ユーザー側で必要なアクションはありません。ワークフローは、インスタンスがアップグレードされるとすぐに再開します。

**Q：アップグレード中も、メッセージ内のトラッキングリンクは機能しますか？**

A：はい。アップグレード中に新しいメールは送信できませんが、既に送信されているメールに含まれるトラッキングリンクは機能します。

**Q：アップグレードが完了したことを確認するにはどうすればよいですか？**

A：Campaign にログオンすると、リリース通知ポップアップが表示され、最新バージョンが表示されます。

その他のご質問については、[アドビクライアントケア](https://helpx.adobe.com/jp/enterprise/using/support-for-experience-cloud.html)にお問い合わせください。
