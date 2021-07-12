---
solution: Campaign Standard
product: campaign
title: Adobe Campaign Standard でのアクセシビリティ
description: Adobe Campaign Standard Workspace でのアクセシビリティのサポートについて説明します。
audience: designing
content-type: reference
topic-tags: accessibility
feature: キャンペーン
role: User
level: Intermediate
exl-id: 958f7beb-ab41-4492-bc0a-e9e342e3c12e
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 100%

---

# Adobe Campaign Standard でのアクセシビリティ {#accessibility-acs}

Adobe Campaign Standard Workspace でのアクセシビリティのサポートについて説明します。

アクセシビリティとは、視覚、聴覚、認知、運動などの障害を持つユーザーに対して、製品を使用できるようにすることです。ソフトウェア製品のアクセシビリティ機能の例としては、意味的に構造化されたコンテンツ、スクリーンリーダーへの対応、グラフィックを表すテキスト、キーボードショートカットなどがあります。

Adobe Campaign Standard には、コントラスト、ラベル、構造化されたコンテンツ、キーボードナビゲーション、コンテキストヘルプなど、利用上のアクセシビリティを向上させる機能が用意されています。

## アクセシビリティ機能 {#accessibility-features}

### コントラストと色 {#contrast}

Adobe Campaign Standard のユーザーインターフェイスは、アプリケーションのコントラストを十分な水準に高め、視力や色覚に障がいのあるユーザーに対して、アクセスしやすい視聴エクスペリエンスを提供します。

* 大きなテキストと見出しのコントラスト比が 3:1 を満たすよう改善されました。

   ![](assets/accessibility_2.png)

* アプリケーション内のヘルプコンテンツと本文のテキストのコントラスト比が 4.5:1 を満たすよう更新されました。

* ワークフローの一時停止アイコンとキャンセルアイコンが更新され、背景色と前景色のコントラストが改善されました。

   ![](assets/accessibility_1.png)

* アプリケーション内の情報や階層は、色、形状、表示場所以外の方法でも示されている場合があります。

### ユーザーインターフェイス {#user-interface}

Adobe Campaign Standard のユーザーインターフェイスは、視覚的要素に代替テキストを追加し、意味的構造を使用して視覚的およびプログラム的に情報を伝えることで、すべてのユーザーがコンテンツを簡単に操作できます。

* ユーザーが必須の ID フィールドを空白のままにすると、エラーのあるフィールドがエラーメッセージテキストとともに視覚的に示され、スクリーンリーダーなどの支援技術を利用するユーザーにも同じ情報がプログラム的に伝達されます。

   ![](assets/accessibility_3.png)

* カーソルを合わせたときやフォーカスしたときに表示されるコンテンツは、ユーザーが閉じることができます。また、他のコンテンツがこれにより隠れることはありません。

   ![](assets/accessibility_4.png)

* 画像の代替テキストとボタンのアクセシビリティ機能用の名前が追加され、要素を識別する視覚的な手掛かりに頼るだけでなく、支援技術を使用して読み上げることができます。

<!--
### Create responsive resize for multiple devices {#resize-devices}

When designing for multiple devices and platforms, it's important to create a seamless experience for screen sizes across mobile and desktop resolutions.

Adobe Campaign Standard allows you to design and test emails and push notifications on different devices such as: iPhone, Android devices, iPad, Android tablet and desktop.

![](assets/accessibility_6.png)
-->

## コンテキストヘルプ {#contextual-help}

コンテキストヘルプは、様々な入力必須フィールドや使用可能な機能をより深く理解するのに役立ちます。また、製品ドキュメントの情報の中から、選択した機能に関する詳細情報を確認できます。

E メールをデザインする際に、機能の説明と製品ドキュメントへのリンクを示すツールチップにアクセスできます。

![](assets/accessibility_7.png)

## 支援技術のサポート {#screen-magnifiers}

改変されたキーボード、画面拡大ソフトウェア、スクリーンリーダー、音声認識ソフトウェアおよびその他の支援機器を含む様々な支援技術により、Adobe Campaign Standard アプリケーションができる限り使いやすくするよう努めています。

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

[アドビのアクセシビリティフィードバックフォーム](https://www.adobe.com/accessibility/feedback.html)を使用して、改善の提案とアクセシビリティに関する問題についてご意見をお寄せください。

また、[Adobe Campaign Standard のリリースノート](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=ja#release-notes)を参照して、最新の改善点と機能をチェックしてください。
