---
title: リリースノート 2020
description: このページでは、2020年リリースのAdobe Campaign標準のすべてをリストしています。
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
source-git-commit: f4c6b74d9b80d80befed65d853cf82b32084c49d

---


# リリースノート 2020{#release-notes-2020}

[リリースの計画](https://helpx.adobe.com/jp/campaign/kb/acs-release-planning.html) | [コントロールパネルのリリース](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html) | [ドキュメントの更新](../../rn/using/documentation-updates.md) | [以前のリリースノート](../../rn/using/release-notes-2019.md) | [非推奨の機能](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)

## リリース20.2 - 2020年4月 {#release-20-2---april-2020}

**新機能**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob統合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure BLOBストレージコネクタを使用して、 <strong>転送ファイル</strong> ・ワークフロー・アクティビティを使用してAdobe Campaignにデータをインポートまたはエクスポートできるようになりました。 </p>
    <p>詳しくは、<a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">詳細ドキュメント</a>を参照してください。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>ターゲットプロファイルを使用した電子メールテスト</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>テストプロファイルに加えて、実際のターゲットプロファイルに対して電子メールをテストできるようになりました。 これにより、プロファイルが受け取るメッセージを正確に表示できます。 カスタムフィールド、動的およびパーソナライズされた情報(ワークフローなどの追加データを含む) </p>
    <p>詳しくは、<a href="../../sending/using/testing-messages-using-target.md">詳細ドキュメント</a>および<a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">チュートリアルビデオ</a>を参照してください。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Google TXTレコード管理、キャンペーン容量の監視、電子メールによる通知など、新しい機能が4月にデータベースコントロールパネルにリリースされます。 これらの機能の詳細については、「 [コントロールパネルリリースノート](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html)」を参照してください。

**強化点**

* トランザクションメッセージングのユーザーエクスペリエンスが強化され、インターフェイスの一貫性が向上しました。 [詳細を表示](../../channels/using/about-transactional-messaging.md)
* Campaign Standardで、ワークフローの追加データを使用して配達確認をテストプロファイルに送信できるようになりました。
* 外部APIアクティビティのガードレールが更新されました。 [詳細を表示](../../automating/using/external-api.md)

**電子メールデザイナーの機能強化**

* パーソナライズされた画像を複数回クリックした場合のエスケープに影響する問題を修正しました。
* 折れ線が複製される可能性のある動的テキストコンポーネントを複製する場合の問題を修正しました。 (CAMP-41249)
* divレベルではなく、テーブルレベルでパディングを定義する場合のOutlookでのパディングの問題を修正しました。
* HTMLモードに切り替えると画像の幅が変更される問題を修正しました。 (CAMP-41116)
* アイコンに代替テキストを指定する場合に、ソーシャルメディアコンポーネントにアクセスできない問題を修正しました。 (CAMP-41345)
* 電子メールデザイナーでコピーペーストを使用すると、表示されている `<br>` タグが表示される問題を修正しました。
* HTMLコンテンツからプレーンテキストに切り替えた後、電子メールにHTMLタグが表示される問題を修正しました。 (CAMP-41138)
* 境界線が1つだけ定義されたボタンをレンダリングできない問題を修正しました。
* Microsoft Outlookで電子メールのフッターが左に移動するHTMLインデントの問題を修正しました。 (CAMP-40987)
* プレーンテキストモードに切り替えると、HTMLで定義されたコレクション属性をターゲットとするパーソナライゼーションフィールドがプレーンテキストコンテンツ内でコピーされる問題を修正しました。 (CAMP-40365)
* 選択したテキストセグメントにリンクが挿入されない問題を修正しました。 (CAMP-41406)
* クエリエディターでタイムゾーンを選択した場合に日付が変更される問題を修正しました。 (CAMP-38277)

**その他の変更**

* Adobe Analytics **（標準）との** KPIの調整ワークフローは、1日ではなく現在の日付まで実行されるようになりました。
* MCPNSは、APNSとAPNS-SANDBOXの両方をアプリ内のプラットフォームとして追加することをサポートしていません。 Adobe Campaign標準で証明書が正常に追加されると、1つのAPNSプラットフォーム（実稼動またはサンドボックス）しかMCPNSアプリに追加できないので、設定を元に戻すことができなくなります。

**エクスペリエンスプラットフォームの統合**

>[!NOTE]
>
>Campaign StandardのAdobe Experience Platform機能は現在ベータ版です。この機能は予告なく頻繁にアップデートされる場合があります。 次の詳細なドキュメントを参照してください。 [エクスペリエンスプラットフォームデータコネクタ](../../developing/using/aep-about-data-connector.md)、 [オーディエンス先](../../audiences/using/aep-about-audience-destinations-service.md)

* ワークフローログで、10分ごとに、現在実行中のジョブで既に処理済みのレコード数がキャンペーンに表示されるようになりました。
* データベースから削除されたAdobe Experience Platformプロファイルを読み込むと発生する可能性がある問題を修正しました。
* ワークフローログで、インポートされたレコードの合計数に誤った結果が表示される問題を修正しました。

**パッチ**

* 「 **Alias** （エイリアス） **」フィールドにスペースを追加し、新しい行項目を作成した場合に発生する可能性がある、** エンリッチメント・ワークフローのアクティビティに関する問題を修正。 (CAMP-39229)
* 配達確認メッセージを送信する際にすべてのテストプロファイルがターゲットになる可能性がある問題を修正しました。
* イベント設定の非公開および削除後に発生していた問題を修正しました。 [詳細を表示](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* ワークフローに変更を加えると、「 **保存** 」ボタンが消える問題を修正しました。
* プライバシー要求の処理後、キャンペーンでプライバシー要求を手動で削除した場合に、その要求に関連付けられたデータがクリーンアップ後も削除されない問題を修正しました。
* Adobe Experience Managerから特殊文字を含むメッセージをプレビューまたは送信する場合に発生する可能性がある問題を修正しました。
* 複数の受信トランジションを使用してアクティビティを実行する場合にワークフローで発生する可能性がある問題を修正しました。
* 標準ユーザーがワークフロークエリーまたは配信で、「購読からアプリへのアクセス」をターゲットディメンションとして使用できない問題を修正しました。 (CAMP-37618)

## リリース20.1.4 - 2020年2月 {#release-20-1-4---february-2020}

* 既存のワークフローで **読み取りオーディエンス** (Read Activity)を開く際の問題を修正しました。 (CAMP-41002)

## リリース20.1.3 - 2020年2月 {#release-20-1-3---february-2020}

* 20.1でCAMP-39273によって導入された、ループホールを使用するお客様の回帰の問題を修正しました。 CAMP-39273は元に戻された。

## リリース20.1.2 - 2020年2月 {#release-20-1-2---february-2020}

**電子メールデザイナーの機能強化**

* パッチを適用してからコンテンツを保存すると、古いフラグメントにHTMLタグ要素が追加される問題を修正しました。 (CAMP-40685)
* 動的コンテンツを使用する場合にスペースが追加される問題を修正しました。 (CAMP-40605)
* トランザクション電子メールテンプレートの設定時に発生していた問題を修正しました。 (CAMP-40604)

## リリース20.1 - 2020年2月 {#release-20-1---february-2020}

**新機能**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector（ベータ版）</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connectorは、Adobe Campaign標準と統合されました。 XTKデータ(キャンペーンで取り込まれたデータ)をAdobe Experience Platform Data Model(XDM)にマッピングすると、キャンペーンデータをAdobe Experience Platformで利用できるようになります。 </p>
    <p>この機能は、Azureでホストされるお客様のみが利用できることに注意してください。 この機能とアクティブ化のための条件について詳しくは、 <a href="../../developing/using/aep-about-data-connector.md">詳細なドキュメント</a> と <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">使い方のビデオを参照してください</a>。</p>
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
   <td> <p>オーディエンスーの宛先を使用すると、Adobe Experience PlatformからAdobe Campaignにセグメントを共有できます。</p>
    <p>この機能は、Azureでホストされるお客様のみが利用できることに注意してください。 この機能とアクティブ化のための条件について詳しくは、 <a href="../../audiences/using/aep-about-audience-destinations-service.md">詳細なドキュメント</a> と <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">使い方のビデオを参照してください</a>。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**強化点**

* 拡張MTAのグローバルな可用性： メッセージ(トランザクションメッセージを含む)は、Adobe Campaign拡張MTAによって送信されるようになりました。これにより、配信性、スループット、バウンス処理を向上させる、アップグレードされた送信インフラストラクチャが提供されます。 [詳細を表示](https://helpx.adobe.com/jp/campaign/kb/campaign-enhanced-mta.html)

* タイムゾーン管理が強化されました。 ワークフロー全体に対して [特定のタイムゾーン](../../automating/using/building-a-workflow.md) を定義できるようになりました。 選択したタイムゾーンが、すべてのワークフローのアクティビティに適用されます。 演算子またはサーバーに対して設定されたタイムゾーンに関する情報が、インターフェイスに（ログに、タイムゾーンを選択した後に）表示されるようになりました。 (CAMP-37672)

* Campaign StandardAPIで、大きなテーブルを使用する場合、呼び出しURLに `_forcePagination=true` パラメーターを追加することでページネーションを実行できるようになりました。 [詳細を表示](../../api/using/pagination.md)

* 配信ログID（各ログの一意の識別子）が、すべてのターゲティングディメンションの配信ログおよびトラッキングログリソースで使用できるようになりました。 これにより、エクスポート時などに送信またはトラッキングログを識別できます。 [詳細を表示](../../automating/using/exporting-logs.md)

**電子メールデザイナーの機能強化**

* オーディエンスを作成する際に、必須のテキストの説明が見つからないことを追加しました。
* 従来の電子メールエディターのウィザードで「 **コンテンツを変更** 」ボタンをクリックした場合の問題を修正しました。
* サービスの概要レポートで、ヘッダーがコンテンツと一致しない問題を修正しました。 (CAMP-38103)
* 件名行の残りの部分に影響を与えることなく、動的コンテンツバリアントを削除できない問題を修正しました。 (CAMP-40096)
* 件名行でBバリアントを使用する場合のA/Bテストの問題を修正しました。 (CAMP-40327)
* HTMLの読み込みをアップロード機能の使用時に、ファイルをドラッグ&amp;ドロップできない問題を修正しました。 (CAMP-39326)
* テキストエディターからテキストをコピーして貼り付けることができない問題を修正しました。 (CAMP-39028)
* サーチクエリが表示されない問題を修正しました。 (CAMP-38970)
* ユーザーがフラグメントを保存できない問題を修正しました。 (ATU-2447)
* 動的構造を複製できない問題を修正しました。 (CAMP-38367)
* 動的コンテンツを複製したときに条件が保持されない問題を修正しました。 (CAMP-39051)

**その他の変更**

* 「準備に失敗した配信」フィルターで、最終変更日ではなく、配信の作成日が考慮されるようになりました。
* 管理者セキュリティグループの組織単位は変更できなくなりました。
* プロファイルを作成する際は、「組織単位」フィールドに値を入力する必要があります。
* Experience Cloudのトリガーを削除できるのは、イベントと、そのテンプレートにリンクされているトランザクションテンプレートの両方が削除された場合のみです。
* Adobe Creative SDKは廃止されました。 Campaign Standardでは非推奨となりました。 機能の [廃止および削除のページを参照してください](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)。


**パッチ**

* プライバシーの削除要求を実行したときに、ユーザーデータが除外ログで削除されない問題を修正しました。 (CAMP-39003)
* コンテナ要素内のテキストのサイズ変更時にアクセシビリティの問題が発生する問題を修正しました。
* マーケティングアクティビティにカーソルを合わせたときに表示されるカレンダーポップアップを解除できない問題を修正しました。
* データが変更されていない場合でもボタンが表示される **[!UICONTROL External API]****[!UICONTROL Confirm]** アクティビティの問題を修正しました。
* ターゲットのサイズが異なるクエリで **[!UICONTROL Union]** アクティビティを使用する場合の問題を修正しました。 トランジションデータには、メインセットのターゲティングディメンションのレコードのみが表示されました。 (CAMP-36831)
* 特定のコンテキストでアクティビティを使用する場合、例えば2つの受信アクティビティを使用する場合に、そのうち1つが除外アクティビティとしてエラーが発生する可能性がある問題を修正しました。 **[!UICONTROL Reconciliation]** (CAMP-37490)
* テストプロファイルを選択および更新する際に発生する可能性があるパフォーマンスの問題を修正しました。 (CAMP-37976)
* ランディングページを使用した購読または購読解除時にエラーページが表示される問題を修正しました。 (CAMP-37771)
* HTMLで参照されているPNGファイルを大文字の拡張子で使用し、zip形式のコンテンツをアップロードする際に発生していた問題を修正しました。 (CAMP-37913)
* 配信にテストプロファイルを追加すると、アプリ内メッセージが送信されない問題を修正しました。
* エンリッチメントアクティビティにリンクされた場合に失敗するExternal APIワークフローアクティビティのエラーを修正しました。
* SMSメッセージのステータスが正しく表示されない問題を修正しました。
* カスタムリソースで、異なるAPIエンドポイントの下に重複エントリが表示される問題を修正しました。
* 投稿後にランディングページを使用できない問題を修正しました。 (CAMP-38695)
* 2つの異なるリソースからの積集合トランジションのデータを表示する際に発生していた問題を修正しました。 (CAMP-38974)
* 配信テンプレートの定義済みリスト値が正しく設定されない問題を修正しました。 (CAMP-38388)
* 電子メールのバルク配信で、配信の状態が「保留」、送信済みのステータスが「完了」と表示されるエラーを修正しました。 (CAMP-35355)
* 動的レポートで送信者のドメインが正しく表示されないエラーを修正しました。 (CAMP-33123)
* 動的なレポートで購読解除数に相違が生じる問題を修正しました。 (CAMP-39949)
* アプリ内メッセージを送信する際に、アドレスがログの送信画面に表示されない問題を修正しました。
* SMS送信ログが正しいバウンス数で更新されない問題を修正しました。 (CAMP-38395)
* アプリケーション購読がpost呼び出しを使用してプッシュ通知トークンを更新できるループホールを修正しました。 (CAMP-39273)
