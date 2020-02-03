---
title: ランディングページの共有
description: Adobe Campaignのランディングページをテストして公開する方法を説明します。
page-status-flag: never-activated
uuid: fb7b087a-3292-496c-bc41-2e3012bacf59
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: f7d4bb71-f957-4f86-97c7-8ac0a0030026
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa92475c1f8b37f995ebdc74c4a1f43692a53c21

---


# ランディングページのテストと公開{#testing-publishing--landing-page}

## ランディングページのパブリケーションについて {#about-landing-page-publication}

ランディングページを公開する前に、次のテストを実行する必要があります。実行を検証し、アクセスを設定し、ランディングページの提供終了を設定します。 これらの手順は前提条件であり、慎重に実行する必要があります。

## ランディングページのテスト {#testing-the-landing-page-}

ランディングページがプラットフォームとデータに影響を与えるので、実行を慎重にテストする必要があります。 手順は次のとおりです。

1. ランディング **[!UICONTROL Test]**ページのアクションバーのボタンをクリックします。
1. テスト画面で、テストプロファイルを選択し、ランディングページで購読を管理する場合はテストサービスを選択します。

   ![](assets/lp_test_2.png)

1. フィールドにデータを入力し、オプションを選択します。
1. ランディングページを送信し、データベースの更新を確認します。

   >[!IMPORTANT]
   >
   >フォームが送信されると、使用されるサービスとプロファイルが更新されます。

1. 様々なプロファイルとデータを使用して、この手順を繰り返します。

   この画面からランディングページのサムネールを生成することもできます。

>[!NOTE]
>
>アプリケーションサーバーのURLがセキュリティで保護されていない場合(https://で始まらない場合)は、Campaignユーザーインターフェイスからランディングページのプレビューを表示できません。 このサーバは、ブランドの設定時 [に定義されます](../../administration/using/branding.md#configuring-and-using-brands)。

## 有効性パラメーターの設定 {#setting-up-validity-parameters}

公開前に、セキュリティ上の理由とプラットフォームのパフォーマンスから、ランディングページのプロパティに有効期限を設定することを強くお勧めします。 選択した日付にランディングページが自動的に非公開になります。 手順は次のとおりです。

1. ランディングページのダッシュボードのボタンを使用してアク ![](assets/edit_darkgrey-24px.png) セスしたランディングページのプロパティを編集します。

   ![](assets/lp_edit_properties_button.png)

1. セクションで有効期限の日時を設定し **[!UICONTROL Publication]**ます。ランディングページは指定した日付に自動的に非公開になるので、使用できなくなります。

   この日時を考慮するタイムゾーンを選択できます。

1. 非アクティブなランディングページにアクセスしようとするときに訪問者をリダイレクトするためのリダイレクトURLを定義します。

   ![](assets/lp_settings_general.png)

>[!IMPORTANT]
>
>また、次の配置日時を定義することもできます。ランディングページは指定した日に自動的に公開されます。

## ランディングページの公開 {#publishing-a-landing-page}

ランディングページを公開すると、ライブになり、訪問者がアクセスできます。

ランディングページは、ボタンを使用して、いつでも非公開または更新および再公開で **[!UICONTROL Publish]**きます。 ただし、再公開に失敗し、ランディングページを未公開にした場合、最初のバージョンはオンラインのままになります。
