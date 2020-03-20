---
title: 最新のリリースノート2020
description: このページには、Adobe Campaign Standardの最新リリースがすべて表示されます。
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
source-git-commit: a6b0dd550dc0f6815cbf25f03fd199f4105de9c3

---


# 最新リリース{#latest-release}

[リリース計画](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |コント [ロールパネルのリリース](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |ドキュメ [ントの更新](../../rn/using/documentation-updates.md) |以前の [リリースノート](../../rn/using/release-notes-2019.md) |非推 [奨の機能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## リリース20.1.4 - 2020年2月 {#release-20-1-4---february-2020}

* 既存のワークフローでオーディエンスを読み取 **りアクティビティ** を開く際の問題を修正しました。 (CAMP-41002)

## リリース20.1.3 - 2020年2月 {#release-20-1-3---february-2020}

* ループホールを使用するお客様に対してCAMP-39273によって20.1で発生していた回帰の問題を修正しました。 39273年、キャンプを取り消された。

## リリース20.1.2 - 2020年2月 {#release-20-1-2---february-2020}

**電子メールデザイナーの機能強化**

* パッチを適用してコンテンツを保存する際に、古いフラグメントにHTMLタグ要素が追加される問題を修正しました。 (CAMP-40685)
* 動的コンテンツを使用するとスペースが追加される問題を修正しました。 (CAMP-40605)
* トランザクション電子メールテンプレートを設定する際の問題を修正しました。 (CAMP-40604)

## リリース20.1 - 2020年2月 {#release-20-1---february-2020}

**新機能?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector（ベータ版）</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connectorは、Adobe Campaign Standardと統合されました。 XTKデータ（Campaignで取り込まれたデータ）をAdobe Experience Platform Data Model(XDM)にマッピングすることで、Adobe Experience Platformでキャンペーンデータを利用できるようにすることができます。 </p>
    <p>この機能は、Azureでホストされている顧客のみが使用できます。 この機能とアクティブ化の条件について詳しくは、詳細なドキュメント <a href="../../administration/using/aep-about-data-connector.md">とハウツー</a> ・ビデオ <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">を参照してください</a>。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>オーディエンスの宛先（ベータ） </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>オーディエンスの宛先を使用すると、Adobe Experience PlatformからAdobe Campaignにセグメントを共有できます。</p>
    <p>この機能は、Azureでホストされている顧客のみが使用できます。 この機能とアクティブ化の条件について詳しくは、詳細なドキュメント <a href="../../audiences/using/aep-about-audience-destinations-service.md">とハウツー</a> ・ビデオ <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">を参照してください</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**強化点**

* 拡張MTAのグローバルな可用性：メッセージ（トランザクションメッセージを含む）がAdobe Campaign Enhanced MTAによって送信されるようになりました。これにより、配信品質、スループットおよびバウンス処理を改善するためのアップグレードされた送信インフラストラクチャが提供されます。 [詳細を表示](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* タイムゾーンの管理が強化されました。 ワークフロー全体の特定のタイムゾーン [を定義できる](../../automating/using/building-a-workflow.md) ようになりました。 選択したタイムゾーンが、すべてのワークフローのアクティビティに適用されます。 オペレータまたはサーバーに対して設定されたタイムゾーンに関する情報が、インターフェイスに（ログ内で、タイムゾーンを選択した後で）表示されるようになりました。 (CAMP-37672)

* キャンペーン標準APIで、呼び出しURLにパラメーターを追加することで、大きなテーブルを使用する場合にページネーシ `_forcePagination=true` ョンを実行できるようになりました。 [詳細を表示](../../api/using/pagination.md)

* 配信ログID（各ログの一意の識別子）が、すべてのターゲットディメンションの配信ログおよび追跡ログのリソースで使用できるようになりました。 これにより、例えばエクスポート時に送信ログや追跡ログを識別できます。 [詳細を表示](../../automating/using/exporting-logs.md)

**電子メールデザイナーの機能強化**

* オーディエンスの作成時に、欠落している必須のテキスト手順を追加しました。
* 従来の電子メールエディターのウィザードで **「コンテンツを変更** 」ボタンをクリックすると発生していた問題を修正しました。
* サービスの概要レポートで、ヘッダーがコンテンツと一致しない問題を修正しました。 (CAMP-38103)
* 件名行の残りの部分に影響を与えることなく、動的コンテンツバリアントを削除できなかった問題を修正しました。 (CAMP-40096)
* 件名行でBバリアントを使用する場合のA/Bテストの問題を修正しました。 (CAMP-40327)
* HTMLの読み込みをアップロード機能を使用すると、ファイルをドラッグ&amp;ドロップできない問題を修正しました。 (CAMP-39326)
* テキストエディターからテキストをコピーして貼り付けできない問題を修正しました。 (CAMP-39028)
* サーチクエリが表示されない問題を修正しました。 (CAMP-38970)
* ユーザーがフラグメントを保存できない問題を修正しました。 (ATU-2447)
* 動的構造が複製できない問題を修正しました。 (CAMP-38367)
* 動的コンテンツが複製時に条件を保持できない問題を修正しました。 (CAMP-39051)

**その他の変更**

* 「準備が失敗した配信」フィルターで、配信の作成日が最終変更日ではなく考慮されるようになりました。
* Administratorsセキュリティグループの組織単位は変更できなくなりました。
* プロファイルを作成する場合、「組織単位」フィールドに入力する必要があります。
* Experience Cloudトリガーは、イベントと、そのイベントにリンクされているトランザクションテンプレートの両方が削除された場合にのみ削除できるようになりました。
* Adobe Creative SDKは廃止されました。 Campaign Standardでは廃止されました。 廃止および削 [除された機能のページを参照](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。


**パッチ**

* プライバシーの削除要求を実行すると、ユーザーデータが除外ログで削除されない問題を修正しました。 (CAMP-39003)
* コンテナ要素内のテキストのサイズを変更する際にアクセシビリティの問題が発生する問題を修正しました。
* マーケティングアクティビティでカーソルを合わせたときに表示されるカレンダーポップアップをユーザーが閉じられない問題を修正しました。
* データが変更されない場合で **[!UICONTROL External API]** もボタンが表示されるア **[!UICONTROL Confirm]** クティビティの問題を修正しました。
* 異なるターゲットディメンションを持つクエ **[!UICONTROL Union]** リーでアクティビティを使用する場合の問題を修正しました。 移行データには、メインセットのターゲットディメンションのレコードのみが表示されました。 (CAMP-36831)
* 2つの受信アクティビティを除外アクティビティとして扱う場合など、特定のコンテキストでアクティビティを使用する **[!UICONTROL Reconciliation]** とエラーが発生する可能性がある問題を修正しました。 (CAMP-37490)
* テストプロファイルを選択して更新する際に発生する可能性があるパフォーマンスの問題を修正しました。 (CAMP-37976)
* ランディングページを購読または購読解除する際にエラーページが表示される問題を修正しました。 (CAMP-37771)
* HTMLで参照されているPNGファイルを大文字の拡張子でZIP形式でアップロードする際に発生していた問題を修正しました。 (CAMP-37913)
* テストプロファイルを配信に追加する際に、アプリ内メッセージが送信されない問題を修正しました。
* エンリッチメントアクティビティにリンクされている場合に失敗するExternal APIワークフローアクティビティのエラーを修正しました。
* SMSメッセージのステータスが正しく表示されない問題を修正しました。
* カスタムリソースで、異なるAPIエンドポイントの下に重複したエントリが表示される問題を修正しました。
* 投稿後にランディングページを使用できない問題を修正しました。 (CAMP-38695)
* 2つの異なるリソースからの交差トランジションのデータを表示する際に発生していた問題を修正しました。 (CAMP-38974)
* 配信テンプレートの列挙値が正しく設定されない問題を修正しました。 (CAMP-38388)
* 電子メールの一括配信で、配信の状態が「保留」、送信のステータスが「完了」と表示されるエラーを修正しました。 (CAMP-35355)
* 動的レポートで送信者ドメインが正しく表示されないエラーを修正しました。 (CAMP-33123)
* 動的レポートで、購読解除のカウントに不一致が生じる問題を修正しました。 (CAMP-39949)
* アプリ内メッセージを送信する際に、アドレスがログを送信画面に表示されない問題を修正しました。
* SMS送信ログが正しいバウンス数で更新されない問題を修正しました。 (CAMP-38395)
* アプリケーションのサブスクリプションPOST呼び出しでプッシュ通知トークンを更新できるループホールを修正しました。 (CAMP-39273)
