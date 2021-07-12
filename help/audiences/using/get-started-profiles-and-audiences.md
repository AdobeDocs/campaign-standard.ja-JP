---
solution: Campaign Standard
product: campaign
title: プロファイルとオーディエンスの基本を学ぶ
description: ターゲット母集団の定義、オーディエンスの選択、受信者のフィルタリング、データの収集、プロファイルの更新をおこないます。
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: プロファイル
role: User
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 25%

---

# プロファイルとオーディエンスの基本を学ぶ{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">セグメント化とターゲティング</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">権限と同意</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">プライバシーの遵守</a></p></td></tr>
</table>

Campaign の統合された顧客プロファイルにより、単一ビューであらゆるチャネルにまたがる顧客とのインタラクションを追跡し、顧客のニーズに応じてパーソナライズされたメッセージを配信できます。

データベースを個々のオーディエンスにセグメント化し、マーケティングキャンペーンのターゲットを最適化します。

顧客の権限および同意を管理し、サービスとランディングページを使用して、オプトインとオプトアウト用の容易なメカニズムを設定します。

## セグメント化とターゲティング {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

キャンペーンまたはメッセージを作成する際に、Campaignデータベース内の連絡先から、単純な条件または詳細な条件を使用して選択するか、オーディエンスを選択することで、配信のターゲットを指定できます。

**統合された顧客プロファイル**、**カスタマイズされたセグメント**、**コントロール母集団**&#x200B;を使用して、すべてのチャネルで顧客をより効果的に識別します。 顧客、興味、人口統計、チャネルの好みを把握している場合は、パーソナライズされたエクスペリエンスを簡単に作成して、気付きを得ることができます。

Adobe Campaignは、リッチな顧客プロファイルをリアルタイムで作成し、顧客の好みの変更に合わせて、より関連性の高いパーソナライズされたオファーを配信できます。 さらに、Adobe Campaignは、高度な分析、データ管理、ターゲティング機能を統合して、オーディエンスを構築します。

**** プロファイルとは、データベースに格納される個々の連絡先です。各プロファイルは、データベース内の1つのエントリに対応し、そのエントリにターゲット設定、認定、個別に追跡するために必要な情報が含まれます。Adobe Campaignは、オンラインとオフラインの両方のチャネルからのすべてのインタラクションを追跡し、1つのプロファイルに結合できます。

**** オーディエンスとは、特定の条件または一連の条件に基づいて作成されたプロファイルのリストです。ワークフローとクエリエディターを使用して、所有する情報、キャンペーンのアクティビティおよびマーケティング履歴に応じて、マーケティングキャンペーンのターゲットとなるオーディエンスを構築できます。 これにより、無制限数の条件に基づいて、購読済みのプロファイル、サンプル、ターゲットオーディエンスの作成をフィルタリングできます。

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

連絡先へのメッセージの送信を開始する前に、その連絡先の権限を取得していることを確認する必要があります。 そうでない場合、Eメールはスパムとしてマークされ、プラットフォームの配信品質に影響を与える可能性があります。 正常なプロファイルデータベースを確実に構築するには、最初の手順としてこの権限を保護します。

Campaignでは、**簡単なオプトインおよびオプトアウトメカニズム**&#x200B;から[サービス](../../audiences/using/creating-a-service.md)、[ランディングページ](../../channels/using/getting-started-with-landing-pages.md)を使用して連絡先情報を更新し、データベースを拡張することをお勧めします。

メッセージに&#x200B;**購読解除リンク**&#x200B;を指定すると、必要に応じてプロファイルをに追加できブロックリスト、プラットフォームの配信品質を向上できます。 管ブロックリスト理について詳しくは、[Campaignのオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)を参照してください。

>[!IMPORTANT]
>
>[Adobe Campaignの許容される使用ポリシー](https://www.adobe.com/legal/terms/aup.html)に従う必要があります。

詳しくは、以下を参照してください。

* [購読について](../../audiences/using/about-subscriptions.md)
* [Campaign のオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## プライバシーの遵守 {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaignは、GDPR、CCPA、その他のプライバシー法に関する&#x200B;**プライバシーコンプライアンス**&#x200B;に役立つ一連のツールを提供しています。

詳しくは、この[この記事](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy.html)では、プライバシー管理と、アクセスする権利、忘れられる権利、同意、データ保持、ユーザーの役割を管理するために提供する機能について説明します。

Campaignのプライバシーと同意とその管理方法については、[この節](../../start/using/privacy.md)を参照してください。 また、アドビのサービスを利用する際にプライバシーの順守に役立つベストプラクティスもご覧いただけます。

## その他のリソース

* [Campaign への Adobe Experience Platform オーディエンスの取り込み](../../integrating/using/ingest-aep-data.md)
* [Microsoft Dynamics 365の使用](../../integrating/using/d365-acs-get-started.md)
* [Adobe共有オーディエンス](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [ワークフローを使用したプロファイルのインポート](../../automating/using/creating-import-workflow-templates.md)
* [プロファイルとオーディエンスのビデオ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html)
