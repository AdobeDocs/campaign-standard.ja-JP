---
title: 疲労ルール
seo-title: 疲労ルール
description: 疲労ルール
seo-description: 疲労ルールを作成してプロファイルとの通信を管理します。
page-status-flag: 常にアクティブ化されていない
uuid: fa5e3sed-36c2-4f16- b97a-119b85adf679
contentOwner: サウビート
products: SG_ CAMPAIGN/STANDARD
audience: 管理
content-type: 参照
topic-tags: working- with- typography- rules
discoiquuid: 4337a80b-0fb9-4a37- bce3- fe2121a66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Fatigue rules{#fatigue-rules}

## About fatigue rules {#about-fatigue-rules}

疲労ルールを使用すると、マーケティング担当者はグローバルなクロスチャネルビジネスルールを設定して、キャンペーンからのプロシークプロファイルを自動的に除外することができます。

疲労ルールを実装するには、プロファイルごとのメッセージの最大数を定義し、ルールを適用する期間を選択します。配信準備中は、既に送信されているメッセージの数に応じて、配信からプロファイルが除外されます。

>[!NOTE]
>
>疲労ルールを適用するには、配信の連絡先日付を定義する必要があります。メッセージをすぐに送信するように選択した場合、疲労ルールは適用されません。

関連トピック:

* [準備](../../administration/using/configuring-email-channel.md#preparation)
* [誤字の管理](../../administration/using/about-typology-rules.md#managing-typologies)
* [タイポロジルール](../../administration/using/about-typology-rules.md#typology-rules)

## Creating a fatigue rule {#creating-a-fatigue-rule}

**[!UICONTROL Fatigue]** タイポロジルールを作成および設定するには、次の手順を適用します。

1. Click the Adobe Campaign logo, in the top left corner of the interface, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. From the list of typology rules, click **[!UICONTROL Create]**.

   ![](assets/fatigue.png)

1. **[!UICONTROL Rule type]** フィールドで、を選択 **[!UICONTROL Fatigue]**&#x200B;します。

   ![](assets/fatigue3.png)

1. **[!UICONTROL Channel]** フィールドで、ルールが適用するチャネルを選択します。You can either select a single channel (email, SMS, direct mail, mobile application) or select **[!UICONTROL All channels]**. See [Choosing the channel](../../administration/using/fatigue-rules.md#choosing-the-channel).

   ![](assets/fatigue5.png)

1. **[!UICONTROL General]** タブで、プロファイルごとのメッセージの最大数を計算する方法を定義します。定数しきい値または変数を選択できます。プロファイルおよび配信のしきい値を調整することもできます。For more on this, refer to [Defining the threshold](../../administration/using/fatigue-rules.md#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Choose a **[!UICONTROL Sliding period]** on which the typology rule will apply. For more on this, refer to [Setting the sliding period](../../administration/using/fatigue-rules.md#setting-the-sliding-period).

   ![](assets/fatigue6.png)

   この例では（以前のスクリーンショットを参照）、スライド期間15日間の最大4つのメッセージを送信するように選択しています。

1. **[!UICONTROL Application criteria]** タブでは、このルールをすべての配信に適用したり、送信するメッセージに従ってルールの適用性を制限したりできます。ルールは、アプリケーション条件が満たされた場合にのみ実行されます。例えば、特定の単語から始まるラベルまたは特定のレターを含むIDでのみルールを適用できます。See [Restricting the applicability of a filtering rule](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule).

   ![](assets/fatigue20.png)

1. **[!UICONTROL Typologies]** タブを選択し、配信に使用するタイポロジルールにリンクします。See [Managing typologies](../../administration/using/about-typology-rules.md#managing-typologies) and [Typology rules](../../administration/using/about-typology-rules.md#typology-rules).

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >タイポロジは、このテンプレートを使用して作成されたすべての配信に自動的に適用されるように、配信テンプレートで定義できます。

配信の準備中、配信済みの配信の数に応じて、配信からプロファイルが除外されます。配信ログで疲労ルールの実行結果を表示できます。See [Viewing the fatigue results](../../administration/using/fatigue-rules.md#viewing-the-fatigue-results).

![](assets/fatigue16.png)

>[!CAUTION]
>
>疲労ルールが機能するには、配信の連絡先日付を定義する必要があります。メッセージをすぐに送信するように選択した場合、疲労ルールは適用されません。

## Choosing the channel {#choosing-the-channel}

様々なチャネルで疲労ルールを使用できます。The channel is defined in the **[!UICONTROL Channel]** field of the typology rule settings. You can either select a single channel or select **[!UICONTROL All channels]**.

![](assets/fatigue5.png)

**使用可能なチャネル**

以下のチャネルを使用できます。

* 電子メール
* モバイル（SMS）
* ダイレクトメール
* モバイルアプリケーション:このチャネルを使用すると、プロファイルまたはアプリの購読者にプッシュ通知を送信できます。プロファイルに通知を送信する場合、それらはマルチチャネルの疲労ルールと互換性があります。

   >[!CAUTION]
   >
   >疲労ルールは、アプリの購読者に送信されるプッシュ通知と互換性がありません。アプリの購読者にメッセージを送信している場合、疲労ルールは適用されません。

* すべてのチャネル:このオプションを使用すると、ルールをすべてのチャネルに適用できます。例えば、チャネルごとに最大3つのメッセージを毎月送信するように指定できます。1週間に2通の電子メールをプロファイルに送信し、プッシュ通知を送信しようとすると、同じプロファイルが除外されます。

**配信タイプ**

疲労ルールは、すべての配信タイプと互換性があります。1件のショット配信、定期配信、ワークフロー配信およびトランザクションメッセージ。

**トランザクションメッセージ** は、リマーケティングメッセージなど、マーケティングメッセージ（RTV）とマーケティングメッセージ（ターゲットプロファイル）をターゲット化するために使用できます。疲労ルールはマーケティングメッセージにのみ互換性があります（ターゲットプロファイル）。イベントトランザクションメッセージにはプロファイル情報は含まれません。したがって、プロファイルを使用した拡張の場合でも、疲労ルールと互換性がありません。With the support of marketing messages in transactional messaging, you can **apply a fatigue rule to all channels including marketing transactional messages**.

## Defining the threshold {#defining-the-threshold}

各疲労ルールは、特定の期間に1つのプロファイルに送信できるメッセージの最大数を表すしきい値を定義します。このしきい値に到達すると、考慮された期間の終わりまで、配信を増やすことができません。このプロセスにより、メッセージがセットしきい値を超えた場合に、それを防ぐために、自動的に配信からプロファイルを除外することができます。

しきい値には、定数または変数を指定できます。つまり、特定の期間において、しきい値はプロファイル間で異なるか、同じプロファイルに対しても異なることがあります。

**修正しきい値の使用**

しきい値は、関連期間中にプロファイルに送信できるメッセージの最大数を表します。

デフォルトでは、しきい値は一定であり、ルールによって許可されるメッセージの最大数を示す必要があります。

![](assets/fatigue2.png)

**変数のしきい値の使用**

To define a variable threshold, select the **[!UICONTROL Depends on the recipient]** value in the **[!UICONTROL Threshold type]** field.

![](assets/fatigue15.png)

次に2つのオプションがあります。

* プロファイルフィールドを選択します。しきい値は、選択したフィールドに従って各プロファイルによって異なります。For example, if you have extended the profiles resource with a 'Communication frequency' field, click the button on the right of the **[!UICONTROL Threshold computation formula]** field and select your field. 各プロファイルについて、しきい値が「通信頻度」フィールドの値になります。

   ![](assets/fatigue21.png)

* define a formula: click the second button on the right of the **[!UICONTROL Threshold computation formula]** field to define an advanced threshold calculation formula. 例えば、プロファイルが属しているセグメントに応じて、認証されたメッセージの数をインデックス化できます。つまり、"Web"セグメントに属するプロファイルは、他のプロファイルよりも多くのメッセージを受け取ることがあります。**[!UICONTROL Iif (@origin='Web', 5, 3)]** タイプ数式では、Webセグメントのプロファイルに5つのメッセージを配信し、他のセグメントに対して3つのメッセージを配信します。

   ![](assets/fatigue14.png)

**プロファイルと配信におけるしきい値の調整**

デフォルトでは、すべてのメッセージがしきい値の計算に考慮されます。Check the **[!UICONTROL Refine Threshold on profiles and deliveries]** box to filter the profiles and deliveries to count when preparing the delivery.

In the following example, only male profiles are counted and only deliveries with a label starting with **Newsletters** are counted.

![](assets/fatigue13.png)

Refining the threshold on deliveries is different than restricting the applicability of the entire rule ( **[!UICONTROL Application criteria]** tab):

* **[!UICONTROL Application criteria]**:を選択します。例えば、アプリケーション条件が「ニュースレターで始まる」の場合、ルールはこの条件を適用する配信にのみ適用されます。配信のラベルが「プロモーション」で始まる場合、ルールはまったく実行されません。
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**:このタイポロジルールを使用して配信するすべての配信は、ルールを実行しますが、過去の配信とスケジュールされた配信をカウントします。例えば、制限が「ニュースレターで始まる」の場合、配信ラベルが「プロモーション」で始まる場合でも、ルールは実行されます。選択したスライド期間に対して、ラベルが「ニュースレター」で始まる配信の数が表示されます。

## Setting the sliding period {#setting-the-sliding-period}

疲労ルールは、周期的な周期で定義されます。The period is configured in the **[!UICONTROL Sliding period]** section, for example 2 weeks, 7 days or 5 hours.

![](assets/fatigue6.png)

ルールが実行されると、過去の配信とスケジュール済み配信の両方が考慮されます。これにより、所定のスライド期間でのしきい値を超えないようにすることが保証されます。

For example, if you define a 48-hour period, the system will be looking 48 hours **before the contact date ** and 48 hours **after the contact date**. したがって、将来の配信と以前の配信の統合を有効にするために、選択した期間が2倍になります。

To restrict the deliveries taken into account to a 2-week period, enter **Day** and **7** or 1 week in the **Sliding period** section. 配信日の7日前に送信され、ルールが適用された配信日から最長7日経過した配信は、計算で考慮されます。

## Viewing the fatigue results {#viewing-the-fatigue-results}

配信の準備中、配信済みの配信の数に応じて、配信からプロファイルが除外されます。To view fatigue rule execution results, click the button in the bottom right corner of the **[!UICONTROL Deployment]** block.

![](assets/fatigue22.png)

3つのタブを使用して、適用したルールの名前を含む疲労実行結果の詳細を表示できます。

* 配信ログ:

   ![](assets/fatigue17.png)

* 除外ログ:

   ![](assets/fatigue18.png)

* 除外の原因:

   ![](assets/fatigue19.png)

## Viewing the fatigue rule summary report {#viewing-the-fatigue-rule-summary-report}

Adobe Campaignでは、疲労ルールに関する専用レポートを使用して、キャンペーンにどのように適用されるかを把握できます。これにより、キャンペーンが相互に影響を与え、適切な調整を行うことができます。

The **[!UICONTROL Fatigue rules summary]** report can be accessed from the **[!UICONTROL Reports]** button, in the top right corner of each program, campaign, and message.

![](assets/fatigue27.png)

画面の左側にある[配信日]のレポートデータをフィルタできます。デフォルトでは、選択した期間が現在の日付より15日前に開始され、15日後に終了します。特定の疲労ルールでもフィルタリングできます。

円グラフには、選択した期間に関する次の情報が表示されます。

* **[!UICONTROL Total targeted]**:メッセージの準備前の合計ターゲット
* **[!UICONTROL Excluded]**:疲労ルールアプリケーションによる除外の合計数
* **[!UICONTROL Other exclusions]**:他のタイポロジルールによる除外の総数
* **[!UICONTROL To deliver]**:メッセージの準備後に配信するメッセージの合計数（ **[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** - **[!UICONTROL Other exclusions]** ）

グラフの右側には、疲労ルールによる除外の数が表示されます。

下の表には、選択した期間内のすべての配信が表示されます。配信ごとに、適用される疲労ルールと、対応する除外を確認できます。連絡先日付を持たない配信もテーブルに表示されます。

* **[!UICONTROL 0]** は、疲労ルールが適用されたが、除外がなかったことを意味します。
* **[!UICONTROL -N]** は、N除外が発生したことを意味します。
* 空のフィールドは、疲労ルールが適用されなかったことを意味します。

>[!NOTE]
>
>表示されるデータは、レポートにアクセスするプログラム、メッセージ、キャンペーンのコンテキストには依存しません。このレポートには、すべての組織単位のすべての疲労ルールと配信が表示されます。これにより、キャンペーンが他のユーザーによってどのように影響を受けるかを把握するために、すべての配信のグローバルビューを取得できます。

## Examples {#examples}

疲労管理の導入には多くの可能性があります。次に、実行できる操作の例を示します。

* Create a fatigue rule using a **constant threshold** that applies to **all channels**:

   例えば、スライディング期間7日間の一定のしきい値を持つマルチチャネルルールを作成します。

   先週、プレミアムプロファイルにプロモーション用の電子メールとトランザクションリマーケティングの電子メールが届きました。また、次の週に送信されるSMSもスケジュールされています。今日は、すべてのプロファイルのプッシュ通知を送信することを決定します。2週間の期間にわたるメッセージの最大数に達したので、プレミアムプロファイルは今日のプッシュから除外されます。

   ![](assets/fatigue23.png)

* Create a fatigue rule using a **variable threshold** based on a **profile field**:

   「通信制限」フィールドのプロファイルリソースを拡張して、プロファイルごとに異なるしきい値を定義しています。疲労ルールで、このフィールドに基づいて変数のしきい値を定義し、2日間のスライディング期間を選択します。次の2つのプロファイルの例を見てみましょう。Johnの通信制限は1で、Davidはしきい値2です。どちらの場合も、昨日ニュースレター電子メールを受信しています。今すぐ電子メールを送信します。ターゲットから除外されたので、Davidのみが受信します。

   ![](assets/fatigue24.png)

* **しきい値計算数式を使用して、疲労ルールを作成**&#x200B;します。

   プロファイルの年齢に応じてしきい値を変更したい。プロファイルが40未満の場合、上限4と古いプロファイルの制限を2に制限します。このしきい値を拡張フィールドと共に各プロファイルに定義する代わりに、疲労ルールに直接数式を作成して、プロファイルの年齢に従ってしきい値を計算できます。In our example, the formula would be **[!UICONTROL Iif (@age<40, 4, 2)]**.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >この節では、しきい値計算数式を使用した疲労ルールの例を示します。

* Create a fatigue rule that **refines the threshold** on profiles and deliveries:

   「スコア」フィールドのプロファイルリソースが拡張され、「タイプ」フィールドの配信リソースも拡張されました。3の定数しきい値を定義したいが、「アラート」または「ブラックフライデー」というタイプのすべての配信と、10を超えるスコアのあるすべてのプロファイルから除外したい場合。ルールが実行されると、過去およびスケジュール済み配信の間に、過去の配信とスケジュールされた配信の間で、スコアが10未満のプロファイルに送信されるすべての配信が、「アラート」または「ブラックフライデー」に送信されます。

   ![](assets/fatigue26.png)

しきい値計算数式を使用して、疲労ルールの例を以下に示します。

この使用事例では、毎週2つ以上のメッセージをプレミアムプロファイルに配信し、週ごとに2メッセージを標準プロファイルに配信するためのタイポロジルールを作成します。

To identify customers and prospects, we extended the profiles resource with the **[!UICONTROL Status]** field, which contains 0 for premium profiles and 1 for standard profiles.

ルールを作成するには、次の手順を適用します。

1. **新しい疲労** タイプのタイポロジルールを作成します。
1. **[!UICONTROL Threshold]** このセクションでは、各プロファイルに応じてしきい値を計算する数式を作成します。Select the **[!UICONTROL Depends on the recipient]** value in the **[!UICONTROL Threshold type]** field, then click the icon the second button on the right of the **[!UICONTROL Threshold computation formula]** field.

   ![](assets/fatigue7.png)

1. **[!UICONTROL List of functions]** セクションで、ノードの **Iif** 関数をダブルクリック **[!UICONTROL Others]** します。

   ![](assets/fatigue8.png)

1. Then select the profile's **Status** in the **[!UICONTROL Available fields]** section.

   ![](assets/fatigue9.png)

1. Enter the desired values to create the following formula: **Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   この数式では、ステータスが0の場合は2、他のすべてのステータスについては4を割り当てることができます。

1. Click **[!UICONTROL Confirm]** to approve the formula.
1. Indicate the **[!UICONTROL Sliding period]** on which the rule will apply: 7 days in this case, to restrict the deliveries taken into account to a 2-week period.

   ![](assets/fatigue11.png)

1. これで、配信に適用するために作成したルールを、タイポロジにリンクします。To do this, select the **[!UICONTROL Typologies]** tab, click **[!UICONTROL Create element]** and select the typology used for your deliveries.

   ![](assets/fatigue12.png)

1. 作成するルールを保存します。

ルールは、タイポロジに基づいてすべての配信に適用されます。
