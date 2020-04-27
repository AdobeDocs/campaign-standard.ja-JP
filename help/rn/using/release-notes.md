---
title: 最新リリース
description: このページでは、リスト標準の最新リリースすべてをAdobe Campaignします。
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
source-git-commit: 86302762a46a814ecc9b14a5fe1bfe1a4a4e0437

---


# 最新リリース{#latest-release}

[リリース計画](../../rn/using/release-planning.md) |コント [ロールパネルのリリース](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html) |ドキュメ [ントの更新](../../rn/using/documentation-updates.md) |以前の [リリースノート](../../rn/using/release-notes-2020.md) |非推 [奨の機能](../../rn/using/deprecated-features.md)

## リリース20.3 - 2020年5月 {#release-20-3---may-2020}

**新機能?**

<table> 
<thead> 
<tr> 
<th> <strong>タイの個人データ保護法(PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>タイの個人データ保護法(PDPA)は、タイのデータ保護要件を調和・最新化する新しいプライバシー法。 本規則は、本国に居住するAdobe Campaignのデータ対象のデータを保持するデータをお客様に適用します。</p>
<p>既にAdobe Campaignで利用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割を含む）に加え、PDPAの準備を容易にするために、この機会に追加の機能を含めます。</p>
<ul>
<li>アクセス権と削除権：gdprとCCPAに追加された機能を活用しています。 <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">さらに詳しく</a> </li>
<li><p>プライバシーリクエストを作成する際に、PDPA規制タイプがプライバシーコアサービスに追加されました。 このメソッドは、すべてのアクセス要求と削除要求に使用する必要があります。 アクセス要求と削除要求に対するキャンペーンAPIとインターフェイスの使用は廃止されました。  廃止された機能 <a href="../../rn/using/deprecated-features.md">と削除された機能の記事を参照してくださ</a>い。</p></li>
</ul>
<p>ハウツービデ <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">オを参照</a>。</p>
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
  <td> <p>External API <strong>アクティビティは</strong> 、ベータ版からGAに移行中です。 このリリースでは、JSON応答本文パーサーに柔軟性をもたらします。 次の操作が可能になりました。</p>
<ul>
<li>最大深度が10レベルのネストされたJSONを解析します。 </li>
<li>選択したプロパティをJSONのリーフノードとして解析し、統合して1つのテーブル行にします。</li>
<li>オブジェクトに「data」という名前を付けたり、最上位レベルに配置したりすることなく、JSONから配列オブジェクトを選択して使用します。</li>
</ul>
<p><strong>注意：</strong> お客様は、ベータ版のExternal API <strong>アクティビティをすべて</strong> 、ワークフロー内のGA External APIアクティビティに置き換える必要があります。  ワークフローがベータ版のExternal APIを使用している場合、20.3では機能しなくなります。</p>
<p>詳しくは、<a href="../../automating/using/external-api.md">詳細ドキュメント</a>および<a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">ハウツービデオ</a>を参照してください。</p>
</td> 
</tr> 
</tbody> 
</table>

**強化点**

* ターゲットプロファイルを使用してメッセージをテストする **ために** 、「プレフィックス」フ [ィールドで使用できる文字数が](../../sending/using/testing-messages-using-target.md) 、32文字から500文字に増えました。
* インスタンスに対して発行できるリアルタイムイベントの最大数が350から2000に増加しました。 (CAMP-41608)

**電子メールデザイナーの機能強化**

* 電子メールデザイナーで、厳密なW3Cよりも柔軟なHTML形式設定を処理できるようになりました。 (CAMP-42529)
* クリック可能な画像がコン [テンツブロック内の](../../designing/using/links.md#inserting-a-link) 、画像の横にリンクが表示されない問題を修正しました。 (CAMP-41586)
* 追跡するURLにランディングページが追加されている場合に、テンプレ [ートにリダイレクト](../../designing/using/links.md#about-tracked-urls) カテゴリできない問題を修正しました。 (CAMP-41537)
* Outlookでのボタンのパディングの問題を修正しました。
* HTMLタグがプレーンテキストで表示される問題を修正しました。
* コンテンツブロックの検索で、サーバーの検索結果とプリロードされた結果が表示されるようになりました。 (CAMP-41870)

**その他の変更**

* エラーメッセージがより明確になるように、カスタムリソースの発行インターフェイスが改善されました。
* 未使用の配信マッピングがインターフェイスから削除されました。
* 不要な管理者の役割がインターフェイスから削除されました。
* チェックボックスを必須にできるようになりました。ランディングページ
* 動的レポートのCSVファイルをダウンロードする際に、200行の制限がなくなりました。 レポートのすべての行を含めることができるようになりました。 (CAMP-40810)
* 多言語電子メールの標準リストにES-US言語を追加。 (CAMP-42279)
* 「ファイルの転送」アクティビティを使用してダウンロードされたファイルは、X日後に削除されるようになりました。Xは、 **Workflowプロパティの** 「 **Execution** 」メニューの「History in days」フィールドで決定されます。 [詳細を表示](../../automating/using/executing-a-workflow.md#workflow-properties)

**エクスペリエンスプラットフォームの統合**

* 読み取りオーディエンス [アクティビティのAdobe](../../automating/using/aep-targeting-audiences.md) Experience Platformオーディエンス **のアクティベーションが改善され、パフォ** ーマンスと安定性が向上しました。 さらに、アクティベーションジョブに関するワークフローログがより明確で詳細になり、Adobe Experience Platformのオーディエンスを読む際の監視とトラブルシューティングが容易になりました。

**パッチ**

* カスタムリソースのパブリケーションジョブ中にゴーストリソースが作成される原因となっていたエラーを修正。
* カスタムリソースを使用してプロファイルリソースが拡張された場合に、プロファイルマーケティング履歴が表示されない問題を修正しました。 (CAMP-41009)
* エディターを開いたときに、標準搭載のランディングページテンプレートのコンテンツがフランス語で表示される問題を修正しました。 (CAMP-41639)
* 動的コンテンツを使用したプッシュ通知で、絵文字の表示が妨げられる問題を修正しました。 (CAMP-40715)
* アウトバウンド補完重複排除 - 重複の1つに **誤ったアクティビティが割り当てられる原因となっていた、** セグメントコードトランジションの問題を修正しました。 (CAMP-41400)
* 予定レポートを削除できないエラーを修正しました。 (CAMP-41302)
* 「配信の概要」レポートと「ダッシュボードの概要」レポートで不一致が発生する **配信** 。 (CAMP-41145)
* ダウンロードしたレポートで文字が重なって表示される問題を修正しました。
* 配信の置き換えで、プレビューが機能しない問題を修正しました。
* アプリ内ローカル通知のカスタムフィールドを削除する際のエラーを修正しました。
* charIndex関数がワークフローの **End** （終了）または **File(ファイル転送** )アクティビティで機能しない問題を修正しました。
* 2つの入力アクティビティ(リンクを持つワークフローリソースを含む)で **エンリッチメント** アクティビティを使用する場合に発生する可能性があるターゲットの問題を修正しました。 (CAMP-42133)
* 不明な関数を使用するとワークフローが実行できない問題を修正しました。 (CAMP-41873)
* 複数の「保存」ワークフローオーディエンスを使用してアクティビティを作成する際に発生する可能性があるの問題を修正し **ました** 。このオーディエンスは、外部トランジションを補完するものです。 (CAMP-39992)
* トランザクション電子メールでパーソナライゼーションを使用すると、データに相違が生じる問題を修正しました。 (CAMP-41842)
* プッシュ通知オプションでカスタムフィールドを削除する際に発生していた問題を修正しました。配信 (CAMP-37586)
* ユーザーがレポートを変更できないエラーを修正しました。 (CAMP-42505)
