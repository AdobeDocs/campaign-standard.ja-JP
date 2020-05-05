---
title: Adobe Experience Platform Data Connector について
description: XDMスキーマを管理して、Campaign StandardデータをAdobe Experience Platformで利用できるようにします。
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1dff41bc7b64d2f7ed7c88e002675e50e68a825f

---


# Adobe Experience Platform Data Connector について {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは、現在ベータ版です。この機能は、予告なく頻繁にアップデートされる場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米向けベータ版のみ）。 アドビカスタマーケアにお問い合わせの際は、アドビカスタマーケアにご連絡ください。

Adobe Experience Platform Data Connectorは、XTKデータ(キャンペーンで取り込まれるデータ)をAdobe Experience PlatformのExperience Data Model(XDM)データにマッピングすることで、既存のお客様がAdobe Experience Platformでデータを利用できるようにするの支援をします。

コネクタは **単方向で** 、Adobe Campaign標準からAdobe Experience Platformにデータを送信します。 データはAdobe Experience PlatformからAdobe Campaign標準に送信されません。

Adobe Experience Platform Data Connectorは、 **Adobe Campaign標準のカスタムリソースを理解し、顧客の全体的なデータスキーマがAdobe Experience Platform内でどのように行われるかを理解している** データエンジニアを対象としています。

以下の節では、Campaign StandardとAdobe Experience Platformの間でデータマッピングを実行するための主な手順について説明します。 XDMスキーマとデータセットの作成に関する開始です。

ハウツービデオも [このページで視聴できます](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)。

>[!NOTE]
>Adobe Experience Platform Data Connectorを設定し、データをAdobe Experience Platformに正常に取り込んだら、データセットを有効にして、リアルタイムカスタマープロファイルにデータが含まれるようにする必要があります。
>
>この処理は、APIまたはAdobe Experience Platformインターフェイスを通じて実行できます。 詳しくは、次の専用ドキュメントを参照してください。
>
>* [リアルタイム顧客プロファイルのデータセットの有効化](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [APIを使用したリアルタイム顧客プロファイルおよびIDサービスのデータセットの設定](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## 重要な概念 {#key-concepts}

* 初期設定のマッピングは、デフォルトでCampaign Standardで提供されるフィールドでのみ使用できます。 すべてのカスタムフィールドとリソースを取り込む場合は、各顧客が独自のマッピングを定義する必要があります。

* Adobe Experience Platform Data Connectorは、一定の間隔でプロファイルデータをプラットフォーム経由でプッシュ&#x200B;します。 間隔の長さは15 mnです。 この値は、 [Adobe Experience Platform APIを使用して変更できます](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)。

* データエンジニアは、キャンペーンからAdobe Experience Platformへのマッピングを公開、変更および一時停止できます。

* 任意のターゲティングディメンションをマッピングできます。 単一のターゲティングディメンション内のすべてのフィールドに対して1つのマッピングを設定することをお勧めします。

* チャネルのオプトインやオプトアウトを含むすべてのプロファイルのアップデートは、バッチアップデートの一部です。

* Adobe Campaign標準またはXDMスキーマの変更は、すべて手動で再マッピングする必要があり&#x200B;ます。

* 追跡ログおよびブロードログデータは、エクスペリエンスイベントとしてAdobe Experience Platformに自動的に取り込まれます。 この取り込みは、Adobe Experience Platformにリアルタイムでストリーミングされます。

* Experience Cloud IDサービス(ECID)は、デフォルトでExperienceイベントと共に送信されるデバイス識別子です。

   このIDは、訪問者に割り当てられる一意で永続的なIDです。Platform Identity Serviceは、同じ訪問者とそのデータを異なるExperience Cloudソリューションで識別するために使用します。 詳しくは、 [Experience Cloud Identity Serviceのヘルプを参照してください](https://docs.adobe.com/content/help/en/id-service/using/home.html)。

   >[!NOTE]
   >
   >2つ以上のプロファイルが同じデバイスを共有している場合、ECIDはUnified Idサービスのこれらの2つのプロファイルで同じになることに注意してください。

## 制限事項 {#limitations}

* 購読イベントの既製の転送はサポートされていません。 購読イベントを転送するには、Adobe Experience Platformで対応するXDMとデータセットを作成し、それらのデータに対するカスタムデータマッピングを設定します。

* プライバシーリクエスト（アクセスアクションと削除アクションの両方）に関しては、 [プライバシーコアサービスを介して個別のリクエストを行う必要があります](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests)。 1つはキャンペーン用、もう1つはAdobe Experience Platform用です。 詳しくは、「プライバシー要求 [について](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess) 」および「キャンペーンでのプライバシー要求の [管理](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) 」を参照してください。

* XDMフィールドごとに、DULEのラベル付けはAdobe Experience Platformで行う必要があります。 これは、DULEラベルを適用するお客様の責任です。

* マーケティングアクションに関する制限は、Adobe Experience PlatformでDULEラベルが適用された後にのみ適用されます。 それ以前は、すべてのタイプのマーケティングアクションですべてのデータを使用できます。

* バッチジョブは15分ごとに実行され、最新のバッチ以降に変更されたレコードが識別されます。 すべてのレコードが同じタイムスタンプで変更されると、すべてのプロファイルの取り込みを管理するためにパフォーマンスのボトルネックが発生する可能性があります。
