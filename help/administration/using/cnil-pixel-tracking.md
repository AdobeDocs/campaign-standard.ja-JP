---
title: メール追跡ピクセルに関するCNIL ガイダンス
description: メール追跡ピクセルに関するCNILの更新されたガイダンスと、コンプライアンスの取り組みをサポートできるAdobe Campaign Standardコントロールについて説明します。
audience: administration
role: Admin
level: Experienced
hide: true
source-git-commit: 75f1f4ad8f7173f4601c9cff1ea93bf4092f274d
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 0%

---


# メール追跡ピクセルに関するCNILの最新のガイダンスについて {#cnil-pixel-tracking}

>[!BEGINSHADEBOX]

**このページでは、** CNILの2026年4月の電子メールトラッキングピクセルに関する推奨事項について説明します。また、コンプライアンスの取り組みをサポートするAdobe Campaign Standard コントロール（トラッキングアクティベーション、リンクレベルのトラッキング、同意データモデル、オプトアウトの仕組み、レポート）をご確認ください。

>[!ENDSHADEBOX]

この記事は、情報提供のみを目的としています。 法的アドバイスではなく、適用法の遵守を保証するものではありません。 以下に説明するAdobe Campaign Standard製品の機能は、適切に設定および操作されたビルディングブロックであり、コンプライアンスの実装をサポートする場合があります。 各顧客は、適用法に基づく義務を決定し、遵守する責任があります。

## 概要 {#overview}

2026年4月14日、フランスのデータ保護機関である&#x200B;*Commission nationale de l&#39;informatique et des libertés* （CNIL）は、メール内でのトラッキングピクセルの使用に関する[の推奨事項](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)を公開しました。 このガイダンスでは、同意が必要なタイミングを明確にし、メールのピクセル追跡における適切な同意管理の重要性を強調しています。 このポリシーは、フランスに拠点を置く購読者にメールを配信するエンティティの送信方法に影響を与える可能性があります。

CNILは、企業がトラッキングピクセルの存在、目的、およびユーザーのオプトアウト権をメール受信者（「ユーザー」）に通知するための推奨日から3か月間を提供しました。 この移行期間中、顧客はユーザーにピクセルトラッキングについて通知し、必要に応じてオプトアウトを提供することが期待されます。 CNILは、2026年7月14日以降に強制執行活動を開始する予定です。

CNILや他の規制当局がピクセルのトラッキングや関連する問題に関するガイダンスを明確にするため、Adobeは引き続きアップデートをモニターし、Adobe Campaign Standardを含むメールマーケティングをサポートするAdobe製品の技術的能力をお客様に通知します。

Adobe Journey Optimizer、Journey Optimizer B2B、Adobe Campaign、Marketo EngageなどのAdobeの電子メールマーケティング実行アプリケーションには、配信レベルや電子メールレベルでオープントラッキングを管理するためのコントロールが備わっています。 顧客は、適用されるCNIL ガイダンスやその他の法律に基づいて独自のコンプライアンス義務を決定する責任を負いますが、これらの機能は顧客コンプライアンスの取り組みをサポートする可能性があります。

### メールトラッキングピクセルとは {#tracking-pixel}

電子メールトラッキングピクセルは、電子メールのHTMLに埋め込まれた1x1の透明画像です。 受信者のメールクライアントがその画像を読み込むと、ピクセルはタイムスタンプ、デバイスの種類、メールクライアント、場合によってはIP アドレスなどのデータを記録するサーバーにping送信し、おおよその場所を確認します。 その後、そのログは受信者のレコードに関連付けられ、マーケターはメールが開封されたかどうかを確認できます。

### カスタマーサポート {#support}

上記の変更の導入についてサポートを求めるお客様は、既存のAdobe エコシステムを利用できます。 参照されているAdobe機能に関する技術的な質問については、カスタマーサクセスマネージャーまたはテクニカルアカウントマネージャーにお問い合わせください。

## メールトラッキングに関連するAdobe Campaign Standard機能 {#acs-functionality}

Adobe Campaign Standardのネイティブなトラッキング、スキーマ、パーソナライゼーションメカニズムを使用して、アーキテクチャを構成する際に特定の要素に対処できます。

### メール分類 {#email-classification}

メールのタイプを示すカスタムフィールド（認証、配信品質のみ、トランザクション、同意を得たマーケティング、B2B見込み顧客）を使用して配信テンプレートを拡張します。 Campaign Standardでは、配信テンプレートを使用して、レポートやワークフローロジックに取り込むカスタムフィールドを管理できます。 この分類により、各送信に適切なトラッキングが決まります。

[配信テンプレートの作成と使用方法を学ぶ](../../channels/using/creating-an-email.md)

### 同意データモデル {#consent-data-model}

Campaign Standard カスタムリソースメカニズム（**管理/開発/カスタムリソース**）を介してプロファイルリソースを拡張し、目的ごとの同意フラグ、同意タイムスタンプ、最新の開封日（日付のみ、時間コンポーネントなし）を実行します。 プロファイルにリンクされた別のカスタムリソースは、個別の同意確認をサポートする追加専用の同意イベントログをキャプチャします。 Campaign Standard ランディングページはプロファイルフィールドに直接書き込むことができるため、現在の同意状態はネイティブで管理できます。同意ログは、環境設定が送信されると、Adobe Campaign Standard REST API （`/profileAndServicesExt`）を介して書き込まれます。

[リソースを作成または拡張する方法を説明します](../../developing/using/creating-or-extending-the-resource.md)

[API経由でカスタムリソースを操作する方法を説明します](../../api/using/interacting-with-custom-resources.md)

### ピクセル放出 {#pixel-emission}

Adobe Campaign Standardは、配信またはテンプレートプロパティの&#x200B;**[!UICONTROL Activate tracking]** トグルを使用して、配信レベルでのトラッキングを制御します。 開封トラッキングが合法でない配信（認証のみ、再勧誘メール）の場合、この切り替えは無効になります。 目的ごとのピクセルの出力が適切な配信の場合、1つのアプローチは、標準の自動挿入ピクセルを無効にし、条件付きの1×1のトラッキングされた画像要素（目的ごとに1つ）を含むコンテンツブロックを使用することです。各画像にはURL カテゴリ（`PIX_DELIV`、`PIX_PERF`、`PIX_PROFILE`、`PIX_FRAUD`）が割り当てられ、受信者の対応する同意フラグがtrueの場合にのみ表示されます。

[電子メールトラッキングパラメーターの設定方法を説明します](configuring-email-channel.md#tracking-parameters)

[メールDesignerでトラッキング対象URLを管理する方法を説明します](../../designing/using/links.md#about-tracked-urls)

[コンテンツブロックを追加する方法](../../designing/using/personalization.md#adding-a-content-block)

### 撤回 {#withdrawal}

登録解除リンクとは異なり、すべてのメールフッターに&#x200B;**トラッカー設定の管理** リンクを追加します。 リンクは、`recipientId`または`urlSubscription` メカニズムを介して認証されたCampaign Standard ランディングページを指しています。受信者は、目的ごとの同意フラグを切り替えて送信します。 確認すると、Campaign Standard REST APIへの小さな呼び出しにより、引き出しイベントが同意ログに書き込まれます。 この推奨事項は、このリンク自体がトラッキング要件から除外されていることを示しています。

[オプトインランディングページとオプトアウトランディングページを設定する方法について説明します](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)

[ランディングページの作成方法](../../channels/using/getting-started-with-landing-pages.md)

### 同意実証 {#consent-proof}

同意の変更（サインアップ時に取得、設定ページから更新、有効期限）ごとに、同意ログカスタムリソースに行が作成され、ワーディングバージョンコード、キャプチャタイムスタンプ、キャプチャソース、スコープが格納されます。 このログは、Campaign Standard エクスプローラーを通じてクエリ可能で、REST APIを介して公開でき、スケジュールされたワークフローを介してDPO レビュー用にエクスポートできます。

[API経由でカスタムリソースを操作する方法を説明します](../../api/using/interacting-with-custom-resources.md)

### 再勧誘ガバナンス {#re-solicitation}

プロファイル上のカスタム `cusLastPixelRefusalDate` フィールドと、選択した期間内にそのフィールドが存在するプロファイルを除外するタイポロジフィルタリングルールを組み合わせると、その時間内に拒否した受信者の再勧誘を防ぐことができます。 スケジュールされたワークフローでは、古いレコードにフラグを付け、有効期限イベントを同意ログに書き込むことで、顧客の同意の有効期限を管理します。

[タイポロジルールの使用方法を説明します](../../sending/using/about-typology-rules.md)

[タイポロジルールの管理方法を学ぶ](../../sending/using/managing-typology-rules.md)

### レポート {#reporting}

Campaign Standardのダイナミックレポートは、URL カテゴリとプロファイルディメンションにもとづいて構築されています。 上記で紹介した目的ごとのURL カテゴリーは、動的レポートに新しいディメンションとして表示され、オペレーターは目的ごとにデータをスライスして開き、クリックすることができます。 同意されたトラッキングと同意されていないトラッキングの違いは、URL カテゴリが配置されるとネイティブに表示されます。

[動的レポートの利用方法](../../reporting/using/about-dynamic-reports.md)

[トラッキング指標について詳しく見る](../../reporting/using/tracking-indicators.md)
