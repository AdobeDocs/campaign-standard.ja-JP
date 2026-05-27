---
title: クエリのサンプル
description: この節では、クエリアクティビティを使用する場合のユースケースを示します。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 0a71e3a7-60e6-49ec-af2e-099ad0d69a15
TQID: https://experienceleague.adobe.com/65HKTwwETEWkW1P6c1pfYBIJQDYwqC-DPmq7JQiye7s
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 339
ht-degree: 76%

---

# クエリのサンプル {#query-samples}

このセクションでは、**[!UICONTROL Query]** アクティビティを使用する場合の使用例を示します。 **[!UICONTROL Query]** アクティビティの使用方法について詳しくは、[この節](../../automating/using/query.md)を参照してください。

## シンプルなプロファイル属性をターゲットにする {#targeting-on-simple-profile-attributes}

次の例は、ロンドンに居住している 18～30 歳の男性をターゲットするように設定されたクエリアクティビティを示しています。

![](assets/query_sample_1.png)

## メール属性のターゲティング {#targeting-on-email-attributes}

次の例は、メールアドレスドメインが「orange.co.uk」のプロファイルをターゲットするように設定されたクエリアクティビティを示しています。

![](assets/query_sample_emaildomain.png)

次の例は、メールアドレスを提供したプロファイルをターゲットするように設定されたクエリアクティビティを示しています。

![](assets/query_sample_emailnotempty.png)

## 今日が誕生日のプロファイルをターゲットにする {#targeting-profiles-whose-birthday-is-today}

次の例は、今日が誕生日のプロファイルをターゲットするように設定されたクエリアクティビティを示しています。

1. クエリに **[!UICONTROL Birthday]** フィルターをドラッグします。

   ![](assets/query_sample_birthday.png)

1. **[!UICONTROL Filter type]** を **[!UICONTROL Relative]** に設定し、「**[!UICONTROL Today]**」を選択します。

   ![](assets/query_sample_birthday2.png)

## 特定の配信を開封したプロファイルをターゲットにする {#targeting-profiles-who-opened-a-specific-delivery}

次の例は、「Summer Time」というラベルの配信を開いたプロファイルをフィルターするように設定されたクエリアクティビティを示しています。

1. クエリに **[!UICONTROL Opened]** フィルターをドラッグします。

   ![](assets/query_sample_opened.png)

1. 配信を選択して「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/query_sample_opened2.png)

## 特定の理由で配信が失敗したプロファイルをターゲットにする {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

次の例は、メールボックスの容量が超過したために配信が失敗したプロファイルをフィルターするように設定されたクエリアクティビティを示しています。 このクエリは、管理権限を持ち、**[!UICONTROL All (all)]** 組織単位に属するユーザーのみが使用できます（[この節](../../administration/using/organizational-units.md)を参照）。

1. 配信ログテーブルで直接フィルターするには、**[!UICONTROL Delivery logs]** リソースを選択します（[ターゲティングディメンションとは異なるリソースの使用](../../automating/using/using-resources-different-from-targeting-dimensions.md)を参照）。

   ![](assets/query_sample_failure1.png)

1. クエリに **[!UICONTROL Nature of failure]** フィルターをドラッグします。

   ![](assets/query_sample_failure2.png)

1. ターゲットする失敗のタイプを選択します。 ここでは **[!UICONTROL Mailbox full]** です。

   ![](assets/query_sample_failure3.png)

## 過去7日間に連絡しなかったプロファイルをターゲットにする {#targeting-profiles-not-contacted-during-the-last-7-days}

次の例は、過去 7 日間に連絡していないプロファイルをフィルターするように設定されたクエリアクティビティを示しています。

1. クエリに **[!UICONTROL Delivery logs (logs)]** フィルターをドラッグします。

   ![](assets/query_sample_7days.png)

   ドロップダウンリストで「**[!UICONTROL Does not exist]**」を選択し、**[!UICONTROL Delivery]** フィルターをドラッグします。

   ![](assets/query_sample_7days1.png)

1. 次のようにフィルターを設定します。

   ![](assets/query_sample_7days2.png)

## 特定のリンクをクリックしたプロファイルをターゲットにする {#targeting-profiles-who-clicked-a-specific-link-}

1. クエリに **[!UICONTROL Tracking logs (tracking)]** フィルターをドラッグします。

   ![](assets/query_sample_trackinglogs.png)

1. **[!UICONTROL Label (urlLabel)]** フィルターをドラッグします。

   ![](assets/query_sample_trackinglogs2.png)

1. 配信にリンクを挿入する際に定義したラベルを「**[!UICONTROL Value]**」フィールドに入力し、確定します。

   ![](assets/query_sample_trackinglogs3.png)
