---
title: リリースノート 2020
description: このページでは、2020年リリースのすべてのリストAdobe Campaign標準を説明します。
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
source-git-commit: d0dde3a445c7047d97c3612b284b9bad36f71539

---


# リリースノート 2020{#release-notes-2020}

[リリース計画](https://helpx.adobe.com/jp/campaign/kb/acs-release-planning.html) |コント [ロールパネルのリリース](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html) |ドキュメ [ントの更新](../../rn/using/documentation-updates.md) |以前の [リリースノート](../../rn/using/release-notes-2019.md) |非推 [奨の機能](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)

## リリース20.2 - 2020年4月 {#release-20-2---april-2020}

**新機能?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob統合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure BLOBストレージコネクタを使用して、ファイル転送ワークフローを使用してAdobe Campaignにデータをインポートまたはエクスポートで <strong>きる</strong> アクティビティ。 </p>
    <p>詳しくは、<a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">詳細ドキュメント</a>を参照してください。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>ターゲットを設定したプロファイル</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>テストプロファイルに加えて、実際のターゲット設定されたプロファイルで電子メールをテストできます。 これにより、メッセージが受信される正確なメッセージをプロファイルが取得できます。カスタムフィールド、動的なパーソナライズされた情報(ワークフローなどの追加データを含む) </p>
    <p>詳しくは、<a href="../../sending/using/testing-messages-using-target.md">詳細ドキュメント</a>および<a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">チュートリアルビデオ</a>を参照してください。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>4月に、Google TXTレコード管理、キャンペーン領域の監視、電子メール通知など、データベースコントロールパネルに新しい機能がリリースされます。 これらの機能の詳細については、「コントロールパネルのリリ [ースノート」を参照してくださ](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html)い。

**強化点**

* トランザクションメッセージングのユーザーエクスペリエンスが強化され、インターフェイスの一貫性が向上しました。 [詳細を表示](../../channels/using/about-transactional-messaging.md)
* Campaign Standardでは、配達確認から追加のデータを使用して、テストプロファイルにワークフローを送信できます。
* 外部APIアクティビティのガードレールが更新されました。 [詳細を表示](../../automating/using/external-api.md)

**電子メールデザイナーの機能強化**

* パーソナライズされた画像を複数回クリックした場合のエスケープに影響する問題を修正しました。
* ダイナミックテキストコンポーネントを複製すると、太い線が複製される問題を修正しました。 (CAMP-41249)
* Outlookでdivレベルではなくテーブルレベルでパディングを定義する際のパディングの問題を修正しました。
* HTMLモードに切り替えると画像の幅が変更される問題を修正しました。 (CAMP-41116)
* アイコンに代替テキストを指定する際に、ソーシャルメディアコンポーネントにアクセスできなかった問題を修正しました。 (CAMP-41345)
* 電子メールデザイナーでコピー `<br>` ペーストを使用すると表示タグが表示される問題を修正しました。
* HTMLコンテンツからプレーンテキストに切り替えた後、HTMLタグが電子メールに表示される問題を修正しました。 (CAMP-41138)
* 境界線が1つだけ定義されたボタンをレンダリングできない問題を修正しました。
* Microsoft Outlookで、電子メールのフッターが左に移動するHTMLインデントの問題を修正しました。 (CAMP-40987)
* プレーンテキストモードに切り替えると、HTMLで定義されたコレクション属性をターゲットとするパーソナライゼーションフィールドがプレーンテキストコンテンツ内でコピーされる問題を修正しました。 (CAMP-40365)
* 選択したテキストセグメントにリンクが挿入されない問題を修正しました。 (CAMP-41406)
* タイムゾーンエディターでタイムゾーンを選択すると日付が変更される問題をクエリしました。 (CAMP-38277)

**その他の変更**

* Adobe Analytics **** （標準搭載）とのKPIの調整は、現在の日付まで実行され、1日のみ実行されるのではなく、実行されるようになりました。
* MCPNSは、APNSとAPNS-SANDBOXの両方をアプリ内のプラットフォームとして追加する機能をサポートしていません。 Adobe Campaign標準で証明書を正常に追加すると、MCPNSアプリに追加できるAPNSプラットフォーム（実稼動またはサンドボックス）が1つだけなので、設定を変更できなくなります。

**エクスペリエンスプラットフォームの統合**

>[!NOTE]
>
>Campaign StandardのAdobe Experience Platform機能は現在ベータ版で、予告なく頻繁に更新される場合があります。 詳細なドキュメントを参照してください。Experience Platform Data Connector [、](../../administration/using/aep-about-data-connector.md)[オーディエンス先](../../audiences/using/aep-about-audience-destinations-service.md)

* ワークフローログで、10分ごとに、キャンペーンは、現在実行中のジョブによって処理済みのレコード数を表示するようになりました。
* データベースから削除されたAdobe Experience Platformデータベースを読み込む際に発生するプロファイルの問題を修正しました。
* ワークフローログで、インポートされたレコードの合計数に対して誤った結果が表示される問題を修正しました。

**パッチ**

* 「 **Alias** 」フィールドにスペースを追加し、新しい行項目を作成すると発生する可能性がある **エンリッチメント** ・ワークフローのアクティビティの問題を修正。 (CAMP-39229)
* メッセージの送信時にすべてのテストプロファイルをターゲットにできる問題を配達確認しました。
* 公開の取り消しと削除の後に発生していたイベント設定の問題を修正。 [詳細を表示](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* ワークフローを変更すると「保存 **** 」ボタンが消える問題を修正しました。
* プライバシー要求を処理した後にキャンペーンで手動で削除すると、クリーンアップ後も要求に関連付けられたデータが削除されない問題を修正しました。
* Adobe Experience Managerから特殊文字を含むメッセージをプレビューまたは送信する際に発生する可能性がある問題を修正しました。
* 複数の受信トランジションを使用してワークフローを実行するとアクティビティが発生する問題を修正しました。
* 標準ユーザーがワークフロークエリまたは配信で、「購読からアプリへのアプリケーション」をターゲットディメンションとして使用できない問題を修正しました。 (CAMP-37618)

## リリース20.1.4 - 2020年2月 {#release-20-1-4---february-2020}

* 既存のアクティビティで読み取りオーディエンス **** (Read Activity)を開く際の問題を修正しました。 (CAMP-41002)

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
   <td> <p>Adobe Experience Platform Data Connectorは、Adobe Standardと統合されました。Adobe Campaign標準。 XTKデータ(キャンペーンで取り込まれたデータ)をAdobe Experience Platform Data Model(XDM)にマッピングすることで、キャンペーンデータをAdobe Experience Platformで使用できるようにすることができます。 </p>
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
   <td> <p>オーディエンスの宛先を使用すると、Adobe Experience PlatformのセグメントをAdobe Campaignで共有できます。</p>
    <p>この機能は、Azureでホストされている顧客のみが使用できます。 この機能とアクティブ化の条件について詳しくは、詳細なドキュメント <a href="../../audiences/using/aep-about-audience-destinations-service.md">とハウツー</a> ・ビデオ <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">を参照してください</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**強化点**

* 拡張MTAのグローバルな可用性：メッセージ(トランザクションメッセージを含む)は、Adobe Campaign拡張MTAによって送信されるようになりました。このMTAは、配信品質、スループット、バウンス処理を改善するためのアップグレードされた送信インフラストラクチャを提供します。 [詳細を表示](https://helpx.adobe.com/jp/campaign/kb/campaign-enhanced-mta.html)

* タイムゾーンの管理が強化されました。 ワークフロー全体の特定のタイムゾーン [を定義できる](../../automating/using/building-a-workflow.md) ようになりました。 選択したタイムゾーンが、すべてのワークフローのアクティビティに適用されます。 オペレータまたはサーバーに対して設定されたタイムゾーンに関する情報が、インターフェイスに（ログ内で、タイムゾーンを選択した後で）表示されるようになりました。 (CAMP-37672)

* Campaign StandardAPIを使用すると、呼び出しURLにパラメーターを追加することで、大きなテーブルを使用する際にページネ `_forcePagination=true` ーションを実行できるようになりました。 [詳細を表示](../../api/using/pagination.md)

* 配信ログID（各ログの一意の識別子）が、すべての配信ログのトラッキングログリソースで使用できるようになりました。 これにより、例えば書き出し時に送信またはトラッキングログを識別できます。 [詳細を表示](../../automating/using/exporting-logs.md)

**電子メールデザイナーの機能強化**

* 必須のテキストの説明が見つからない場合に、説明を追加してオーディエンスしました。
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

* 「準備が失敗した配信」フィルターで、最後の変更日ではなく、配信の作成日が考慮されるようになりました。
* Administratorsセキュリティグループの組織単位は変更できなくなりました。
* これで、プロファイルを作成する際に、[組織単位]フィールドに入力する必要があります。
* Experience Cloudトリガーを削除できるのは、イベントと、そのテンプレートにリンクされているトランザクションテンプレートの両方が削除された場合のみです。
* Adobe Creative SDKは廃止されました。 現在は、廃止されています。Campaign Standard 廃止および削 [除された機能のページを参照](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)。


**パッチ**

* プライバシーの削除要求を実行すると、ユーザーデータが除外ログで削除されない問題を修正しました。 (CAMP-39003)
* 要素要素内のテキストのサイズを変更する際にアクセシビリティの問題が発生するコンテナを修正しました。
* マーケティングアクティビティにカーソルを合わせたときに表示されるカレンダーポップアップをユーザーが閉じられない問題を修正しました。
* データが変更されない場合でも **[!UICONTROL External API]** アクティビティにボタンが表 **[!UICONTROL Confirm]** 示される問題を修正しました。
* 異なるクエリサイズでアクティビティを使用する場合の問題を修 **[!UICONTROL Union]** 正しました。ターゲットのサイズが異なる トランジションデータには、メインセットのレコードのみが表示されていました。ターゲティングディメンション (CAMP-36831)
* 特定のコンテキストでアクティビティを使用する場合、例えば2つの受信アクティビティを使用する場合に、そのうち1つが除外アクティビティとしてエラーが発生する可能性がある問題を修正しました。 **[!UICONTROL Reconciliation]** (CAMP-37490)
* テストオプションを選択して更新する際に発生する可能性があるパフォーマンスの問題を修正しました。プロファイル (CAMP-37976)
* 購読または購読解除時にエラーページが表示される問題を修正しました。ランディングページを使用して (CAMP-37771)
* HTMLで参照されているPNGファイルを大文字の拡張子でZIP形式でアップロードする際に発生していた問題を修正しました。 (CAMP-37913)
* テストメッセージをアプリに追加すると、アプリ内メッセージが送信されないプロファイルの問題を修正しました。
* 外部APIワークフローアクティビティがワークフローワークフローにリンクされている場合に失敗するエラーをエンリッチメントアクティビティ。
* SMSメッセージのステータスが正しく表示されない問題を修正しました。
* カスタムリソースで、異なるAPIエンドポイントの下に重複エントリが表示される問題を修正しました。
* 投稿後にランディングページを利用できない問題を修正しました。 (CAMP-38695)
* 2つの異なるリソースからのデータを積集合トランジションから表示する際に発生していた問題を修正しました。 (CAMP-38974)
* 配信テンプレートの定義済みリスト値が正しく設定されない問題を修正しました。 (CAMP-38388)
* 電子メールのバルク配信で、配信の状態が「保留」、送信済みステータスが「完了」と表示されるエラーを修正しました。 (CAMP-35355)
* 動的ドメインで送信者ドメインが正しく表示されないエラーを修正しました。レポート (CAMP-33123)
* 動的なレポートで購読解除数が一致しない問題を修正しました。 (CAMP-39949)
* アプリ内メッセージを送信する際に、アドレスがログを送信画面に表示されない問題を修正しました。
* SMS送信ログが正しいバウンス数で更新されない問題を修正しました。 (CAMP-38395)
* プッシュ通知トークンを更新するアプリケーション購読のpost呼び出しが許可されていたループホールを修正しました。 (CAMP-39273)
