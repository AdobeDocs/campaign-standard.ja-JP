---
title: Adobe Experience Platform Data Connector について
description: XDM スキーマを管理して、Adobe Experience PlatformでCampaign Standard データを利用できるようにします。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
source-git-commit: 7ad12890a24b2c0b8730d09b7d161bff511f4c69
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 3%

---

# Adobe Experience Platform Data Connector について {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは非推奨になりました。 非推奨（廃止予定）の機能は引き続き利用できますが、それ以上強化したり、サポートしたりすることはありません。 詳細[このページ内](../../rn/using/deprecated-features.md)

Adobe Experience Platform Data Connectorは、XTK データ（Campaignに取り込まれたデータ）をAdobe Experience PlatformのExperience Data Model （XDM）データにマッピングすることで、Adobe Experience Platformでデータを利用できるようにします。

コネクタは&#x200B;**一方向**&#x200B;であり、Adobe Campaign StandardからAdobe Experience Platformにデータを送信することに注意してください。 Adobe Experience PlatformからAdobe Campaign Standardにデータが送信されることはありません。

Adobe Experience Platform Data Connectorは、Adobe Campaign Standardのカスタムリソースを理解し、お客様の全体的なデータスキーマをAdobe Experience Platform内でどのように使用すべきかを理解している&#x200B;**データエンジニア**&#x200B;を対象としています。

次の節では、Campaign StandardとAdobe Experience Platform間のデータマッピングを実行するための主な手順について説明します。 まず、XDM スキーマとデータセットを作成します。

![](assets/do-not-localize/how-to-video.png) [ビデオでこの機能を確認する](#video)

>[!NOTE]
>Adobe Experience Platform Data Connectorが設定され、データがAdobe Experience Platformに正常に取り込まれたら、データがリアルタイム顧客プロファイルに含まれるように、データセットを有効にする必要があります。
>
>これは、APIまたはAdobe Experience Platformインターフェイスを通じて実行できます。 詳しくは、専用のドキュメントを参照してください。
>
>* [&#x200B; リアルタイム顧客プロファイルのデータセットを有効にする](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [APIを使用したリアルタイム顧客プロファイルおよびID サービスのデータセットの設定](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)

## 主な概念 {#key-concepts}

* 標準提供のマッピングは、デフォルトでCampaign Standardで提供されるフィールドでのみ使用できます。 すべてのカスタムフィールドとリソースを取り込むには、各顧客が独自のマッピングを定義する必要があります。

* Adobe Experience Platform Data Connectorは、プロファイルデータを定期的にプラットフォームにプッシュします&#x200B; インターバル期間は15分です。 この値は、[Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html)を使用して変更できます。

* データエンジニアは、CampaignからAdobe Experience Platformへのマッピングを公開、変更、一時停止できます。

* あらゆるターゲティングディメンションをマッピングできます。 1つのターゲティングディメンションのすべてのフィールドに対して1つのマッピングを設定することをお勧めします。

* チャネルのオプトイン/オプトアウトを含むすべてのプロファイル更新は、バッチアップデートの一部です。

* Adobe Campaign StandardまたはXDM スキーマの変更は、手動で再マッピングする必要があります。&#x200B;

* トラッキングログとブロードログデータは、Experience EventsとしてAdobe Experience Platformに自動的に取り込まれます。 この取り込みは、Adobe Experience Platformにリアルタイムでストリーミングされます。

* Experience Cloud ID サービス（ECID）は、Experience Eventsでデフォルトで送信されるデバイス IDです。

  これは、訪問者に割り当てられた一意の永続的なIDで、Platform ID サービスが同じ訪問者と異なるExperience Cloud ソリューション内のデータを識別するために使用できます。 詳しくは、[Experience Cloud Identity Service ヘルプ &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を参照してください。

  >[!NOTE]
  >
  >2つ以上のプロファイルが同じデバイスを共有する場合、ECIDはUnified ID サービス内のこれらの2つのプロファイルに対して同じになります。

## 制限事項 {#limitations}

* サブスクリプションイベントのすぐに使用できる転送はサポートされていません。 サブスクリプションイベントを転送するには、Adobe Experience Platformで対応するXDMとデータセットを作成し、これらのデータにカスタムデータマッピングを設定します。

* プライバシーリクエスト（アクセスと削除の両方のアクション）について、お客様は[Privacy Core Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)を介して個別のリクエストを配置する必要があります。Campaign用とAdobe Experience Platform用です。 詳しくは、「[&#x200B; プライバシーリクエストについて](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#righttoaccess)および[Campaignでのプライバシーリクエストの管理](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)」を参照してください。

* XDM フィールドごとに、DULE ラベル付けをAdobe Experience Platformで行う必要があります。 DULE ラベルを適用するのはお客様の責任です。

* マーケティングアクションに対する制限は、DULE ラベルがAdobe Experience Platformで適用された後にのみ適用されます。 それ以前は、あらゆる種類のマーケティング活動に関するすべてのデータが利用可能です。

* 15分ごとに、バッチジョブが実行され、最新のバッチ以降に変更されたレコードが識別されます。 すべてのレコードが同じタイムスタンプで変更された場合、すべてのプロファイルの取り込みを管理するためにパフォーマンスのボトルネックが発生する可能性があります

## チュートリアルビデオ {#video}

このビデオでは、Adobe Experience Platform Data Connectorの概要を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Adobe Experience Platform Data Connectorに関連するその他のビデオについては、[こちら](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)を参照してください。
