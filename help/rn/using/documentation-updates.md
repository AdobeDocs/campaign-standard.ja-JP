---
title: ドキュメントの更新
description: Adobe Campaign Standard ドキュメントのすべての最新アップデートについて説明します。
feature: Overview
role: User
level: Beginner
exl-id: 3f77825e-cb98-4cb1-9775-a8b6995e9da1
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '7221'
ht-degree: 99%

---

# ドキュメントの更新{#documentation-updates}

このページでは、Adobe Campaign の[リリースノート](../../rn/using/release-notes.md)に加えて、Adobe Campaign Standard のドキュメントの新規更新をすべて紹介します。

## リリース 22.2 - 2022年6月 {#release-22-2}

**リリースに含まれる改善点**

* **アドビ通知サービス** - Experience Cloud ソリューションは、Campaign に搭載されているアドビ通知サービスを使用して、ユーザーが把握しておくべき重要なアクティビティに関して Experience Cloud のどこからでもユーザーにアラートを表示できます。[詳細情報](../../administration/using/sending-internal-notifications.md)。

**その他の変更**

Adobe Experience Platform Data Connector および Audience Destinations サービスとの統合は、非推奨（廃止予定）となりました。 [詳細情報](deprecated-features.md)

SMTP テストモードの使用方法が詳しく説明されました。 [詳細情報](../../administration/using/configuring-email-channel.md#smtp-test-mode)

## 2022年3月 {#doc-updates-march-2022}

プロファイルの置き換えを使用して配達確認を送信すると、選択したプロファイルのログにレコードが追加されることを明記したメモを追加しました。[詳細情報](../../sending/using/testing-messages-using-target.md)

## リリース 22.1 - 2022年2月 {#release-22-1}

**リリースに含まれる機能強化**

URL から読み込まれたコンテンツを含め、配信の再試行メカニズムが改善されました。 [詳細情報](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

「監査」を制御するオプションのアクセスレベルを更新しました。[機能管理者](../../administration/using/users-management.md#functional-administrators)は有効／無効にする以前のオプション[監査記録](../../administration/using/audit.md)にアクセスできませんでした。この変更により監査のアクセスレベルが変更され、機能管理者が制御できるようになります。 [詳細情報](../../administration/using/audit.md#enable-disable-audit)

新しい&#x200B;**ジョブ履歴**&#x200B;ドロップダウンがメッセージダッシュボードに追加されました。 [詳細を表示](../../sending/using/monitoring-a-delivery.md)

**その他の変更**

自動 SMS 返信をトリガーするキーワードに関する警告メモを追加しました。英数字のみを含める必要があります。 [詳細情報](../../channels/using/managing-incoming-sms.md)

A/B テスト用電子メールの節に次の注意事項を追加しました：母集団の合計が 50,000 未満の場合、各バリアントは合計母集団の少なくとも 10％を表す必要があります。 そうしなかった場合、ログに警告が表示されます。[詳細情報](../../channels/using/designing-an-a-b-test-email.md)

**ファイル転送**&#x200B;アクティビティの **[!UICONTROL Delete the source files after transfer]** オプションの説明を更新しました。このオプションが選択されていない場合、SFTP ディレクトリにアーカイブされたコンテンツのサイズを手動で監視するリマインダーを含みます。[詳細情報](../../automating/using/transfer-file.md)

**プライバシー**&#x200B;セクションの古いリンクをすべて更新しました。[詳細情報](../../start/using/privacy.md)

Campaign Standard ドキュメントのコンテンツ表内にある、Campaign コントロールパネルドキュメントへ直接リンクを追加しました。

## リリース 21.3 - 2021 年 9 月 {#release-21-3---september-2021}

**本リリースに含まれる新機能**

統合 Experience Cloud インターフェイスの改善 - [詳細情報](../../start/using/interface-description.md#top-bar)

新しい監査記録機能 - [詳細情報](../../administration/using/audit.md)

ワークフロー診断モード - [詳細情報](../../automating/using/managing-execution-options.md)

**本リリースに伴うその他のドキュメントの更新**

強制隔離リストからアドレスを削除する方法に関する新しい節が追加されました。[詳細情報](../../sending/using/understanding-quarantine-management.md#removing-a-quarantined-address)

**強制隔離とブロックリスト**&#x200B;の節の内容が明快になりました。[詳細情報](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

## 2021 年 7 月 {#doc-updates-july-2021}

ユーザーが単一のランディングページから複数のサービスを購読または購読解除できるようにする方法について説明する新しい節が追加されました。[詳細情報](../../channels/using/managing-landing-page-form-data.md#multiple-subscriptions)

**ランディングページフォームデータの管理**&#x200B;の節が更新され、明確になりました。 [詳細情報](../../channels/using/managing-landing-page-form-data.md)

## リリース 21.2 - 2021 年 6 月 {#release-21-2---june-2021}

**リリースに含まれる新機能**

ランディングページの検証 - ランディングページに必須の契約オプションを追加できるようになりました。[詳細情報](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)

**E メールのサイズ**&#x200B;の節で、E メールの最大サイズに関する情報が更新されました。最大サイズは、デフォルトで 100 MB に設定されるようになりました。[詳細を表示](../../sending/using/design-and-personalize.md#email-size)

**リリースに伴うその他のドキュメントのアップデート**

トランザクションプッシュ通知でターゲットマッピングを変更する方法に関する情報が追加されました。 [詳細情報](../../channels/using/transactional-push-notifications.md#change-target-mapping)

## 2021 年 5 月 {#doc-updates-may-2021}

**アクティブプロファイル**&#x200B;レポートセクションが更新されました。 [詳細情報](../../audiences/using/active-profiles.md)

**リリース計画**&#x200B;ページが新しい日付に更新されました。 [詳細情報](../../rn/using/release-planning.md)


## 2021 年 4 月 {#doc-updates-april-2021}

Adobe Experience Platform のソースと宛先を使用して Campaign Standard と Adobe Real-time Customer Data Platform（RTCDP）の間でデータを共有する方法に関する新しい節が追加されました。[詳細情報](../../integrating/using/get-started-sources-destinations.md)

## 2021 年 3 月 {#doc-updates-march-2021}

新しい&#x200B;**ヘルプとサポートのオプション**&#x200B;ページです。 [詳細情報](../../support.md)

メッセージを送信するための主要な手順をリストするセクションは、追加情報と参照で強化されました。[詳細情報](../../channels/using/key-steps-to-send-a-message.md)

クエリで au オーディエンスを選択するとき、その定義が参照されるのではなくコピーされるように指定するための情報が追加されました。[詳細情報](../../audiences/using/selecting-an-audience-in-a-message.md)

オーディエンス宛先サービスおよび Adobe Experience Platform データコネクタに関する情報が、新しい節に再編成されました。 [詳細情報](../../integrating/using/aep-about-audience-destinations-service.md)

**宣言済み ID** データソースを People コアサービス統合でも使用できるようになりました。 Campaign-Audience Manager または People コアサービス統合ドキュメントに情報が追加されました。 [詳細情報](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

モバイルアプリケーション用にローカルトラッキングを実装する方法に関する情報が追加されました。 [詳細情報](../../administration/using/local-tracking.md)

[配信品質](../../sending/using/about-deliverability.md)の節が更新され、新しい[アドビ配信品質のベストプラクティスガイド](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=ja)へのリンクが追加されました。 様々なアドビソリューションに適用できる配信品質に関する一般的な情報はすべて、[ベストプラクティスガイド付録](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=ja#additional-resources)に移動しました。

## リリース 21.1 - 2021 年 2 月 {#release-21-1---february-2021}

**リリースに含まれる新機能**

E メールフィードバックサービス - [詳細情報](../../sending/using/confirming-the-send.md#message-indicators)

Adobe Experience Manager 統合の強化 - [詳細情報](../../integrating/using/creating-multilingual-email-aem.md)

統合 Experience Cloud インターフェイス - [詳細情報](../../start/using/interface-description.md#top-bar)

**リリースに伴うその他のドキュメントのアップデート**

E メール、名前（姓）、名前（名）または任意のカスタムフィールドに基づいてプロファイルを検索する方法についての情報が追加されました。 [詳細を表示](../../audiences/using/integrated-customer-profile.md)

新しい GetOption 関数に関する情報が追加され、外部パラメーターを使用してワークフローを呼び出すときに、指定した関数の値を返せるようになりました。 [詳細を表示](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)

**[!UICONTROL Transfer file]** アクティビティを使用した後に利用できる新しい **[!UICONTROL filesCount]** 出力変数に情報が追加されました。 [詳細を表示](../../automating/using/transfer-file.md#output-variables)

**E メールチャネルの設定**&#x200B;の節が更新され、該当する最新の E メール設定が明確になりました。 一部の顧客で引き続き使用されている従来のパラメーターは、このページの下に表示されています。 [詳細情報](../../administration/using/configuring-email-channel.md)

以前実行された 1 つ以上のタスクがまだ保留中の場合、スケジュール済みのワークフローが再スケジュールされないようにする方法に関する情報が追加されました。 [詳細情報](../../automating/using/scheduled-workflows-execution.md)

## 2020 年 12 月 {#doc-updates-december-2020}

**予測件名行**&#x200B;機能は廃止されました。[詳細を表示](../../rn/using/deprecated-features.md)

**トランザクションメッセージングの概要**&#x200B;の節に[拡張スキーマ](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)を追加して、プロセスを理解しやすくしました。

トランザクションメッセージングの実装プロセスを示すエンドツーエンドのユースケースが利用できるようになりました。 [詳細を表示](../../channels/using/transactional-messaging-use-case.md)

**プライバシー**&#x200B;の節は[こちら](../../start/using/privacy.md)に移動しました。

新しい&#x200B;**アクセシビリティ**&#x200B;のページが利用できます。このページでは Adobe Campaign Standard ワークスペースでのアクセシビリティのサポートに関する詳細を説明しています。 [詳細を表示](../../start/using/accessibility.md)

最適なパフォーマンスを得るために、公開トランザクションメッセージ数は100未満に抑える必要があるという注意事項を追加しました。 [詳細を表示](../../channels/using/transactional-messaging-limitations.md#transactional-message-number)

SMS コネクタのプロトコルと設定についてのページが[こちら](../../administration/using/sms-protocol.md)に移動しました。

**トランザクションメッセージでの製品リストの使用**&#x200B;の節は[こちら](../../designing/using/using-product-listings.md)に移動しました。

## 2020 年 11 月 {#doc-updates-november-2020}

**個人データとペルソナ**&#x200B;の節には、プライバシーに関して様々なペルソナがどのように関わっているかを示す、ユースケースのシナリオが追加更新されました。[詳細を表示](../../start/using/privacy.md#use-case-scenario)

プライバシーに関してよくある質問の一覧を記載した新しい節を追加しました。[詳細を表示](../../start/using/privacy-faq.md)

**プライバシー**&#x200B;の節は移動し、[プライバシー管理](../../start/using/privacy-management.md)と[プライバシーリクエストの管理](../../start/using/privacy-requests.md)の 2 ページが新しく追加されました。

**トランザクションメッセージング**&#x200B;の節は、ナビゲーションを改善するために再編成され、1 か所にまとめられました。[詳細情報](../../channels/using/getting-started-with-transactional-msg.md)

プライバシー管理に関連するデータマッピング検証エラーおよびトラブルシューティング方法に関する情報が、Adobe Experience Platform Data Connector 節に追加されました。[詳細を表示](../../integrating/using/aep-mapping-activation.md)

## リリース 20.4 - 2020 年 10 月 {#release-20-4---october-2020}

**リリースに含まれる新機能**

コントロール母集団 - [詳細を表示](../../sending/using/control-group.md)

外部 API（OAuth のサポート）- [詳細を表示](../../automating/using/external-api.md)

ジャーニー AI との統合 - [詳細を表示](../../sending/using/predictive.md)

**リリースに伴うその他のドキュメントのアップデート**

外部パラメーターを使用したワークフローの呼び出し方法に関する節に、式エディターで利用できる新しい関数が追加されました。[詳細を表示](../../automating/using/customizing-workflow-external-parameters.md)

ワークフローのベストプラクティスに、1 つのワークフローで使用するアクティビティ数に関する推奨事項が追加されました。[詳細を表示](../../automating/using/best-practices-workflows.md#number-activities)

配信のベストプラクティスに関する新しい節が追加されました。[詳細を表示](../../sending/using/delivery-best-practices.md)

新しいフィルターについて説明する節が追加され、そのイベントのステータスと最後にイベントが受信された時点に従って設定を検索できるようになりました。[詳細情報](../../channels/using/configuring-transactional-event.md#searching-transactional-events)

## 2020 年 9 月 {#doc-updates-september-2020}

**イベントトランザクションメッセージ**&#x200B;の節が整理され、明確になりました。[詳細を表示](../../channels/using/editing-transactional-message.md)

ログのアクセスに関連する権限制限についてユーザーに警告するための注意事項が追加されました。[詳細を表示](../../administration/using/users-management.md)

新しいブランドを作成するプロセスに関する新しい節が追加されました。[詳細を表示](../../administration/using/branding.md#creating-a-brand)

Campaign Standard と Microsoft Dynamics 365 の統合を新たに利用できるようになりました。[詳細を表示](../../integrating/using/d365-acs-get-started.md)

アクティブなプロファイルレポートの匿名ソースに関する情報が追加されました。[詳細を表示](../../audiences/using/active-profiles.md)

## 2020 年 8 月 {#doc-updates-august-2020}

トランザクションメッセージの概要に関する節が更新されました。[詳細を表示](../../channels/using/getting-started-with-transactional-msg.md)

**トランザクションメッセージの制限**&#x200B;の節が、[こちら](../../channels/using/transactional-messaging-limitations.md)に移動しました。.

**送信の準備**&#x200B;の節が[こちら](../../sending/using/preparing-the-send.md)に移動しました。

## 2020 年 7 月 {#doc-updates-july-2020}

Campaign Standard の監視に関するガイドラインを含む新しい節が追加されました。[詳細を表示](../../administration/using/monitoring-guidelines.md)

外部 API ガードレールと制限の節が更新されました。[詳細を表示](../../automating/using/external-api.md#guardrails)

「プライバシー管理の概要」ページが更新され、タイの個人データ保護法（PDPA）とブラジルの Lei Geral de Proteção de Dados（LGPD）に関する情報が含まれるようになりました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/campaign-privacy-overview.html#whatisgdpr)

モバイルチャネルガイドが、構成を変更して改訂されました。新しいモバイルチャネルの設定ガイドと、モバイル設定に関するテクニカルドキュメントが追加されました。[詳細を表示](../../administration/using/push-tracking.md)

Campaign Standard のプライバシー管理ページが更新され、プライバシーコアサービスの統合を通じてプライバシーリクエストを管理する方法が明確になりました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)

AI を利用した新しい E メール機能（送信時間の最適化とプロファイルスコアリング）が導入されました。[詳細情報](../../sending/using/predictive.md)

## 2020 年 6 月 {#doc-updates-june-2020}

ワークフローの使用例が更新され、主題の節に再構成されました。[詳細を表示](../../automating/using/about-workflow-use-cases.md)

コントロールパネルと Campaign ワークフローを使用したデータの[暗号化](../../automating/using/managing-encrypted-data.md#use-case-gpg-encrypt)および[](../../automating/using/managing-encrypted-data.md#use-case-gpg-decrypt)復号化の方法に関する使用例が追加されました。

従来のサポート Web サイトへの参照は、新しい URL に置き換えられました。[詳細情報](../../support.md)

インボックスレンダリング機能からカスタム Litmus アカウント設定が削除されました。[詳細を表示](../../sending/using/email-rendering.md)

Campaign Standard と Microsoft Dynamics 365 の統合は、現在使用できません。新しいコネクタが開発中で、今後利用できる予定です。関連するヘルプページは削除されました。[詳細を表示](../../integrating/using/d365-acs-get-started.md)

## 2020 年 5 月 {#doc-updates-may-2020}

Campaign Standard の概要ページが改善され、テーマごとのトピックに再構成されました。[詳細を表示](../../start/using/about-campaign-standard.md)

E メールチャネルのパラメーターの節で、許可されたマスクのフィールドと配信レポート ID に関する詳細情報が表示されるようになり、内容が明確になりました。[詳細を表示](../../administration/using/configuring-email-channel.md)

Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定がコアドキュメントに追加され、ローンチからのモバイルアプリ AEPSDK の同期テクニカルワークフローに関する詳細情報が記載されています。[詳細情報](../../administration/using/configuring-a-mobile-application.md)

## リリース 20.3 - 2020 年 5 月 {#release-20-3---may-2020}

**リリースに含まれる新機能**

タイの個人情報保護法（PDPA） - [詳細情報](https://helpx.adobe.com/content/help/jp/campaign/kb/acs-privacy.html)

外部 API アクティビティ（GA） - [詳細情報](../../automating/using/external-api.md)

**リリースに伴うその他のドキュメントのアップデート**

ワークフローのプロパティの「**[!UICONTROL History in days]**」フィールドについての情報が追加され、「**[!UICONTROL Transfer file]**」アクティビティでダウンロードされたファイルについて記述されています。[詳細を表示](../../automating/using/managing-execution-options.md)

プロファイルの置き換えの節に、件名行のプレフィックスの文字数制限（500 文字）に関する情報が追加されました。[詳細を表示](../../sending/using/testing-messages-using-target.md)

プライバシーと同意に関する新しい節がコアドキュメントに追加されました。[詳細を表示](../../start/using/privacy.md)

レガシーエディターの E メールを E メールデザイナーに変換できる使用例が追加されました。[詳細を表示](../../designing/using/converting-emails-from-legacy-editor.md)

E メールデザイナーに関するよくある質問の節が追加されました。[詳細情報](../../designing/using/faq-email-designer.md)

## 2020 年 4 月 {#doc-updates-april-2020}

Microsoft Dynamics 365 と Adobe Campaign Standard の統合に関するドキュメントが、コアドキュメントで利用できるようになりました。[詳細を表示](../../integrating/using/d365-acs-get-started.md)

追加のリソースがドキュメントホームページに追加されました。[詳細を表示](../../campaign-standard-home.md)

Experience Cloud ID サービス（ECID）に関する情報が、Adobe Experience Platform Data Connector のドキュメントに追加されました。[詳細を表示](../../integrating/using/aep-about-data-connector.md#key-concepts)

トランザクションメッセージの節が改訂され、最新のトランザクションイベントへのアクセス方法に関する情報と、最新のスクリーンショットが追加されました。[詳細を表示](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

タイポロジとタイポロジルールに関するドキュメントが改訂され、ビルトインタイポロジルール関する情報が追加されました。[詳細を表示](../../sending/using/about-typology-rules.md)

「**[!UICONTROL Transfer file]**」アクティビティの「**[!UICONTROL File listing]**」アクションに関する情報が追加されました。[詳細を表示](../../automating/using/transfer-file.md)

一時的な配信エラーの後の再試行に関するドキュメントが更新され、Enhanced MTA にアップグレードした後の再試行の管理方法に関する詳細が追加されました。[詳細を表示](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)

トランザクションメッセージの削除の節が改訂され、明確になりました。[詳細を表示](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message)

**配信メッセージのプレビュー**&#x200B;の節が更新され、モバイル配信の例が追加されました。[詳細を表示](../../sending/using/previewing-messages.md)

トランザクションメッセージングと未使用のリアルタイムイベントの削除に関するベストプラクティスが追加されました。[詳細を表示](../../channels/using/configuring-transactional-event.md#creating-an-event)

E メールチャネルの設定の節が更新され、Adobe Campaign Enhanced MTA で管理されるすべての E メール設定の内容が明確になりました。[詳細を表示](../../administration/using/configuring-email-channel.md)

トランザクションメッセージの節が更新され、イベント設定の編集に必要な権限や、トランザクションメッセージでコレクションをエンリッチメントする方法についての詳細が追加されました。[詳細情報](../../channels/using/configuring-transactional-event.md)。

## リリース 20.2 - 2020 年 4 月 {#release-20-2---april-2020}

**リリースに含まれる新機能**

Azure Blob 統合 - [詳細情報](../../administration/using/external-accounts.md#microsoft-azure-external-account)

ターゲットプロファイルを使用した E メールテスト - [詳細情報](../../sending/using/testing-messages-using-target.md)

**リリースに伴うその他のドキュメントのアップデート**

アプリ内メッセージのレンダリングに制限が追加されました。[詳細を表示](../../channels/using/customizing-an-in-app-message.md)

「**[!UICONTROL Query]**」アクティビティでの集計の使用方法に関する情報が追加されました。[詳細を表示](../../automating/using/query.md#adding-an-aggregate)

モバイルアプリケーションの設定時の MCPNS について制限が追加されました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/configuring-app-sdk.html)

新しい設定のガイドラインの節が管理ガイドに追加されました。互換性のあるブラウザーとオペレーティングシステムに関する節は、始める前にからこの節に移動しました。Campaign Standard ネットワークエンドポイントに関するテクニカルノートもこの節に追加されました。[詳細を表示](../../administration/using/about-configuration-guidelines.md)

イベント設定の削除方法を説明する新しい節が追加されました。[詳細を表示](../../channels/using/publishing-transactional-event.md#deleting-an-event)

トランザクションメッセージの節が更新され、複数のユーザーインターフェイスに関するいくつかの更新と改善が反映されました。[詳細を表示](../../channels/using/getting-started-with-transactional-msg.md)

外部 API アクティビティガードレールに関する情報が更新されました。[詳細情報](../../automating/using/external-api.md)

## 2020 年 3 月 {#doc-updates-march-2020}

Enhanced MTA の詳細がコアドキュメントに追加されました。特に、E メール処理ルールやバウンスメールの選定に関する詳細が追加されています。[詳細を表示](../../administration/using/configuring-email-channel.md#email-processing-rules)

E メール BCC でのアーカイブに関する節が移動され、更新されました。[詳細を表示](../../sending/using/archiving.md)

モバイルアプリケーションの設定ドキュメントと関連ページが更新され、SDK V4 が非推奨になっていることが反映されています。[詳細を表示](https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq)

Adobe Campaign Standard／Adobe Experience Manager の統合に関するドキュメントが更新され、改訂されました。[詳細を表示](../../integrating/using/configure-experience-manager.md)

Campaign E メールデザイナーのドキュメントと関連ページが更新され、[!DNL Adobe Creative SDK] が非推奨になっていることが反映されました。[詳細を表示](../../rn/using/deprecated-features.md)

Campaign Standard データモデルのベストプラクティスに関する新しい節が追加されました。[詳細を表示](../../developing/using/data-model-best-practices.md)

**[!UICONTROL Workflow]** のビルトイン権限に関する情報が追加されました。[詳細を表示](../../administration/using/list-of-roles.md)

ワークフローのプロパティで使用できる **[!UICONTROL History in days field]** に関する情報が追加されました。[詳細を表示](../../automating/using/about-workflow-execution.md)

## リリース 20.1 - 2020 年 2 月 {#release-20-1---february-2020}

**リリースに含まれる新機能**

Adobe Experience Platform Data Connector（ベータ版） - [詳細情報](../../integrating/using/aep-about-data-connector.md)

Audience Destinations（ベータ版） - [詳細情報](../../integrating/using/aep-about-audience-destinations-service.md)

**リリースに伴うその他のドキュメントのアップデート**

プライバシー管理に関するドキュメントが更新され、カスタムプロファイルリソース用の CCPA オプトアウトフィールドの作成方法に関する情報が追加されました。[詳細を表示](https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html)

リリースノートが、構成を変更して改訂されました。[詳細を表示](../../rn/using/release-notes.md)

管理者セキュリティグループに関連する情報が追加されました。このグループに「**[!UICONTROL All (all)]**」組織単位が割り当てられ、変更できないことが明記されています。[詳細を表示](../../administration/using/managing-groups-and-users.md)

ワークフローでデフォルトで使用する特定のタイムゾーンを定義する方法に関する情報が追加されました。[詳細を表示](../../automating/using/building-a-workflow.md)

新しい **_forcePagination=true** パラメーターに関する情報が、API の操作の節に追加され、大きなテーブルでページ編集ができるようになりました。[詳細を表示](../../api/using/pagination.md)

メッセージダッシュボードに表示できる警告について説明する新しい節が追加されました。[詳細を表示](../../channels/using/message-dashboard.md#warnings)

Adobe Campaign Enhanced MTA のドキュメントが利用できるようになりました。このドキュメントは配信品質、スループット、バウンス処理を改善するためアップグレードされた送信インフラストラクチャについて説明しています。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/campaign-enhanced-mta.html)

Campaign のユーザーインターフェイスからランディングページとミラーページのプレビューを表示するには、アプリケーションサーバーとミラーページサーバーの URL がセキュリティで保護されている必要があることを示すメモが追加されました。[詳細を表示](../../administration/using/branding.md#configuring-and-using-brands)

ログの書き出しの節が更新されました。配信ログとトラッキングログのリソースで配信ログ ID が使用でき、各ログの一意の識別子を書き出せるようになったことが反映されています。[詳細情報](../../automating/using/exporting-logs.md)

## 2020 年 1 月 {#doc-updates-january-2020}

配信品質に関するドキュメントが更新され、IP 証明書に関する新しい節が追加されました。<!--[Read more](../../sending/using/ip-certification.md)-->

クロスチャネル配信ワークフローの作成方法を説明する新しい節が追加されました。[詳細を表示](../../automating/using/workflow-cross-channel-delivery.md)

動的レポートのインジケーターの計算に関する節が更新されました。[詳細を表示](../../reporting/using/indicator-calculation.md)

Adobe Campaign Standard のモバイル配信に関する一般的なガイドラインに関する新しいページが追加されました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/acs-mobile.html)

Campaign と Experience Manager の使用に関するドキュメントが更新され、**Campaign と Experience Manager の統合の使用方法に関するヒント**&#x200B;の節が新しく追加されました。[詳細を表示](../../integrating/using/integrating-with-experience-manager.md#tips-aem)

API ドキュメントのホームページが改善され、各種のトピックへのリダイレクトが追加されました。[詳細を表示](../../api/using/get-started-apis.md)

## 2019 年 11 月〜12 月 {#doc-updates-december-2019}

S3 外部アカウントの設定に関するドキュメントが更新されました。[詳細を表示](../../administration/using/external-accounts.md#amazon-s3-external-account)

E メールコンテンツのデザインの節の構成を変更しました。[詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md)

配信品質の入門ガイドは、コアドキュメントに統合され、更新されました。[詳細を表示](../../sending/using/about-deliverability.md)

カスタムリソースの書き出し／インポートの方法に関する入門ガイドが、コアドキュメントに統合されました。[詳細を表示](../../automating/using/exporting-importing-custom-resources.md)

Campaign Standard 内のワークフローを使用してコントロール母集団を構築する方法を説明する新しい使用例が追加されました。

ランディングページのプロパティに関する情報が、専用の節に移動されました。[詳細を表示](../../channels/using/configuring-landing-page.md)

コントロールパネルのドキュメントは、新しいコラボレーションドキュメントセットに統合されました。[詳細を表示](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=ja)

**指標の計算**&#x200B;テーブルが更新されました。[詳細を表示](../../reporting/using/indicator-calculation.md)

API ドキュメントセットは、Campaign Standard ドキュメントに統合されました。[詳細を表示](../../api/using/get-started-apis.md)

パーソナライズされた E メールの作成入門ガイドの節を移動し、更新しました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/acs-get-started-with-emails.html)

配信のベストプラクティス入門ガイドが更新されました。[詳細を表示](../../sending/using/delivery-best-practices.md)

データモデルは、Campaign Standard ドキュメントに統合されました。[詳細を表示](../../developing/using/datamodel-audience.md)

新しい API エンドポイント **/customResources** が API ドキュメントに追加されました。[詳細を表示](../../api/using/interacting-with-custom-resources.md)

## リリース 19.4 - 2019 年 10 月 {#release-19-4---october-2019}

**リリースに含まれる新機能**

カリフォルニア州消費者プライバシー法（CCPA） - [詳細を表示](https://helpx.adobe.com/jp/campaign/kb/acs-privacy.html#ccpa)

Microsoft Dynamics 365 統合（GA） - [詳細情報](../../integrating/using/d365-acs-get-started.md)

**リリースに伴うその他のドキュメントのアップデート**

Adobe Campaign のエラーメッセージのリストが更新されました。[詳細を表示](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

GDPR の入門ガイドが改善され、強化されました。GDPR や CCPA を含む、プライバシー管理に関するドキュメントになりました。[詳細を表示](https://helpx.adobe.com/content/help/jp/campaign/kb/campaign-privacy.html)

トランザクションメッセージングの公開プロセスを示す新しいチャートが追加されました。[詳細を表示](../../channels/using/publishing-transactional-message.md#transactional-messaging-pub-process)

配信のベストプラクティス入門ガイドが移動され、更新されました。[詳細を表示](../../sending/using/delivery-best-practices.md)

新しい節が追加されました。Campaign Standard データベースを拡張する各種の方法の概要を説明しています。[詳細を表示](../../audiences/using/enriching-campaign-database.md)

E メールデザイナーでリンクのスタイルを設定する方法を説明する節を新しく追加しました。[詳細を表示](../../designing/using/styles.md#about-styling-links)

プライバシーに関する情報が API ドキュメントに追加されました。[ここをクリック](../../api/using/creating-a-privacy-request.md)

## 2019 年 9 月～ 10 月 {#doc-updates-october-2019}

Campaign Standard 設定に関連する新しい節が追加されました。[詳細を表示](../../administration/using/about-campaign-standard-settings.md)

特定のサービスに登録しているプロファイルに、自動カスタム確認 E メールを送信する方法について説明する新しい節が追加されました。[詳細を表示](../../audiences/using/confirming-subscription-to-a-service.md)

トランザクションメッセージの節が変更され、E メールデザイナーでのコンテンツの編集などの最新の UI の更新が反映されました。[詳細を表示](../../channels/using/editing-transactional-message.md)

ランディングページの章の構成が変更されました。また、ランディングページの設定手順を詳しく説明する新しい節が追加されました。[詳細を表示](../../channels/using/getting-started-with-landing-pages.md)

モバイルアプリケーションの登録データに基づくプロファイル情報の作成および更新の方法について、「プッシュ通知」の節に新しい節が追加されました。[詳細を表示](../../channels/using/updating-profile-with-mobile-app-data.md)

「ファイル読み込み」アクティビティから取得した追加データが含まれる E メールの送信方法を示す新しい例が追加されました。[詳細を表示](../../automating/using/sending-email-enriched-fields.md)

トラッピングの使用方法に関する新しい節が追加されました。[詳細を表示](../../sending/using/using-traps.md)

Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定方法に関するページに、**Launch_URL_**（Launch_URL_Platform）に関する注意が追加されました。[詳細を表示](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)

E メールデザイナーガイドの構成が変更されました。[詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md)

## 2019 年 8 月 {#doc-updates-august-2019}

クエリに注目したワークフローの使用例を紹介する新しい節を追加しました。[詳細を表示](../../automating/using/workflow-created-query-with-complement.md)

トラブルシューティングの節で、「ログ」タブに SQL クエリを表示する方法に関するワークフローの手順が追加されました。[詳細を表示](../../automating/using/best-practices-workflows.md#troubleshooting-data-management-activities)

コントロールパネル内でのサブドメインと証明書の管理に関する情報を紹介する新しいヘルプ記事が追加されました。[詳細を表示](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=ja)

コンテンツテンプレートとフラグメントについて説明する節が更新されました。[詳細を表示](../../designing/using/using-reusable-content.md#content-templates)

E メールデザイナーで E メールコンテンツをテンプレートとして保存する方法に関する新しい節が追加されました。[詳細を表示](../../designing/using/using-reusable-content.md#saving-content-as-template)

## リリース 19.3 - 2019 年 7 月 {#release-19-3---july-2019}

**リリースに含まれる新機能**

外部 API アクティビティ（公開ベータ版） - [詳細情報](../../automating/using/external-api.md)

ワークフローセグメントに関するレポート - [詳細情報](../../reporting/using/creating-a-report-workflow-segment.md)

**リリースに伴うその他のドキュメントのアップデート**

Campaign Standard 実装ガイドが公開されました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/campaign-standard-implementation-guide.html)

Microsoft Dynamics 365 コネクタの実装と使用に関する一連の新しいヘルプ記事が作成されました。この機能は現在、使用が制限されています。[詳細を表示](../../integrating/using/d365-acs-get-started.md)

配信の準備とその集計期間に関する注意事項が[パラメーターを使用したワークフローの呼び出し](../../automating/using/calling-a-workflow-with-external-parameters.md)の節に追加されました。

ワークフローの外部シグナルアクティビティで宣言されたイベント変数を使用して、配信のラベルをパーソナライズする方法に関する情報が追加されました。[詳細を表示](../../automating/using/external-signal.md)

Adobe Campaign Standard でユーザーを作成する方法の詳細を説明する新しい節が追加されました。[詳細を表示](../../administration/using/users-management.md)

製品ドキュメントやチュートリアルビデオへのリンクなど、マーケティングキャンペーンを簡素化するためのヒントを紹介する新しい記事が追加されました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/simplify-campaign-management.html)

動的レポートに関するトラブルシューティングが追加されました。[詳細を表示](../../reporting/using/troubleshooting.md)

各種のアプリ内テンプレートでの個人情報の処理方法を説明する図が追加されました。[詳細を表示](../../channels/using/preparing-and-sending-an-in-app-message.md)

E メールデザイナーで E メールコンテンツをフラグメントとして保存する方法に関する節が更新されました。[詳細を表示](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

余分な空白が E メールコンテンツのレイアウトに与える影響に関する警告が追加されました。[詳細を表示](../../designing/using/personalization.md#creating-custom-content-blocks)

E メールデザイナーの推奨されるアップデートに関する新しい節が追加されました。[詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

<!-- A new section on how to send proofs using real customer data has been added. [Read more](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs-using-additional-data) -->

ワークフローのベストプラクティスに関する新しい節が追加されました。[詳細を表示](../../automating/using/best-practices-workflows.md)

 Standard および Campaign Classic のエラーメッセージのリストが更新されました。[詳細を表示](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

カスタムリソースドキュメントに警告を追加しました。カスタムリソース ID には使用する文字は最大 30 文字にすることをお勧めします。これは、カスタムのリソースフィールド、キー、インデックス、リンクについても同様です。[詳細を表示](../../developing/using/creating-or-extending-the-resource.md)

## 2019 年 6 月～7 月 {#doc-updates-2019}

ランディングページの制限に関する新しいページを追加しました。[詳細を表示](../../channels/using/getting-started-with-landing-pages.md#landing-page-limitations)

複合識別キーを使用したプロファイルの呼び出し方法に関する使用例が追加されました。[詳細を表示](../../developing/using/uc-calling-resource-id-key.md)

パラメーターを使用してワークフローを呼び出す場合の、集計期間のない繰り返し配信の使用に関する推奨事項が追加されました。[詳細を表示](../../automating/using/calling-a-workflow-with-external-parameters.md)

 Standard および Campaign Classic のエラーメッセージのリストが更新されました。[詳細を表示](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

カスタムリソースドキュメントに警告を追加しました。カスタムリソース ID には使用する文字は最大 30 文字にすることをお勧めします。これは、カスタムのリソースフィールド、キー、インデックス、リンクについても同様です。[詳細を表示](../../developing/using/creating-or-extending-the-resource.md)

## リリース 19.2 - 2019 年 5 月 {#release-19-2---may-2019}

**リリースに含まれる新機能**

コントロールパネル - [詳細を表示](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html)

ローカル通知 - [詳細を表示](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)

ワークフローの強化 - 外部信号アクティビティにペイロードを追加 - [詳細を表示](../../automating/using/calling-a-workflow-with-external-parameters.md)

ランディングページ機能の強化 - Google reCAPTCHA - [詳細を表示](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)

**リリースに伴うその他のドキュメントのアップデート**

ドメイン名の委任に関する記事が更新されました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/domain-name-delegation.html)

リリース計画に関する新しい記事が公開され、今後のリリース日程が発表されました。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/acs-release-planning.html)

Adobe Campaign から直接利用できるコンテキストヘルプリンクが更新されました。

次の[ページは](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=ja) Adobe Campaign Standard の公式ビデオページになります。

標準テーブルのデフォルトの保持率など、データ保持に関する節を追加しました。[詳細を表示](../../administration/using/data-retention.md)

アップデートとメンテナンスの操作に関する節を追加しました。[詳細を表示](../../administration/using/updates-and-maintenance-operations.md)

「**ファイル転送**」アクティビティの新しい並べ替えオプションに関する情報が追加されました。[詳細を表示](../../automating/using/transfer-file.md)

[REST API のドキュメント](../../api/using/get-started-apis.md)が更新されました。

* Campaign Standard REST API を使用する理由に関する一般的な情報を含む、新しい節が追加されました。
* 一般的な使用例を表す、事前設計された API リクエストの一群が利用可能になりました。
* 組織単位の管理方法に関する新しい節が追加されました。
* サービスの作成方法に関する情報が追加されました。
* パラメーターを使用してワークフローを呼び出す方法に関する情報が追加されました。

新しい「**テスト**」アクティビティに情報が追加されました。[詳細を表示](../../automating/using/test.md)

自動化ガイドが更新され、関連するワークフローアクティビティへのリンクが追加されました。[詳細を表示](../../automating/using/workflow-interface.md#palette)

動的レポートのインジケーターの計算に関する節が更新されました。[詳細を表示](../../reporting/using/indicator-calculation.md)

ディメンションと指標の互換性をより深く理解できるように、動的レポートの互換性の表が追加されました。[詳細を表示](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

ワークフローの関数のリストが更新されました。[詳細を表示](../../automating/using/list-of-functions.md)

コンテンツのデザインの章の構成を変更し、改訂しました。既存のコンテンツを使用して E メールデザイナーで E メールをデザインする方法について説明する節が新たに追加されました。[詳細を表示](../../designing/using/using-existing-content.md)

E メールデザイナーで E メールコンテンツをフラグメントとして保存する方法に関する新しい節が追加されました。[詳細を表示](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

「リンクの管理」の節が更新され、E メールデザイナーで追跡する URL を管理する方法に関する情報が追加されました。[詳細を表示](../../designing/using/links.md#inserting-a-link)

特定のトランザクションメッセージの再試行プロセスを説明する新しい節が追加されました。[詳細を表示](../../channels/using/transactional-message-execution.md#transactional-message-retry-process)

API 拡張によるリソースの公開の節が明確になり、最新の UI の変更が反映されました。[詳細を表示](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

E メールのアーカイブの節の名前と構成が変更されました。[詳細を表示](../../sending/using/archiving.md)

E メールの作成の節が更新され、最新のインターフェイス変更が反映されました。[詳細を表示](../../channels/using/creating-an-email.md)

[SMS コネクタのプロトコルと設定](https://helpx.adobe.com/jp/campaign/kb/sms-connector-protocol-and-settings.html)のナレッジベース記事が更新されました。SMPP プロバイダーに接続できる MTA インスタンスの数を制限するための新しいオプションが SMS 外部アカウントに追加されています。

入門ガイドが強化され、構成が変更されました。[詳細を表示](../../start/using/about-campaign-standard.md)

廃止および削除された機能ページが更新されました。[詳細を表示](../../rn/using/deprecated-features.md)

Dreamweaver の統合に関する節が更新および改訂されました。[詳細を表示](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)

## リリース 19.1 - 2019 年 2 月 {#release-19-1---february-2019}

**リリースに含まれる新機能**

プッシュチャネルレポートの強化 - [詳細を表示](../../reporting/using/push-notification-report.md)

モバイルアプリのローンチ統合 - [詳細を表示](../../administration/using/configuring-a-mobile-application.md#using-adobe-experience-platform-sdk)

モバイルアプリ内メッセージ - [詳細を表示](../../channels/using/about-in-app-messaging.md)

ワークフローの強化 - 詳細を表示（[こちら](../../automating/using/workflow-interface.md#duplicating-workflow-activities)と[こちら](../../automating/using/load-file.md#configuration)）

**リリースに伴うその他のドキュメントのアップデート**

E メールコンテンツを作成する新しいオンボードエクスペリエンスと、E メールデザイナーのその他の機能強化が、E メールの内容の編集の章に追加されました。[詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)

トランザクションメッセージの制限に関する新しい節を追加しました。[詳細を表示](../../channels/using/transactional-messaging-limitations.md)

Adobe Campaign の各種の E メールオーサリングオプションを比較した新しい節を追加しました。[詳細を表示](../../designing/using/using-integrations.md#email-design-options-comparison)

カスタムコンテンツブロックの作成の節が改訂され、ターゲティングディメンションの詳細が追加されました。[詳細を表示](../../designing/using/personalization.md#creating-custom-content-blocks)

E メールデザイナーが Internet Explorer 11 をサポートしていないことを示す警告が追加されました。[詳細を表示](../../administration/using/about-configuration-guidelines.md)

リソースの削除の節に、再ドラフト化の影響に関する警告が追加されました。[詳細を表示](../../developing/using/deleting-a-resource.md)

リソースの追加または拡張方法に関する章が更新されました。[詳細を表示](../../developing/using/creating-or-extending-the-resource.md)

プロファイルのカスタムリソースを拡張する方法に関する使用例が追加されました。[詳細を表示](../../developing/using/extending-the-profile-resource-with-a-new-field.md)

カスタムリソースをリンクする方法に関する情報を追加しました。[詳細を表示](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)

Adobe Campaign Standard のプッシュ通知から画像を表示する方法に関する新しいテクニカルノートが追加されました。[詳細を表示](../../administration/using/image-push-notification.md)

プッシュトラッキングの実装に関する新しいテクニカルノートが追加されました。[詳細を表示](../../administration/using/push-tracking.md)

 Standard および Campaign Classic のエラーメッセージのリストが更新されました。[詳細を表示](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

トリガー - Campaign の統合ドキュメントが更新されました。[詳細を表示](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Adobe Campaign から直接利用できるコンテキストヘルプリンクが更新されました。

却下情報が含まれるファイルの名前にタイムスタンプを追加した場合の注意が追加されました。[詳細を表示](../../automating/using/load-file.md#configuration)

固定長の列で構成されたフィールドをインポートする際の情報を追加しました。[詳細を表示](../../automating/using/load-file.md#configuration)

ファイル内に却下情報を保持できるオプションに関する情報を追加しました。このオプションを使用すると、却下情報が含まれるファイルに後処理ステージを適用できます。[詳細を表示](../../automating/using/load-file.md#configuration)

コピーと貼り付けによるワークフローアクティビティの複製方法に関する節を新しく追加しました。[詳細を表示](../../automating/using/workflow-interface.md#duplicating-workflow-activities)

「クエリ」アクティビティ（[詳細を表示](../../automating/using/query-samples.md)）と「セグメント化」アクティビティ（[詳細を表示](../../automating/using/segmentation.md)）の新しいオプションに関する情報を追加しました。アクティビティでデータが取得されなかった場合、アクティビティの後で送信トランジションを追加できます。

「データ更新」アクティビティの節に新しい「バッチサイズ」フィールドに関する情報を追加しました。このフィールドではアップロードするデータの最大バッチサイズを定義できます。[詳細を表示](../../automating/using/update-data.md#configuration)

「ファイルの抽出」アクティビティの節に、送信トランジションが空の場合にファイル生成プロセスを無効にする新しいオプションに関する情報を追加しました。[詳細を表示](../../automating/using/extract-file.md#configuration)

## リリース 19.0 - 2019 年 1 月 {#release-19-0---january-2019}

**リリースに含まれる新機能**

E メールデザイナーの一般提供 - [詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md)

トランザクション E メールの製品リスト - [詳細を表示](../../designing/using/using-product-listings.md)

E メールデザイナーのモバイル表示- [詳細を表示](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)

アプリ内メッセージベータ版の改善 - [詳細を表示](../../channels/using/about-in-app-messaging.md)

**リリースに伴うその他のドキュメントのアップデート**

コンテンツのデザインガイドが更新され、E メールデザイナーの一般提供と、従来の E メールコンテンツエディターの廃止が反映されました。[詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md)

[アプリ内](../../channels/using/about-in-app-messaging.md)および[プッシュ通知](../../channels/using/about-push-notifications.md)に関するドキュメントを更新しました。

Adobe Campaign の各種のオーディエンスに関する詳細を追加しました。[詳細を表示](../../audiences/using/about-audiences.md)

ユーザーとセキュリティの章を更新し、地理的単位の廃止を反映しました。[詳細を表示](../../administration/using/organizational-units.md)

「データの読み込み」アクティビティの新しいオプションに関する情報を追加しました。このオプションを使用すると、後処理ステージを、却下されたレコードが含まれるファイルに適用できます（例：Zip 形式の圧縮）。[詳細を表示](../../automating/using/load-file.md)

「データ更新」アクティビティの新しいフィールドに関する情報を追加しました。このフィールドでは、アップロードするデータの最大バッチサイズを設定できます。[詳細を表示](../../automating/using/update-data.md)

[URL からのコンテンツのインポート](../../designing/using/using-existing-content.md#importing-content-from-a-url)ドキュメントが更新され、E メールデザイナーに関連する情報が追加されました。

Microsoft Edge（最新バージョン）が、コンピューター用の互換性のあるブラウザーのリストに追加されました。[詳細を表示](../../administration/using/about-configuration-guidelines.md)

「ファイルの抽出」アクティビティの新しいオプションに関する情報が追加されました。このオプションは、受信トランジションが空の場合に、ファイルが生成されないようにします。[詳細を表示](../../automating/using/extract-file.md)

SDK V4 を使用したモバイルアプリケーションの設定の節は、[ここ](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html)に移動しました。

Adobe Experience Platform SDK を使用したモバイルアプリケーションの設定の節は、[ここ](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)に移動しました。

ビデオが更新され、[ここ](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html)に移動しました。

ユーザーのタイプの節を更新しました。[詳細を表示](../../administration/using/users-management.md)

## リリース 18.9 - 2018 年 9 月 {#release-18-9---september-2018}

**リリースに含まれる新機能**

アプリ内メッセージ（ベータ版） - [詳細を表示](../../channels/using/about-in-app-messaging.md)

モバイルアプリの Adobe Launch 統合（ベータ版）- [詳細を表示](../../sending/using/managing-typologies.md)

**リリースに伴うその他のドキュメントのアップデート**

プッシュ通知ガイドが更新され、インターフェイスの変更が反映されました。[詳細を表示](../../channels/using/about-push-notifications.md)

オーディエンスの削除方法に関する情報を追加しました。[詳細を表示](../../audiences/using/creating-audiences.md#deleting-audiences)

プッシュ通知のビルトインレポートの節を更新しました。[詳細を表示](../../reporting/using/push-notification-report.md)

## リリース 18.7 - 2018 年 7 月 {#release-18-7---july-2018}

**リリースに含まれる新機能**

モバイルアプリ購読者の[優先度高フラグ](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android)と[タイポロジーフィルター](../../sending/using/managing-typologies.md)。

準備時の URL からのコンテンツインポートを自動化。[詳細を表示](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

**リリースに伴うその他のドキュメントのアップデート**

SMS コネクタのプロトコルと設定に関する新しいテクニカルノートを追加しました。[詳細を表示](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html)

Experience Manager と Adobe Campaign との統合に関するドキュメントを更新しました。[詳細を表示](../../reporting/using/creating-a-custom-profile-dimension.md)

「コンテンツのデザイン」ガイドの構成が全面的に更新され、E メール用のコンテンツを設計するための 2 種類のエディターが紹介されています。[詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md)

既存の E メールからフラグメントを作成し、Creative SDK で全面的に編集可能な外部コンテンツを簡単に作成する方法を説明します。[詳細を表示](../../designing/using/designing-from-scratch.md)

Creative Designer に完全に対応するための HTML 属性のリストを、この[節](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer)で紹介します。

多言語テンプレートのデフォルト言語に関する情報を追加しました。[詳細を表示](../../channels/using/multilingual-messages-template.md)

ユーザーとセキュリティガイドが更新され、18.7 リリース以降、新しい Campaign Standard インスタンスおよび地理的単位が作成されていない既存インスタンスで、地理的単位機能が廃止されたことが反映されています。[詳細を表示](../../rn/using/deprecated-features.md)

## リリース 18.6 - 2018 年 6 月 {#release-18-6---june-2018}

**リリースに含まれる新機能**

API ドキュメントが更新され、**履歴** API に関する情報が追加されました。プロファイルに送信された配信のミラーページを取得する方法に関する使用例が追加されました。[詳細を表示](../../api/using/interacting-with-marketing-history.md)

**リリースに伴うその他のドキュメントのアップデート**

トリガー - Campaign の統合ドキュメントが更新され、構成が変更されました。[詳細を表示](../../integrating/using/about-adobe-experience-cloud-triggers.md)

カスタムプロファイルディメンションの作成方法に関するステップバイステップの使用例を追加しました。[詳細を表示](../../reporting/using/creating-a-custom-profile-dimension.md)

Campaign と Audience Manager または People コアサービスの使用ドキュメントの構成を変更しました。[詳細を表示](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

「配信役割の定義の準備」を更新しました。[詳細を表示](../../administration/using/list-of-roles.md)

「クエリ」アクティビティの節に、配信内の特定のリンクをクリックしたプロファイルをターゲットにする方法についての例を追加しました。[詳細を表示](../../automating/using/query-samples.md#targeting-profiles-who-clicked-a-specific-link-)

API ドキュメントに、**カスタムフィルター**&#x200B;に関連する節を追加しました。[詳細を表示](../../api/using/filtering.md)

## リリース 18.5 - 2018 年 5 月 {#release-18-5---may-2018}

**リリースに含まれる新機能**

GDPR：コアサービスの統合 - [詳細を表示](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=ja)

プッシュ機能の強化 - 詳細な配信フィードバック - [詳細を表示](../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification)

配信ログ拡張機能 - [詳細を表示](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

カスタムプロファイルデータによる動的レポート- [詳細を表示](../../channels/using/creating-a-multilingual-push-notification.md)

**リリースに伴うその他のドキュメントのアップデート**

Analytics の Campaign 指標のリストを追加しました。[詳細を表示](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Administration メニューの「ライセンス」オプションに関する情報を追加しました。[詳細を表示](../../administration/using/licenses.md)

プッシュ通知でのカスタムフィールドの使用方法に関する情報を追加しました。[詳細を表示](../../channels/using/customizing-a-push-notification.md#add-custom-fields)

配信のベストプラクティスのステップバイステップガイドを更新しました。[詳細を表示](../../sending/using/delivery-best-practices.md)

トラッキングログのタイプに関する情報を追加しました。[詳細を表示](../../sending/using/tracking-messages.md#tracking-logs)

「クエリ」アクティビティの節が更新され、クエリの例が追加されました。[詳細を表示](../../automating/using/query.md#query-samples)

ブロックリストに関する節の名称を「オプトインおよびオプトアウトプロセスについて」に変更しました。特定のチャネルに対するオプトインの管理方法、およびオプトインとオプトアウトを管理するランディングページの設定方法に関する情報が更新されました。[詳細を表示](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

アドビがホストする SFTP サーバーを使用する際のベストプラクティスについて説明します。[詳細を表示](../../administration/using/external-accounts.md#sftp-external-account)

トリガーとの統合でサポートされる Analytics SKU のリストが更新されました。[詳細を表示](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)

コンテンツエディターのドキュメントの一部のページが統合され、使用可能な各種のアクションを総合的に参照できるようになりました。[詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md)

## リリース 18.3 - 2018 年 3 月 {#release-18-3---march-2018}

**リリースに含まれる新機能**

EU 一般データ保護規則（GDPR） - [詳細を表示](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html)

E メール用 Creative Designer - [詳細を表示](../../designing/using/designing-content-in-adobe-campaign.md)

多言語プッシュ配信- [詳細を表示](../../channels/using/creating-a-multilingual-push-notification.md)

トランザクションメッセージでのカスタムリソースの使用 - [詳細を表示](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)

**リリースに伴うその他のドキュメントのアップデート**

GDPR API は、GDPR リクエストの自動処理を可能にする機能を再グループ化します。[詳細を表示](../../api/using/creating-a-privacy-request.md)

受信者をブロックリストに登録できるようにランディングページを設定する方法に関する情報を追加しました。[詳細を表示](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)

[トランザクションメッセージの設定](../../channels/using/configuring-transactional-event.md)の節の構成が変更され、[ステップバイステップの使用例](../../channels/using/transactional-messaging-use-case.md)が追加されました。

プッシュ通知に使用する多言語の CSV ファイルを生成する方法を説明するテクニカルノートが追加されました。[詳細を表示](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push.html)

**ダイレクトメール用の強制隔離と配信ログの更新**&#x200B;インポートテンプレートに関する情報を追加しました。[詳細を表示](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)

テクニカルワークフローのリストを更新しました。[詳細を表示](../../administration/using/technical-workflows.md)

スケジューラーアクティビティの節を更新しました。[詳細を表示](../../automating/using/scheduler.md)

Campaign とアドビソリューションの統合に関するヘルプ資料のリストを更新しました。[詳細を表示](../../integrating/using/get-started-campaign-integrations.md)

Campaign Standard の製品内コンテキストヘルプを更新しました。

## リリース 18.2 - 2018 年 2 月 {#release-18-2---february-2018}

**リリースに含まれる新機能**

購読 - プロファイルのリストを複数のサービスで購読または登録解除 - [詳細を表示](../../automating/using/subscription-services.md)

エンリッチメントアクティビティ - 以前のトランジションに基づくデータの強化 - [詳細を表示](../../automating/using/enrichment.md)

**リリースに伴うその他のドキュメントのアップデート**

Campaign とアドビソリューションの統合のほとんどの URL が変更されました。ブックマークを確認してください。[詳細を表示](../../integrating/using/get-started-campaign-integrations.md)

データモデル v1 を、ビルトインリソース用の SQL 構造で使用できるようになりました。[詳細を表示](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/developing/datamodel/datamodel-audience.html)

配信でのメッセージの準備方法に関する情報を追加しました。[詳細を表示](../../sending/using/preparing-the-send.md)

リリースノートが複数のページに整理され、すべての異なるリリースの全体像を把握できます。

**[!UICONTROL Working with typologies]** の節が更新され、可視性が向上しました。[詳細を表示](../../sending/using/about-typology-rules.md)

**[!UICONTROL Query]** で多数の追加データを定義する際にパフォーマンスを向上できる新しいオプションが使用できるようになりました。[詳細を表示](../../automating/using/query-samples.md)

プロファイルのインポートの例が更新され、プロファイルがダイレクトメールを受け取れるようにするためのヒントが追加されました。[詳細を表示](../../automating/using/about-data-import-and-export.md)

ワークフローで新しく「**[!UICONTROL Enrichment]**」アクティビティが使用できるようになりました。[詳細を表示](../../automating/using/enrichment.md)

「**[!UICONTROL Subscription Services]**」アクティビティが更新され、1 つのファイルを使用して複数のサービスへの登録を更新するなど、より多くの使用例をサポートできるようになりました。[詳細を表示](../../automating/using/subscription-services.md)

配信の準備方法に関するステップバイステップの使用例を追加しました。[詳細を表示](../../sending/using/preparing-the-send.md)

認証のリストが記載された節は削除されました。[詳細を表示](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)（PDF）

SMS 自動返信に関するステップバイステップの使用例を追加しました。[詳細を表示](../../channels/using/managing-incoming-sms.md#managing-stop-sms)

繰り返しワークフローでユーザーのタイムゾーンに応じて配信を送信する方法に関する情報を追加しました。[詳細を表示](../../automating/using/recurring-push-notifications.md)

**[!UICONTROL Customizing a push notification]** の節の構成が変更され、ステップバイステップの使用例が追加されました。[詳細を表示](../../channels/using/customizing-a-push-notification.md)

ブロックリスト管理に関する新しい節が追加されました。[詳細を表示](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

配信の失敗と強制隔離に関する情報を更新しました。[詳細を表示](../../sending/using/monitoring-a-delivery.md)

[ターゲットマッピング](../../administration/using/target-mappings-in-campaign.md)、[ターゲティングディメンションとリソース](../../automating/using/query.md#targeting-dimensions-and-resources)に関する新しい節です。

## リリース 18.1 - 2018 年 1 月 {#release-18-1---january-2018}

**リリースに含まれる新機能**

疲労管理のレポート- [詳細を表示](../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report)

レポートの共有 - [詳細を表示](../../reporting/using/reporting-interface.md#share-tab)

プッシュ機能の強化 - 詳細を表示（[こちら](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)と[こちら](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios)）

タイムゾーンに最適化された配信 - [詳細を表示](../../automating/using/scheduler.md)

API シグナルアクティビティトリガー - [詳細を表示](../../api/using/triggering-a-signal-activity.md)

**リリースに伴うその他のドキュメントのアップデート**

サービス作成に関する節を更新しました。[詳細を表示](../../audiences/using/creating-a-service.md)

セキュリティグループとユニットを詳しく理解するための使用例を追加しました。[詳細を表示](../../administration/using/organizational-units.md)

動的レポートのディメンション、指標およびセグメントの定義と計算を改訂しました。[詳細を表示](../../reporting/using/list-of-components-.md)

ワークフローを使用した受信 SMS メッセージの取得に関する情報を追加しました。[詳細を表示](../../administration/using/configuring-sms-channel.md)

「ファイル転送」アクティビティの履歴化設定に関する情報を追加しました。[詳細を表示](../../automating/using/transfer-file.md)

Audience Manager または People コアサービスとの統合を設定する手順が更新されました。[詳細を表示](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

## リリース 17.10 - 2017 年 10 月 {#release-17-10---october-2017}

**リリースに含まれる新機能**

疲労管理 - [詳細を表示](../../sending/using/fatigue-rules.md)

コンテンツの作成：URL からインポート - [詳細を表示](../../designing/using/using-existing-content.md#importing-content-from-a-url)

**リリースに伴うその他のドキュメントのアップデート**

A/B テストのサンプルを更新しました。[詳細を表示](../../channels/using/designing-an-a-b-test-email.md)

モバイルアプリが「PII 収集」データを送信する際のプロファイルデータの作成または更新方法に関する新しいテクニカルノート。[詳細を表示](https://docs.adobe.com/content/help/ja-JP/campaign-standard/using/communication-channels/push-notifications/updating-profile-with-mobile-app-data.html)

新しい書き出しトラッキング機能に関する節を追加しました。[詳細を表示](../../administration/using/auditing-export-logs.md)

ビルトインパッケージの書き出しに関する精度を追加しました。[詳細を表示](../../automating/using/managing-packages.md)

外部アカウントの定義とサンプルを更新しました。[詳細を表示](../../administration/using/external-accounts.md)

クエリエディターのカテゴリの変更を反映するため、多数のスクリーンショットを更新しました。

[配信警告](../../sending/using/receiving-alerts-when-failures-happen.md)の節が移動され、構成が変更されました。

カスタムリソースの節に、[フィルターの定義](../../developing/using/configuring-filter-definition.md)方法に関する詳細な手順が追加されました。

Adobe Marketing Cloud Mobile SDK をモバイルアプリと統合して Adobe Campaign Standard のプッシュ通知を受信する方法に関する[テクニカルノート](https://helpx.adobe.com/jp/campaign/kb/integrate-mobile-sdk.html)を更新して明確にしました。

モバイルアプリで受け取るペイロードの構造を説明するテクニカルノートを追加しました。[詳細を表示](../../administration/using/push-payload.md)

[プッシュチャネルの設定](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)の節が更新され、Adobe Mobile Services のインターフェイスでポストバックを定義する際に追加される OS バージョンの新しいペイロードデータが追加されました。

SMS ドキュメントが更新され、[SMS 自動返信](../../channels/using/managing-incoming-sms.md#managing-stop-sms)の節に説明が追加されました。

API によるワークフロー管理に関する新しい節。[詳細を表示](../../api/using/controlling-a-workflow.md)

プライマリキーと、API で Business ID をキーとして使用することについて説明する新しい節です。[詳細を表示](../../api/using/get-started-apis.md)

API の単純なフィルターと複数のフィルターに関する情報を追加しました。[詳細を表示](../../api/using/filtering.md)

## リリース 17.9 - 2017 年 9 月 {#release-17-9---september-2017}

**リリースに含まれる新機能**

E メールのライブラリテンプレート - [詳細を表示](../../designing/using/using-reusable-content.md#content-templates)

プロファイルデータによる動的レポート- [詳細を表示](../../reporting/using/about-dynamic-reports.md)

一括登録機能強化 - [詳細を表示](../../automating/using/subscription-services.md)

**リリースに伴うその他のドキュメントのアップデート**

動的レポートで使用可能なすべてのコンポーネントの詳細リストと、数式の一部の変更です。[詳細を表示](../../reporting/using/list-of-components-.md)

Adobe Analytics と共有される KPI の詳細リストです。[詳細を表示](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

新しい動的レポートのビデオです。

S3 アカウントの推奨事項を追加しました。[詳細を表示](../../administration/using/external-accounts.md#amazon-s3-account-recommendations)

様々なユーザーのタイプに関する節を更新しました。[詳細を表示](../../administration/using/users-management.md)

画像ソースのパーソナライズ機能に関する節を更新しました。[詳細を表示](../../designing/using/personalization.md#personalizing-an-image-source)

アクティブなプロファイルレポート関するドキュメントが追加されました。[詳細を表示](../../audiences/using/active-profiles.md)

[配信の警告](../../sending/using/receiving-alerts-when-failures-happen.md#delivery-alerting-reasons)に関するドキュメントが更新され、アラートの受信時に実行できる操作に関するヒントが記載されたトラブルシューティングの節が追加されました。

はじめにガイドが新しく公開されました。配信の作成とターゲティングから送信や監視に至るまで、Adobe Campaign での配信に関するベストプラクティスを説明します。[詳細を表示](https://helpx.adobe.com/jp/campaign/kb/delivery-best-practices.html)

フォローアップメッセージのドキュメントが更新され、使用例が改訂されました。[詳細を表示](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)

ACS ID に関するドキュメントが追加されました。[詳細を表示](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

新しい暗号化およびハッシュ関数とその例が追加されました。[詳細を表示](../../automating/using/list-of-functions.md)

「ファイル転送」ワークフローアクティビティの節を更新しました。[詳細を表示](../../automating/using/transfer-file.md)

「E メール配信」ワークフローアクティビティの「メッセージを送信する前に確認を要求する」オプションに関する情報が追加されました。[詳細を表示](../../automating/using/email-delivery.md)

## リリース 17.7 - 2017 年 7 月 {#release-17-7---july-2017}

**リリースに含まれる新機能**

多言語配信（E メールと SMS）- [詳細を表示](../../channels/using/creating-a-multilingual-email.md)

Adobe Campaign 通知 - [詳細を表示](../../administration/using/sending-internal-notifications.md)

配信アラート - [詳細を表示](../../sending/using/receiving-alerts-when-failures-happen.md)

データソース内の暗号化された宣言済み ID - [詳細を表示](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Campaign から Analytics への KPI 共有 - [詳細を表示](../../integrating/using/about-campaign-analytics-integration.md)

ダイレクトメールチャネル - 送信者に返信、[詳細を表示](../../channels/using/return-to-sender.md)

**リリースに伴うその他のドキュメントのアップデート**

入門ガイドと使い方に関するビデオは、専用の節にまとめられました。

E メールレンダリングのドキュメントが更新されました。[詳細を表示](../../sending/using/email-rendering.md)

レポートインジケーターの計算表が更新されました。[詳細を表示](../../reporting/using/indicator-calculation.md)

レポートドキュメントが更新され、4 つの新しい指標が追加されました。[詳細を表示](../../reporting/using/list-of-components-.md)

プロファイルの一意の ID 生成に関するドキュメントが追加されました。[詳細を表示](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

二重オプトインメカニズムがドキュメント化され、ステップバイステップの手順が紹介されています。[詳細を表示](../../channels/using/setting-up-a-double-opt-in-process.md)

「役割のリスト」の節が更新されました。[詳細を表示](../../administration/using/list-of-roles.md)

## リリース 17.5 - 2017 年 5 月 {#release-17-5---may-2017}

**リリースに含まれる新機能**

ダイレクトメール - [詳細を表示](../../channels/using/about-direct-mail.md)

E メール BCC - [詳細を表示](../../sending/using/archiving.md)

**リリースに伴うその他のドキュメントのアップデート**

「配信」ガイドの構成が変更され、名前が「チャネル」に変更されました。[詳細を表示](../../channels/using/get-started-communication-channels.md)

多くのスクリーンショットが更新され、インターフェイスの変更が反映されています。

新しいテクニカルノート「Adobe Mobile SDK とモバイルアプリの統合」が発表されました。[詳細を表示](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)

People コアサービスまたは Audience Manager と Adobe Campaign の統合を設定する手順が追加されました。[詳細を表示](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

特定の役割の機能を明確にするために、認証表が改訂されました。[詳細を表示](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

Adobe Campaign から直接利用できるコンテキストヘルプリンクが更新されました。

## リリース 17.4 - 2017 年 4 月 {#release-17-4---april-2017}

**リリースに含まれる新機能**

Creative SDK による画像編集機能の強化 - [詳細を表示](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)

トランザクションプッシュ通知 - [詳細を表示](../../channels/using/transactional-push-notifications.md)

繰り返しプッシュ通知 - [詳細を表示](../../automating/using/push-notification-delivery.md)

Amazon Simple Storage Service（S3）コネクタ - [詳細を表示](../../administration/using/external-accounts.md)

Dreamweaver との統合（実稼働） - [詳細を表示](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=ja)

**リリースに伴うその他のドキュメントのアップデート**

Adobe Campaign ユーザーの様々なタイプに関する節を追加しました。[詳細を表示](../../administration/using/users-management.md)

ワークフローガイドが再構成され、拡張されました。ワークフローの[作成](../../automating/using/building-a-workflow.md)および[実行](../../automating/using/about-workflow-execution.md)、データの[ターゲティング](../../automating/using/about-targeting-activities.md)および[管理](../../automating/using/about-targeting-activities.md#enriching-data)、データの[読み込みおよびび書き出し](../../automating/using/about-data-import-and-export.md)、ワークフローデータを使用したデータベースの更新または配信をおこなう方法を容易に確認できます。

動的レポートでレポートインジケーター計算が使用できるようになり、完全な説明や計算式を参照できます。[詳細を表示](../../reporting/using/indicator-calculation.md)

Adobe Campaign でプッシュ通知と目標地点データを使用するための Adobe Mobile Services の設定に関する新しい専用の節。[詳細を表示](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)

モバイルアプリの設定および実装の節が更新されました。プッシュ通知を設定および送信するための詳細な手順が追加されています。[詳細を表示](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)

Campaign での画像の操作方法に関する節を更新しました。[詳細を表示](../../designing/using/images.md#setting-up-image-properties)

Adobe Analytics for Mobile（目標地点）との統合が更新され、設定手順や使用例が追加されました。[詳細を表示](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

## リリース 17.2 - 2017 年 3 月 {#release-17-2---march-2017}

**リリースに含まれる新機能**

動的レポート- [詳細を表示](../../reporting/using/about-dynamic-reports.md)

Dreamweaver の統合（ラボ） - [詳細を表示](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html)

手動送信時間の最適化 - [詳細を表示](../../sending/using/optimizing-the-sending-time.md)

プッシュ通知の強化 - [詳細を表示](../../channels/using/about-push-notifications.md)

ワークフロー：新しい「シグナル」アクティビティ - [詳細を表示](../../automating/using/external-signal.md)

ワークフロー：新しい「オーディエンスの閲覧」アクティビティ - [詳細を表示](../../automating/using/read-audience.md)

目標地点データ - [詳細を表示](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

REST API でリンクされたリソース - [詳細を表示](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

**リリースに伴うその他のドキュメントのアップデート**

トリガーの統合：2 つの使用例が追加されました。[詳細を表示](../../integrating/using/abandonment-triggers-use-cases.md)

開発者 API ドキュメントのデザインを一新し、新しい情報とコードスニペットを追加してユーザーエクスペリエンスを改善しました。[詳細を表示](../../api/using/get-started-apis.md)

新しい「[オーディエンスの閲覧](../../automating/using/read-audience.md)」および「[外部シグナル](../../automating/using/external-signal.md)」ワークフローアクティビティの例を紹介します。

## リリース 17.1 - 2017 年 1 月 {#release-17-1---january-2017}

**リリースに含まれる新機能**

外部レポート用のログのエクスポート - [詳細を表示](../../automating/using/exporting-logs.md)

トランザクションメッセージング API - [詳細を表示](../../api/using/get-started-apis.md)

トランザクションメッセージ用のマーケティング機能 - [詳細を表示](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)

**リリースに伴うその他のドキュメントのアップデート**

「増分処理クエリ」ワークフローアクティビティ：新しい増分モード - [詳細を表示](../../automating/using/incremental-query.md)

「スケジューラー」ワークフローアクティビティの更新 - [詳細を表示](../../automating/using/scheduler.md)

URL の変更：Assets コアサービス - [詳細を表示](../../integrating/using/working-with-campaign-and-assets-core-service.md)

URL の変更：People コアサービス - [詳細を表示](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

プロファイルとオーディエンスに関するガイドの構成が変更されました。[詳細を表示](../../audiences/using/get-started-profiles-and-audiences.md)
