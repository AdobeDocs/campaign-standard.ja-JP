---
title: 動的レポートの基本を学ぶ
description: 動的レポートを使用して、変数とディメンションをフリーフォーム環境にドラッグ&ドロップし、キャンペーンの成功を分析します。
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 6%

---

# 動的レポートの基本を学ぶ {#about-dynamic-reports}

動的レポートは、完全にカスタマイズ可能なリアルタイムのレポートを提供します。 プロファイルデータへのアクセスが追加され、開封数やクリック数などの機能的なメールキャンペーンデータに加えて、性別、市区町村、年齢などのプロファイルディメンション別のデモグラフィック分析を可能にします。ドラッグ&amp;ドロップインターフェイスを使用すると、データを調査し、最も重要な顧客セグメントに対するメールキャンペーンのパフォーマンスを判断し、受信者に与える影響を測定できます。

>[!NOTE]
>
>新しいレポートを作成または保存できるのは、管理権限または組織単位が **すべて** に設定されているユーザーのみです。 詳しくは、[この節](../../administration/using/users-management.md)を参照してください。

## 動的レポートへのアクセス {#accessing-dynamic-reports}

レポートには、次の方法でアクセスできます。

* のホームページで、上部バーまたは **[!UICONTROL Reports]** ールカードの「」タブ **[!UICONTROL Reports]** 選択して、すべての配信のレポートにアクセスします。

  ![](assets/campaign_reports_access.png)

* 各プログラム、キャンペーン、メッセージでは、**動的レポート** をクリックして、**レポート** ボタンから配信に固有のレポートのみを表示します。

  ![](assets/campaign_reports_description.png)

情報の収集と処理にかかる時間によっては、配信直後に特定のレポートを使用できないことがあります。

動的レポートは次の 2 つのカテゴリに分かれています。

* **テンプレート** （**名前を付けて保存** オプション（**プロジェクト/名前を付けて保存…**）を選択します。
* **カスタムレポート** （青で識別）。（レポート **ホームページの「** 新規プロジェクトの作成 **」ボタンをクリックして直接作成でき** す。

>[!NOTE]
>
>データは、組織単位に応じてフィルタリングされます。

![](assets/dynamic_report_overview.png)

## 動的レポート使用契約 {#dynamic-reporting-usage-agreement}

動的レポート使用契約の目的は、データ処理のポップアップ同意として機能することです。 デフォルトでは、この契約書は表示のみ可能で、管理権限を割り当てられたユーザーのみが承諾または却下できます。

次の 3 つのオプションを選択できます。

* **[!UICONTROL Ask me later]**: **後で確認する** をクリックすると、ウィンドウは 24 時間表示されなくなります。 契約を承諾または拒否するまで、プロファイルの寸法はレポートに表示されず、顧客の個人情報は収集または送信されません。
* **[!UICONTROL Accept]**：お客様は、本契約に同意することにより、Adobe Campaignがお客様の個人 ID を収集し、それをレポートまたはデータセンターに転送することを承認するものとします。
* **[!UICONTROL Decline]**：契約を拒否すると、プロファイルのディメンションはレポートに表示されず、顧客の個人識別情報は収集または送信されません。 この場合でも、externalID は引き続き収集され、エンドユーザーの識別に使用されます。

次の表は、お客様の地域に応じて、この契約書に同意した後の動作を示しています。

|  | 動的レポート | Microsoft Dynamics 365 コネクタ |
|---|---|---|
| 南北アメリカおよび APAC （アジア太平洋） | **利用可能な機能**。 <br> すべての標準提供（市区町村、国/地域、州、性別、年齢ベースのセグメント）と、米国レポートセンターにプッシュされたカスタムプロファイル情報。 プロファイルディメンションについて詳しくは、この [&#x200B; ページ &#x200B;](../../reporting/using/list-of-components.md) を参照してください | **利用可能な機能**。 <br> すべての標準およびカスタムプロファイルフィールドとAdobe Campaign Standard イベントフィールドは、米国データセンターで処理されます。 |
| EMEA （ヨーロッパ、中東、アフリカ） | **利用可能な機能**。 <br> すべての標準提供（市区町村、国/地域、都道府県、性別、年齢ベースのセグメント）と、EMEA レポートセンターにプッシュされたカスタムプロファイル情報。 プロファイルディメンションについて詳しくは、この [&#x200B; ページ &#x200B;](../../reporting/using/list-of-components.md) を参照してください | **機能を使用できます。** <br>EMEA データセンターで処理されるすべての標準およびカスタムプロファイルフィールドとAdobe Campaign Standard イベントフィールド。 米国データセンターで送信および保存されるAdobe I/Oのエンドユーザーイベントの顧客登録データおよび ID を含む <br>**[!UICONTROL Control data]**。 |

次の表は、お客様の地域に応じて、この契約を拒否した後の動作を示しています。 この契約を拒否した場合でも、配信とMicrosoft Dynamics 365 の統合に関するレポートは引き続き使用できます。

| 地域 | 動的レポート | Microsoft Dynamics 365 コネクタ |
|---|---|---|
| 南北アメリカおよび APAC （アジア太平洋） | **利用可能な機能**。 <br>ExternalID を除き、米国のレポートセンターにプッシュされた標準およびカスタムプロファイル情報はありません。 | **利用可能な機能**。 <br> 外部 ID と受信者 ID を除き、米国データセンターに送信される標準またはカスタムプロファイルフィールドはありません。 <br> ミラーページ ID を除く、米国データセンターで処理されるすべてのAdobe Campaign Standard イベントフィールド。 <br>Microsoft Dynamics 365 の統合について詳しくは、この [&#x200B; ページ &#x200B;](../../integrating/using/d365-acs-get-started.md) を参照してください。 |
| EMEA （ヨーロッパ、中東、アフリカ） | **利用可能な機能**。 <br>ExternalID を除き、EMEA のレポートセンターにプッシュされた標準およびカスタムプロファイル情報はありません。 | **機能を使用できます。** <br> 外部 ID と受信者 ID を除き、EMEA データセンターに送信される、標準またはカスタムプロファイルフィールドはありません。 <br> ミラーページ ID を除く、EMEA データセンターで処理されるすべてのAdobe Campaign Standard イベントフィールド。  米国データセンターで送信および保存されるAdobe I/Oのエンドユーザーイベントの顧客登録データおよび ID を含む <br>**[!UICONTROL Control data]**。<br>Microsoft Dynamics 365 の統合について詳しくは、この [&#x200B; ページ &#x200B;](../../integrating/using/d365-acs-get-started.md) を参照してください。 |

この選択は最終的なものではなく、**[!UICONTROL Administration]**/**[!UICONTROL Application Settings]**/**[!UICONTROL Options]** で **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** を選択することでいつでも変更できます。

この値はいつでも変更できます。 値 1 は **[!UICONTROL Ask me later]**、2 **[!UICONTROL Decline]**、3 **[!UICONTROL Accept]** に対応します。

![](assets/pii_window_2.png)
