---
title: Adobe Experience Platform Data Connector について
description: XDMスキーマを管理して、Adobe Experience PlatformでCampaign Standardデータを利用できるようにします。
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 5%

---

# Adobe Experience Platform Data Connector について {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは現在ベータ版です。通知なしに頻繁に更新される可能性があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米でのみベータ版）。 にアクセスする場合は、Adobeカスタマーケアにお問い合わせください。

Adobe Experience Platform Data Connectorを使用すると、XTKデータ（Campaignで取り込んだデータ）をAdobe Experience PlatformのExperience Data Model(XDM)データにマッピングすることで、既存のお客様がAdobe Experience Platformでデータを利用できるようになります。

コネクタは&#x200B;**一方向**&#x200B;で、Adobe Campaign StandardからAdobe Experience Platformにデータを送信します。 データはAdobe Experience PlatformからAdobe Campaign Standardに送信されません。

Adobe Experience Platform Data Connectorは、Adobe Campaign Standardのカスタムリソースを理解し、顧客の全体的なデータスキーマをAdobe Experience Platform内に配置する方法を理解できる&#x200B;**データエンジニア**&#x200B;を対象としています。

次の節では、Adobe Experience PlatformとCampaign Standardの間でデータマッピングを実行するための主な手順について説明します。 まず、XDMスキーマとデータセットの作成から始めます。

![](assets/do-not-localize/how-to-video.png) [この機能をビデオで確認](#video)

>[!NOTE]
>Adobe Experience Platform Data Connectorを設定し、データがAdobe Experience Platformに正常に取り込まれたら、データがリアルタイム顧客プロファイルに含まれるようにデータセットを有効にする必要があります。
>
>これは、APIまたはAdobe Experience Platformインターフェイスを使用して実行できます。 詳しくは、該当するドキュメントを参照してください。
>
>* [リアルタイム顧客プロファイルのデータセットの有効化](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [APIを使用したリアルタイム顧客プロファイルおよびIDサービスのデータセットの設定](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)


## 主要概念 {#key-concepts}

* デフォルトのマッピングは、デフォルトで「Campaign Standard」で指定されるフィールドに対してのみ使用できます。 すべてのカスタムフィールドとリソースを取り込むには、各顧客が独自のマッピングを定義する必要があります。

* Adobe Experience Platform Data Connectorは、一定の間隔でプラットフォームを通じてプロファイルデータをプッシュしま&#x200B;す。 期間は15分です。 この値は、[Adobe Experience Platform API](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html)を使用して変更できます。

* データエンジニアは、CampaignからAdobe Experience Platformへのマッピングをパブリッシュ、変更および一時停止できます。

* 任意のターゲティングディメンションをマッピングできます。 単一のターゲティングディメンションでは、すべてのフィールドに対して1つのマッピングを使用することをお勧めします。

* チャネルのオプトイン/オプトアウトを含むすべてのプロファイル更新は、一括更新の一部です。

* Adobe Campaign StandardまたはXDMスキーマの変更は、手動で再マッピングする必要がありま&#x200B;す。

* トラッキングログおよびBroadLogデータは、Adobe Experience Platformにエクスペリエンスイベントとして自動的に取り込まれます。 この取り込みは、Adobe Experience Platformにリアルタイムでストリーミングされます。

* Experience CloudIDサービス(ECID)は、デフォルトでエクスペリエンスイベントと共に送信されるデバイス識別子です。

   訪問者に割り当てられる一意の永続的IDで、Platform IDサービスで、異なるExperience Cloudソリューションで同じ訪問者とそのデータを識別するために使用できます。 詳しくは、Experience CloudIDサービスのヘルプ[を参照してください。](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)

   >[!NOTE]
   >
   >2つ以上のプロファイルが同じデバイスを共有する場合、統合IDサービスのこれら2つのプロファイルでECIDは同じになることに注意してください。

## 制限事項 {#limitations}

* 購読イベントの既製の転送はサポートされていません。 サブスクリプションイベントを転送するには、対応するXDMとデータセットをAdobe Experience Platform上に作成し、それらのデータのカスタムデータマッピングを設定します。

* プライバシーリクエスト（アクセスアクションと削除アクションの両方）に関しては、[Privacy Core Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)を介して個別のリクエストをおこなう必要があります。1つはキャンペーン用、もう1つはAdobe Experience Platform用です。 詳しくは、Campaignの[プライバシーリクエスト](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#righttoaccess)および[プライバシーリクエストの管理](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)を参照してください。

* XDMフィールドごとに、DULEラベル付けをAdobe Experience Platformでおこなう必要があります。 DULEラベルを適用するのは、お客様の責任です。

* マーケティングアクションの制限は、Adobe Experience Platformでデータラベルが適用された後にのみ適用されます。 それ以前は、すべてのタイプのマーケティングアクションですべてのデータを使用できます。

* バッチジョブは15分ごとに実行され、最新のバッチ以降に変更されたレコードを識別します。 すべてのレコードが同じタイムスタンプで変更されると、すべてのプロファイルの取り込みを管理するパフォーマンスのボトルネックが発生する可能性があります

## チュートリアルビデオ {#video}

このビデオでは、Adobe Experience Platform Data Connectorの概要を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Adobe Experience Platform Data Connectorに関するその他のビデオは、[こちら](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)から参照できます。
