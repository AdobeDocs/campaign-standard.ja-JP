---
solution: Campaign Standard
product: campaign
title: 早期リリースノート
description: 早期リリースノート
feature: 概要
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 89514dad1e318f32dafd3d8add664c37b03c8fb7
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 45%

---

# 早期リリースノート {#new-release}

このページでは、次回の Campaign Standard リリースに含まれる新機能、改善点、修正点について説明します。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。


## リリース 21.3 - 2021 年 9 月 {#release-21-3---sept-2021}


**新機能**


<table> 
<thead> 
<tr> 
<th> <strong>統合 Experience Cloud インターフェイス</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign のヘッダーバーが変更され、すべての Experience Cloud 製品およびサービスで統一されて、エクスペリエンスが向上しました。以下のような変更によって、より快適なエクスペリエンスが得られます。</p>
<ul>
<li>組織間または別のアプリケーション間の切り替えが容易になりました。</li>
<li>ユーザーガイドの強化 - Experience League を製品に取り込むと、検索結果にコミュニティフォーラムの結果やビデオコンテンツも含まれ、より多くのコンテンツに簡単にアクセスでき、アプリを最大限に活用できます。 また、ヘルプメニューにフィードバックのメカニズムが追加され、問題の報告やアイデアの共有が容易になりました。</li>
<li>通知機能の改善 - 通知ドロップダウンに 2 つのタブが追加されました。1 つは独自の製品通知用、もう 1 つはグローバルな製品のお知らせ用です。</li>
</ul>
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>監査記録</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>新しい監査記録機能は、Adobe Campaign内で発生するアクションとイベントの包括的なリストをリアルタイムでキャプチャします。 データの履歴にアクセスして次のような質問に答えるセルフサービスの手段が含まれています。</p>
<ul>
<li>このワークフローはどうなりましたか。最後に更新したのは誰ですか。</li>
<li>最後に変更を加えたのは誰ですか。</li>
<li>前の状態</li>
</ul>
<p>Adobe Campaignは、次の項目の作成、編集、削除アクションを監査するようになりました。ワークフロー、オプション、カスタムリソース。 これらの項目の変更も追跡されます。</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>ワークフロー診断モード</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Campaignワークフローを診断モードで実行できるようになりました。 このモードでは、実行の問題のトラブルシューティングに役立つ情報が記録されます。 ワークフロークエリがデフォルトで1分以上かかる場合、実行プラン全体がログに記録されます。</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**改善点**

* ワークフローで繰り返し配信を作成し、Adobe Experience Managerコンテンツにリンクする際、送信前にコンテンツの承認ステータスがチェックされるようになりました。
* 接続エラーを回避するために、データベース接続の制限がキャンペーンパッケージに合わせられるようになりました。
* カスタムリソースのインデックスを作成する際の整合性チェックを追加し、エラーメッセージを改善しました。

**パッチ**

* URLからEメールコンテンツを読み込む際のタイムアウトエラーを修正しました。 （CAMP-49054）
* ブックマークされたURLにアクセスする場合や、ブラウザーからページを更新する場合にセッションが終了することに起因するエラー(-69)を修正しました。 (CAMP-49003、CAMP-48930、CAMP-48894)
* 従来の配信品質サーバーから新しい配信品質サーバーにルールを同期する際の問題を修正しました。 （CAMP-48923）
* Eメールデザイナーで、HTMLタグを含むEメールテンプレートを読み込む際の問題を修正しました。 （CAMP-48243）
