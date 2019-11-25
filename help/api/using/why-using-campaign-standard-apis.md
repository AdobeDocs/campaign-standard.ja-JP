---
title: キャンペーン標準APIを使用する理由
description: キャンペーン標準APIとその使用理由について詳しく説明します。
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 47b5cf6aee969c7a199ec934b5be6bf80bee590e

---


# キャンペーン標準APIを使用する理由 {#why-using-campaign-standard-apis}

Adobe Campaign Standardは、既存のシステムをACSプラットフォームと統合し、リアルタイムで現実世界の問題を解決するAPIを提供します。

サインアップページやオプトアウトページなどの公開Webサイトは、プロファイル情報を保存するためにバックエンドシステムに接続する必要があります。 Adobe Campaignなどのバックエンドシステムには、プロファイルデータを取り込んでカスタム操作を実行する柔軟性と能力があります。

以下に例を示します。

* 見込み客のオンライン登録。
* 既存の顧客プロファイルおよびマーケティングコミュニケーションプリファレンス管理。
* イベントベースのトランザクション通信のトリガー — 注文確認、旅程の予約、パスワードのリセットなど。
* 買い物かご放棄の電子メール通信も可能。

入会ランディングページを使用すると、顧客や見込み客が名前と電子メールアドレスを登録できます。 キャンペーン標準は、プロファイル情報と環境設定を取り込むと、個人の興味に基づいてパーソナライズされたメッセージを送信できます。

以下の要素を使用して構築されます。

1. キャンペーンAPIリスナーを含む登録フォーム。

   ![代替テキスト](assets/apis_uc1.png)

1. チェックボックスに基づいて実行されるカスタムアクション。 「スペシャルオファーを電子メールで送信」を選択した顧客には、通常の登録プロセスとは異なるギフトクーポン付きのカスタムメールが送信されます。

   ![代替テキスト](assets/apis_uc2.png)

1. 電子メール内の「詳細を更新」リンクをクリックした後で、プロファイルの詳細が変更される場合があります。 これにより、プロファイルが「プロファイルとプリファレンスの詳細を更新」ページに表示されます。 この操作を実行するには、プロファイルの詳細(Pkey)がCampaignサーバーに渡され、プロファイルが取得され、表示されます。 プロファイルが「Update」ボタンをクリックすると、情報が（PATCHコマンドを使用して）システムに更新されます。

   ![代替テキスト](assets/apis_uc3.png)

キャンペーン標準APIリクエストについて理解するために、リクエストの集まりを利用できます。 このJSON形式のコレクションは、一般的な使用例を表す事前に設計されたAPIリクエストを提供します。

以下の手順では、コレクションをインポートして使用し、Campaign Standardデータベースでプロファイルを作成する際の使用例を順を追って説明します。

>[!NOTE]
>
>例では郵便配達人を使用します。 ただし、お気に入りのRESTクライアントを自由に使用できます。

1. JSONコレクションをダウンロードするには、ここをク [リックしま](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip)す。

1. Postmanを開き、「ファイル/インポ **ート** 」メニ **ューを選択します** 。

1. ダウンロードしたファイルをウィンドウにドラッグ&amp;ドロップします。 事前に設計されたAPIリクエストが表示され、すぐに使用できます。

   ![代替テキスト](assets/postman_collection.png)

1. 「プロフ **ァイル要求の作成****** 」を選択し、POST要求と「ヘッダー」タブを更新して、独自の情報(&lt;ORGANIZATION&gt;、&lt;API_KEY&gt;、&lt;ACCESS_TOKEN&gt;)を使用します。 詳しくは、[この節](../../api/using/setting-up-api-access.md)を参照してください。

   ![代替テキスト](assets/postman_uc1.png)

1. 新しいプロフ **ァイルに追加する情報を「Body** 」タブに入力し、「 **Send** 」ボタンをクリックしてリクエストを実行します。

   ![代替テキスト](assets/postman_uc2.png)

1. オブジェクトが作成されると、そのオブジェクトに主キー(PKey)が関連付けられます。 リクエストの応答に加え、他の属性にも表示されます。

   ![代替テキスト](assets/postman_uc3.png)

1. キャンペーン標準インスタンスを開き、ペイロードのすべての情報と共にプロファイルが作成されていることを確認します。

   ![代替テキスト](assets/postman_uc4.png)
