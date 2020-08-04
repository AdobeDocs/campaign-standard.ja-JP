---
title: リリースノート 2020
description: このページでは、Adobe Campaign Standard の 2020 年の全リリースを紹介します。
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
translation-type: ht
source-git-commit: f4c6b74d9b80d80befed65d853cf82b32084c49d
workflow-type: ht
source-wordcount: '1825'
ht-degree: 100%

---


# リリースノート 2020{#release-notes-2020}

[リリース計画](https://helpx.adobe.com/jp/campaign/kb/acs-release-planning.html) | [コントロールパネルのリリース](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html) | [ドキュメントの更新](../../rn/using/documentation-updates.md) | [以前のリリースノート](../../rn/using/release-notes-2019.md) | [非推奨（廃止予定）の機能](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)

## リリース 20.2 - 2020 年 4 月{#release-20-2---april-2020}

**新機能**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure BLOB との統合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure BLOB ストレージコネクタを使用して、「<strong>ファイル転送</strong>」ワークフローアクティビティで Adobe Campaign との間でデータのインポート／エクスポートをおこなえるようになりました。 </p>
    <p>詳しくは、<a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">詳細ドキュメント</a>を参照してください。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>ターゲットプロファイルを使用した E メールテスト</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>テストプロファイルに加えて、実際のターゲットプロファイルを対象に E メールをテストできるようになりました。これにより、プロファイルが受け取るメッセージ（ワークフローからの追加データを含め、カスタムフィールド、動的情報、パーソナライズされた情報など）が正確に表示されます。 </p>
    <p>詳しくは、<a href="../../sending/using/testing-messages-using-target.md">詳細ドキュメント</a>および<a href="https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">チュートリアルビデオ</a>を参照してください。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Google TXT レコード管理、データベース領域の監視、E メールアラートなど、新しい機能が 4 月に Campaign コントロールパネルにリリースされます。これらの機能について詳しくは、[コントロールパネルリリースノート](https://docs.adobe.com/content/help/ja-JP/control-panel/using/release-notes.html)を参照してください。

**強化点**

* トランザクションメッセージングのユーザーエクスペリエンスが強化され、インターフェイスの一貫性が向上しました。[詳細を表示](../../channels/using/about-transactional-messaging.md)
* Campaign Standard で、ワークフローの追加データを使用して配達確認をテストプロファイルに送信できるようになりました。
* 「外部 API」アクティビティのガードレールが更新されました。[詳細を表示](../../automating/using/external-api.md)

**E メールデザイナーの機能強化**

* パーソナライズされた画像を複数回クリックした場合にエスケープに影響が及ぶ問題を修正しました。
* 動的テキストコンポーネントを複製すると誤った行が複製されることがある問題を修正しました。（CAMP-41249）
* div レベルではなくテーブルレベルでパディングを定義するときに Outlook で生じるパディングの問題を修正しました。
* HTML モードに切り替えると画像の幅が変更される問題を修正しました。（CAMP-41116）
* アイコンに代替テキストを指定すると、ソーシャルメディアコンポーネントにアクセスできなくなる問題を修正しました。（CAMP-41345）
* E メールデザイナーでコピー＆ペーストを使用すると `<br>` タグが表示される問題を修正しました。
* HTML コンテンツからプレーンテキストに切り替えた後、E メールに HTML タグが表示される問題を修正しました。（CAMP-41138）
* 境界が 1 つしか定義されていないボタンのレンダリングができない問題を修正しました。
* Microsoft Outlook で HTML インデントにより E メールのフッターが左側に配置される問題を修正しました。（CAMP-40987）
* プレーンテキストモードへの切り替え時に、HTML で定義されたコレクション属性をターゲットとするパーソナライゼーションフィールドがプレーンテキストコンテンツにコピーされる問題を修正しました。（CAMP-40365）
* 選択されたテキストセグメントにリンクを挿入できない問題を修正しました。（CAMP-41406）
* クエリエディターでタイムゾーンを選択すると日付が変更される問題を修正しました。（CAMP-38277）

**その他の変更**

* そのまま使用できる「**KPIs Reconciliation with Adobe Analytics**」（Adobe Analytics との KPI 紐付け）ワークフローが、1 日だけでなく現在の日付まで実行されるようになりました。
* MCPNS では、APNS と APNS-SANDBOX の両方をプラットフォームとしてアプリに追加することはできません。Adobe Campaign Standard に証明書が正常に追加された後は、設定を元に戻すことはできなくなりました。MCPNS アプリに追加できるのは、1 つの APNSプラットフォーム（実稼動またはサンドボックス）に限られるからです。

**Experience Platform との統合**

>[!NOTE]
>
>Campaign Standard の Adobe Experience Platform 機能は現在ベータ版であるため、予告なしに頻繁にアップデートされる場合があります。詳細なドキュメント（[Adobe Experience Platform Data Connector について](../../developing/using/aep-about-data-connector.md)、[Audience Destinations サービスについて](../../audiences/using/aep-about-audience-destinations-service.md)）を参照してください。

* ワークフローログで、現在実行中のジョブで既に処理されたレコードの件数が 10 分ごとに Campaign に表示されるようになりました。
* データベースから削除された Adobe Experience Platform プロファイルをインポートするときに生じる可能性のある問題を修正しました。
* ワークフローログで、インポートしたレコードの合計件数が誤って表示される問題を修正しました。

**パッチ**

* 「**エンリッチメント**」ワークフローアクティビティで「**Alias**」フィールドにスペースを追加して新しい行項目を作成したときに生じる可能性がある問題を修正しました。（CAMP-39229）
* 配達確認メッセージの送信時に、すべてのテストプロファイルがターゲットになる可能性がある問題を修正しました。
* イベント設定を非公開にして削除した後で生じていた問題を修正しました。[詳細を表示](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* ワークフローに変更を加えると「**Save**」ボタンが表示されなくなる問題を修正しました。
* プライバシーリクエストを処理した後、Campaign で手動で削除したとき、リクエストに関連付けられたデータがクリーンアップ後も削除されない問題を修正しました。
* 特殊文字を含んだメッセージを Adobe Experience Manager からプレビューまたは送信したときに生じる可能性がある問題を修正しました。
* 複数のインバウンドトランジションを含んだアクティビティの実行時にワークフローで生じる可能性がある問題を修正しました。
* 標準ユーザーがワークフローのクエリまたは配信で「アプリケーションの購読」をターゲットディメンションとして使用できない問題を修正しました。（CAMP-37618）

## リリース 20.1.4 - 2020 年 2 月 {#release-20-1-4---february-2020}

* 既存のワークフローで「**オーディエンスの閲覧**」アクティビティを開く際の問題を修正しました。（CAMP-41002）

## リリース 20.1.3 - 2020 年 2 月 {#release-20-1-3---february-2020}

* ループホール使用に対処する CAMP-39273 が原因で 20.1 リリースに発生するようになった回帰の問題を修正しました。CAMP-39273 による修正は元に戻されました。

## リリース 20.1.2 - 2020 年 2 月 {#release-20-1-2---february-2020}

**E メールデザイナーの機能強化**

* パッチを適用してコンテンツを保存すると旧フラグメントに HTML タグ要素が追加される問題を修正しました。（CAMP-40685）
* 動的コンテンツの使用時にスペースが追加される問題を修正しました。（CAMP-40605）
* トランザクション E メールテンプレートの設定時に生じていた問題を修正しました。（CAMP-40604）

## リリース 20.1 - 2020 年 2 月 {#release-20-1---february-2020}

**新機能**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector（ベータ版）</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector が Adobe Campaign Standard に統合されるようになりました。XTK データ（Campaign でインジェストされたデータ）を Adobe Experience Platform Data Model（XDM）にマッピングすることにより、Campaign のデータを Adobe Experience Platform で利用できるようになります。 </p>
    <p>なお、この機能は Azure でホストされるお客様のみが利用できることにご注意ください。この機能、およびその有効化の条件について詳しくは、<a href="../../developing/using/aep-about-data-connector.md">詳細なドキュメント</a>と<a href="https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.translate.html">ハウツービデオ</a>を参照してください。</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations（ベータ）</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Audience Destinations を使用することにより、Adobe Experience Platform のセグメントを Adobe Campaign で共有できるようになります。</p>
    <p>なお、この機能は Azure でホストされるお客様のみが利用できることにご注意ください。この機能、およびその有効化の条件について詳しくは、<a href="../../audiences/using/aep-about-audience-destinations-service.md">詳細なドキュメント</a>と<a href="https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html">ハウツービデオ</a>を参照してください。 </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**強化点**

* Enhanced MTA のグローバルな可用性：メッセージ（トランザクションメッセージも含む）は、Adobe Campaign Enhanced MTA で送信されるようになったので、送信側のインフラストラクチャーがアップグレードされた結果、配信品質、スループット、バウンス処理が向上しています。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/campaign-enhanced-mta.html)

* タイムゾーン管理が強化されました。ワークフロー全体に対して[特定のタイムゾーン](../../automating/using/building-a-workflow.md)を定義できるようになりました。選択されたタイムゾーンが、すべてのワークフローアクティビティに適用されます。オペレーターまたはサーバーに対して設定されていたタイムゾーンに関する情報は、インターフェイス（ログ内、およびタイムゾーンの選択後に）表示されるようになりました。（CAMP-37672）

* Campaign Standard API では、サイズの大きいテーブルを使用するときに、呼び出し URL に `_forcePagination=true` パラメーターを追加することでページ編集を実行できるようになりました。[詳細を表示](../../api/using/pagination.md)

* 配信ログ ID（各ログの一意の識別子）が、すべてのターゲティングディメンションを対象とした配信ログおよびトラッキングログのリソースで利用できるようになりました。これにより、例えば、エクスポート時などに送信ログまたはトラッキングログを特定できます。[詳細を表示](../../automating/using/exporting-logs.md)

**E メールデザイナーの機能強化**

* オーディエンスの作成時に、不足していた必須のテキスト説明を補いました。
* 従来の E メールエディターのウィザードで「**Change content**」ボタンをクリックしたときの問題を修正しました。
* 「サービスの概要」レポートで、ヘッダーがコンテンツの位置と一致しない問題を修正しました。（CAMP-38103）
* 動的コンテンツのバリアントを削除すると、件名行の残りの部分に影響が及ぶ問題を修正しました。（CAMP-40096）
* 件名行で B バリアントを使用するときの A/B テストの問題を修正しました。（CAMP-40327）
* 「HTML インポートのアップロード」機能を使用するときに、ファイルをドラッグ＆ドロップできない問題を修正しました。（CAMP-39326）
* テキストエディターからテキストをコピー＆ペーストできない問題を修正しました。（CAMP-39028）
* 単語の候補が表示されない問題を修正しました。（CAMP-38970）
* フラグメントを保存できない問題を修正しました。（ATU-2447）
* 動的構造を複製できない問題を修正しました。（CAMP-38367）
* 動的コンテンツを複製するときに条件が保持されない問題を修正しました。（CAMP-39051）

**その他の変更**

* 「Deliveries with preparation failed」フィルターで、最後の変更日ではなく、配信の作成日が考慮されるようになりました。
* 管理者セキュリティグループの組織単位は変更できなくなりました。
* プロファイルの作成時に、「Organizational unit」フィールドへの入力が必須になりました。
* Experience Cloud のトリガーを削除できるのは、トリガーにリンクされたイベントとトランザクションテンプレートの両方を削除する場合に限られるようになりました。
* Adobe Creative SDK は廃止されました。Campaign Standard では廃止されています。[廃止および削除された機能](https://helpx.adobe.com/jp/campaign/kb/acs-deprecated-and-removed-features.html)のページを参照してください。


**パッチ**

* プライバシーリクエストの削除を実行したときに、ユーザーデータが除外ログから削除されない問題を修正しました。（CAMP-39003）
* コンテナ要素にあるテキストのサイズ変更で生じるアクセシビリティの問題を修正しました。
* マーケティングアクティビティにカーソルを合わせたときに表示されるカレンダーポップアップが解除されない問題を修正しました。
* データが変更されていない場合でも「**[!UICONTROL External API]**」アクティビティに「**[!UICONTROL Confirm]**」ボタンが表示される問題を修正しました。
* ターゲットディメンションが異なるクエリで「**[!UICONTROL Union]**」アクティビティを使用した場合の問題を修正しました。トランジションデータでは、メインセットのターゲティングディメンションのレコードだけが表示されていました。（CAMP-36831）
* 特定のコンテキストで「**[!UICONTROL Reconciliation]**」アクティビティを使用するとエラーになる問題を修正しました。例えば、2 つのインバウンドアクティビティがあって、その一方が除外アクティビティになっている場合などに生じる問題です。（CAMP-37490）
* テストプロファイルを選択および更新時に生じることのあるパフォーマンスの問題を修正しました。（CAMP-37976）
* ランディングページを介した購読時または購読解除時にエラーページが表示される問題を修正しました。（CAMP-37771）
* HTML で参照される PNG ファイルの拡張子を大文字で指定したコンテンツを zip 形式でアップロードしたときに生じる問題を修正しました。（CAMP-37913）
* テストプロファイルを配信に追加すると、アプリ内メッセージが送信されない問題を修正しました。
* 「エンリッチメント」アクティビティにリンクされているときに「外部 API」ワークフローアクティビティが失敗するエラーを修正しました。
* SMS メッセージのステータスが正しく表示されない問題を修正しました。
* カスタムリソースで異なる API エンドポイントの下に重複したエントリが表示される問題を修正しました。
* 公開した後、ランディングページが使用できなくなる問題を修正しました。（CAMP-38695）
* 2 つの異なるリソースから得られる積集合トランジションのデータを表示する際に生じる問題を修正しました。（CAMP-38974）
* 配信テンプレートの定義済みリストが正しく設定されない問題を修正しました。（CAMP-38388）
* E メールの一括配信で、配信状態が「保留」、送信済みステータスが「完了」と表示されるエラーを修正しました。（CAMP-35355）
* 動的レポートで送信者のドメインが正しく表示されないエラーを修正しました。（CAMP-33123）
* 動的レポートで購読解除数に不一致が生じる問題を修正しました。（CAMP-39949）
* アプリ内メッセージの送信時に送信ログ画面にアドレスが表示されない問題を修正しました。
* SMS 送信ログが正しいバウンス数に更新されない問題を修正しました。（CAMP-38395）
* アプリケーション購読の POST 呼び出しでプッシュ通知トークンを更新できるループホールを修正しました。（CAMP-39273）
