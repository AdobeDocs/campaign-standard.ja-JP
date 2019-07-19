---
title: ランディングページの共有
seo-title: ランディングページの共有
description: ランディングページの共有
seo-description: Adobe Campaignでランディングページをテストして公開する方法について説明します。
page-status-flag: 常にアクティブ化されていない
uuid: fb7b087a-3292-496c- bc41-2e3012batchf59
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: チャネル
content-type: 参照
topic-tags: ランディングページ
discoiquuid: f7d4bb71- f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Sharing a landing page{#sharing-a-landing-page}

## About landing page publication {#about-landing-page-publication}

ランディングページを公開する前に、テストを実行する必要があります。実行を検証し、アクセスを設定して、ランディングページの提供終了を設定します。これらの手順は前提条件となり、慎重に実行する必要があります。

## Testing the landing page {#testing-the-landing-page-}

ランディングページがプラットフォームとデータに影響するので、実行を慎重にテストする必要があります。これを行うには、次の手順に従います。

1. Click the **[!UICONTROL Test]** button in the action bar of the landing page.
1. テスト画面で、テストプロファイルを選択し、ランディングページが購読を管理する場合はテストサービスを選択します。

   ![](assets/lp_test_2.png)

1. フィールドにデータを入力し、オプションを選択します。
1. ランディングページを送信し、データベースの更新をチェックします。

   >[!CAUTION]
   >
   >フォームが送信されると、使用されるサービスとプロファイルが更新されます。

1. これを様々なプロファイルやデータで繰り返します。

   この画面からランディングページのサムネールを生成することもできます。

## Setting up validity parameters {#setting-up-validity-parameters}

セキュリティ上の理由から公開する前に、セキュリティ上の理由から、ランディングページのプロパティに有効期限を設定することを強くお勧めします。選択した日付で、ランディングページが自動的に非公開になります。これを行うには、次の手順に従います。

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) button in the landing page dashboard.

   ![](assets/lp_edit_properties_button.png)

1. **[!UICONTROL Publication]** セクションで有効期限の日時を設定します。ランディングページは指定した日付で自動的に非公開になり、使用できなくなります。

   この日時に考慮するタイムゾーンを選択できます。

1. アクティブでないランディングページにアクセスしようとしたときに訪問者をリダイレクトするリダイレクトURLを定義します。

   ![](assets/lp_settings_general.png)

>[!CAUTION]
>
>展開日時を定義することもできます。ランディングページは、指定した日付に自動的に投稿されます。

## Publishing a landing page {#publishing-a-landing-page}

ランディングページを公開すると、そのランディングページはライブになり、訪問者がアクセスできます。

**[!UICONTROL Publish]** ボタンを使用して、いつでもランディングページの公開を取り消したり、更新したり、再公開したりできます。ただし、再公開が失敗してランディングページの公開がまだ完了していない場合、最初のバージョンはオンラインままになります。
