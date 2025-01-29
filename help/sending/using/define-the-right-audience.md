---
title: 適切なオーディエンスの定義
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: コンテンツの準備が整ったら、メッセージを受け取るユーザーを慎重に定義する方法を説明します。
feature: Deliverability
role: User
level: Intermediate
exl-id: 1e06fd9d-e850-4856-8f7b-b581dbe157df
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 72%

---

# 適切なオーディエンスの定義 {#define-the-right-audience}

ターゲット母集団が鍵です。リストを慎重に作成し、一般的なメールクライアントやモバイルデバイスでメールをテストし、メールリストが最新のものであるか（不明なアドレスや古いアドレスが含まれていないこと）を確認します。また、もれのない検証サイクルを確立するために、配達確認を送信することもできます。

ターゲット母集団について詳しくは、[この節](../../audiences/using/selecting-an-audience-in-a-message.md)を参照してください。

## 適切なオーディエンスのターゲティング {#target-the-right-audience}

コンテンツを用意できたら、メッセージの受信者を慎重に定義する必要があります。

配信を適切におこなうには、適切な受信者に最も関連性の高いパーソナライズされたコンテンツを送信する必要があります。Adobe Campaign では、精度の高いターゲットを作成できます。つまり、年齢、場所、購入履歴、以前の配信でリンクをクリックしたかどうかなどの条件に基づいて、受信者を選択できます。また、ターゲットの的確性を確認するために、テストプロファイル、コントロール母集団、シードアドレスを定義することもできます。

## ターゲットマッピング {#target-mappings}

配信テンプレートのデフォルトのターゲットは **プロファイル** です。 Adobe Campaign では、必要に応じて、これ以外のターゲットマッピングも配信に使用できます。

これらのマッピングについては、[この節](../../automating/using/query.md#targeting-dimensions-and-resources)を参照してください。

また、カスタマイズしたターゲットマッピングを作成して使用することもできます。詳しくは、[この節](../../administration/using/target-mappings-in-campaign.md)を参照してください。

## 外部データ {#external-data}

データベースに保存されている受信者ではなく、外部ファイルに保存されている受信者に配信できます。これを行うには、ワークフローを設計して、ファイルからデータベースにデータを読み込み、関連するオーディエンスを作成します。  詳しくは [ このユースケースでは ](../../automating/using/use-case-calling-workflow.md) を参照してください。 [ パラメーターを使用したワークフローの呼び出し ](../../automating/using/calling-a-workflow-with-external-parameters.md) も参照してください。

## 購読者への送信 {#send-to-subscribers}

ニュースレターの購読者にメッセージを送信するには、対応する情報サービスの購読者を直接ターゲットにできます。詳しくは、[この節](../../audiences/using/about-subscriptions.md)を参照してください。

**ヒント** - ワークフローを使用して、ニュースレターの購読者をターゲットにするリストオーディエンスを作成できます。 その後、配信でこのオーディエンスを選択できます。 詳しくは、[ リストオーディエンスの作成 ](../../audiences/using/creating-audiences.md#creating-list-audiences) を参照してください。

## 配達確認、テストプロファイル、コントロールグループ {#proofs-test-control-groups}

配信をテストするには、メインターゲットに送信する前に配達確認を使用します。
配達確認の受信者には適切な人を選択してください。配達確認の受信者は、メッセージのフォームとコンテンツを検証する必要があります。配達確認を送信する手順については、[ この節 ](../../sending/using/sending-proofs.md) を参照してください。

テストプロファイルの詳細については [ この節 ](../../audiences/using/managing-test-profiles.md) を参照してください。

[ コントロール母集団 ](../../sending/using/control-group.md) を使用すると、オーディエンスの一部を除外して、キャンペーンの影響を測定できます。 その後、メッセージを受け取ったターゲット母集団の行動と、ターゲット設定されていない連絡先の行動を比較できます。送信ログに基づいて、今後のキャンペーンでコントロール母集団をターゲットすることもできます。

## アドレスの重複排除 {#deduplicate-addresses}

重複したメールアドレスがあると、ターゲットに影響する可能性があるので、メールアドレスの重複を回避することが重要です。

* ターゲットが分割されている場合は、同じメッセージを複数回送信できます。

* 受信者がメッセージを受信後に購読解除しても、重複したプロファイルはその後もメッセージを受信します。

アドレスの重複は、送信レピュテーションを保護し、適切な強制隔離管理をおこなうためのものです。

詳しくは、[この使用例](../../automating/using/deduplicating-data-imported-file.md)を参照してください。
