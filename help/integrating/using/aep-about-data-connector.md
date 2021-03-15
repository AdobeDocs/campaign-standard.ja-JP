---
solution: Campaign Standard
product: campaign
title: Adobe Experience Platform Data Connector について
description: XDMスキーマを管理して、Campaign StandardデータをAdobe Experience Platformで利用できるようにします。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM統合
role: Data Architect
level: 経験豊富な
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 6%

---


# Adobe Experience Platform Data Connector について {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platformデータコネクタは現在ベータ版で、予告なく頻繁に更新される可能性があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 ご利用になる場合は、Adobeカスタマーケアにお問い合わせください。

Adobe Experience PlatformData Connectorは、XTKデータ(キャンペーンで取り込まれたデータ)をAdobe Experience Platformのエクスペリエンスデータモデル(XDM)データにマッピングすることで、既存のお客様がAdobe Experience Platformでデータを利用できるようにします。

コネクタは&#x200B;**単方向**&#x200B;で、データをAdobe Campaign StandardからAdobe Experience Platformに送信します。 データはAdobe Experience PlatformからAdobe Campaign Standardに送られません。

Adobe Experience Platformデータコネクタは、Adobe Campaign Standardのカスタムリソースを理解し、お客様の全体的なデータスキーマがAdobe Experience Platform内でどのように行われるべきかを理解している&#x200B;**データエンジニア**&#x200B;を対象としています。

以下の節では、Campaign StandardとAdobe Experience Platformの間のデータマッピングを実行するための主な手順について説明します。 XDMスキーマとデータセットの作成に関する開始です。

![](assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

>[!NOTE]
>Adobe Experience Platformデータコネクタを設定し、データをAdobe Experience Platformに正常に取り込んだら、データセットを有効にして、リアルタイムカスタマープロファイルにデータが含まれるようにする必要があります。
>
>これは、APIまたはAdobe Experience Platformインターフェイスを通して実行できます。 詳しくは、次の専用ドキュメントを参照してください。
>
>* [リアルタイム顧客プロファイルのデータセットの有効化](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [APIを使用したリアルタイム顧客プロファイルおよびIDサービスのデータセットの設定](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## 重要な概念 {#key-concepts}

* 初期設定のマッピングは、デフォルトでCampaign Standardで提供されるフィールドでのみ使用できます。 すべてのカスタムフィールドとリソースを取り込む場合は、各顧客が独自のマッピングを定義する必要があります。

* Adobe Experience PlatformData Connectorは、プロファイルデータを一定の間隔でプラットフォーム経由でプッシュ&#x200B;します。 間隔の長さは15分です。 この値は[Adobe Experience PlatformAPI](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)を使用して変更できます。

* データエンジニアは、キャンペーンからAdobe Experience Platformへのマッピングを公開、変更、および一時停止できます。

* 任意のターゲティングディメンションをマッピングできます。 単一のターゲティングディメンション内のすべてのフィールドに対して1つのマッピングを設定することをお勧めします。

* チャネルのオプトインやオプトアウトを含むすべてのプロファイルのアップデートは、バッチアップデートの一部です。

* Adobe Campaign StandardまたはXDMスキーマの変更は、手動で再マッピングする必要があり&#x200B;ます。

* トラッキングログおよびブロードログデータは、エクスペリエンスイベントとして自動的にAdobe Experience Platformに取り込まれます。 この摂取は、Adobe Experience Platformにリアルタイムでストリーミングされる。

* Experience CloudIDサービス(ECID)は、エクスペリエンスイベントと共にデフォルトで送信されるデバイス識別子です。

   このIDは、訪問者に割り当てられる一意で永続的なIDです。Platform Identity Serviceは、同じ訪問者とそのデータを異なるExperience Cloudソリューションで識別するために使用できます。 詳しくは、[Experience CloudIDサービスのヘルプ](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.translate.html)を参照してください。

   >[!NOTE]
   >
   >2つ以上のプロファイルが同じデバイスを共有している場合、ECIDはUnified Idサービスのこれらの2つのプロファイルで同じになることに注意してください。

## 制限事項{#limitations}

* 購読イベントの既製の転送はサポートされていません。 購読イベントを転送するには、Adobe Experience Platformで対応するXDMとデータセットを作成し、それらのデータに対するカスタムデータマッピングを設定します。

* プライバシーリクエスト（アクセスと削除の両方のアクション）について、お客様は、[プライバシーコアサービス](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)を介して個別にリクエストを行う必要があります。一つはキャンペーン用、もう一つはAdobe Experience Platform用。 詳しくは、「プライバシー要求について[キャンペーンでの](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#righttoaccess)」および「[プライバシー要求の管理](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)」を参照してください。

* XDMフィールドごとに、DULEのラベル付けはAdobe Experience Platformで行う必要があります。 これは、DULEラベルを適用するお客様の責任です。

* マーケティングアクションに関する制限は、Adobe Experience PlatformでDULEラベルが適用された後にのみ適用されます。 それ以前は、すべてのタイプのマーケティングアクションですべてのデータを使用できます。

* バッチジョブは15分ごとに実行され、最新のバッチ以降に変更されたレコードが識別されます。 すべてのレコードが同じタイムスタンプで変更されると、すべてのプロファイルの取り込みを管理するためにパフォーマンスのボトルネックが発生する可能性があります。

## チュートリアルビデオ {#video}

このビデオでは、Adobe Experience PlatformのData Connectorの概要を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Adobe Experience PlatformのData Connectorに関する追加のビデオは、[こちら](https://docs.adobe.com/content/help/ja-JP/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.translate.html)で参照できます。
