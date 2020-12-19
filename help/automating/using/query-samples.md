---
solution: Campaign Standard
product: campaign
title: クエリのサンプル
description: この節では、クエリアクティビティを使用する場合の使用例を示します。
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# クエリのサンプル {#query-samples}

この節では、**[!UICONTROL Query]**&#x200B;アクティビティを使用する場合の使用例を示します。 **[!UICONTROL Query]**&#x200B;アクティビティの使い方の詳細については、[この](../../automating/using/query.md)を参照してください。

## シンプルなプロファイルの属性のターゲティング {#targeting-on-simple-profile-attributes}

次の例は、ロンドンに居住している 18～30 歳の男性をターゲットするように設定されたクエリアクティビティを示しています。

![](assets/query_sample_1.png)

## E メールの属性のターゲティング {#targeting-on-email-attributes}

次の例は、E メールアドレスドメインが「orange.co.uk」のプロファイルをターゲットするように設定されたクエリアクティビティを示しています。

![](assets/query_sample_emaildomain.png)

次の例は、E メールアドレスを提供したプロファイルをターゲットするように設定されたクエリアクティビティを示しています。

![](assets/query_sample_emailnotempty.png)

## 今日が誕生日のプロファイルのターゲティング {#targeting-profiles-whose-birthday-is-today}

次の例は、今日が誕生日のプロファイルをターゲットするように設定されたクエリアクティビティを示しています。

1. クエリに **[!UICONTROL Birthday]** フィルターをドラッグします。

   ![](assets/query_sample_birthday.png)

1. **[!UICONTROL Filter type]** を **[!UICONTROL Relative]** に設定し、「**[!UICONTROL Today]**」を選択します。

   ![](assets/query_sample_birthday2.png)

## 特定の配信を開いたプロファイルのターゲティング {#targeting-profiles-who-opened-a-specific-delivery}

次の例は、「Summer Time」というラベルの配信を開いたプロファイルをフィルターするように設定されたクエリアクティビティを示しています。

1. クエリに **[!UICONTROL Opened]** フィルターをドラッグします。

   ![](assets/query_sample_opened.png)

1. 配信を選択して「**[!UICONTROL Confirm]**」をクリックします。

   ![](assets/query_sample_opened2.png)

## 特定の理由で配信が失敗したプロファイルのターゲティング {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

次の例は、メールボックスの容量が超過したために配信が失敗したプロファイルをフィルターするように設定されたクエリアクティビティを示しています。このクエリは、管理権限を持ち、**[!UICONTROL All (all)]** 組織単位に属するユーザーのみが使用できます（[この節](../../administration/using/organizational-units.md)を参照）。

1. 配信ログテーブルで直接フィルターするには、**[!UICONTROL Delivery logs]** リソースを選択します（[ターゲティングディメンションとは異なるリソースの使用](../../automating/using/using-resources-different-from-targeting-dimensions.md)を参照）。

   ![](assets/query_sample_failure1.png)

1. クエリに **[!UICONTROL Nature of failure]** フィルターをドラッグします。

   ![](assets/query_sample_failure2.png)

1. ターゲットする失敗のタイプを選択します。ここでは **[!UICONTROL Mailbox full]** です。

   ![](assets/query_sample_failure3.png)

## 過去 7 日間に連絡していないプロファイルのターゲティング {#targeting-profiles-not-contacted-during-the-last-7-days}

次の例は、過去 7 日間に連絡していないプロファイルをフィルターするように設定されたクエリアクティビティを示しています。

1. クエリに **[!UICONTROL Delivery logs (logs)]** フィルターをドラッグします。

   ![](assets/query_sample_7days.png)

   ドロップダウンリストで「**[!UICONTROL Does not exist]**」を選択し、**[!UICONTROL Delivery]** フィルターをドラッグします。

   ![](assets/query_sample_7days1.png)

1. 次のようにフィルターを設定します。

   ![](assets/query_sample_7days2.png)

## 特定のリンクをクリックしたプロファイルのターゲティング {#targeting-profiles-who-clicked-a-specific-link-}

1. クエリに **[!UICONTROL Tracking logs (tracking)]** フィルターをドラッグします。

   ![](assets/query_sample_trackinglogs.png)

1. **[!UICONTROL Label (urlLabel)]** フィルターをドラッグします。

   ![](assets/query_sample_trackinglogs2.png)

1. 配信にリンクを挿入する際に定義したラベルを「**[!UICONTROL Value]**」フィールドに入力し、確定します。

   ![](assets/query_sample_trackinglogs3.png)
