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
source-wordcount: '591'
ht-degree: 14%

---

# プロファイルとオーディエンスの基本を学ぶ{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">セグメント化とターゲティング</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">許可と同意</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">プライバシーコンプライアンス</a></p></td></tr>
</table>

Campaign 統合顧客プロファイルを使用すると、1 つのビュー内のすべてのチャネルをまたいで顧客とのすべてのインタラクションを追跡でき、関連性が高くパーソナライズされたメッセージを顧客に提供できます。

データベースを個々のオーディエンスにセグメント化し、マーケティングキャンペーンのターゲットを最適化します。

顧客の権限および同意を管理し、サービスとランディングページを使用して、オプトインとオプトアウト用の容易なメカニズムを設定します。

## セグメント化とターゲティング {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

キャンペーンやメッセージを作成する際は、Campaign データベースの連絡先から選択するか、簡単または高度な条件を使用するか、オーディエンスを選択することで、配信のターゲットを指定できます。

**統合顧客プロファイル**、**カスタマイズされたセグメント** および **コントロール母集団** を使用して、すべてのチャネルにわたって効果的に顧客を特定します。 顧客、興味、人口統計、チャネルの環境設定がわかっている場合は、パーソナライズされたエクスペリエンスを作成して気づくことがより簡単になります。

Adobe Campaignは、豊富な顧客プロファイルをリアルタイムで構築するので、顧客の好みの変化に合わせて、より関連性が高く、パーソナライズされたオファーを提供できます。 さらに、Adobe Campaignでは、高度な分析、データ管理およびターゲティング機能を統合して、オーディエンスを構築します。

**プロファイル** は、データベースに保存される個々の連絡先です。 各プロファイルは、データベース内の 1 つのエントリに対応します。このエントリには、そのプロファイルがターゲットとなり、選定され、個別に追跡されるために必要な情報が含まれています。Adobe Campaignでは、オンラインチャネルとオフラインチャネルの両方からのすべてのインタラクションを追跡し、それを 1 つのプロファイルに結合できます。

**オーディエンス** は、特定の条件または一連の条件に基づいて作成されたプロファイルのリストです。 ワークフローとクエリエディターを使用すると、マーケティングキャンペーンに関する情報、アクティビティ、マーケティング履歴に応じて、マーケティングキャンペーンのターゲットとなるオーディエンスを構築できます。 これにより、購読しているプロファイルやサンプルをフィルタリングしたり、無制限の数の条件でターゲットオーディエンスを作成したりできます。

詳しくは、以下を参照してください。

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [アクティブなプロファイル](../../audiences/using/active-profiles.md)
* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [Campaign データベースの強化](../../audiences/using/enriching-campaign-database.md)
* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
* [コントロール母集団の追加](../../sending/using/control-group.md)

## 許可と同意 {#permission}

<img src="assets/do-not-localize/icon_permission.svg"  width="60px">

連絡先にメッセージを送信する前に、その連絡先の権限を取得する必要があります。 そうでない場合、メールはスパムとしてマークされる可能性があり、プラットフォームの配信品質に影響を与えます。 正常なプロファイルデータベースを確実に作成するには、最初の手順としてこの権限を保護します。

Campaign では、[ サービス ](../../audiences/using/creating-a-service.md) および [ ランディングページ **を通じて** 簡単なオプトインおよびオプトアウトメカニズム ](../../channels/using/getting-started-with-landing-pages.md) を使用して、連絡先情報を更新し、データベースを強化することをお勧めします。

メッセージに **購読解除リンク** を提供すると、必要に応じてプロファイルをブロックリストに追加できるので、プラットフォームの配信品質が向上します。 ブロックリストの管理について詳しくは、[Campaign のオプトインとオプトアウトについて ](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md) を参照してください。

>[!IMPORTANT]
>
>[Adobe Campaignの利用規定 ](https://www.adobe.com/legal/terms/aup.html) に従う必要があります。

詳しくは、以下を参照してください。

* [購読について](../../audiences/using/about-subscriptions.md)
* [Campaign のオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## プライバシーコンプライアンス {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaignには、GDPR、CCPA およびその他のプライバシー保護法に関する **プライバシーコンプライアンス** に役立つ各種のツールが用意されています。

プライバシー管理と、アクセス権、忘れられる権利、同意、データ保持、ユーザーの役割を管理するために提供する機能について詳しくは、この [ この記事 ](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy.html) を参照してください。

Campaign のプライバシーと同意、およびその管理方法については、[ この節 ](../../start/using/privacy.md) を参照してください。 また、アドビのサービスを利用する際にプライバシーの順守に役立つベストプラクティスもご覧いただけます。

## その他のリソース

* [Campaign への Adobe Experience Platform オーディエンスの取り込み](../../integrating/using/ingest-aep-data.md)
* [Microsoft Dynamics 365 の操作](../../integrating/using/d365-acs-get-started.md)
* [共有オーディエンスのAdobe](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [ワークフローを使用したプロファイルのインポート](../../automating/using/creating-import-workflow-templates.md)
* [ プロファイルとオーディエンスビデオ ](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html?lang=ja)
