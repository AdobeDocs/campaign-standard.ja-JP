---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard でのアクセシビリティ
description: Adobe Campaign Standard Workspace でのアクセシビリティのサポートについて説明します。
audience: designing
content-type: reference
topic-tags: accessibility
translation-type: tm+mt
source-git-commit: 6ea28c457b1024dab315b60281adaee56eb80cd0
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 45%

---


# Adobe Campaign Standard でのアクセシビリティ {#accessibility-acs}

Adobe Campaign Standard Workspace でのアクセシビリティのサポートについて説明します。

アクセシビリティとは、視覚、聴覚、認知、運動などの障害を持つユーザーに対して、製品を使用できるようにすることです。 ソフトウェア製品のアクセシビリティ機能の例としては、セマンティック構造のコンテンツ、スクリーンリーダーのサポート、グラフィックのテキスト等価、キーボードショートカットなどがあります。

Adobe Campaign Standardには、コントラスト、ラベル、構造化コンテンツ、キーボードナビゲーション、コンテキストヘルプなど、使いやすい機能が用意されています。

## アクセシビリティ機能 {#accessibility-features}

### コントラストと色{#contrast}

Adobe Campaign Standardのユーザーインターフェイスは、アプリケーションの十分なコントラストを提供するように取り組み、低視覚または色の欠陥を持つユーザーにとって、アクセシブルな表示エクスペリエンスを保証します。

* 大きなテキストと見出しのコントラスト比が3:1になるように拡張されました。

   ![](assets/accessibility_2.png)

* アプリケーション内のヘルプコンテンツと本文のテキストが、4.5:1のコントラスト比に合わせて更新されました。

* ワークフローの一時停止アイコンとキャンセルアイコンが更新され、背景色と前景色のコントラストが改善されました。

   ![](assets/accessibility_1.png)

* 色、形状、場所は、アプリケーション内の情報や階層を伝える唯一の方法ではありません。

### ユーザーインターフェイス {#user-interface}

Adobe Campaign Standardのユーザーインターフェイスを使用すると、視覚要素に代替テキストを追加し、セマンティック構造を使用して視覚的およびプログラム的に情報を伝えることで、すべてのユーザーがコンテンツを簡単に操作できます。

* ユーザーが必須IDフィールドを空白のままにすると、エラーメッセージテキストが表示され、エラーのあるフィールドが視覚的に示され、スクリーンリーダーなどの支援技術を持つユーザーにも同じ情報がプログラム的に伝達されます。

   ![](assets/accessibility_3.png)

* カーソルを合わせたときやフォーカスしたときに表示されるコンテンツは、ユーザーが閉じることができます。また、他のコンテンツがこれにより隠れることはありません。

   ![](assets/accessibility_4.png)

* 画像の代替テキストとボタンのアクセシブルな名前が追加され、要素を識別する視覚的なキューに頼るだけでなく、支援テクノロジーを使用して読み上げることができます。

<!--
### Create responsive resize for multiple devices {#resize-devices}

When designing for multiple devices and platforms, it's important to create a seamless experience for screen sizes across mobile and desktop resolutions.

Adobe Campaign Standard allows you to design and test emails and push notifications on different devices such as: iPhone, Android devices, iPad, Android tablet and desktop.

![](assets/accessibility_6.png)
-->

## コンテキストヘルプ {#contextual-help}

コンテキストヘルプを使用すると、様々な要求されたフィールドや機能をより深く理解できます。 また、製品ドキュメントの情報の中から、選択した機能に関する詳細情報を確認できます。

電子メールをデザインする際に、機能の説明と製品ドキュメントへのリンクを示すツールチップにアクセスできます。

![](assets/accessibility_7.png)

## 支援テクノロジーのサポート{#screen-magnifiers}

キーボード、画面拡大ソフト、スクリーンリーダー、音声認識ソフト、その他の補助機器など、様々な支援技術によって、Adobe Campaign Standardのアプリケーションを可能な限り使いやすくするよう努めています。

## 設定言語で作業 {#languages}

Adobe Campaign Standard は、英語、フランス語、ドイツ語の各言語で使用できます。

言語はインストール時に設定され、後で変更することはできません。

## キーボードショートカット {#shortcuts}

### ホームページ {#homepage-shortcuts}

| ショートカット | アクション |
|:-:|:-:|
| タブ | ユーザーインターフェイスの個々の要素間を移動する |
| Enter または Space キー | 選択した項目をアクティブにする |

### E メールデザイナー {#email-designer-shortcuts}

| ショートカット | アクション |
|:-:|:-:|
| Ctrl + Z | 取り消し |
| Ctrl + Y | やり直し |

### 動的レポート {#report-shortcuts}

| ショートカット | アクション |
|:-:|:-:|
| Ctrl + O | プロジェクトを開く |
| Ctrl + S | 保存 |
| Shift + Ctrl + S | 名前を付けて保存 |
| Alt + R | プロジェクトを更新 |
| Shift + Ctrl + V | CSV をダウンロード |
| Alt + P | 印刷 |
| Ctrl + Z | 取り消し |
| Ctrl + Shift + Z | やり直し |
| Alt + B | 新しい空白のパネル |
| Alt + A | 新しいフリーフォーム |
| Alt + 1 | 新しいフリーフォームテーブル |
| Alt + 2 | 新しい行 |
| Alt + 3 | 新しいバー |
| Alt + S | 今すぐレポートを送信 |
| Shift + Alt + S | スケジュールに従ってレポートを送信 |
| Shift + Alt + L | 予定レポート |

## 参考資料 {#further-reading}

Adobe Campaign Standard では、誰でも使いやすくなるように、アクセシビリティの改善を進めています。

[アドビのアクセシビリティフィードバックフォーム](https://www.adobe.com/accessibility/feedback.html)を使用して、改善の提案とアクセシビリティに関する問題を送信することをお勧めします。

また、[Adobe Campaign Standard のリリースノート](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=ja#release-notes)を参照して、最新の改善点と機能をチェックしてください。