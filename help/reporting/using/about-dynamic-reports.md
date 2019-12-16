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
source-git-commit: f78e101b8abea3640ad93db6ff53243a42e07086

---


# 動的レポートについて{#about-dynamic-reports}

>[!NOTE]
>
>管理権限を持つユーザー、または組織単位( **All** )に設定されているユーザーのみが、新しいレポートを作成または保存できます。 詳しくは、[この節](../../administration/using/users-management.md)を参照してください。

![](assets/dynamic_report_intro.png)

Dynamic Reportingは、完全にカスタマイズ可能なリアルタイムレポートを提供します。 プロファイルデータへのアクセスを追加し、オープン数やクリック数などの機能的な電子メールキャンペーンデータに加え、性別、市区町村、年齢などのプロファイルディメンション別の人口統計分析を可能にします。 ドラッグ&amp;ドロップインターフェイスを使用すると、データを調査し、最も重要な顧客セグメントに対する電子メールキャンペーンの効果を判断し、受信者への影響を測定できます。

ドラッグ&amp;ドロップメニューとカスタマイズ可能なビジュアライゼーションにより、動的レポート機能を使用すると、ディメンション、指標および時間範囲を任意の組み合わせで組み合わせ、無制限の分類と比較を行うことができます。


**関連トピック：**

* [レポートリスト](../../reporting/using/defining-the-report-period.md)
* [組織単位](../../administration/using/organizational-units.md)
* [動的レポート](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-dynamic-report-feature-video-use.html) （ビデオ）

## 動的レポートへのアクセス {#accessing-dynamic-reports}

レポートには次の情報がアクセスできます。

* ホームページから、トップバーのタ **[!UICONTROL Reports]** ブまたはカードを選択して、すべての配 **[!UICONTROL Reports]** 信のレポートにアクセスします。

   ![](assets/campaign_reports_access.png)

* 各プログラム、キャンペーンおよびメッセージで、「 **Reports** 」ボタンから「 **Dynamic Reports** 」をクリックして、配信に固有のレポートのみを表示します。

   ![](assets/campaign_reports_description.png)

情報の収集と処理に要する時間によっては、配信後すぐにレポートを使用できない場合があります。

動的レポートは、次の2つのカテゴリに分かれています。

* **テンプレート**。「名前を付けて保存」オプション(プロジェクト/名前を付けて保存 **)を使用してテンプレ****ートをコピーすると、変更できます。**)をテンプレートに追加します。
* **カスタムレポート** （青色で識別）。レポートのホームページの「新しいプロジェク **トを作成** 」ボタンをクリックして直 **接作成できます** 。

>[!NOTE]
>
>データは、組織単位に応じてフィルタされます。

![](assets/dynamic_report_overview.png)

## 動的レポートの使用許諾契約 {#dynamic-reporting-usage-agreement}

動的レポートの使用許諾契約の目的は、データ処理のポップアップ同意として機能することです。 デフォルトでは、契約は表示されるだけで、管理権限を持つユーザーのみが承諾または拒否できます。

次の3つのオプションを使用できます。

* **[!UICONTROL Ask me later]**:[後で確認 **する**]をクリックすると、ウィンドウの表示が24時間停止します。 契約に同意するか却下するまで、プロファイルディメンションはレポートに表示されず、顧客の個人ID情報は収集も送信もされません。
* **[!UICONTROL Accept]**:本契約に同意することにより、お客様の個人ID情報を収集し、レポートやデータセンターに転送することをAdobe Campaignに許可します。
* **[!UICONTROL Decline]**:契約を拒否すると、プロファイルディメンションはレポートに表示されず、顧客の個人ID情報は収集も送信もされません。 この場合も、externalIDは収集され、エンドユーザーの識別に使用されます。

以下の表に、お客様の地域に応じて、本契約に同意した後の動作を示します。

|  | 動的レポート | Microsoft Dynamics 365コネクタ |
|---|---|---|
| アメリカおよびAPAC（アジア太平洋） | **機能を利用できます**。 <br>すべての標準（市、国/地域、州、性別、セグメントを年齢ベース）と、米国のレポートセンターに送り込まれるカスタムプロファイル情報。 For more information on profile dimensions, refer to this [page](../../reporting/using/list-of-components-.md) | **機能を利用できます**。 <br>すべての標準プロファイルおよびカスタムプロファイルフィールドとAdobe Campaign Standardイベントフィールドは、米国のデータセンターで処理されます。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **機能を利用できます**。 <br>すべての標準（市、国/地域、州、性別、セグメントを年齢ベース）と、EMEAレポートセンターに送り込まれたカスタムプロファイル情報。 For more information on profile dimensions, refer to this [page](../../reporting/using/list-of-components-.md) | **機能を利用できます。** EMEAデ <br>ータセンターで処理される、すべてのデフォルトのプロファイルおよびカスタムプロファイルフィールドとAdobe Campaign Standardイベントフィールド。 <br>**[!UICONTROL Control data]** このIDには、米国のデータセンターで送信および保存される顧客エンドユーザーイベントのAdobe I/O登録データとIDが含まれます。 |

下の表に、お住まいの地域に応じて、この契約を却下した後の状況を示します。 この契約に同意しない場合でも、配信とMicrosoft Dynamics 365統合に関するレポートは引き続き使用できます。

| 地域 | 動的レポート | Microsoft Dynamics 365コネクタ |
|---|---|---|
| アメリカおよびAPAC（アジア太平洋） | **機能を利用できます**。 <br> ExternalIDを除き、標準搭載されたカスタムプロファイルおよびカスタムプロファイル情報は、米国のレポートセンターにプッシュされません。 | **機能を利用できます**。 <br>外部IDと受信者IDを除き、標準搭載のカスタムプロファイルフィールドまたはカスタムプロファイルフィールドはUSデータセンターに送信されません。 <br>ミラーページIDを除く、米国のデータセンターで処理されるすべてのAdobe Campaign Standardイベントフィールド。 <br>Microsoft Dynamics 365の統合の詳細については、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)。 |
| EMEA（ヨーロッパ中東およびアフリカ） | **機能を利用できます**。 <br>ExternalIDを除き、EMEAレポートセンターに追加設定不要のプロファイルおよびカスタムプロファイル情報は送信されません。 | **機能を利用できます。** 外部ID <br>と受信者IDを除き、EMEAデータセンターには標準搭載されたカスタムプロファイルフィールドやカスタムプロファイルフィールドは送信されません。 <br>ミラーページIDを除き、EMEAデータセンターで処理されるすべてのAdobe Campaign Standardイベントフィールド。  <br>**[!UICONTROL Control data]** このIDには、米国のデータセンターで送信および保存される顧客エンドユーザーイベントのAdobe I/O登録データとIDが含まれます。<br>Microsoft Dynamics 365の統合の詳細については、このページを参照してく [ださい](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)。 |

この選択は最終的なものではありません。//を選択して、い **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** つでも **[!UICONTROL Administration]** 変更で **[!UICONTROL Application Settings]** きま **[!UICONTROL Options]**&#x200B;す。

この値は、いつでも変更できます。 値1は、、2および3 **[!UICONTROL Ask me later]**&#x200B;に対応 **[!UICONTROL Decline]** します **[!UICONTROL Accept]**。

![](assets/pii_window_2.png)
