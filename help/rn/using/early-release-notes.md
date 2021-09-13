---
title: 早期リリースノート
description: 早期リリースノート
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 100%

---

# 早期リリースノート {#new-release}

このページでは、次回の Campaign Standard リリースに含まれる新機能、改善点、修正点について説明します。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

## リリース 21.3 - 2021年9月 {#release-21-3---sept-2021}


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
<p>新しい監査記録機能は、Adobe Campaign 内で発生するアクションとイベントの包括的なリストをリアルタイムで取得します。これには、データの履歴にアクセスして次のような質問に答えるのに役立つセルフサービス式の方法が含まれています。</p>
<ul>
<li>このワークフローに何が起こりましたか？最後に更新したのは誰ですか？</li>
<li>最後に変更したのは誰ですか？</li>
<li>以前のステートは何でしたか？</li>
</ul>
<p>Adobe Campaign は、ワークフロー、オプション、カスタムリソースの作成、編集および削除アクションを監査するようになりました。これらの項目の変更もトラッキングされます。</p>
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
<p>Campaign ワークフローを診断モードで実行できるようになりました。このモードでは、実行の問題のトラブルシューティングに役立つ情報が記録されます。ワークフロークエリが 1 分（デフォルト）以上かかる場合、実行プラン全体がログに記録されます。</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**改善点**

* Adobe Experience Manager のコンテンツにリンクされたワークフローで繰り返し配信を作成する際、送信前にコンテンツの承認ステータスが確認されるようになりました。
* データベース接続制限が、接続エラーを回避するために Campaign パッケージと連携されるようになりました。
* カスタムリソースでインデックスを作成する際の整合性チェックを追加し、エラーメッセージを改善しました。

**パッチ**

* URL からメールコンテンツをインポートする際のタイムアウトエラーを修正しました。（CAMP-49054）
* ブックマークされた URL にアクセスしたり、ブラウザーからページを更新したりするときに、セッションの終了によって発生するエラー（-69）を修正しました。（CAMP-49003、CAMP-48930、CAMP-48894）
* 従来の配信サーバーから新しい配信サーバーにルールを同期する際の問題を修正しました。（CAMP-48923）
* 電子メールデザイナーで、HTML タグを含む電子メールテンプレートを読み込む際の問題を修正しました。（CAMP-48243）
