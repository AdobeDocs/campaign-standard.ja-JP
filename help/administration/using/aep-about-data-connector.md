---
title: Adobe Experience Platform Data Connector について
description: XDMスキーマを管理し、Campaign StandardデータをAdobe Experience Platformで利用できるようにします。
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
source-git-commit: 9388df151eabbc6f63461e854d0276c14d9ef93d

---


# Adobe Experience Platform Data Connector について {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectorは現在ベータ版で、予告なく頻繁に更新される場合があります。 これらの機能にアクセスするには、お客様はAzureでホストされる必要があります（現在、北米の場合のみベータ版）。 ご利用になりたい場合は、アドビカスタマーケアにお問い合わせください。

Adobe Experience Platform Data Connectorは、XTKデータ(キャンペーンで取り込んだデータ)をAdobe Experience PlatformのExperience Data Model(XDM)データにマッピングすることで、既存のお客様がデータをAdobe Experience Platformで利用できるようにするのに役立ちます。

コネクタは単方向であり、 **Adobe Campaign** StandardからAdobe Experience Platformにデータを送信します。 データは、Adobe Experience PlatformからAdobe Standardに送信されることはありません。Adobe Campaign標準。

Adobe Experience Platform Data Connectorは、Adobe Campaign標準のカスタムリソースを理解し **** 、顧客の全体的なデータスキーマがAdobe Experience Platform内でどのように行われるかを理解しているデータエンジニアを対象としています。

以下の節では、Adobe Experience Platformとの間でデータマッピングを実行するための重要なCampaign Standard手順について説明します。 この開始は、XDMデータセットとスキーマセットの作成に関連しています。

ハウツービデオもこのページで視聴 [できます](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html)。

>[!NOTE]
>Adobe Experience Platform Data Connectorを設定し、データがAdobe Experience Platformに正常に取り込まれたら、データセットを有効にして、データがリアルタイム顧客プロファイルに含まれるようにする必要があります。
>
>これは、APIまたはAdobe Experience Platformインターフェイスを通じて実行できます。 詳しくは、次の専用ドキュメントを参照してください。
>
>* [リアルタイム顧客データセットの有効化プロファイル](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [APIを使用したリアルタイム顧客プロファイルおよびIDサービスのデータセットの設定](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## 重要な概念 {#key-concepts}

* デフォルトの「初期設定のマッピング」は、デフォルトでフィールドに対してのみCampaign Standardできます。 すべてのカスタムフィールドとリソースを取り込む場合、各顧客は独自のマッピングを定義する必要があります。

* Adobe Experience Platform Data Connectorは、一定の間隔でプロファイルデータをプラットフォーム経由でプッシュし&#x200B;ます。間隔の長さは15分です。 この値は、 [Adobe Experience Platform APIを使用して変更できます](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)。

* データエンジニアは、マッピングをAdobe Experience Platformに公開、変更およびキャンペーンできます。

* 任意のターゲティングディメンションをマップできます。 単一のマッピングで、すべてのフィールドに対して1つのマッピングを設定することをお勧めします。ターゲティングディメンション

* プロファイルのオプトインやオプトアウトを含むすべてのチャネルのアップデートは、バッチアップデートの一部です。

* Adobe Campaign標準またはXDMスキーマの変更は、手動で再マッピングする必要があり&#x200B;ます。

* 追跡ログとブロードログデータは、エクスペリエンスイベントとしてAdobe Experience Platformに自動的に取り込まれます。 この取り込みは、リアルタイムでAdobe Experience Platformにストリーミングされます。

* Experience Cloud IDサービス(ECID)は、デフォルトでエクスペリエンスのイベントと共に送信されるデバイス識別子です。

   これは、訪問者に割り当てられた一意で永続的なIDで、Platform Identity Serviceで同じ訪問者とそのデータを異なるExperience Cloudソリューションで識別するために使用できます。 詳しくは、 [Experience Cloud Identity Serviceヘルプを参照してください](https://docs.adobe.com/content/help/en/id-service/using/home.html)。

   >[!NOTE]
   >
   >2つ以上のプロファイルが同じデバイスを共有する場合、ECIDはUnified Idサービスのこれら2つのプロファイルに対して同じになることに注意してください。

## 制限事項 {#limitations}

* すぐに使用できる購読イベントの転送はサポートされません。 購読イベントを転送するには、対応するXDMとデータセットをAdobe Experience Platformで作成し、これらのデータに対するカスタムデータマッピングを設定します。

* プライバシーリクエスト（アクセスと削除の両方のアクション）に関して、顧客は別々のリクエストを作成する必要があります。1つはプライバシーコアサービスの統合(この節を [参照](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess))を介したキャンペーン用で、もう1つはプライバシーサービスを介したAdobe Experience Platform用 [です](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)。 アクセスおよび削除のリクエストについて詳しくは、このページを [参照してくださ](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)い。

* XDMフィールドごとに、DULEのラベル付けはAdobe Experience Platformで行う必要があります。 これは、DULEラベルを適用するお客様の責任です。

* マーケティングアクションに関する制限は、Adobe Experience PlatformでDULEラベルが適用された後にのみ適用されます。 その前に、すべてのタイプのマーケティングアクションですべてのデータを使用できます。

* バッチジョブは15分ごとに実行され、最新のバッチ以降に変更されたレコードを識別します。 すべてのレコードが同じタイムスタンプで変更されると、パフォーマンスのボトルネックが発生し、すべてのプロファイルの取り込みを管理
