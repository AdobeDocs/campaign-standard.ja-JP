---
title: Adobe Campaign基準におけるプライバシーと同意
description: この節では、Adobe Campaign標準のプライバシー管理、個人データ管理、同意管理、およびこれらを処理するために利用できるツールの概要について説明します。
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: faddcc870adcf9e71e50004a69a219b16ddc044f

---


# Privacy and Consent{#privacy-and-consent}

## 一般的な推奨事項 {#general-recommendations}

Adobe Campaignは、個人情報や機密データなど、非常に大量のデータを収集し、処理する強力なツールです。 そのため、プライバシー管理は慎重に行う必要があります。

* 常に、個人情報を責任を持って倫理的に使用しなさい。

* 迷惑メール、プッシュ通知、SMSメッセージ（「スパム」）を送信しないでください。 アドビは、顧客の生涯価値や忠誠度を高めるための許可型マーケティングの原則を強く信じており、そのため、非要請メッセージの送信におけるAdobe Campaignの使用を厳禁しています。

### プライバシー規制 {#privacy-regulations}

プライバシーを正しく処理し、個人データを管理するには、業務を行う地域に適用できる議会内で作業します。 次の規則が含まれます。
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) （ヨーロッパの全般的なデータ保護規制）
* [DPA](https://www.gov.uk/data-protection) （英国のGDPR実装）
* [プライバシーと電子通信に関する欧州指令](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) （商用電子メールのルールと要件を設定する米国の法律）
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) （カリフォルニア消費者プライバシー法）
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) （タイ個人データ保護法）

>[!NOTE]
>
>GDPR、CCPA、およびPDPAがAdobe Campaignにどのように適用されるかについて詳しくは、 [このページを参照してください](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr)。

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

Adobe Campaignは、Adobe Experience Cloudソリューションの一部です。 Adobe Experience Cloudの一般原則（例：次のような）に従って、キャンペーンでのプライバシーの処理方法を指定します。

* **Adobe Experience Cloudを使用する際に収集される情報**

   Adobe Experience Cloudソリューションを使用する会社は、収集する情報を選択し、Adobe Experience Cloudアカウントに送信します。 収集される情報のタイプの例としては、ウェブ閲覧アクティビティ、IPアドレス、モバイルデバイスからの場所情報、キャンペーン成功率、購入した品目、買い物かごに入れた品目などがあります。

   >[!NOTE]
   >
   >すべてのアドビ製品について、キャンペーンはアプリとWebサイトのユーザーに関する情報を収集します。 詳しくは、 [アドビのプライバシーポリシーを参照してください](https://www.adobe.com/privacy/policy.html)。

* **Adobe Experience Cloudを使用した情報収集の仕組み**

   * Adobe Experience Cloudソリューションでは、情報を収集できるように、Webビーコン（タグやピクセルとも呼ばれます）などのcookieおよび同様のテクノロジーを使用します。 CookieおよびAdobe Campaignを使用した追跡機能について詳しくは、 [この節を参照してください](#tracking-capabilities)。
   * モバイルアプリでAdobe Experience Cloudテクノロジーを使用することもできます。 キャンペーンと共にモバイル配信を送信する方法について詳しくは、 [このページを参照してください](https://helpx.adobe.com/jp/campaign/kb/acs-mobile.html)。

* **Adobe Experience Cloudの使用に関するユーザーのプライバシー選択**

   アドビから、次の内容を説明するプライバシーポリシーをお客様に提供するように求められます。

   * Adobe Experience Cloudに関するプライバシープラクティス
   * Adobe Experience Cloudに関連して、ユーザーが情報の収集や使用に関する環境設定を行う方法
   >[!NOTE]
   >
   >すべてのアドビ製品について、キャンペーンユーザーは、収集した情報をアプリやWebサイトで共有することをオプトアウトできます。 詳しくは、 [Adobe Experience Cloudの使用状況に関するFAQを参照してください](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html)。

Adobe Experience Cloudのプライバシーについて詳しくは、 [このページを参照してください](https://www.adobe.com/privacy/marketing-cloud.html)。

## 個人データと個人 {#personal-data}

プライバシーを管理する際は、データの扱い方と扱い方を明確にすることが重要です。
* **「個人データ** 」は、生きている個人を直接または間接的に識別できる情報です。
* **「個人の機密データ** 」は、個人の人種、政治表示、宗教的信念、犯罪的背景、遺伝情報、健康データ、性的嗜好、生体認証情報、および貿易和集合の会員に関する情報です。

主な [立法は](#privacy-regulations) 、次のようにデータを管理する様々なエンティティを指します。
* Data **Controller** （データコントローラ）は、個人データの収集、使用、共有の方法と目的を決定する権限です。
* デ **ータプロセッサ** (Data Processor)は、データコントローラーの指示に従って個人データを収集、使用、または共有する個人または関係者です。
* 「 **データの対象** 」とは、個人データが収集、使用、共有され、その個人データを参照して直接または間接的に識別できる、生きている個人のことです。

したがって、個人データを収集し共有する会社として、お客様はData Controllerであり、お客様のクライアントはData Subjectsであり、Adobe Campaignは、お客様の指示に従って個人データを処理する際に、Data Processorとして機能します。 データサブジェクトとの関係( [プライバシー要求の管理など)は、データコントローラとしてお客様の責任で処理する必要があります](#privacy-requests)。

オーディエンスを [オーディエンス先サービス、](../../audiences/using/aep-about-audience-destinations-service.md)Adobe Analytics [、](../../integrating/using/about-campaign-analytics-integration.md)オーディエンスマネージャー [、Peopleコアサービスなど、別のシステムにキャンペーンを移行できる他のExperience Cloudソリューションとの統合時には、個人データ保護のための特別な支援が必要](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)[](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)です。

## データの取得 {#data-acquisition}

Adobe Campaignを使用すると、個人情報や機密情報などのデータを収集できます。 したがって、受信者の同意を受け取り、監視する必要があります。

* 受信者は常に通信の受信に同意するようにします。 これを行うには、できるだけ早くオプトアウト要求を実行し、重複のオプトインプロセスを通じて同意を確認します。 詳しくは、「キャンペーンでのオプトインおよびオプトアウトの [管理](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) 」および「重複オプトインプロセスの [設定](../../channels/using/setting-up-a-double-opt-in-process.md)」を参照してください。
* 不正なリストを読み込んだり、トラップを使用して、クライアントファイルが不正に使用されていないかどうかを確認したりしないでください。 詳しくは、「トラップの [使用](../../sending/using/using-traps.md)」を参照してください。
* 同意と権限管理を通じて、受信者の好みを追跡でき、組織内の誰がどのデータにアクセスできるかを管理できます。 詳しくは、[この節](#consent)を参照してください。
* 受信者からのプライバシー要求を容易にし、管理できます。 詳しくは、[この節](#privacy-requests)を参照してください。

## プライバシーの管理 {#privacy-management}

プライバシー管理とは、プライバシー規制（GDPR、CCPAなど）の遵守に役立つすべてのプロセスとツールを指します。 このページのプライバシー管理の概要を確認 [します](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy-overview.html)。

Adobe Campaignでは、プライバシー管理に関する様々な機能を提供しています。
* 同意の管理、データ保持、ユーザーの役割を参照してください。 [この節](#consent)を参照してください。
* プライバシー要請（アクセス権と忘れ去られる権利） [この節](#privacy-requests)を参照してください。
* 個人情報の販売のオプトアウト（CCPA固有） [この節](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)を参照してください。

キャンペーンの主なプライバシー機能と関与する個人の例を [この節に示します](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)。


### 同意、リテンション、役割 {#consent}

もともと、Adobe Campaignオファーはプライバシーに不可欠な重要な機能です。

* **同意の管理**: 購読管理プロセスを通じて、受信者の環境設定を管理し、どの受信者がどの購読のタイプにオプトインしたかを追跡できます。 詳しくは、「 [購読](../../audiences/using/about-subscriptions.md) と [ランディングページ」を参照してください](../../channels/using/getting-started-with-landing-pages.md)。
* **データ保持**: すべての組み込みの標準ログ・テーブルには事前に設定された保存期間があり、通常、データのストレージは6か月以下に制限されます。 その他の保存期間は、ワークフローで設定できます。 詳しくは、アドビのコンサルタントまたは技術管理者にお問い合わせください。
* **権限管理**: Adobe Campaignでは、様々な事前ビルドロールまたはカスタムロールを使用して、様々なキャンペーン操作者に割り当てられた権限を管理できます。 これにより、会社内で様々なタイプのデータにアクセス、変更、またはエクスポートできるユーザーを管理できます。 For more on this, see [About access management](../../administration/using/about-access-management.md).

これらの機能およびAdobe Campaignでの管理方法について詳しくは、 [このページを参照してください](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent)。

### Privacy requests {#privacy-requests}

Adobe Campaignは、特定のプライバシー要求に対するデータコントローラーとしての準備を容易にするための追加機能を提供します。

* The **Right to Access** is the right for the Data Subject to obtain from the Data Controller confirmation as to whether or not personal data concerning them is being processed, where and why.

* 「 **Right to be Fogrotted** (delete request)」は、Data Subjectに対して、Data Controllerが個人データを消去する権限を与えます。

>[!NOTE]
>
>GDPR、CCPA、およびPDPAのプライバシーコンプライアンスに役立つツール群です。 これらの様々な規則について詳しくは、 [このページを参照してください](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr)。

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

**Access** 要求と **Delete要求は、** このページに表示されます [](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess)。 これらのリクエストを作成するための実装手順について詳し [くは、このページを参照してください](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)。 チュートリアルは [こちら](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html)。

## トラッキング機能 {#tracking-capabilities}

Adobe Campaignでは、その追跡機能のおかげで、セッションcookieと永続的なcookieを使用して、配信受信者の動作を追跡できます。 追跡について詳しくは、 [このページを参照してください](../../sending/using/tracking-messages.md)。

>[!NOTE]
>
>GDPR(General Data Protection Regulation)などの規制では、会社はCookieをインストールする前にWebサイト利用者の同意が必要であると規定されています。 認証リクエストを通じて、貴社のサイトにWebトラッキングツールが装備されていることをユーザに通知する必要があります。

また、メッセージに [追跡リンク](../../designing/using/links.md#about-tracked-urls) を追加して、組み込みのトラッキングインジケーター [(](../../reporting/using/tracking-indicators.md) 追跡インジケーター [)レポートでの配信と受信者の動作の影響を測定したり、独自の](../../reporting/using/about-dynamic-reports.md)専用レポートを作成したりすることもできます。
