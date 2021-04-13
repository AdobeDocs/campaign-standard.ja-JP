---
solution: Campaign Standard
product: campaign
title: プロファイルとオーディエンスの概要
description: ターゲット母集団の定義、オーディエンスの選択、受信者のフィルタリング、データの収集、プロファイルの更新をおこないます。
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: プロファイル
role: Business Practitioner
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
translation-type: tm+mt
source-git-commit: c5a9c27a2ce459dfd0f04159095bfc8a2cf4c0f6
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 23%

---

# プロファイルとオーディエンスの概要{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">セグメント化とターゲット設定</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">許可及び同意</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">プライバシーコンプライアンス</a></p></td></tr>
</table>

Campaign の統合された顧客プロファイルにより、単一ビューであらゆるチャネルにまたがる顧客とのインタラクションを追跡し、顧客のニーズに応じてパーソナライズされたメッセージを配信できます。

データベースをオーディエンスとしてセグメント化し、マーケティングキャンペーンのターゲットを最適化します。

顧客の権限および同意を管理し、サービスとランディングページを使用して、容易なオプトインおよびオプトアウトメカニズムを設定します。

## セグメント化とターゲット設定{#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

キャンペーンやメッセージを作成する場合は、キャンペーンデータベースの連絡先から選択するか、単純または詳細な条件を使用するか、オーディエンスを選択して、配信のターゲットを指定できます。

**統合顧客プロファイル**、**カスタマイズセグメント**、**コントロール母集団**&#x200B;を使用して、すべてのチャネルで顧客をより効果的に識別します。 顧客、興味、人口統計およびチャネルの環境設定を把握している場合は、気付かれるパーソナライズされたエクスペリエンスを簡単に作成できます。

Adobe Campaignはリッチな顧客プロファイルをリアルタイムで作成し、顧客の好みが変化した場合に、より関連性の高いパーソナライズされたオファーを提供できます。 さらに、Adobe Campaignは、高度な分析、データ管理、およびターゲット設定機能を統合してオーディエンスを構築します。

**** プロファイルは、データベースに格納されている個々の連絡先です。各プロファイルはデータベース内の1つのエントリに対応し、そのプロファイルがターゲット設定され、資格を持ち、個別に追跡されるために必要な情報が格納されます。Adobe Campaignは、オンラインとオフラインの両方のチャネルからすべてのインタラクションを追跡し、それを1つのプロファイルに統合できます。

**オーディエンス** とは、特定の条件または条件のセットに基づいて作成されたプロファイルのリストを指します。ワークフローとクエリエディターを使用すると、マーケティングキャンペーンが対象とするオーディエンスを構築できます。アクティビティ、マーケティング履歴に関する情報に応じて、その情報が表示されます。 これにより、登録済みのプロファイルをフィルタリング、サンプル、またはターゲットオーディエンスを無制限の数の条件で作成できます。

詳しくは、以下を参照してください。

* [プロファイルについて](../../audiences/using/about-profiles.md)
* [アクティブなプロファイル](../../audiences/using/active-profiles.md)
* [テストプロファイルの管理](../../audiences/using/managing-test-profiles.md)
* [Campaign データベースの強化](../../audiences/using/enriching-campaign-database.md)
* [オーディエンスについて](../../audiences/using/about-audiences.md)
* [メッセージ内のオーディエンスの選択](../../audiences/using/selecting-an-audience-in-a-message.md)
* [コントロール母集団の追加](../../sending/using/control-group.md)

## 許可と同意{#permission}

<img src="assets/do-not-localize/icon_permission.svg"  width="60px">

連絡先にメッセージを送信する前に、連絡先の権限が与えられていることを確認する必要があります。 そうでない場合は、電子メールがスパムとしてマークされる可能性があり、これはプラットフォームの配信品質に影響します。 正常なプロファイルデータベースを確実に作成するには、最初の手順としてこの権限を保護します。

キャンペーン上、**[サービス](../../audiences/using/creating-a-service.md)を通じて**&#x200B;簡単なオプトインとオプトアウトのメカニズムを使用し、[ランディングページ](../../channels/using/getting-started-with-landing-pages.md)を使用して連絡先情報を更新し、データベースを拡張することをお勧めします。

メッセージに&#x200B;**購読解除リンク**&#x200B;を指定すると、必要に応じてプロファイルをに追加できるので、プラットフォームの配信品質を向上できます。 キャンペーン管理について詳しくは、[でのオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)を参照してください。

>[!IMPORTANT]
>
>[Adobe Campaignが許容する使用ポリシー](https://www.adobe.com/legal/terms/aup.html)を尊重する必要があります。

詳しくは、以下を参照してください。

* [サブスクリプションについて](../../audiences/using/about-subscriptions.md)
* [Campaign のオプトインとオプトアウトについて](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## プライバシーへの準拠{#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaignオファーは、**GDPR、CCPA、その他のプライバシー法に関するプライバシーコンプライアンス**&#x200B;を支援するツールのセットを提供しています。

この[プライバシー管理と、アクセス権、忘れ去られる権利、同意、データ保持、ユーザーの役割を管理するために提供される機能についての詳細は、この記事](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy.html)を参照してください。

キャンペーンに関するプライバシーと同意、およびそれらの管理方法については、[このセクション](../../start/using/privacy.md)を参照してください。 また、アドビのサービスを利用する際にプライバシーの順守に役立つベストプラクティスもご覧いただけます。

## その他のリソース

* [Adobe Experience Platformオーディエンスをキャンペーンに取り込む](../../integrating/using/ingest-aep-data.md)
* [Microsoft Dynamics 365の操作](../../integrating/using/d365-acs-get-started.md)
* [Adobe共有オーディエンス](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [ワークフローを使用したプロファイルの読み込み](../../automating/using/creating-import-workflow-templates.md)
* [プロファイルとオーディエンスのビデオ](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html)
