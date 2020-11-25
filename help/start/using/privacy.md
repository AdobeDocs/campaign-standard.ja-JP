---
solution: Campaign Standard
product: campaign
title: プライバシーと同意
description: Adobe Campaign Standardでのプライバシー、個人データ、同意管理について説明します。
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: c76f4b6e3bc0feb50e5776836552fdceaff61ea7
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 69%

---


# プライバシーと同意 {#privacy-and-consent}

## 一般的な推奨事項 {#general-recommendations}

Adobe Campaign は、個人情報や機密データを含む膨大な量のデータを収集および処理するための強力なツールです。そのため、プライバシー管理は慎重におこなう必要があります。

* 常に、個人情報を責任を持って倫理的に使用してください。

* 迷惑メール／プッシュ通知／SMS メッセージ（「スパム」）を送信しないでください。アドビは、顧客の生涯価値およびロイヤリティを促進するうえで許可型マーケティングの原則を重要視しています。したがって、未承諾メッセージの送信に Adobe Campaign を使用することを固く禁止しています。

### プライバシー規制 {#privacy-regulations}

プライバシーを正しく処理し、個人データを管理するには、事業をおこなう地域に適用される法律の範囲内で作業してください。次の規則が含まれます。
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)（ヨーロッパの一般データ保護規則）
* [DPA](https://www.gov.uk/data-protection)（英国実施の GDPR）
* [プライバシーと電子通信に関する欧州指令](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM 法](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)（商用 E メールのルールと要件を設定する米国の法律）
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)（カリフォルニア州消費者プライバシー法）
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)（タイ個人データ保護法）

>[!NOTE]
>
>For more on how GDPR, CCPA, PDPA, and LGPD apply to Adobe Campaign, see [this section](../../start/using/privacy-management.md#privacy-management-regulations).

### Adobe Experience Cloud プライバシー {#experience-cloud-privacy}

Adobe Campaign は、Adobe Experience Cloud ソリューションの一部です。キャンペーンでのプライバシーの処理方法は、次のようなAdobe Experience Cloudの一般原則に従います。

* **Adobe Experience Cloud を使用する際に収集される情報**

   Adobe Experience Cloud ソリューションを使用する会社は、収集して Adobe Experience Cloud アカウントに送信する情報を選択します。収集される情報のタイプの例としては、web 閲覧アクティビティ、IP アドレス、モバイルデバイスからの位置情報、キャンペーン成功率、購入品目、買い物かごに入れた品目などがあります。

   >[!NOTE]
   >
   >すべてのアドビ製品について、Campaign はアプリと web サイトのユーザーに関する情報を収集します。詳しくは、[アドビのプライバシーポリシー](https://www.adobe.com/jp/privacy/policy.html)を参照してください。

* **Adobe Experience Cloud を使用した情報収集の仕組み**

   * Adobe Experience Cloud ソリューションでは、情報を収集できるように、web ビーコン（タグやピクセルとも呼ばれます）などの Cookie および同様のテクノロジーを使用します。Cookie および Adobe Campaign を使用した追跡機能について詳しくは、[この節](#tracking-capabilities)を参照してください。
   * モバイルアプリで Adobe Experience Cloud テクノロジーを使用することもできます。キャンペーンと共にモバイル配信を送信する方法について詳しくは、 [このページを参照してください](https://helpx.adobe.com/jp/campaign/kb/acs-mobile.html)。

* **Adobe Experience Cloud の使用に関するユーザーのプライバシー選択**

   アドビから、次の内容を説明するプライバシーポリシーをお客様に提供するように求められます。

   * Adobe Experience Cloud に関するプライバシープラクティス
   * Adobe Experience Cloud に関連して、ユーザーが情報の収集や使用に関する環境設定をおこなう方法

   >[!NOTE]
   >
   >すべてのアドビ製品と同様に、Campaign のユーザーは、アプリや web サイトを通じて収集した共有情報をオプトアウトできます。詳しくは、[Adobe Experience Cloud の使用に関する FAQ](https://www.adobe.com/jp/privacy/experience-cloud-usage-info-faq.html) を参照してください。

Adobe Experience Cloud のプライバシーについて詳しくは、[このページ](https://www.adobe.com/jp/privacy/marketing-cloud.html)を参照してください。

## 個人データとペルソナ{#personal-data}

プライバシーを管理する場合、どのデータを誰がどのように扱うかを定義することが重要です。
* **個人データ**&#x200B;は、生きている個人を直接または間接的に識別できる情報です。
* **個人の機密データ**&#x200B;は、個人の人種、政治観、宗教的信念、犯罪歴、遺伝情報、健康データ、性的嗜好、生体認証情報、および労働組合の組合員に関する情報です。

When integrating Campaign with other Experience Cloud solutions where audiences can be transferred from one system to another, such as the [Audience Destinations service](../../audiences/using/aep-about-audience-destinations-service.md), [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager or People core service](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md), or with other solutions such as [Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md), you need to pay extra care to personal data protection.

The [main regulations](#privacy-regulations) refer to the different entities that manage data as follows:
* **データ管理者**&#x200B;は、個人データの収集、使用、共有の方法と目的を決定する権限です。
* **データ処理者**&#x200B;は、データ管理者の指示に従って個人データを収集、使用、または共有する個人または関係者です。
* **データ主体**&#x200B;は、個人データが収集、使用、共有され、その個人データを参照して直接または間接的に識別できる、生きている個人のことです。

したがって、個人データを収集し共有する会社はデータ管理者で、そのクライアントはデータ主体です。Adobe Campaign は、お客様の指示に従って個人データを処理する際に、データ処理者として機能します。[プライバシーリクエスト](#privacy-requests)を管理する場合など、データ主体との関係を処理するのはデータ管理者としての責任であることに注意してください。

### 使用事例シナリオ {#use-case-scenario}

以下は、GDPRの顧客体験の高度な使用例です。

この例では、航空会社の会社はAdobe Campaignの顧客です。 This company is the **Data Controller** and all the clients of the airline company are **Data Subjects**. この場合、Lauraは航空会社の顧客です。

この例は次の関係者で構成されます。

* **Laura** は&#x200B;**データ主体**&#x200B;で、彼女は航空会社の会社からメッセージを受け取る受信者です。 Lauraは頻繁にチラシになる可能性がありますが、ある時点では、航空会社の会社からの個人向けの広告やマーケティングのメッセージは望まないと判断する場合もあります。 そのため、航空会社に（所定のプロセスに基づいて）リピーター番号を削除するよう要求します。

* **Anne** は、航空会社の会社の **データコントローラー** です。 Laura からの要求を受け取り、このデータ主体を識別するための有意な ID を取得して、要求内容を Adobe Campaign に登録します。

* **Adobe Campaign** は **Data Processor**。

![](assets/privacy-gdpr-flow.png)

この例での一般的なフローを以下に示します。

1. The **Data Subject** (Laura) sends a GDPR request to the **Data Controller**, via email, customer care or a web portal.

1. **Data Controller** (Anne)は、GDPR要求をインターフェイス経由またはAPIを使用してキャンペーンにプッシュします。

1. Once the **Data Processor** (Adobe Campaign) receives the information, it takes action on the GDPR request and sends a response or acknowledgement to the **Data Controller** (Anne).

1. The **Data Controller** (Anne) then reviews the information and sends it back to the **Data Subject** (Laura).

## データの取得 {#data-acquisition}

Adobe Campaign を使用すると、個人情報や機密情報などのデータを収集できます。したがって、受信者の同意を受け取り、監視する必要があります。

* 受信者は常に通信の受信に同意するようにします。これをおこなうには、できるだけ早くオプトアウトリクエストを守り、二重のオプトインプロセスを通じて同意を確認します。詳しくは、「キャンペーンでのオプトインおよびオプトアウトの [管理](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) 」および「重複オプトインプロセスの [設定](../../channels/using/setting-up-a-double-opt-in-process.md)」を参照してください。
* 不正なリストを読み込んだり、トラップを使用して、クライアントファイルが不正に使用されていないかどうかを確認したりしないでください。 詳しくは、「トラップの [使用](../../sending/using/using-traps.md)」を参照してください。
* 同意と権限の管理を通じて、受信者の好みを追跡し、組織内の誰がどのデータにアクセスできるかを管理できます。詳しくは、[この節](#consent)を参照してください。
* 受信者からのプライバシーリクエストを促進および管理します。詳しくは、[この節](#privacy-requests)を参照してください。

## プライバシーの管理 {#privacy-management}

プライバシー管理とは、プライバシー規制（GDPR、CCPA など）の遵守に役立つすべてのプロセスとツールを指します。Get an overview of what Privacy management is on [this page](../../start/using/privacy-management.md).

Adobe Campaign では、プライバシー管理に関する様々な機能を提供しています。
* 同意の管理、データ保持、ユーザーの役割：[この節](#consent)を参照してください。
* プライバシーリクエスト（アクセスする権利と忘れられる権利）：[この節](#privacy-requests)を参照してください。
* 個人情報の販売のオプトアウト（CCPA 固有）：[この節](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ccpa)を参照してください。

Campaign の主なプライバシー機能と関与するペルソナの例を[この節](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)に示します。


### 同意、リテンション、役割 {#consent}

元々、Adobe Campaign はプライバシーに不可欠な重要な機能を提供しています。

* **同意の管理**：購読管理プロセスを通じて、受信者の環境設定を管理し、どの受信者がどの購読タイプにオプトインしたかを追跡できます。詳しくは、「 [購読](../../audiences/using/about-subscriptions.md) と [ランディングページ」を参照してください](../../channels/using/getting-started-with-landing-pages.md)。
* **データ保持**：すべての組み込みの標準ログテーブルには事前に設定された保存期間があり、通常、データのストレージは 6 か月以下に制限されます。その他の保存期間は、ワークフローで設定できます。詳しくは、アドビのコンサルタントまたは技術管理者にお問い合わせください。
* **権限管理**：Adobe Campaign では、事前作成された役割またはカスタムの役割を使用して、様々な Campaign オペレーターに割り当てられている権限を管理できます。これにより、会社内で様々なタイプのデータにアクセス、変更、書き出しできるユーザーを管理できます。詳しくは、[アクセス管理について](../../administration/using/about-access-management.md)を参照してください。

For more on these features and how to manage them in Adobe Campaign, see [this section](../../start/using/privacy-management.md#consent-retention-roles).

### プライバシーリクエスト {#privacy-requests}

Adobe Campaign は、特定のプライバシーリクエストに対するデータコントローラーとしての準備を容易にするための追加機能を提供します。

* **アクセスする権利**&#x200B;とは、データ主体がデータ管理者に対し、自分に関する個人データが処理されているかどうか、また処理されている場合はその場所と目的について確認できることを指します。

* 「**忘れられる権利**（削除リクエスト）」は、データ主体に対して、データ管理者が個人データを消去する権限を与えます。

The **Access** and **Delete** requests are presented in [this section](../../start/using/privacy-management.md#right-access-forgotten).

これらのリクエストを作成するための実装手順については、[この節](../../start/using/privacy-requests.md)で詳しく説明します。Tutorialsは [こちらからもご利用いただけます](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html)。

## トラッキング機能 {#tracking-capabilities}

Adobe Campaignでは、その追跡機能のおかげで、セッションcookieと永続的なcookieを使用して、配信受信者の動作を追跡できます。 For more on tracking, see [this section](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>GDPR（一般データ保護規則）などの規制では、企業は Cookie をインストールする前に web サイトのユーザーの同意をリクエストすることが規定されています。認証リクエストを通じて、貴社のサイトにWebトラッキングツールが装備されていることをユーザに通知する必要があります。

また、メッセージに [追跡リンク](../../designing/using/links.md#about-tracked-urls) を追加して、組み込みのトラッキングインジケーター [(](../../reporting/using/tracking-indicators.md) 追跡インジケーター [)レポートでの配信と受信者の動作の影響を測定したり、独自の](../../reporting/using/about-dynamic-reports.md)専用レポートを作成したりすることもできます。
