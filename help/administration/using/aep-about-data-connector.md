---
title: Adobe Experience Platform Data Connectorについて
description: XDMスキーマを管理して、Adobe Experience PlatformでCampaign Standardデータを利用できるようにします。
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
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# Adobe Experience Platform Data Connectorについて {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、Azureでホストする必要があります（現在、北米向けベータ版のみ）。 ご希望の場合は、アドビカスタマーケアにお問い合わせください。

Adobe Experience Platform Data Connectorは、XTKデータ（Campaignで取り込んだデータ）をAdobe Experience PlatformのExperience Data Model(XDM)データにマッピングすることで、既存のお客様がAdobe Experience Platformでデータを利用できるようにするの支援を行います。

コネクターは一方向で **あり** 、データをAdobe Campaign StandardからAdobe Experience Platformに送信します。 データはAdobe Experience PlatformからAdobe Campaign Standardに送信されません。

Adobe Experience Platform Data Connectorは、Adobe Campaign Standardのカスタムリソースを理解し、顧客の全体的なデータスキーマをAdobe Experience Platform内でどのように扱うべきかを理解しているデータエンジニアを対象としています。 ****

以下の節では、Campaign StandardとAdobe Experience Platformの間でデータマッピングを実行するための主要な手順について説明します。 これは、XDMスキーマとデータセットの作成から始まります。

>[!NOTE]
>Adobe Experience Platform Data Connectorを設定し、データがAdobe Experience Platformに正常に取り込まれたら、データセットを有効にして、リアルタイムカスタマープロファイルにデータが含まれるようにする必要があります。
>
>これは、APIまたはAdobe Experience Platformインターフェイスを通じて実行できます。 詳しくは、次の専用ドキュメントを参照してください。
>
>* [リアルタイム顧客プロファイルのデータセットの有効化](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/data_ingestion_tutorial/data_ingestion_tutorial.md)
>* [APIを使用したReal-time Customer Profile and Identity Serviceのデータセットの設定](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/unified_profile_dataset_tutorial/unified_profile_dataset_api_tutorial.md)


## 重要な概念 {#key-concepts}

* デフォルトのデフォルトのマッピングは、Campaign Standardでデフォルトで提供されるフィールドに対してのみ使用できます。 すべてのカスタムフィールドとリソースを取り込む場合は、各顧客が独自のマッピングを定義する必要があります。

* Adobe Experience Platform Data Connectorは、一定の間隔でプラットフォームを通じてプロファイルデータをプッシュしま&#x200B;す。間隔の長さは15分です。 この値は変更できません。

   >[!NOTE]
   >
   >この期間は、 [Adobe Experience Platform APIを使用して変更できます](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/authenticate_to_acp_tutorial/authenticate_to_acp_tutorial.md)。

* データエンジニアは、CampaignからAdobe Experience Platformへのマッピングを公開、変更および一時停止できます。

* 任意のターゲットディメンションをマッピングできます。 単一のターゲットディメンション内のすべてのフィールドに対して、1つのマッピングを設定することをお勧めします。

* チャネルオプトインやオプトアウトを含むすべてのプロファイルの更新は、バッチ更新の一部です。

* Adobe Campaign StandardまたはXDMスキーマの変更は、手動で再マッピングする必要がありま&#x200B;す。

* 追跡ログとブロードローグデータは、エクスペリエンスイベントとしてAdobe Experience Platformに自動的に取り込まれます。 このインジェストは、Adobe Experience Platformにリアルタイムでストリーミングされます。

## 制限事項 {#limitations}

* 購読イベントの既製の転送はサポートされていません。 購読イベントを転送するには、Adobe Experience Platformで対応するXDMとデータセットを作成し、これらのデータに対するカスタムデータマッピングを設定します。

* プライバシーリクエストに関しては、顧客は、アクセスおよび削除の両方のアクションに対して、CampaignコアプライバシーサービスとAdobe Experience Platformに対して別々のリクエストを行う必要があります。

* XDMフィールドごとに、DULEのラベル付けはAdobe Experience Platformで行う必要があります。 これは、DULEラベルを適用するお客様の責任です。

* マーケティングアクションに関する制限は、Adobe Experience PlatformでDULEラベルが適用された後にのみ適用されます。 その前に、すべてのタイプのマーケティングアクションですべてのデータを使用できます。

* バッチジョブは15分ごとに実行され、最新のバッチ以降に変更されたレコードを識別します。 すべてのレコードが同じタイムスタンプで変更されると、すべてのプロファイルの取り込みを管理するためのパフォーマンスのボトルネックが発生する可能性があります。
