---
title: 早期リリースノート
description: 早期リリースノート
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 66aed3668dc0eb2041312dcbaebe7c36f54b13a5
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 100%

---

# 早期リリースノート {#new-release}

このページでは、次回の Campaign Standard リリースに含まれる新機能、改善点、修正点について説明します。

>[!CAUTION]
>
> この内容は、ステージング環境のアップグレード日まで予告なしに変更される場合があります。詳しくは、[リリース計画のページ](../../rn/using/release-planning.md)を参照してください。

## リリース 22.2 - 2022年6月 {#rn-2022}

**改善点**

* **アドビ通知サービス** - Experience Cloud ソリューションは、Campaign に搭載されているアドビ通知サービスを使用して、ユーザーが把握しておくべき重要なアクティビティに関して Experience Cloud のどこからでもユーザーにアラートを表示できます。バージョン 22.2 以降、ユーザーエクスペリエンスが向上しました。通知が優先され、製品から生成される通知は、ステータスに応じたアドビからのお知らせとは別に表示されます。さらに、通知で特定のワークフローが参照されている場合、メール通知または製品内通知から直接、対応するワークフローにアクセスできるようになりました。Adobe Campaign 通知について詳しくは、[Adobe Campaign 通知](../../administration/using/sending-internal-notifications.md)を参照してください。

* **ワークフロー起動時の最適化** - 同じ頃に開始されるワークフローの数を調整できる新しい機能が追加されました。これは、サービスの中断やダウンタイムにつながる可能性のある CPU スパイクを防ぐうえで役に立ちます。この機能は 22.2 リリース以降で有効になります。これに関しては、お客様側でさらに対応が必要な項目はありません。

* **アクセシビリティ** - アプリケーションの全体的な使いやすさを改善するために、アクセシビリティに関する多くの修正を行いました。これらの機能は、現在、一部の早期導入ユーザーに対してのみ有効になっており、ACS 22.3 リリースですべてのお客様にロールアウトされる予定です。アクセシビリティの向上には、例えば次のものがあります。

   * 各画面のフォーカス可能な要素に対するフォーカスインジケーターの確実な表示
   * ナビゲーションを容易にするためのページランドマークの作成
   * 多くのコントロールの名前、役割、値、状態の追加
   * メイン画面のダイナミックフォーカス順序で発生した問題の修正


**パッチ**

* キーの重複エラーによる請求テクニカルワークフローの問題を修正しました。（CAMP-51029）
* 欠落していた Microsoft Edge ブラウザーカテゴリをトラッキングレポートに追加しました。以前は、Microsoft Chrome のオープンに分類されていました。（CAMP-51165）
* GDPR リクエストで子テーブルからデータが削除されない問題を修正しました。（CAMP-48276）
* 電子メールデザイナーでフラグメントの表示条件がトランザクションメッセージテンプレートに保存されない原因となる問題を修正しました。（CAMP-50338）
* Campaign レポートで日付範囲が考慮されない原因となる問題を修正しました。（CAMP-50991）
* スケジュールされたメールが失敗するエラーを修正しました。配信ステータスが「再試行待ち」のままであったことが原因で、配信分析を開始できませんでした。（CAMP-50302）
* 電子メールデザイナーでプロファイルの置き換えを使用してメールをプレビューする際の問題を修正しました。（CAMP-49312）
* カスタム列挙の空の値に関する問題を修正しました。値が 1 つしかないテキスト列挙フィールドでカスタムリソースを作成する場合、この値がデフォルトで設定され、このフィールドに単純なリクエストとしてクエリを作成できるようになりました。（CAMP-50606）
