---
title: 最新リリース
description: このページでは、Adobe Campaign標準の最新リリースをすべてリストしています。
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e59562bd4f258c4259b8e8e5d9648397d5718792
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 5%

---


# 最新リリース{#latest-release}

[リリースの計画](../../rn/using/release-planning.md) | [コントロールパネルのリリース](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html) | [ドキュメントの更新](../../rn/using/documentation-updates.md) | [以前のリリースノート](../../rn/using/release-notes-2020.md) | [非推奨の機能](../../rn/using/deprecated-features.md)

## リリース20.3 - 2020年5月 {#release-20-3---may-2020}

**新機能**

<table> 
<thead> 
<tr> 
<th> <strong>タイの個人データ保護法(PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>タイの個人データ保護法(PDPA)は、タイのデータ保護に関する要件を調和・近代化する新しいプライバシー法です。 本規則は、本国に居住するデータ・サブジェクトのデータを保持するAdobe Campaignのお客様に適用されます。</p>
<p>Adobe Campaignで既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）に加え、PDPAの準備を容易にするための追加機能を追加する予定です。</p>
<ul>
<li>アクセス権と削除権： GDPRとCCPAに追加された機能を活用しています。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">さらに詳しく</a> </li>
<li><p>プライバシー要求を作成する際に、PDPA規制タイプがプライバシーコアサービスに追加されました。 このメソッドは、すべてのアクセスおよび削除リクエストに対して使用する必要があるメソッドです。 アクセス要求および削除要求に対するキャンペーンAPIとインターフェイスの使用は廃止されました。  廃止された機能と <a href="../../rn/using/deprecated-features.md">削除された機能の記事を参照してください</a>。</p></li>
</ul>
<p>使い方のビデオ <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">を参照してください</a>。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>外部APIアクティビティ(GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>External API <strong></strong> アクティビティは、ベータ版からGAに移行中です。 このリリースでは、JSON応答本文パーサーに柔軟性をもたらします。 次の操作が可能になりました。</p>
<ul>
<li>最大深さが10レベルのネストされたJSONを解析する。 </li>
<li>選択したプロパティをJSONのリーフノードとして解析し、統合して1つのテーブル行にします。</li>
<li>JSONから配列オブジェクトを選択して使用します。オブジェクトに「data」という名前を付けたり、最上位レベルに配置したりする必要はありません。</li>
</ul>
<p><strong>注意：</strong> お客様は、ベータ版External APIアクティビティをすべて、ワークフロー内のGA External APIアクティビティに <strong>置き換える必要があります</strong> 。  ベータ版のExternal APIを使用するワークフローは、20.3では動作を停止します。</p>
<p>詳しくは、<a href="../../automating/using/external-api.md">詳細ドキュメント</a>および<a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">ハウツービデオ</a>を参照してください。</p>
</td> 
</tr> 
</tbody> 
</table>

>[!NOTE]
>
>CNAMEサブドメインの証明書の更新は、5月にキャンペーンのコントロールパネルでリリースされます。 詳しくは、「 [コントロールパネルリリースノート](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html)」を参照してください。

**強化点**

* ターゲットプロファイルを使用してメッセージを **テストする際に、「** プレフィックス [](../../sending/using/testing-messages-using-target.md) 」フィールドで使用できる文字数が32文字から500文字に増えました。
* インスタンスに発行できるリアルタイムイベントの最大数が350から2000に増えました。 (CAMP-41608)
* Adobe LaunchとCampaign Standardの同期が、syncWithLaunchテクニカルワークフローを使用して改善されました。 このワークフローにより、Adobe LaunchのすべてのモバイルプロパティをAdobe Campaign標準に自動インポートできます。 詳しくは、[このページ](../../administration/using/technical-workflows.md)を参照してください。

   お使いのキャンペーンインスタンスでsyncWithLaunchテクニカルワークフローを有効にするには、チケットをアドビカスタマーケアに（直接またはアドビの担当者を通じて）送信する必要があります。 (CAMP-40082)

**電子メールデザイナーの機能強化**

* 電子メールデザイナーは、厳密なW3Cよりも柔軟なHTML形式設定を処理できるようになりました。 (CAMP-42529)
* コンテンツブロック内の画像の横にリンクが表示されない [ように、](../../designing/using/links.md#inserting-a-link) クリック可能な画像に関する問題を修正しました。 (CAMP-41586)
* ト [ラッキングするURLにカテゴリが追加されている場合に、ランディングページにリダイレクトできない問題を修正しました](../../designing/using/links.md#about-tracked-urls) 。 (CAMP-41537)
* Outlookでボタンのパディングの問題を修正しました。
* HTMLタグがプレーンテキストで表示される問題を修正しました。
* コンテンツブロック検索で、サーバーの検索結果とプリロードされた結果が表示されるようになりました。 (CAMP-41870)

**その他の変更**

* カスタムリソースのパブリケーションインターフェイスが改善され、より明確なエラーメッセージが表示されるようになりました。
* 未使用の配信マッピングはインターフェイスから削除されました。
* 不要な管理者の役割がインターフェイスから削除されました。
* ランディングページでチェックボックスを必須にできるようになりました。
* 動的レポートのCSVファイルをダウンロードする場合、200行までという制限はなくなりました。 レポートのすべての行を含めることができるようになりました。 (CAMP-40810)
* 多言語電子メールの標準リストにES-US言語が追加されました。 (CAMP-42279)
* 「ファイルの転送」アクティビティでダウンロードされたファイルは、X日後に削除されるようになりました。Xは、Workflowプロパティの「 **Execution****（実行）** 」メニューの「History in days（履歴）」フィールドによって決定されます。 [詳細を表示](../../automating/using/managing-execution-options.md)

**エクスペリエンスプラットフォームの統合**

* 読み取りオーディエンス [アクティビティからのAdobe](../../automating/using/aep-targeting-audiences.md)**** Experience Platformオーディエンスのアクティベーションが向上し、パフォーマンスと安定性が向上しました。 さらに、アクティベーションジョブに関するワークフローログがより明確で詳細になり、Adobe Experience Platformオーディエンスを読む際の監視とトラブルシューティングが容易になりました。

**パッチ**

* カスタムリソースのパブリケーションジョブ中にゴーストリソースが作成される原因となっていたエラーを修正。
* プロファイルリソースがカスタムリソースを使用して拡張された場合に、プロファイルのマーケティング履歴が表示されない問題を修正しました。 (CAMP-41009)
* 標準搭載されたランディングページテンプレートで、エディターを開いたときにコンテンツがフランス語で表示される問題を修正しました。 (CAMP-41639)
* 動的コンテンツを含むプッシュ通知で、絵文字の表示を妨げる可能性がある問題を修正しました。 (CAMP-40715)
* アウトバウンド補完トランジションの1つに誤ったセグメントコードが割り当てられる原因となる **重複排除 - 重複** アクティビティの問題を修正しました。 (CAMP-41400)
* 予定レポートを削除できないエラーを修正しました。 (CAMP-41302)
* 配信のダッシュボードと **配信の概要** (Summary)レポートに食い違いがある問題を修正しました。 (CAMP-41145)
* ダウンロードしたレポートで文字が重なって表示される問題を修正しました。
* 配信のプレビューが配達確認の置き換えで機能しない問題を修正しました。
* アプリ内ローカル通知のカスタムフィールドを削除する際のエラーを修正しました。
* charIndex関数がワークフロー内の **End** ( **終了)または** File transfer（ファイル転送）アクティビティで動作しない問題を修正しました。
* エンリッチメントリソースと **** アクティビティの間にリンクを持つワークフローリソースを含む2つの入力アクティビティを使用する場合に発生する可能性があるターゲットの問題を修正しました。 (CAMP-42133)
* 不明な関数を使用する場合に、ワークフローが実行されない可能性がある問題を修正しました。 (CAMP-41873)
* 送信トランジションを補完する複数の「 **保存」オーディエンス** アクティビティを使用してオーディエンスを作成する場合に発生する可能性があるワークフローの問題を修正しました。 (CAMP-39992)
* トランザクション電子メールでパーソナライゼーションを使用すると、データに食い違いが生じる問題を修正しました。 (CAMP-41842)
* プッシュ通知配信のカスタムフィールドを削除する際に発生していた問題を修正しました。 (CAMP-37586)
* ユーザーがレポートを変更できないエラーを修正しました。 (CAMP-42505)
