---
title: クエリのサンプル
description: この節では、クエリアクティビティを使用する場合の使用例を示します。
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---


# クエリのサンプル {#query-samples}

この節では、 **[!UICONTROL Query]** アクティビティを使用する場合の使用例を示します。 For more on how to use a **[!UICONTROL Query]** activity, refer to [this section](../../automating/using/query.md).

## Targeting on simple profile attributes {#targeting-on-simple-profile-attributes}

次の例は、18歳から30歳の男性をターゲットするように設定され、ロンドンに住んでいるクエリアクティビティを示しています。

![](assets/query_sample_1.png)

## 電子メール属性のターゲット設定 {#targeting-on-email-attributes}

次の例は、電子メールアドレスドメインが「orange.co.uk」のターゲットプロファイルに対して設定されたクエリアクティビティを示しています。

![](assets/query_sample_emaildomain.png)

次の例は、電子メールアドレスが入力されたターゲットプロファイルに対して設定されたクエリアクティビティを示しています。

![](assets/query_sample_emailnotempty.png)

## 誕生日が今日のプロファイルをターゲットに設定 {#targeting-profiles-whose-birthday-is-today}

次の例は、今日の誕生日を持つターゲットプロファイルに設定されたクエリアクティビティを示しています。

1. クエリーに **[!UICONTROL Birthday]** フィルターをドラッグします。

   ![](assets/query_sample_birthday.png)

1. をに設定 **[!UICONTROL Filter type]** し、を **[!UICONTROL Relative]** 選択し **[!UICONTROL Today]**&#x200B;ます。

   ![](assets/query_sample_birthday2.png)

## 特定の配信を開いたプロファイルをターゲットに設定する {#targeting-profiles-who-opened-a-specific-delivery}

次の例は、「Summer Time」というラベルを付けて配信を開いたプロファイルをフィルターするように設定されたクエリアクティビティを示しています。

1. クエリーに **[!UICONTROL Opened]** フィルターをドラッグします。

   ![](assets/query_sample_opened.png)

1. 配信を選択し、をクリックし **[!UICONTROL Confirm]**&#x200B;ます。

   ![](assets/query_sample_opened2.png)

## 特定の理由で配信が失敗したプロファイルをターゲットに設定する {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

次の例は、メールボックスがいっぱいになったために配信が失敗したプロファイルをフィルタするように構成されたクエリアクティビティを示しています。 このクエリは、管理権限を持ち、 **[!UICONTROL All (all)]** 組織単位に属するユーザーのみが使用できます( [この節を参照](../../administration/using/organizational-units.md))。

1. 配信ログテーブルで直接フィルタリングするには、リ **[!UICONTROL Delivery logs]** ソースを選択します(ターゲティングディメンションとは異なるリソースの [使用を参照](../../automating/using/using-resources-different-from-targeting-dimensions.md))。

   ![](assets/query_sample_failure1.png)

1. クエリーに **[!UICONTROL Nature of failure]** フィルターをドラッグします。

   ![](assets/query_sample_failure2.png)

1. ターゲットする失敗の種類を選択します。 我々の場合は **[!UICONTROL Mailbox full]**。

   ![](assets/query_sample_failure3.png)

## 過去7日間に連絡がなかったプロファイルをターゲットにする {#targeting-profiles-not-contacted-during-the-last-7-days}

次の例は、過去7日間に連絡がなかったプロファイルをフィルターするように設定されたクエリアクティビティを示しています。

1. クエリーに **[!UICONTROL Delivery logs (logs)]** フィルターをドラッグします。

   ![](assets/query_sample_7days.png)

   ドロップダウンリスト **[!UICONTROL Does not exist]** でを選択し、 **[!UICONTROL Delivery]** フィルターをドラッグします。

   ![](assets/query_sample_7days1.png)

1. 次のようにフィルターを設定します。

   ![](assets/query_sample_7days2.png)

## 特定のリンクをクリックしたプロファイルをターゲットにする {#targeting-profiles-who-clicked-a-specific-link-}

1. クエリーに **[!UICONTROL Tracking logs (tracking)]** フィルターをドラッグします。

   ![](assets/query_sample_trackinglogs.png)

1. フィルターをドラッグし **[!UICONTROL Label (urlLabel)]** ます。

   ![](assets/query_sample_trackinglogs2.png)

1. 配信にリンクを挿入する際に定義したラベルを **[!UICONTROL Value]** フィールドに入力し、確認します。

   ![](assets/query_sample_trackinglogs3.png)
