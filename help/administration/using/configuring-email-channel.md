---
title: 電子メールチャネルの構成
seo-title: 電子メールチャネルの構成
description: 電子メールチャネルの構成
seo-description: 電子メールチャネルの構成方法を説明します。
page-status-flag: 未活性化の
uuid: 9fdb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: サウビア
products: SG_CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: 設定，チャネル
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail，概要；emailConfig，メイン；ruleSet，概要；配信，プロパティ，開く
internal: 〜の
snippet: イー
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# 電子メールチャネルの構成{#configuring-email-channel}

## 電子メールチャネルパラメータ {#email-channel-parameters}

電子メール構成画面では、電子メールチャネルのパラメータを定義できます。

![](assets/channels_1.png)

* **送信済み電子メールのヘッダーパラメータ**

   このセクションでは、送信者アドレスとエ **[!UICONTROL masks]** ラーアドレスに対して承認されたを指定できます。 必要に応じて、これらのマスクはコンマで区切ることができます。 この構成はオプションです。 これらのフィールドを入力すると、メッセージの準備段階で、入力したアドレスが有効であるかどうかがAdobe Campaignで確認されます。 この動作モードでは、配信性の問題を引き起こす可能性のあるアドレスが使用されないことを保証します。 配信アドレスは、配信サーバーで構成する必要があります。

* **配信性**

   このIDはサポートによって提供されます。 配布可能性レポートが正しく動作する必要があります。

* **搬送パラメータ**

   Adobe Campaignは、開始日から開始するメッセージを送信します。 このフ **[!UICONTROL Message delivery duration]** ィールドでは、メッセージを送信する期間を指定できます。

   このフィ **[!UICONTROL Online resources validity duration]** ールドは、主にミラーページとイメージに対して、アップロードされたリソースに使用されます。 このページのリソースは、（ディスク領域を節約するために）限られた時間有効です。

* **再試行**

   一時的に配信されないメッセージは、自動再試行の対象となります。 このセクションでは、送信が開始された後の1日に実行する再試行の回数(**Number of retries**)と、再試行の間の最小遅延(**Retry period**)を示します。

   デフォルトでは、最小1時間の間隔で最初の日に5回の再試行がスケジュールされ、24時間にわたって繰り返されます。 1日に1回の再試行が、その後、およびセクションで定義されている配信期限までプログラムさ **[!UICONTROL Delivery parameters]** れます。

* **電子メール検疫パラメーター**

   フィールド **[!UICONTROL Time between two significant errors]** に値を入力し、エラーが発生した場合にエラー·カウンタを増やすまで待機する時間を定義します。 既定値：「 **1d」**、1日間

   値に達す **[!UICONTROL Maximum number of errors before quarantine]** ると、電子メールアドレスが検疫されます。 既定値： **5''**:アドレスは6番目のエラーで検疫されます。 つまり、連絡先は後続の搬送から自動的に除外されます。

**関連トピック**:

[検疫管理の理解](../../sending/using/understanding-quarantine-management.md)

## 電子メールルーティングアカウント {#email-routing-accounts}

既定で **[!UICONTROL Integrated email routing]** は、外部アカウントが提供されます。 これには、アプリケーションが電子メールを送信するための技術的なパラメータが含まれます。

![](assets/channels_2.png)

アカウントタイプは常ににに、チャネル **[!UICONTROL Routing]**&#x200B;はに、配信モードは **[!UICONTROL Email]** に設定する必要がありま **[!UICONTROL Bulk delivery]**&#x200B;す。

**関連トピック**:

[外部勘定](../../administration/using/external-accounts.md)

## 電子メール処理ルール {#email-processing-rules}

これらの規則には、リモートサーバから返される文字列のリストが含まれ、エラー(**Hard**、 **Soft** 、 **Ignored**)を修正できます。

デフォルトの規則は次のとおりです。

**メールのバウンス**

電子メールが失敗すると、リモート·メッセージ·サーバは、アプリケーション設定で指定されたアドレスにバウンス·エラー·メッセージを返します。 Adobe Campaignは、各バウンスメールの内容をルールのリスト内の文字列と比較し、3種類のエラーのいずれかを割り当てます。

ユーザは独自のルールを作成できます。

>[!CAUTION]
>
>パッケージをインポートする場合、および配信可能なワークフローのた **めに更新を使用してデータを更新する場合** 、ユーザーが作成した規則が上書きされます。

**電子メールドメインの管理**

ドメイン管理規則は、特定のドメインの送信電子メールのフローを制御するために使用されます。 バウンスメッセージをサンプリングし、必要に応じて送信をブロックします。 Adobe Campaignメッセージングサーバーは、ドメインに固有の規則を適用し、規則のリストにアスタリスクが表示される一般的な大文字と小文字の規則を適用します。 HotmailドメインとMSNドメインのルールは、Adobe Campaignで既定で使用できます。

ドメイン管理規則を構成するには、しきい値を設定し、特定のSMTPパラメータを選択します。 しきい値 **は** 、特定のドメインに向かうすべてのメッセージがブロックされるエラー率として計算される制限です。

たとえば、一般的には、最低300件のメッセージの場合、エラー率が90%に達すると、3時間の電子メールの送信がブロックされます。

SMTPパラメ **ータは** 、ブロック規則に適用されるフィルタとして機能します。

* 特定の識別標準と暗号化キーをアクティブ化して、 **Sender ID**、 **DomainKeys**、 **DKIM**、 **** S/MIMEなどのドメイン名を確認するかどうかを選択できます。
* **SMTPリレー**:では、特定のドメインのIPアドレスと中継サーバのポートを構成できます。

**MX管理**

各規則は、MXのアドレスマスクを定義します。 したがって、このマスクと名前が一致するMXはすべて有効です。 マスクには、「*」と「?」を含めることができます。 汎用文字。

たとえば、次のアドレスを指定します。

* a.mx.yahoo.com
* b.mx.yahoo.com
* c.mx.yahoo.com

は、次のマスクと互換性があります。

* *.yahoo.com
* ?.mx.yahoo.com

次の規則が順に適用されます。mxマスクがターゲットのMXと互換性がある最初の規則が適用されます。

各規則に対して次のパラメータを使用できます。

* **[!UICONTROL Range of IDs]**:このオプションを使用すると、規則が適用される識別子(publicId)の範囲を指定できます。 次の項目を指定できます。

   * 番号：この規則は、このpublicIdにのみ適用されます。
   * 数値の範囲（数値1 ~数値2）:この規則は、この2つの数値の間のすべてのpublicIdに適用されます。
   フィールドが空の場合は、すべてのIDにルールが適用されます。

* **[!UICONTROL Shared]**:このオプションは、この規則にリンクされているすべてのMXに1時間あたりのメッセージ数と接続数が最も多いことを示します。
* **[!UICONTROL Maximum number of connections]**:指定されたアドレスからMXへの同時接続の最大数。
* **メッセージの最大数**:1つの接続で送信できるメッセージの最大数。 この量が過ぎると、接続が閉じ、新しい接続が再び開かれます。
* **[!UICONTROL Messages per hour]**:指定されたアドレスを介してMXに対して1時間で送信できるメッセージの最大数。

>[!CAUTION]
>
>* パラメータが変更された場合は、配信サーバ(MTA)を再起動する必要があります。
>* 管理ルールの変更または作成は、エキスパート·ユーザーのみに適用されます。
>



## 電子メールのプロパティの一覧 {#list-of-email-properties}

このセクションでは、電子メールまたは電子メールテンプレートのプロパティ画面で使用可能なパラメータのリストにつ [いて説明します](../../start/using/about-templates.md)。

>[!NOTE]
>
>一部のパラメータは、テンプレートでのみ使用できます。 アクセスできるパラメ [ータは、権限によって異なります](../../administration/using/users-management.md)。

電子メールまたは電子メールテンプレートのプロパティを編集するには、ボタンを使用 **[!UICONTROL Edit properties]** します。

![](assets/delivery_options_1.png)

### 一般パラメータ {#general-parameters}

電子メールパラメータ画面の上部で、とフィールドを使用して電子メールを **[!UICONTROL Label]** 識別 **[!UICONTROL ID]** します。 この情報はインターフェイスに表示されますが、メッセージの受信者には表示されません。

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>IDは一意である必要があります。

このフ **[!UICONTROL Brand]** ィールドでは、配信にリンクされたブランドを選択できます。 ブランドの使用と構成の詳細については、「ブランド化」の項を参照 [してく](../../administration/using/branding.md) ださい。

このフ **[!UICONTROL Campaign]** ィールドでは、電子メールにリンクされたキャンペーンを入力できます。

対応するフィールドにを追 **[!UICONTROL Description]** 加し、リスト内の電子メールサムネイルに表示されるイメージを編集することもできます。

### パラメータの送信 {#sending-parameters}

このセクシ **[!UICONTROL Send]** ョンは、電子メールテンプレートに対してのみ使用できます。 次のパラメータが含まれます。

#### 再試行パラメータ {#retries-parameters}

一時的に配信されないメッセージは、自動再試行の対象となります。 このセクションでは、送信が開始された後の日に実行する再試行の回数( **[!UICONTROL Max. number of retries]** )と、再試行の間の最小遅延( **[!UICONTROL Retry period]** )を示します。

デフォルトでは、最小1時間の間隔で最初の日に5回の再試行がスケジュールされ、24時間にわたって繰り返されます。 1日に1回の再試行が、その後、および「有効期間パラメータ」セクションで定義されている配信期限までプ [ログラムされます](../../administration/using/configuring-email-channel.md#validity-period-parameters) 。

再試行回数は、グローバルに変更できます（Adobeのテクニカル管理者に問い合わせてください）。また、配信または配信テンプレートごとに変更できます

#### 電子メール形式パラメータ {#email-format-parameters}

送信する電子メールの形式を構成できます。 次の3つのオプションを使用できます。

* **受信者の環境設定** （既定のモード）を使用する：メッセージの形式は、受信者プロファイルに格納されたデータに基づいて定義され、既定では **Email formatフィールド** (@emailFormat)に格納されます。 受信者が特定の形式でメッセージを受信したい場合は、この形式が送信されます。 フィールドが完了していない場合は、マルチパート代替メッセージが送信されます（以下を参照）。
* **受信者のメールクライアントに最も適切な形式を選択させる（マルチパート代替）**:メッセージには、次の両方の形式が含まれます。テキストとHTML 受信時に表示される形式は、受信者のメールソフトウェアの構成（複数部の代替）によって異なります。

   >[!CAUTION]
   >
   >このオプションには、メッセージの両方のバージョンが含まれます。 したがって、メッセージ·サイズが大きいため、配信スループットに影響を与えます。

* **すべてのメッセージをテキスト形式で送信する**:メッセージはテキスト形式で送信されます。 HTML形式は送信されませんが、ミラーページに対して使用されるのは、受信者がメッセージ内のリンクをクリックしたときだけです。

#### SMTPテスト·モード {#smtp-test-mode}

このオプ **[!UICONTROL Enable SMTP test mode]** ションを使用すると、実際にメッセージを送信せずに、SMTP接続を介して電子メールを送信するテストを行うことができます。
メッセージは、SMTPサーバとの接続が確立されるまで処理されますが、送信されません。

![](assets/smtp-test-mode.png)

このオプションは、電子メールおよび電子メールテンプレートで使用できます。

電子メールテンプレートのSMTPテストモードオプションを有効にした場合、このテンプレートから作成されたすべての電子メールメッセージは、このオプションを有効にします。

>[!CAUTION]
>
>このオプションを電子メールに対して有効にすると、オフになるまでメッセージは送信されません。
>電子メールまたは電子メールテンプレートのダッシュボードに警告が表示されます。

SMTPの構成の詳細については、「電子メールSMTPパラメータのリ [スト」の項を参照してください](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters) 。

### 有効期間パラメータ {#validity-period-parameters}

このセクシ **[!UICONTROL Validity]** ョンには、次のパラメータが含まれます。

* **[!UICONTROL Explicitly set validity dates]**:このチェックボックスがオフの場合は、とフィールドに期間を入力する必要 **[!UICONTROL Delivery duration]** があ **[!UICONTROL Resource validity limit]** ります。 特定の日時を定義する場合は、このボックスをオンにします。
* **[!UICONTROL Delivery duration]**:Adobe Campaignは、開始日から開始するメッセージを送信します。 このフィールドでは、メッセージを送信する期間を指定できます。
* **[!UICONTROL Resource validity duration]**:このフィールドは、主にミラーページとイメージに対して、アップロードされたリソースに使用されます。 このページのリソースは、（ディスク領域を節約するために）限られた時間有効です。
* **[!UICONTROL Mirror page management]**:ミラーページは、Webブラウザを介してオンラインでアクセス可能なHTMLページである。 内容は電子メールの内容と同じです。 既定では、リンクがメールコンテンツに挿入された場合、ミラーページが生成されます。 このフィールドを使用すると、このページの生成方法を変更できます。

   >[!CAUTION]
   >
   >ミラー·ページを作成する電子メールには、HTMLコンテンツが定義されている必要があります。

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** （デフォルトモード）:メールコンテンツにリンクが挿入されると、ミラーページが生成されます。
   * **ミラーページの生成を強制する**:ミラーページへのリンクがメッセージに挿入されていない場合でも、ミラーページが作成されます。
   * **ミラーページを生成しない**:メッセージ内にリンクが存在しても、ミラーページは生成されません。
   * **メッセージIDのみを使用してアクセス可能なミラーページを生成します**。このオプションを使用すると、配信ログウィンドウで、個人用設定情報を含むミラーページのコンテンツにアクセスできます。

>[!NOTE]
>
>とのパラ **[!UICONTROL Explicitly set validity dates]** メー **[!UICONTROL Delivery duration]** タは、トランザクションメッセージには適用されません。 トランザクションメッセージングの詳細については、このセクショ [ンを参照してくださ](../../channels/using/about-transactional-messaging.md)い。

### 追跡パラメータ {#tracking-parameters}

このセクシ **[!UICONTROL Tracking]** ョンには、次のパラメータが含まれます。

* **[!UICONTROL Activate tracking]**:メッセージのURL追跡を有効/無効にできます。 各メッセージURLの追跡を管理するには、電子メール·デザイナのア **[!UICONTROL Links]** クション·バーのアイコンを使用します。 追跡URLにつ [いてを参照してください](../../designing/using/links.md#about-tracked-urls)。
* **[!UICONTROL Tracking validity limit]**:URL上で追跡を有効にする期間を定義できます。
* **[!UICONTROL Substitution URL for expired URLs]**:追跡の有効期限が切れた後に表示されるWebページのURLを入力できます。

### 詳細パラメータ {#advanced-parameters}

セクションに **[!UICONTROL Advanced parameters]** は複数のパラメータが含まれます。

最初の2つのフィールドには、電子メールメッセージのヘッダー（返信アドレスと返信アドレスのテキスト）を入力するために必要な情報を入力できます。 この情報は個別化できます。 これを行うには、変更するフィールドの右側にあるボタンをクリックし、個人用設定フィールドを追加します。 個人用設定フィールドの挿入と使用の詳細については、「個人用設定フ [ィールドの挿入](../../designing/using/personalization.md#inserting-a-personalization-field) 」の項を参照してください。

#### ターゲットコンテキスト {#target-context}

ターゲットコンテキストを使用すると、電子メールのターゲット（対象ユーザー定義画面）と個人用設定（HTMLコンテンツエディタで個人用設定フィールドを定義）に使用する一連のテーブルを定義できます。

#### ルーティング {#routing}

このフィールドは、使用されるルーティングモードを示します。 外部アカウントを参照します。 たとえば、特定のブランド構成を含む外部アカウントを使用する場合に使用できます。

>[!NOTE]
>
>外部アカウントは、「管理」&gt;「アプリケーション設定」&gt;「外部アカウント」 **(** Administration **)メニューからアク** セスできます **** 。

#### 準備 {#preparation}

メッセージの準備の詳細は、「メッセージの承認」セ [クション](../../sending/using/preparing-the-send.md) を参照してください。

* **[!UICONTROL Typology]**:送信する前に、内容と構成を検証するためにメッセージを準備する必要があります。 準備段階で適用される検証規則は類型で定義さ **れる**。 たとえば、電子メールの場合、件名、URL、画像などを確認する準備が必要です。 このフィールドで適用する類型を選択します。

   >[!NOTE]
   >
   >&gt; &gt; &gt;メニューからアクセスできる **[!UICONTROL Administration]** 類型は、 **[!UICONTROL Channels]****[!UICONTROL Typologies]** 「類型」セクションに表示さ [れます](../../administration/using/about-typology-rules.md) 。

* **[!UICONTROL Compute the label during delivery preparation]**:個人用設定フィールド、コンテンツブロック、および動的テキストを使用して、メッセージ準備フェーズ中の電子メールのラベル値を計算できます。

   また、ワークフローの外部シグナルアクティビティに宣言されたイベント変数を使用して、配信ラベルをパーソナライズすることもできます。 For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**:このオプションを使用すると、準備フェーズ中にSQLクエリログをジャーナルに追加できます。

### 電子メールSMTPパラメータの一覧 {#list-of-email-smtp-parameters}

このセクシ **[!UICONTROL SMTP]** ョンには、次のパラメータが含まれます。

* **[!UICONTROL Character encoding]**:メッセージエ **[!UICONTROL Force encoding]** ンコードを強制する場合は、ボックスをオンにし、使用するエンコードを選択します。
* **[!UICONTROL Bounce mails]**:デフォルトでは、バウンスメールはプラットフォームのエラー受信トレイ(&gt; &gt; **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]****[!UICONTROL Configuration]** screenで定義)で受信されます。 電子メールの特定のエラー·アドレスを定義するには、フィールドにアドレスを入力 **[!UICONTROL Error address]** します。
* **[!UICONTROL Additional SMTP headers]**:このオプションを使用すると、メッセージに追加のSMTPヘッダを追加できます。 フィールドに入力するス **[!UICONTROL Headers]** クリプトは、1行に1つのヘッダーを **name:valueの形式で参照する必要があります**。 必要に応じて、値は自動的にエンコードされます。

   >[!CAUTION]
   >
   >追加のSMTPヘッダーを挿入するスクリプトの追加は、上級ユーザー用に予約されています。 このスクリプトの構文は、次のコンテンツタイプの要件に従う必要があります。未使用のスペースがない、空の行がないなど

### アクセス許可パラメータの一覧 {#list-of-access-authorization-parameters}

このセクシ **[!UICONTROL Access authorization]** ョンには、次のパラメータが含まれます。

* このフ **[!UICONTROL Organizational unit]** ィールドを使用すると、特定のユーザーに対してこの電子メールへのアクセスを制限できます。 指定したユニットまたは親ユニットに関連付けられたユーザーは、この電子メールに対する読み取りおよび書き込みアクセス権を持ちます。 子ユニットに関連付けられたユーザーは、この電子メールに対する読み取りアクセス権のみを持ちます。

   >[!NOTE]
   >
   >組織単位は、[管理] &gt; [ユーザーとセキュリティ] **メニューか** ら構成できます **** 。

* 、、およ **[!UICONTROL Created by]**&#x200B;びフィ **[!UICONTROL Created]**&#x200B;ールドは自 **[!UICONTROL Modified by]** 動的に **[!UICONTROL Last modified]** 入力されます。

## メールのアーカイブ {#archiving-emails}

Adobe Campaignを設定して、プラットフォームから送信された電子メールのコピーを保持できます。

ただし、Adobe Campaign自体はアーカイブされたファイルを管理しません。 これにより、選択したメッセージを専用のアドレスに送信し、外部システムを使用して処理およびアーカイブを行うことができます。

配信テンプレートでアクティブにすると、この機能を使用して、指定する必要のあるBCC電子メールアドレス（配信先には表示されない）に、対応する送信済みメッセージの正確なコピーを送信できます。

### 推奨事項と制限事項 {#recommendations-and-limitations}

* この機能はオプションです。 ライセンス契約を確認し、アカウントエグゼクティブに連絡してライセンス認証を行ってください。
* BCC電子メールアドレスは1つのみ使用できます。
* 正常に送信されたEメールのみが考慮されます。 バウンスはありません。
* プライバシー上の理由から、BCC eメールは、PII(Securely Perordial Identability Information)を保存できるアーカイブ·システムで処理する必要があります。
* 新しい配信テンプレートを作成する場合、オプションが購入されていても、既定では[E-メールBCC]は有効になりません。 使用する各配送テンプレートで、手動で有効にする必要があります。

### Eメールのアーカイブの有効化 {#activating-email-archiving}

電子メールテンプレートでは、次の専用オ [プションを使用し](../../start/using/about-templates.md)てEメールBCCがアクティブ化されます。

1. 「生産資源」&gt;「テンプレ **ート」** &gt;「配信テンプレ **ート」に移動します******。
1. 標準テンプレートを複製し **[!UICONTROL Send via email]** ます。
1. 複製したテンプレートを選択します。
1. ボタンをク **[!UICONTROL Edit properties]** リックして、テンプレートのプロパティを編集します。
1. 断面を展開 **[!UICONTROL Send]** します。
1. このテンプレート **[!UICONTROL Archive emails]** に基づいて、各配信に対して送信されたすべてのメッセージのコピーを保持する場合は、このボックスをオンにします。

   ![](assets/email_archiving.png)

>[!NOTE]
>
>BCCアドレスに送信された電子メールが開かれ、をクリックした場合、送信分析では、と送信分析では、これが考慮され、誤算が発生する可 **[!UICONTROL Total opens]** 能性 **[!UICONTROL Clicks]** があります。

