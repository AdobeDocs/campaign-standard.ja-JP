---
title: 最新リリース
description: このページには、Adobe Campaign Standard の最新リリースがすべて記載されています。
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
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 90%

---


# 最新リリース{#latest-release}

[リリース計画](../../rn/using/release-planning.md) | [コントロールパネルのリリース](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html) | [ドキュメントの更新](../../rn/using/documentation-updates.md) | [以前のリリースノート](../../rn/using/release-notes-2020.md) | [非推奨（廃止予定）の機能](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **新しいコントロールパネル 6 月のリリース** - アクティブなプロファイルの監視、サブドメイン配信品質の監査、GPG キー管理。[詳細情報](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html)。

## リリース 20.3 - 2020 年 5 月 {#release-20-3---may-2020}

**新機能**

<table> 
<thead> 
<tr> 
<th> <strong>タイの個人データ保護法（PDPA）</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>タイの個人データ保護法（PDPA）は、タイのデータ保護要件を調整および最新化するための新しいプライバシー法です。この規制は、タイに居住するデータ主体のデータを保有している Adobe Campaign のお客様に適用されます。</p>
<p>Adobe Campaign で既に利用可能なプライバシー機能（同意管理、データ保持設定、ユーザーの役割など）に加え、PDPA への対応をサポートするための機能を追加する予定です。</p>
<ul>
<li>アクセス権と削除権：GDPR および CCPA 用に追加された機能を活用します。<a href="https://helpx.adobe.com/content/help/jp/campaign/kb/acs-privacy.html#righttoaccess">さらに詳しく</a> </li>
<li><p>プライバシーリクエストを作成する際に、PDPA 規制タイプが Privacy コアサービスに追加されました。すべてのアクセス要求と削除要求に対して、このメソッドを使用する必要があります。アクセス要求および削除要求に対する Campaign API およびインターフェイスの使用は廃止されています。<a href="../../rn/using/deprecated-features.md">廃止および削除された機能の記事</a>を参照してください。</p></li>
</ul>
<p><a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">ハウツービデオ</a>を参照してください。</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>外部 API アクティビティ（GA）</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p><strong>外部 API</strong> アクティビティは、ベータ版から GA に移行中です。このリリースでは、JSON 応答本文パーサーがより柔軟になっています。次が可能になりました。</p>
<ul>
<li>最大深度が 10 のネストされた JSON を解析する。 </li>
<li>選択したプロパティを JSON のリーフノードとして解析し、統合して 1 つのテーブル行にする。</li>
<li>オブジェクトに「data」という名前を付けたり、最上位レベルに配置したりする必要なく、JSON から配列オブジェクトを選択して使用する。</li>
</ul>
<p><strong>注意：</strong><strong>すべてのベータ版外部 API アクティビティを、ワークフロー内の GA 外部 API アクティビティで置き換える必要があります</strong>。ベータ版の外部 API を使用するワークフローは、20.3 以降では動作しなくなります。</p>
<p>詳しくは、<a href="../../automating/using/external-api.md">詳細ドキュメント</a>および<a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">ハウツービデオ</a>を参照してください。</p>
</td> 
</tr> 
</tbody> 
</table>

**その他の機能** （7月13日より開始）

* **AIを利用した送信時間の最適化とプロファイルスコアリング** — お客様のジャーニーの設計と配信を最適化して、個々の関与の優先度を予測できるようになりました。 Adobe Campaignは、遍歴AIを基にして、過去の関与指標に基づいて、オープン率、最適な送信時間および確率変化を分析し、予測できます。 [詳細情報](../../sending/using/predictive.md)
* **ブラジルの新しいプライバシー規制** -キャンペーンで既に提供されているプライバシー機能に加え、AdobeはブラジルのLei Geral de Proteçao de Datos (LGPD)に対する準備を促進します。 プライバシーの要請を作成する際、LGPD規則がAdobeプライバシーコアサービスに追加されました。 [詳細情報](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy-overview.html)

**強化点**

* ターゲット設定された[プロファイル](../../sending/using/testing-messages-using-target.md)を使用してメッセージをテストする際に、「**Prefix**」フィールドで使用できる文字数が 32 文字から 500 文字に増えました。
* インスタンスに公開できるリアルタイムイベントの最大数が 350 から 2000 に増えました。（CAMP-41608）
* Adobe Launch と Campaign Standard の同期が、syncWithLaunch テクニカルワークフローを使用して改善されました。このワークフローにより、Adobe Launch のすべてのモバイルプロパティを Adobe Campaign Standard に自動インポートできます。詳しくは、[このページ](../../administration/using/technical-workflows.md)を参照してください。

   お使いの Campaign インスタンスで syncWithLaunch テクニカルワークフローを有効にするには、チケットをアドビカスタマーケアに（直接またはアドビの担当者を通じて）送信する必要があります。（CAMP-40082）

**E メールデザイナーの機能強化**

* E メールデザイナーは、厳密な W3C よりも柔軟な HTML 形式設定を処理できるようになりました。（CAMP-42529）
* [クリック可能な画像](../../designing/using/links.md#inserting-a-link)に関して、コンテンツブロック内の画像の横にリンクが表示されない問題を修正しました。（CAMP-41586）
* [トラッキングされる URL](../../designing/using/links.md#about-tracked-urls) のテンプレートにカテゴリが追加されている場合に、ランディングページにリダイレクトできない問題を修正しました。（CAMP-41537）
* Outlook でのボタンのパディングの問題を修正しました。
* HTML タグがプレーンテキストで表示される問題を修正しました。
* コンテンツブロック検索で、サーバーの検索結果とプリロードされた結果が表示されるようになりました。（CAMP-41870）

**その他の変更**

* カスタムリソースの公開インターフェイスが改善され、より明確なエラーメッセージが表示されるようになりました。
* 未使用の配信マッピングがインターフェイスから削除されました。
* 不要な管理者の役割がインターフェイスから削除されました。
* ランディングページでチェックボックスを必須にできるようになりました。
* 動的レポートの CSV ファイルをダウンロードする場合、200 行までという制限がなくなりました。レポートのすべての行を含めることができるようになりました。（CAMP-40810）
* 多言語の E メール用の標準言語リストに ES-US が追加されました。（CAMP-42279）
* ファイル転送アクティビティでダウンロードされたファイルは、X 日後に削除されるようになりました。X は、ワークフロープロパティの **Execution** メニューの「**History in days**」フィールドによって決定されます。[詳細を表示](../../automating/using/managing-execution-options.md)

**Experience Platform との統合**

* 「**Read audience**」アクティビティからの Adobe [Experience Platform オーディエンス](../../automating/using/aep-targeting-audiences.md)のアクティベーションが改善され、パフォーマンスと安定性が向上しました。さらに、アクティベーションジョブに関するワークフローログがより明確で詳細になり、Adobe Experience Platform オーディエンスを閲覧する際の監視とトラブルシューティングが容易になりました。

**パッチ**

* カスタムリソースの公開ジョブ中にゴーストリソースが作成される原因となっていたエラーを修正しました。
* プロファイルリソースがカスタムリソースを使用して拡張された場合に、プロファイルのマーケティング履歴が表示されない可能性がある問題を修正しました。（CAMP-41009）
* 標準ランディングページテンプレートで、エディターを開いたときにコンテンツがフランス語で表示される問題を修正しました。（CAMP-41639）
* 動的コンテンツを含むプッシュ通知で、絵文字の表示を妨げる可能性がある問題を修正しました。（CAMP-40715）
* アウトバウンド補集合トランジションの 1 つに間違ったセグメントコードが割り当てられる原因となる「**Deduplication**」アクティビティの問題を修正しました。（CAMP-41400）
* スケジュールされたレポートを削除できないエラーを修正しました。（CAMP-41302）
* 配信のダッシュボードと **Delivery Summary** レポートに矛盾が生じる問題を修正しました。（CAMP-41145）
* ダウンロードしたレポートで文字が重なって表示される問題を修正しました。
* 配信のプレビューが配達確認の置き換えで機能しない問題を修正しました。
* アプリ内ローカル通知のカスタムフィールドを削除する際のエラーを修正しました。
* charIndex 関数がワークフローの「**End**」アクティビティや「**File transfer**」アクティビティで動作しない問題を修正しました。
* リンクされているターゲットリソースを含む 2 つの入力アクティビティで「**Enrichment**」アクティビティを使用すると発生する可能性があるワークフローの問題を修正しました。（CAMP-42133）
* 不明な関数を使用する場合に、ワークフローが実行されない可能性がある問題を修正しました。（CAMP-41873）
* アウトバウンド補集合トランジションを伴う複数の「**Save audience**」アクティビティを使用してオーディエンスを作成する場合に発生する可能性があるワークフローの問題を修正しました。（CAMP-39992）
* トランザクション E メールでパーソナライズ機能を使用するとデータに矛盾が生じる問題を修正しました。（CAMP-41842）
* プッシュ通知配信のカスタムフィールドを削除する際に発生していた問題を修正しました。（CAMP-37586）
* ユーザーがレポートを変更できないエラーを修正しました。（CAMP-42505）


![](assets/do-not-localize/cp-icon.png) **新しいCampaign コントロールパネル5月** 、CNAMEサブドメインの証明書の更新を含む [詳細情報](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html)。
