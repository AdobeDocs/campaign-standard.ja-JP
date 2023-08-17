---
title: プロファイルとオーディエンスの基本を学ぶ
description: ターゲット母集団の定義、オーディエンスの選択、受信者のフィルタリング、データの収集、プロファイルの更新を行います。
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: Profiles
role: User
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 25%

---

# プロファイルとオーディエンスの基本を学ぶ{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">セグメント化とターゲティング</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">権限と同意</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">プライバシーコンプライアンス</a></p></td></tr>
</table>

Campaign の統合された顧客プロファイルにより、単一ビューであらゆるチャネルにまたがる顧客とのインタラクションを追跡し、顧客のニーズに応じてパーソナライズされたメッセージを配信できます。

データベースを個々のオーディエンスにセグメント化し、マーケティングキャンペーンのターゲットを最適化します。

顧客の権限および同意を管理し、サービスとランディングページを使用して、オプトインとオプトアウト用の容易なメカニズムを設定します。

## セグメント化とターゲティング {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

キャンペーンまたはメッセージを作成する際に、Campaign データベース内の連絡先から、単純な条件または詳細な条件を使用して選択するか、オーディエンスを選択することで、配信のターゲットを指定できます。

を使用して、すべてのチャネルにわたってより効果的に顧客を特定する **統合顧客プロファイル**, **カスタマイズされたセグメント** および **コントロール母集団**. 顧客、興味、デモグラフィック、チャネルの環境設定を把握していれば、パーソナライズされたエクスペリエンスを簡単に作成して、気付きを得ることができます。

Adobe Campaignは、豊富な顧客プロファイルをリアルタイムで作成し、顧客の環境設定が変更されたときに、より関連性の高いパーソナライズされたオファーを配信できます。 また、Adobe Campaignは、高度な分析、データ管理、ターゲティング機能を統合して、オーディエンスを構築します。

**プロファイル** は、データベースに保存されている個々の連絡先です。 各プロファイルは、ターゲット設定、選定、個別追跡のために必要な情報を含む、データベース内の 1 つのエントリに対応します。Adobe Campaignでは、オンラインとオフラインの両方のチャネルからすべてのインタラクションを追跡し、1 つのプロファイルに結合できます。

**オーディエンス** は、特定の条件または条件のセットに基づいて作成されたプロファイルのリストです。 ワークフローとクエリエディターを使用すると、閲覧中の情報、閲覧中のアクティビティ、および閲覧履歴に応じて、マーケティングキャンペーンのターゲットとなるオーディエンスを構築できます。 これにより、無制限数の条件に基づいて、購読済みのプロファイルやサンプルを絞り込んだり、ターゲットオーディエンスを作成したりできます。

詳しくは、以下を参照してください。

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [アクティブなプロファイル](../../audiences/using/active-profiles.md)
* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [Campaign データベースの強化](../../audiences/using/enriching-campaign-database.md)
* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
* [コントロール母集団の追加](../../sending/using/control-group.md)

## 権限と同意 {#permission}

<img src="assets/do-not-localize/icon_permission.svg"  width="60px">

連絡先へのメッセージの送信を開始する前に、その連絡先の権限を取得していることを確認する必要があります。 そうでない場合、E メールがスパムとしてマークされている可能性があり、プラットフォームの配信品質に影響を与えます。 正常なプロファイルデータベースを確実に構築するには、最初の手順としてこの権限を保護します。

Campaign では、 **簡単なオプトインおよびオプトアウトメカニズム** 経由 [services](../../audiences/using/creating-a-service.md)、および [ランディングページ](../../channels/using/getting-started-with-landing-pages.md) 連絡先情報を更新し、データベースを拡張する場合。

提供中 **購読解除リンク** メッセージ内でプロファイルを必要に応じてブロックリストに加えるに追加できるので、プラットフォームの配信品質を向上できます。 管ブロックリストに加える理について詳しくは、 [Campaign のオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!IMPORTANT]
>
>次の項目を尊重する必要があります。 [Adobe Campaign使用許諾ポリシー](https://www.adobe.com/legal/terms/aup.html).

詳しくは、以下を参照してください。

* [購読について](../../audiences/using/about-subscriptions.md)
* [Campaign のオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## プライバシーコンプライアンス {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaignには、 **プライバシーコンプライアンス** GDPR、CCPA およびその他のプライバシーに関する法律に準拠する必要があります。

詳しくは、こちらを参照してください。 [この記事](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy.html) プライバシー管理と、アクセスする権利、忘れられる権利、同意、データ保持、ユーザーの役割を管理するために提供される機能について説明します。

Campaign のプライバシーと同意およびその管理方法については、 [この節](../../start/using/privacy.md). また、アドビのサービスを利用する際にプライバシーの順守に役立つベストプラクティスもご覧いただけます。

## その他のリソース

* [Campaign への Adobe Experience Platform オーディエンスの取り込み](../../integrating/using/ingest-aep-data.md)
* [Microsoft Dynamics 365 の操作](../../integrating/using/d365-acs-get-started.md)
* [Adobe共有オーディエンス](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [ワークフローを使用したプロファイルのインポート](../../automating/using/creating-import-workflow-templates.md)
* [プロファイルとオーディエンスのビデオ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html)
