---
title: Campaign Standard API を使用する理由?
description: Campaign StandardAPIと、それらを使用する理由について詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: ef045e5d-cd02-44a0-9a1e-d468483a38d9
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 3%

---

# Campaign Standard API を使用する理由 {#why-using-campaign-standard-apis}

Adobe Campaign Standardは、既存のシステムをCampaignプラットフォームと統合して、リアルタイムで実際の問題を解決するAPIを提供します。

サインアップやオプトアウトページなどの公開Webサイトは、バックエンドシステムに接続して、プロファイル情報を保存する必要があります。 Adobe Campaignなどのバックエンドシステムは、プロファイルデータをに取り込み、カスタム操作を実行する柔軟性と能力を備えています。

次に例を示します。

* 見込み客のオンライン登録。
* 既存の顧客プロファイルとマーケティングコミュニケーションの優先順位の管理。
* イベントベースのトランザクション通信トリガー（注文確認、予約の旅程、パスワードリセットなど）
* 買い物かごが放棄された場合でも、Eメールによる通信。

新規登録ランディングページを使用すると、顧客や見込み客が自分の名前と電子メールアドレスを登録できます。 Campaign Standardは、プロファイル情報と環境設定を取り込むと、個人の興味に基づいてパーソナライズされたメッセージを送信できます。

これらは以下の要素を使用して構築されます。

1. キャンペーンAPIリスナーを使用した登録フォーム。

   ![代替テキスト](assets/apis_uc1.png)

1. チェックボックスに基づいて実行するカスタムアクション。 「特別なメールを送信」を選択する顧客には、通常の登録プロセスとは異なり、ギフトクーポン付きのカスタムメールが送信されます。

   ![代替テキスト](assets/apis_uc2.png)

1. 電子メール内の「詳細を更新」リンクをクリックすると、プロファイルの詳細が変更される場合があります。 これにより、「プロファイルと環境設定の詳細の更新」ページが表示されます。 操作を実行するには、プロファイルの詳細(Pkey)がCampaignサーバーに渡され、プロファイルが取得されて表示されます。 プロファイルが「更新」ボタンをクリックすると、情報が(PATCHコマンドを使用して)システムに更新されます。

   ![代替テキスト](assets/apis_uc3.png)

Campaign StandardAPIリクエストの理解に役立つリクエストのコレクションを利用できます。 このJSON形式のコレクションは、一般的な使用例を表す事前設計済みのAPIリクエストを提供します。

以下の手順では、コレクションを読み込んで使用し、Campaign Standard・データベース内にプロファイルを作成する手順を順を追って説明します。

>[!NOTE]
>
>この例ではPostmanを使用します。 ただし、お気に入りのRESTクライアントを自由に使用できます。

1. [ここ](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip)をクリックして、JSONコレクションをダウンロードします。

1. Postmanを開き、**ファイル** / **インポート**&#x200B;メニューを選択します。

1. ダウンロードしたファイルをウィンドウにドラッグ&amp;ドロップします。 事前に設計されたAPIリクエストが表示され、使用できる状態になります。

   ![代替テキスト](assets/postman_collection.png)

1. **POST**&#x200B;リクエストを作成し、プロファイルリクエストと「**ヘッダー**」タブを更新して、独自の情報(&lt;ORGANIZATION>、&lt;API_KEY>、&lt;ACCESS_TOKEN>)を表示します。 詳しくは、[この節](../../api/using/setting-up-api-access.md)を参照してください。

   ![代替テキスト](assets/postman_uc1.png)

1. 新しいプロファイルに追加する情報を「**Body**」タブに入力し、「**送信**」ボタンをクリックしてリクエストを実行します。

   ![代替テキスト](assets/postman_uc2.png)

1. オブジェクトが作成されると、プライマリキー(PKey)が関連付けられます。 リクエストの応答やその他の属性に表示されます。

   ![代替テキスト](assets/postman_uc3.png)

1. Campaign Standardインスタンスを開き、ペイロードのすべての情報を使用して、プロファイルが作成されたことを確認します。

   ![代替テキスト](assets/postman_uc4.png)
