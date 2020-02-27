---
title: 最新リリース
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
source-git-commit: 14f764b92fef81c06551fb0f13b11b41e94095f0

---


# 最新リリース{#latest-release}

[リリース計画](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |コント [ロールパネルのリリース](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |ドキュ [メントの更新](../../rn/using/documentation-updates.md) |以前の [リリースノート](../../rn/using/release-notes-2019.md) |非推 [奨の機能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## リリース20.1.3 - 2020年2月 {#release-20-1-3---february-2020}

* 20.1でCAMP-39273によって導入された、ループホールを使用するお客様の回帰の問題を修正しました。 39273年、キャンプを取り消した。

## リリース20.1.2 - 2020年2月 {#release-20-1-2---february-2020}

**電子メールデザイナーの機能強化**

* パッチを適用してコンテンツを保存する際に、古いフラグメントにHTMLタグ要素が追加される問題を修正しました。 (CAMP-40685)
* 動的コンテンツを使用する際にスペースが追加される問題を修正しました。 (CAMP-40605)
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
   <td> <p>Adobe Experience Platform Data Connectorは、Adobe Campaign Standardと統合されました。 XTKデータ（Campaignで取り込んだデータ）をAdobe Experience Platform Data Model(XDM)にマッピングすることで、Adobe Experience Platformでキャンペーンデータを利用できるようにできます。 </p>
    <p>この機能は、Azureでホストされている顧客のみが使用できることに注意してください。 この機能とアクティブ化の条件について詳しくは、詳細なドキュメント <a href="../../administration/using/aep-about-data-connector.md">とハウツー</a> ・ビデオ <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">を参照してください</a>。</p>
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
    <p>この機能は、Azureでホストされている顧客のみが使用できることに注意してください。 この機能とアクティブ化の条件について詳しくは、詳細なドキュメント <a href="../../audiences/using/aep-about-audience-destinations-service.md">とハウツー</a> ・ビデオ <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">を参照してください</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**強化点**

* 拡張MTAのグローバルな可用性：メッセージ（トランザクションメッセージを含む）がAdobe Campaign Enhanced MTAによって送信されるようになりました。これにより、配信品質、スループットおよびバウンス処理を向上させるためのアップグレードされた送信インフラストラクチャが提供されます。 [詳細を表示](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* タイムゾーン管理が強化されました。 ワークフロー全体に対して特定のタ [イムゾーンを定義で](../../automating/using/building-a-workflow.md) きるようになりました。 選択したタイムゾーンが、すべてのワークフローのアクティビティに適用されます。 オペレーターまたはサーバーに対して設定されたタイムゾーンに関する情報が、インターフェイスに（ログに）表示され、タイムゾーンを選択した後に)表示されるようになりました。 (CAMP-37672)

* キャンペーン標準APIで、呼び出しURLにパラメーターを追加することで、大きなテーブルを使用する場合にページネーションを実 `_forcePagination=true` 行できるようになりました。 [詳細を表示](../../api/using/pagination.md)

* 配信ログID（各ログの一意の識別子）が、すべてのターゲットディメンションの配信ログおよび追跡ログのリソースで使用できるようになりました。 これにより、例えば書き出し時に送信ログや追跡ログを識別できます。 [詳細を表示](../../automating/using/exporting-logs.md)

**電子メールデザイナーの機能強化**

* オーディエンスの作成時に、足りない必須テキストの説明を追加しました。
* レガシー電子メールエディターのウィザードで **「コンテンツを変更** 」ボタンをクリックすると発生していた問題を修正しました。
* サービスの概要レポートのコンテンツにヘッダーを合わせることができない問題を修正しました。 (CAMP-38103)
* 件名行の残りの部分に影響を与えることなく動的コンテンツバリアントを削除できない問題を修正しました。 (CAMP-40096)
* 件名行でBバリアントを使用する場合のA/Bテストの問題を修正しました。 (CAMP-40327)
* HTMLの読み込みをアップロード機能を使用すると、ファイルをドラッグ&amp;ドロップできない問題を修正しました。 (CAMP-39326)
* テキストエディターからテキストをコピーして貼り付けできない問題を修正しました。 (CAMP-39028)
* サーチクエリが表示されない問題を修正しました。 (CAMP-38970)
* ユーザーがフラグメントを保存できない問題を修正しました。 (ATU-2447)
* 動的構造を複製できない問題を修正しました。 (CAMP-38367)
* 動的コンテンツを複製した場合に、条件が保持されない問題を修正しました。 (CAMP-39051)

**その他の変更**

* 「準備が失敗した配信」フィルターで、配信の作成日が最終変更日ではなく考慮されるようになりました。
* Administratorsセキュリティグループの組織単位は変更できなくなりました。
* プロファイルを作成する場合は、「組織単位」フィールドに入力する必要があります。
* Experience cloudトリガーは、イベントと、そのイベントにリンクされているトランザクションテンプレートの両方が削除された場合にのみ削除できるようになりました。
* Adobe Creative SDKは廃止されました。 Campaign Standardでは廃止されました。 廃止および削 [除された機能のページを参照](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)。


**パッチ**

* プライバシーの削除要求を実行すると、ユーザーデータが除外ログで削除されない問題を修正しました。 (CAMP-39003)
* コンテナ要素内のテキストのサイズを変更するとアクセシビリティの問題が発生する問題を修正しました。
* マーケティングアクティビティでカーソルを合わせたときに表示されるカレンダーポップアップをユーザーが閉じられない問題を修正しました。
* データが変更されていない場合で **[!UICONTROL External API]** もボタンが表示されるア **[!UICONTROL Confirm]** クティビティの問題を修正しました。
* 異なるターゲットディメンションを持つクエリ **[!UICONTROL Union]** ーでアクティビティを使用する場合の問題を修正しました。 移行データには、メインセットのターゲットディメンションのレコードのみが表示されました。 (CAMP-36831)
* 特定のコンテキストでアクティビティを使用する場合、例えば2つの受信アクティビティを使用する場合に、そのうち1つが除外アクティビティであるというエラーが発生する可能性がある問題を修正しました。 **[!UICONTROL Reconciliation]** (CAMP-37490)
* テストプロファイルを選択して更新する際に発生する可能性があるパフォーマンスの問題を修正しました。 (CAMP-37976)
* ランディングページを購読または購読解除する際にエラーページが表示される問題を修正しました。 (CAMP-37771)
* HTMLで参照されているPNGファイルを大文字で拡張子と共にZIP形式でコンテンツをアップロードする際に発生していた問題を修正しました。 (CAMP-37913)
* テストプロファイルを配信に追加する際に、アプリ内メッセージが送信されない問題を修正しました。
* エンリッチメントアクティビティにリンクされている場合に失敗するExternal APIワークフローアクティビティのエラーを修正しました。
* SMSメッセージのステータスが正しく表示されない問題を修正しました。
* カスタムリソースで、異なるAPIエンドポイントの下に重複したエントリが表示される問題を修正しました。
* 投稿後にランディングページを使用できない問題を修正しました。 (CAMP-38695)
* 2つの異なるリソースからの交差トランジションのデータを表示する際に発生していたバグを修正しました。 (CAMP-38974)
* 配信テンプレートの列挙値が正しく設定されない問題を修正しました。 (CAMP-38388)
* 電子メールの一括配信で、配信の状態が「保留」、送信済みのステータスが「完了」と表示されるエラーを修正しました。 (CAMP-35355)
* 動的レポートで送信者ドメインが正しく表示されないエラーを修正しました。 (CAMP-33123)
* 動的レポートで、購読解除数に相違が生じる問題を修正しました。 (CAMP-39949)
* アプリ内メッセージを送信する際に、アドレスがログの送信画面に表示されない問題を修正しました。
* SMS送信ログが正しいバウンス数で更新されない問題を修正しました。 (CAMP-38395)
* アプリケーションのサブスクリプションPOST呼び出しでプッシュ通知トークンを更新できるループホールを修正しました。 (CAMP-39273)
