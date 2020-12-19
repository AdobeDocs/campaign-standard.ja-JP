---
solution: Campaign Standard
product: campaign
title: Campaign Standard API を使用する理由?
description: Campaign StandardAPIとそれらを使用する理由について詳しく説明します。
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Campaign Standard API を使用する理由 {#why-using-campaign-standard-apis}

Adobe Campaign Standardは、既存のシステムをACSプラットフォームと統合し、現実の問題をリアルタイムで解決するAPIを提供しています。

サインアップページやオプトアウトページなどの公開Webサイトでは、プロファイル情報を保存するためにバックエンドシステムに接続する必要があります。 Adobe Campaignなどのバックエンドシステムには、プロファイルデータを取り込んだり、カスタム操作を実行したりする柔軟性と能力があります。

次に例を示します。

* 見込み客のオンライン登録。
* 既存の顧客プロファイルおよびマーケティングコミュニケーションプリファレンス管理。
* イベントベースのトランザクション通信のトリガ — 注文確認、旅行予約、パスワードのリセットなど。
* 買い物かご放棄の電子メール通信も含みます。

入会ランディングページを使用すると、顧客や見込み客が氏名や電子メールアドレスを登録できます。 Campaign Standardは、プロファイル情報と環境設定を取り込むと、個人の興味に基づいてパーソナライズされたメッセージを送信できます。

これらは、次の要素を使用して構築されます。

1. キャンペーンAPIリスナーを使用した登録フォーム。

   ![代替テキスト](assets/apis_uc1.png)

1. チェックボックスに基づいて実行されるカスタムアクション。 「特別なオファーを電子メールで送信」を選択した顧客には、通常の登録プロセスとは異なるギフト券が付いたカスタムメールが送信されます。

   ![代替テキスト](assets/apis_uc2.png)

1. プロファイルは、電子メール内の「詳細を更新」リンクをクリックすると、詳細を変更する場合があります。 これにより、プロファイルが「プロファイルと環境設定の詳細を更新」ページに移動します。 この操作を行うために、プロファイル詳細(Pkey)をキャンペーンサーバに渡し、プロファイルを検索して表現する。 プロファイルが「Update」ボタンをクリックすると、PATCHコマンドを使用して情報がシステムに更新されます。

   ![代替テキスト](assets/apis_uc3.png)

Campaign StandardAPIリクエストについて理解を深めるために、一連のリクエストを利用できます。 JSON形式のこのコレクションは、一般的な使用例を表す、事前に設計されたAPIリクエストを提供します。

次の手順では、コレクションを読み込んで使用し、Campaign Standardデータベース内にプロファイルを作成する際の使用例を説明します。

>[!NOTE]
>
>この例では郵便番号を使用します。 ただし、お気に入りのRESTクライアントを自由に使用できます。

1. [ここ](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip)をクリックして、JSONコレクションをダウンロードします。

1. Postmanを開き、**ファイル** / **読み込み**&#x200B;メニューを選択します。

1. ダウンロードしたファイルをウィンドウにドラッグ&amp;ドロップします。 事前に設計されたAPIリクエストが表示され、使用可能な状態です。

   ![代替テキスト](assets/postman_collection.png)

1. **プロファイル**&#x200B;リクエストの作成を選択し、POSTリクエストと「**ヘッダー**」タブを更新します(&lt;ORGANIZATION>、&lt;API_KEY>、&lt;ACCESS_TOKEN>)。 詳しくは、[こちらの節](../../api/using/setting-up-api-access.md)を参照してください。

   ![代替テキスト](assets/postman_uc1.png)

1. 「**ボディ**」タブに新しいプロファイルに追加する情報を入力し、「**送信**」ボタンをクリックしてリクエストを実行します。

   ![代替テキスト](assets/postman_uc2.png)

1. 作成されたオブジェクトには、主キー(PKey)が関連付けられます。 リクエストの応答に加え、他の属性にも表示されます。

   ![代替テキスト](assets/postman_uc3.png)

1. Campaign Standardインスタンスを開き、ペイロードのすべての情報と共にプロファイルが作成されたことを確認します。

   ![代替テキスト](assets/postman_uc4.png)
