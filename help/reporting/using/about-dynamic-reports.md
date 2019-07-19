---
title: 動的レポートについて
seo-title: 動的レポートについて
description: 動的レポートについて
seo-description: 動的レポートを使用して、変数とディメンションをフリーフォーム環境にドラッグ&ドロップし、キャンペーンの成功を分析します。
page-status-flag: 常にアクティブ化されていない
uuid: a84a18bd-4e33-466e- a6ce- d7008fe12746
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: レポート
content-type: 参照
topic-tags: about- reporting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 08b2363076adcc101b741ab66b85285e7a510baa

---


# About dynamic reports{#about-dynamic-reports}

>[!NOTE]
>
>Only users with administration rights or with organizational units set to **All** can create or save a new report. For more on this, refer to this [section](../../administration/using/types-of-users.md).

![](assets/dynamic_report_intro.png)

動的レポートは、完全にカスタマイズ可能なリアルタイムレポートを提供します。プロファイルデータへのアクセスを追加し、開封やクリックなどの機能的な電子メールキャンペーンデータに加えて、性別、市、年齢などのプロファイルディメンションによる人口統計分析を可能にします。ドラッグアンドドロップインターフェースにより、データを調査し、最も重要な顧客セグメントに対して電子メールキャンペーンがどのように実行されたかを判断し、受信者への影響を測定することができます。

ドラッグ&amp;ドロップメニューおよびカスタマイズ可能なビジュアライゼーションにより、動的レポート機能を使用すると、ディメンション、指標、時間範囲を組み合わせて組み合わせ、無制限に分類および比較できます。


**関連トピック:**

* [レポートリスト](../../reporting/using/defining-the-report-period.md)
* [組織単位](../../administration/using/organizational-units.md)
* [動的レポート](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-dynamic-report-feature-video-use.html) のビデオ

## Accessing dynamic reports {#accessing-dynamic-reports}

レポートにアクセスするには:

* From the home page by selecting **[!UICONTROL Reports]** tab in the top bar or the **[!UICONTROL Reports]** card to access reports for all deliveries.

   ![](assets/campaign_reports_access.png)

* In each program, campaign, and message, from the **Reports** button by clicking **Dynamic Reports** to only view the reports specific to the delivery.

   ![](assets/campaign_reports_description.png)

特定のレポートは、情報の収集および処理に要する時間に応じて、配信の直後に使用できません。

動的レポートは、次の2つのカテゴリに分類されます。

* **テンプレート**&#x200B;は、 **「保存」** オプション（**プロジェクト/名前を付けて保存）を使用してコピーして変更できます。**) を使用します。
* **カスタムレポート** （青色で識別）。レポートホームページの「新規プロジェクト **を作成** 」ボタンをクリックして直接 **作成** できます。

>[!NOTE]
>
>組織単位によってデータがフィルタされます。

![](assets/dynamic_report_overview.png)


## Dynamic reporting usage agreement {#dynamic-reporting-usage-agreement}

動的レポートを使用すると、プロファイルディメンションを使用してプロファイルデータに基づいてレポートをフィルターできます。

プロファイルディメンションは、動的レポート使用規約を受け入れた後、レポートでのみ表示および使用できます。デフォルトでは、契約は表示され、管理者権限に割り当てられているユーザーによってのみ受け入れられるか拒否されます。

この契約により、次のプロファイルデータの米国における転送とストレージが可能になります。都市、国、地域、性別、性別、セグメント。

本契約を承認すると、欧州および欧州以外のすべてのデータが米国に転送されます。

![](assets/pii_window.png)

3つのオプションを使用できます。

* **[!UICONTROL Ask me later]**:「後で確認」をクリックすると、ウィンドウの表示が24時間停止します。
* **[!UICONTROL Accept]**:この契約を承認することで、Adobe Campaignは顧客の個人識別情報を収集し、それらを米国に転送することを承認します。
* **[!UICONTROL Decline]**:契約を却下すると、プロファイルディメンションはレポートに表示されず、顧客の個人識別情報は収集または送信されません。

This choice is not final, you can always change it by selecting **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Options]**.

値はいつでも変更できます。The value -1 corresponds to **[!UICONTROL Ask me later]**, 1 **[!UICONTROL Accept]** and 0 **[!UICONTROL Decline]**.

![](assets/pii_window_2.png)

