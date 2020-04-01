---
title: 最新リリース
description: このページには、Adobe Campaign Standardの最新リリースがすべてリストされています。
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
source-git-commit: ce0ddc11c239dd72f14ace56ad008717ebaa47de

---


# 最新リリース{#latest-release}

[リリース計画](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) |コント [ロールパネルのリリース](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) |ドキュメ [ントの更新](../../rn/using/documentation-updates.md) |以前の [リリースノート](../../rn/using/release-notes-2019.md) |非推 [奨の機能](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

[リリース通知を購読するには](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) 、ここをクリックします。また、最新のAdobe Experience Cloudリリースの詳細を受信トレイに直接表示するには、ここをクリックします。

## リリース20.2 - 2020年3月 {#release-20-2---march-2020}

**新機能?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob統合</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure BLOBストレージコネクタを使用して、ファイル転送ワークフローアクティビティを使用して、Adobe Campaignにデータをインポートまたはエクスポ <strong>ートでき</strong> ます。 </p>
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
>4月に、Google TXTレコード管理、キャンペーン領域の監視、電子メール通知など、データベースコントロールパネルに新しい機能がリリースされます。 これらの機能の詳細については、「コントロールパネルのリリ [ースノート」を参照してくださ](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)い。

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
* MCPNSは、APNSとAPNS-SANDBOXの両方をアプリ内のプラットフォームとして追加する機能をサポートしていません。 Adobe Campaign Standardで証明書を正常に追加すると、MCPNSアプリに追加できるAPNSプラットフォーム（実稼動またはサンドボックス）が1つだけなので、設定を変更できなくなります。

**エクスペリエンスプラットフォームの統合**

>[!NOTE]
>
>Campaign StandardのAdobe Experience Platform機能は現在ベータ版で、予告なく頻繁に更新される場合があります。 詳細なドキュメントを参照してください。Experience Platform Data Connector [、](../../administration/using/aep-about-data-connector.md)[オーディエンス先](../../audiences/using/aep-about-audience-destinations-service.md)

* ワークフローログで、10分ごとに、キャンペーンは、現在実行中のジョブによって処理済みのレコード数を表示するようになりました。
* データベースから削除されたAdobe Experience Platformプロファイルを読み込む際に発生する可能性がある問題を修正しました。
* ワークフローログで、インポートされたレコードの合計数に対して誤った結果が表示される問題を修正しました。

**パッチ**

* 「 **Alias** 」フィールドにスペースを追加し、新しい行項目を作成した場合に発生する可能性がある **エンリッチメント** ・ワークフローのアクティビティの問題を修正。 (CAMP-39229)
* メッセージの送信時にすべてのテストプロファイルをターゲットにできる問題を配達確認しました。
* 公開の取り消しと削除の後に発生していたイベント設定の問題を修正。 [詳細を表示](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* ワークフローを変更すると「保存 **** 」ボタンが消える問題を修正しました。
* プライバシー要求を処理した後にキャンペーンで手動で削除すると、クリーンアップ後も要求に関連付けられたデータが削除されない問題を修正しました。
* Adobe Experience Managerから特殊文字を含むメッセージをプレビューまたは送信する際に発生する可能性がある問題を修正しました。
* 複数の受信トランジションを使用してワークフローを実行するとアクティビティが発生する問題を修正しました。