---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform Data Connector について
description: XDMスキーマを管理して、Campaign StandardデータをAdobe Experience Platformで利用できるようにします。
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 5%

---


# Adobe Experience Platform Data Connector について {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platformデータコネクタは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

Adobe Experience PlatformData Connectorは、XTKデータ(キャンペーンで取り込まれたデータ)をAdobe Experience Platformのエクスペリエンスデータモデル(XDM)データにマッピングすることで、既存のお客様がAdobe Experience Platformでデータを利用できるようにします。

コネクタは **単方向で** 、データをAdobe Campaign StandardからAdobe Experience Platformに送信します。 データはAdobe Experience PlatformからAdobe Campaign Standardに送られません。

Adobe Experience Platformデータコネクタは、 **Adobe Campaign Standardのカスタムリソースを理解し、お客様の全体的なデータスキーマがAdobe Experience Platform内でどのように行われるべきかを理解している** データエンジニアを対象としています。

以下の節では、Campaign StandardとAdobe Experience Platformの間のデータマッピングを実行するための主な手順について説明します。 XDMスキーマとデータセットの作成に関する開始です。

ハウツービデオも [このページで視聴できます](https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.translate.html)。

>[!NOTE]
>Adobe Experience Platformデータコネクタを設定し、データがAdobe Experience Platformに正常に取り込まれたら、データセットを有効にして、リアルタイムカスタマープロファイルにデータが含まれるようにする必要があります。
>
>これは、APIまたはAdobe Experience Platformインターフェイスを通して実行できます。 詳しくは、次の専用ドキュメントを参照してください。
>
>* [リアルタイム顧客プロファイルのデータセットの有効化](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [APIを使用したリアルタイム顧客プロファイルおよびIDサービスのデータセットの設定](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## 重要な概念 {#key-concepts}

* 初期設定のマッピングは、デフォルトでCampaign Standardで提供されるフィールドでのみ使用できます。 すべてのカスタムフィールドとリソースを取り込む場合は、各顧客が独自のマッピングを定義する必要があります。

* Adobe Experience PlatformData Connectorは、プロファイルデータを一定の間隔でプラットフォーム経由でプッシュ&#x200B;します。 間隔の長さは15 mnです。 この値は [Adobe Experience PlatformAPIを使用して変更できます](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)。

* データエンジニアは、キャンペーンからAdobe Experience Platformへのマッピングを公開、変更、および一時停止できます。

* 任意のターゲティングディメンションをマッピングできます。 単一のターゲティングディメンション内のすべてのフィールドに対して1つのマッピングを設定することをお勧めします。

* チャネルのオプトインやオプトアウトを含むすべてのプロファイルのアップデートは、バッチアップデートの一部です。

* Adobe Campaign StandardまたはXDMスキーマの変更は、手動で再マッピングする必要があり&#x200B;ます。

* トラッキングログおよびブロードログデータは、エクスペリエンスイベントとして自動的にAdobe Experience Platformに取り込まれます。 この摂取は、Adobe Experience Platformにリアルタイムでストリーミングされる。

* Experience CloudIDサービス(ECID)は、エクスペリエンスイベントと共にデフォルトで送信されるデバイス識別子です。

   このIDは、訪問者に割り当てられる一意で永続的なIDです。Platform Identity Serviceは、同じ訪問者とそのデータを異なるExperience Cloudソリューションで識別するために使用できます。 詳しくは、 [Experience CloudIDサービスのヘルプを参照してください](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.translate.html)。

   >[!NOTE]
   >
   >2つ以上のプロファイルが同じデバイスを共有している場合、ECIDはUnified Idサービスのこれらの2つのプロファイルで同じになることに注意してください。

## 制限事項{#limitations}

* 購読イベントの既製の転送はサポートされていません。 購読イベントを転送するには、Adobe Experience Platformで対応するXDMとデータセットを作成し、それらのデータに対するカスタムデータマッピングを設定します。

* プライバシーリクエスト（アクセスアクションと削除アクションの両方）に関しては、 [プライバシーコアサービスを介して個別のリクエストを設定する必要があります](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)。一つはキャンペーン用、もう一つはAdobe Experience Platform用。 詳しくは、「プライバシー要求 [について](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess) 」および「キャンペーンでのプライバシー要求の [管理](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) 」を参照してください。

* XDMフィールドごとに、DULEのラベル付けはAdobe Experience Platformで行う必要があります。 これは、DULEラベルを適用するお客様の責任です。

* マーケティングアクションに関する制限は、Adobe Experience PlatformでDULEラベルが適用された後にのみ適用されます。 それ以前は、すべてのタイプのマーケティングアクションですべてのデータを使用できます。

* バッチジョブは15分ごとに実行され、最新のバッチ以降に変更されたレコードが識別されます。 すべてのレコードが同じタイムスタンプで変更されると、すべてのプロファイルの取り込みを管理するためにパフォーマンスのボトルネックが発生する可能性があります。
