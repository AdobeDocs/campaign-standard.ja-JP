---
title: リリースノート 2022
description: このページでは、Adobe Campaign Standard の 2022 年の全リリースを紹介します。
feature: Overview
role: User
level: Beginner
source-git-commit: 1d1869a6c503773f4aaecb6a77f1b72585c88865
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 100%

---

# リリースノート 2022{#release-notes-2022}

[リリース計画](../../rn/using/release-planning.md) | [コントロールパネルのリリース](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=ja) | [ドキュメントの更新](../../rn/using/documentation-updates.md) | [以前のリリースノート](../../rn/using/release-notes-2020.md) | [非推奨（廃止予定）の機能](../../rn/using/deprecated-features.md)


## リリース 22.1 - 2022年2月 {#feb-2022}

**新機能**

<table> 
<thead> 
<tr> 
<th> <strong>Apache Log4j セキュリティ脆弱性に対するセキュリティ更新</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j は、Apache log4j v2.17.1 リリースで報告された脆弱性を修正しました。Adobe Campaign Standard は Apache log4j を使用しており、このリリースにはこの最新の Apache log4j v2.17.1 が含まれています </p>
</td> 
</tr> 
</tbody> 
</table>

**セキュリティの修正**

* このリリースに含まれる、トラッキング用の新しい URL 署名メカニズム。一部の有効な署名済みトラッキングリンクが、サードパーティのセキュリティツールによって変更された後、誤ってブロックされるという問題を回避するために、以前のメカニズムが無効になりました。（CAMP-48983）

**改善点**

* システムの読み込み過剰を回避するために、レポートデータの処理を改善しました。（CAMP-47578）
* アプリ内メッセージを送信した後に、配信の非アクティブ化を選択できるようになりました。これにより、レポートデータを失うことなく配信を削除できます。（CAMP-48469）
* 問題を回避するために、ユーザーは、データベースの自動プライマリキー `"<dataType><resourceName>Id"` に使用されたのと同じ名前をカスタムテーブル列に使用できなくなりました。（CAMP-49358）
* メッセージのダッシュボードにある新しい&#x200B;**ジョブ履歴**&#x200B;ドロップダウンを使用して、配信を監視し、ジョブのログを追跡できるようになりました。[詳細情報](../../sending/using/monitoring-a-delivery.md)（CAMP-49840）
* 時間の経過と共にすべてのチャネルに大量のメッセージが送信される場合に、無効なタプルを減らすことで、安定性とデータベースの状態が向上しました。（CAMP-49755、CAMP-49792、CAMP-49849）
* データベースがクラッシュした場合や再起動した場合にデータベース接続が自動的に更新されるように、Campaign メール転送エージェント（MTA）に改善が実装されました。（CAMP-48063）
* 新しいトラッキングオプション **メールの上部にあるトラッキングピクセルを使用**&#x200B;がメールプロパティに追加され、下部ではなくメールの上部でトラッキングピクセルを動かせるようになりました。（CAMP-49672）

**パッチ**

* 動的レポートの「**今すぐレポートを送信**」オプションの問題（PDF 生成ジョブが複数のバリアントを含む配信で失敗した）を修正しました。（CAMP-49120）
* Adobe Experience Manager（AEM）内の重複したコンテンツが同じキー（cq:uuid）を共有している場合に、ユーザーが Adobe Campaign Standard の配信から AEM コンテンツを更新またはリンク解除できない問題を修正しました。（CAMP-49161）
* ページが読み込まれない、配信を開けない、または保留中の変更を保存できないインスタンスにアクセスする際のエラーを修正しました。（CAMP-50195）
* この基準によって適用される「**配信フィルター**」フィールドが入力されていない場合に配信アラート基準が開かない問題を修正しました。（CAMP-49093）
* アプリ内配信の「**セカンダリ**」ボタンを編集するときに変更が考慮されない問題を修正しました。（CAMP-50250）
* 日本語インスタンスにおいて、ユーザーが&#x200B;**スケジューラー**&#x200B;アクティビティの「**実行頻度**」で 1 日に数回の頻度を選択できなかったエラーを修正しました。（CAMP-50247）
* 日本語ユーザーインターフェイスでの作業時に、スケジューラーアクティビティで時間を選択するとエラーメッセージが表示される問題を修正しました。（CAMP-49289）
* 却下されたプッシュ通知が&#x200B;**インプレッション**&#x200B;ではなく&#x200B;**オープン**&#x200B;として表示されるプッシュ通知レポートのエラーを修正しました。（CAMP-45980）
* レポートを開く際にエラーが発生する可能性がある問題を修正しました。（CAMP-49222）
* AEM コンテンツへのリンクを削除した後、メールの準備に失敗する可能性がある問題を修正しました。（CAMP-49877）
* 様々な問題を解決するために、URL から読み込まれたコンテンツを含む配信の再試行メカニズムが改善されました。[詳細情報](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)（CAMP-48888）
* カスタムリソースで新しいフィルターを作成し、ランディングページで紐付けキーとして使用した後に発生していた問題を修正しました。カスタムリソースが再度公開された場合、ランディングページで使用可能な紐付けキーのリストからフィルターが削除されました。（CAMP-49516）
* チェックボックスで動的条件を使用する場合のランディングページの問題を修正しました。（CAMP-48604）
* 「10月以前」のフィルター条件を使用したときに&#x200B;**クエリ**&#x200B;アクティビティで発生していた問題を修正しました。ヨーロッパのタイムゾーンに設定されたインスタンスから作業する場合、タイムゾーンの変換時に問題が発生したため、フィルターに選択した月に10月ではなく9月が表示されました。（CAMP-48602）
* 配信品質を最適化するために、Adobe Campaignでは 8 ビットではなく 7 ビットエンコーディングを使用してメールを送信するようになりました。これにより、中間リレーが DKIM 署名を無効にして、メッセージの信頼性に影響を与える可能性がなくなります。（CAMP-49016）
* 大きなオーディエンスを扱う際の問題を回避するために、オーディエンスの複製時のパフォーマンスが強化されました。（CAMP-49639）
* **クエリー**&#x200B;アクティビティで使用したときにカスタムフィルターが正しい結果を表示できない可能性がある問題を修正しました。（CAMP-49417）
* 配信で名前にコンマを含むフラグメントを使用しようとするとエラーメッセージが表示されるエラーを修正しました。問題は解決され、フラグメント名でコンマを使用できるようになりました。（CAMP-49216）
