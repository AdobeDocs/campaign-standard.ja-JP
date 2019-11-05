---
title: フィルタールール
description: フィルタリングルールを使用して、メッセージのオーディエンスを絞り込みます。
page-status-flag: 非活性化の
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: ソビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: 活字体系ルール
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# フィルタールール{#filtering-rules}

フィルタリングルールを使用すると、隔離されたプロファイルや、特定の数の電子メールが既に送信されたプロファイルなど、クエリで定義された条件に従って、メッセージターゲットの一部を除外できます。

例えば、18歳未満の購読者が通信を受け取らないように、ニュースレターの購読者をフィルターできます。

## フィルタールールの作成 {#creating-a-filtering-rule}

1. すべての通 **信チャネルに適用できるフィルタリング** ・タイポロジ・ルールを作成します。

   ![](assets/typology_create-rule.png)

1. タブで、 **[!UICONTROL Filtering criteria]** カテゴリ内の購読を選択し **[!UICONTROL Subscription]** ます。

   ![](assets/typology_create-rule-subscription.png)

1. クエリー **[!UICONTROL Explorer]** エディターのタブで、画面のメインパー **[!UICONTROL Subscriber]** ツにノードをドラッグ&amp;ドロップします。

   ![](assets/typology_create-rule-subscriber.png)

1. フィールド **[!UICONTROL Age]** を選択し、購読者の年齢が18才以上になるようにフィルター条件を定義します。

   ![](assets/typology_create-rule-age.png)

1. タブで、こ **[!UICONTROL Typologies]** のルールをタイポロジにリンクします。

   ![](assets/typology_create-rule-typology.png)

1. 使用する配信テンプレートで、該当するタイポロジが選択されていることを確認します。

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >配信テンプレートにアクセスするには、ナビゲ **[!UICONTROL Resources]** ーションメ **[!UICONTROL Templates]** ニューで/を選択します。このメニューは、Adobe Campaignロゴを使用してアクセスできます。

このルールをメッセージで使用する場合は、未成年と見なされるサブスクライバーが自動的に除外されます。

## フィルタリングルールの適用の制限 {#restricting-the-applicability-of-a-filtering-rule}

送信するメッセージに従って、フィルタリングルールの適用を制限できます。

1. タイポロジルールのタブで、オ **[!UICONTROL Application criteria]** プションをオフにしま **[!UICONTROL Apply the rule on all deliveries]** す。このオプションはデフォルトで有効です。

   ![](assets/typology_limit.png)

1. クエリーエディターを使用して、フィルターを定義します。 例えば、特定の単語で始まるラベルや、特定の文字を含むIDを持つメッセージに対してのみ、ルールを適用できます。

   ![](assets/typology_limit-rule.png)

この場合、ルールは定義された条件に対応するメッセージにのみ適用されます。

## デフォルトの配信性能除外ルール {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). 電子メールの分析時には、配信性能インスタンスで管理された暗号化グローバル抑止リストに含まれている禁止アドレスや禁止ドメイン名がこれらのルールによって照合され、受信者の電子メールアドレスが該当していないかどうかの確認処理が実行されます。該当した場合、その受信者宛てにはメッセージが送信されません。

これは、Spamtrap などの悪意あるアクティビティによってブラックリストに登録されることを防ぐためです。例えば、会社の Web フォーム経由で Spamtrap を使用して購読処理が実行されると、Spamtrap 宛てに確認メールが自動送信され、お使いのアドレスが自動的にブラックリスト登録される結果になります。

>[!NOTE]
>
>グローバル抑止リストに含まれているアドレスやドメイン名は非公開です。除外された受信者の数に関する情報だけが配信分析ログに記録されます。

