---
title: 動的レポートについて
description: 動的レポートを使用して、変数やディメンションをフリーフォーム環境にドラッグ&ドロップし、キャンペーンの成功を分析します。
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6bf67d05ec8f5b4024df29c7ee7df7fc15e95e0a

---


# 動的レポートについて{#about-dynamic-reports}

動的レポートは、完全にカスタマイズ可能なリアルタイムレポートを提供します。 プロファイルデータへのアクセスを追加し、開封やクリックなどの機能的な電子メールキャンペーンデータに加え、性別、市区町村、年齢などのプロファイルディメンション別の人口統計分析を可能にします。 ドラッグ&amp;ドロップインターフェイスを使用すると、データを調べ、最も重要な顧客セグメントに対する電子メールキャンペーンのパフォーマンスを判断し、受信者への影響を測定できます。

>[!NOTE]
>
>管理権限を持つユーザ、または組織単位( **All** )に設定されたユーザのみが、新しいレポートを作成または保存できます。 詳しくは、[この節](../../administration/using/users-management.md)を参照してください。

![](assets/dynamic_report_intro.png)

ドラッグ&amp;ドロップメニューとカスタマイズ可能なビジュアライゼーションにより、動的レポート機能を使用すると、ディメンション、指標および時間範囲を任意の組み合わせで組み合わせ、無制限の分類と比較を行うことができます。


**関連トピック：**

* [レポートリスト](../../reporting/using/defining-the-report-period.md)
* [組織単位](../../administration/using/organizational-units.md)
* [動的レポート](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/creating-a-dynamic-report.html) （ビデオ）

## 動的レポートへのアクセス {#accessing-dynamic-reports}

レポートにアクセスできます。

* ホームページから、上部バ **[!UICONTROL Reports]** ーのタブまたはカードを選択して、す **[!UICONTROL Reports]** べてのオプションのレポートにアクセスします。

   ![](assets/campaign_reports_access.png)

* 各プログラム、キャンペーンおよびメッセージで、「 **Dynamic Reports** 」ボタンをクリックして、 **配信に固有のレポートのみを表示します** 。

   ![](assets/campaign_reports_description.png)

情報の収集と処理に要する時間によっては、配信の直後にレポートを使用できない場合があります。

動的レポートは、次の2つのカテゴリに分かれます。

* **テンプレート**。「名前を付けて保存」オプション(プロジェクト/名前を付けて保存 **)を使用してテンプレ****ートをコピーすると、変更できます。**)をテンプレート内に置き換えます。
* **カスタムレポート** （青色で識別）。レポート **ホームページの「新しいプロジェクトを作成」ボタ** ンをクリックして **、直接作成で** きます。

>[!NOTE]
>
>データは組織単位に応じてフィルタされます。

![](assets/dynamic_report_overview.png)

## 動的なレポート使用許諾契約 {#dynamic-reporting-usage-agreement}

動的レポートの使用許諾契約の目的は、データ処理のポップアップ同意として機能することです。 デフォルトでは、契約は表示されるのみで、管理権限を持つユーザーによってのみ承認または拒否できます。

次の 3 つのオプションを選択できます。

* **[!UICONTROL Ask me later]**:[後で確認 **する**]をクリックすると、ウィンドウの表示が24時間停止します。 契約に同意するか却下するまで、プロファイルディメンションはレポートに表示されず、顧客の個人ID情報は収集または送信されません。
* **[!UICONTROL Accept]**:本契約に同意することで、Adobe Campaignが顧客の個人ID情報を収集し、顧客をレポートまたはデータセンターに転送することを許可します。
* **[!UICONTROL Decline]**:契約を拒否すると、プロファイルディメンションはレポートに表示されず、顧客の個人ID情報は収集も送信もされません。 この場合、externalIDは引き続き収集され、エンドユーザーの識別に使用されます。

次の表に、お客様の地域に応じて、本契約に同意した後の動作を示します。

|  | 動的レポート | Microsoft Dynamics 365コネクタ |
|---|---|---|
| アメリカおよびAPAC（アジア太平洋） | **機能を使用できます**。 <br>すべての設定なし（市、国/地域、州、性別、セグメントを年齢ベースで設定）、および米国のレポートセンターに送り込まれるカスタムプロファイル情報。 For more information on profile dimensions, refer to this [page](../../reporting/using/list-of-components-.md) | **機能を使用できます**。 <br>すべての標準設定およびカスタムプロファイルフィールドとAdobe Campaign標準イベントフィールドは、米国のデータセンターで処理されます。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **機能を使用できます**。 <br>すべての設定なし（市、国/地域、州、性別、セグメントを年齢ベース）およびカスタムプロファイル情報が、EMEAレポートセンターに送り込まれます。 For more information on profile dimensions, refer to this [page](../../reporting/using/list-of-components-.md) | **機能を使用できます。** EMEAデー <br>タセンターで処理される、すべての標準搭載およびカスタムプロファイルフィールドとAdobe Campaign標準イベントフィールド。 <br>**[!UICONTROL Control data]** このIDには、米国のデータセンターで送信および保存される顧客エンドイベントのAdobe I/O登録データとIDが含まれます。 |

下の表に、お住まいの地域に応じてこの契約を拒否した後の状況を示します。 この契約に同意しない場合でも、配信とMicrosoft Dynamics 365統合のレポートは引き続き使用できます。

| 地域 | 動的レポート | Microsoft Dynamics 365コネクタ |
|---|---|---|
| アメリカおよびAPAC（アジア太平洋） | **機能を使用できます**。 <br> ExternalIDを除き、標準搭載されたプロファイルやカスタム情報が米国のレポートセンターにプッシュされることはありません。 | **機能を使用できます**。 <br>外部IDとプロファイルIDを除き、標準搭載のフィールドやカスタム受信者フィールドは米国のデータセンターに送信されません。 <br>Adobe CampaignIDを除き、米国のデータセンターで処理されるすべてのミラーページ標準イベントフィールド。 <br>Microsoft Dynamics 365の統合の詳細については、このページを参照してく [ださい](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **機能を使用できます**。 <br>ExternalIDを除き、EMEAレポートセンターにプロファイル情報を転送することなく、そのまま使用できます。 | **機能を使用できます。** 外部ID <br>と受信者IDを除き、EMEAデータセンターには、そのまま使用できるプロファイルフィールドやカスタム情報フィールドは送信されません。 <br>Adobe CampaignIDを除く、EMEAデータセンターで処理されるすべてのミラーページ標準イベントフィールド。  <br>**[!UICONTROL Control data]** このIDには、米国のデータセンターで送信および保存される顧客エンドイベントのAdobe I/O登録データとIDが含まれます。<br>Microsoft Dynamics 365の統合の詳細については、このページを参照してく [ださい](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)。 |

この選択は最終的なものではありません。//を選択して、い **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** つでも **[!UICONTROL Administration]** 変更で **[!UICONTROL Application Settings]** きます **[!UICONTROL Options]**。

値はいつでも変更できます。 値1は、、2および3 **[!UICONTROL Ask me later]**&#x200B;に対応 **[!UICONTROL Decline]** します **[!UICONTROL Accept]**。

![](assets/pii_window_2.png)
