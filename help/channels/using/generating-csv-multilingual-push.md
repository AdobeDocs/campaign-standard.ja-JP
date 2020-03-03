---
title: Campaign Standardを使用した多言語プッシュ通知用のCSVファイルの生成
description: CSVファイルをアップロードして配信用のコンテンツを生成する機能は、多言語プッシュ通知をサポートするために使用されます。
page-status-flag: never-activated
uuid: e90f4ec8-14e3-4304-b5fc-bce0ba08a4ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: 79231445-1d51-499a-adcf-0c0f6db1cfa3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c6df07dd78de6b15971937d574429d3ba5dc1a15

---


# 多言語プッシュ通知用のCSVファイルの生成{#generating-csv-multilingual-push}

CSVファイルをアップロードして配信用のコンテンツを生成する機能は、多言語のプッシュ通知をサポートするために使用されます。 ファイルのアップロードを成功させ、その結果配信を作成できるようにするには、CSVファイルの形式が特定のガイドラインに従っている必要があります。 以下の節では、ファイル形式とその考慮事項について説明します。

## ファイルのフォーマット {#file-format}

多言語プッシュには、CSVファイルに14列が必要です。

* タイトル
* messageBody
* 音
* バッジ
* deeplinkURI
* category
* iosMediaAttachmentURL
* androidMediaAttachmentURL
* isContentAvailable
* isMutableContent
* customFields
* locale
* language
* silentPush

![](assets/multilingual_push_1.png)

ウィンドウのをクリックして、CSVサンプル **[!UICONTROL Download a sample file]** を確認し **[!UICONTROL Manage Content Variants]** ます。 For more on this, refer to the this [section](../../channels/using/creating-a-multilingual-push-notification.md).

* **title, messageBody, sound, badge, deeplinkURI, category, iosMediaAttachmentURL, androidMediaAttachmentURL**:通常のプッシュペイロードのコンテンツ。 この情報は、プッシュ配信を作成する場合と同じ方法で提供する必要があります。
* **Custom Fields**: カスタムフィールドにJSON形式を使用します（例：&quot;{&quot;&quot;key1&quot;:&quot;&quot;value1&quot;&quot;,&quot;&quot;key2&quot;&quot;:&quot;&quot;value2&quot;&quot;}&quot;）。 カスタムフィールドの例については、上記のサンプルファイルを参照してください。
* **isContentAvailable**:「使用可能なコンテンツ」チェックのフラグ、値1はtrue、値0はfalseを示します。 デフォルト値は0です。 この列を空白にすると、値は0と見なされます。
* **isMutableContent**:可変コンテンツのフラグ、値1はtrue、値0はfalseを示します。 デフォルト値は0です。 この列を空白にすると、値は0と見なされます。
* **locale**:localeは言語バリアントのフィールドです。例えば、US-Englishの場合は「en_us」、フランス — フランス語の場合は「fr_fr」。
* **language**:ロケールに関連付けられている言語の名前。 例えば、ロケールが「en_us」の場合、言語の名前は「English-United States」にする必要があります。
* **silentPush**:プッシュ通知タイプのフラグ。 通常のプッシュ通知の場合、値は0にする必要があります。 サイレントプッシュの場合、値は1にする必要があります。 デフォルト値は0です。 この列を空白にすると、値は0と見なされます。

## CSVファイル作成の制約とガイドライン {#constraints-guideline-csv}

**各列の名前は固定されます**。
CSVファイルに各列の名前を含める必要があります。コンテンツに列を使用しない場合は、空白のままにします。

**「locale」列と「language」列は必須で、値は各行で一意です。**
この列に空白の値を指定すると、ファイルのアップロードに失敗します。

**列の順序は重要です**。 アップロードされたファイルの列の順序は、サンプルファイルと同じ形式に従う必要があります。

**列の内容を引用**。 これはCSV（コンマ区切り値）ファイルなので、コンマ(,)を含む列のコンテンツはすべて引用符で囲む必要があります。 例えば、「Hello, Tom!」と入力します。

**国際文字にはUTF-8エンコードが必要です。**

**プレーンテキストでファイルを生成する場合は、各列を「,」で区切ります。**

**バリアントの不一致** 特定の言語のコンテンツブロックとターゲットオーディエンスを使用する場合は、CSVファイルにターゲット言語をすべてリストする必要があります。リストしないと、配信の送信時にエラーが発生します。

## CSVファイルへのパーソナライゼーションフィールドの挿入 {#personalization-field-csv}

パーソナライゼーションフィールドを使用する場合は、ファイルにタ <span> グを含める必要があります。

「firstName」パーソナライゼーションフィールドをmessageBodyに挿入するには、次のメッセージが必要です。

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

「firstName」フィールドは、次のように表されます。

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

スパンには、次の2つの必須属性があります。

* 一つは静的なクラスです。 どのパーソナライゼーションフィールドを使用する場合でも、常にclass=&quot;nl-dce-field nl-dce-done&quot;になります。

* もう1つはdata-nl-exprで、これはパーソナライゼーションフィールドのパスです。 例えば、UIから「firstName」パーソナライゼーションフィールドを挿入すると、ナビゲーションパスは> > **[!UICONTROL Context (context)]** >と **[!UICONTROL Profile (profile)]****[!UICONTROL First name (firstName)]** なります（下の画像を参照）。 この場合、パスは

   ```
   /context/profile/firstName. data-nl-expr="/context/profile/firstName".
   ```

![](assets/multilingual_push_2.png)

## ロケールと言語名 {#locale-language-names}

次の言語がサポートされています。

| locale | language |
|:-:|:-:|
| af_za | アフリカ語 — 南アフリカ |
| sq_al | アルバニア語 — アルバニア |
| ar_dz | アラビア語 — アルジェリア |
| ar_bh | アラビア語 — バーレーン |
| ar_iq | アラビア語 — イラク |
| ar_il | アラビア語 — イスラエル |
| ar_jo | アラビア語 — ヨルダン |
| ar_kw | アラビア語 — クウェート |
| ar_lb | アラビア語 — レバノン |
| ar_ma | アラビア語 — モロッコ |
| ar_om | アラビア語 — オマーン |
| ar_qa | アラビア語 — カタール |
| ar_sa | アラビア語 — サウジアラビア |
| ar_sy | アラビア語 — シリア |
| ar_tn | アラビア語 — チュニジア |
| ar_ae | アラビア語 — アラブ首長国連邦 |
| ar_ye | アラビア語 — イエメン |
| hy_am | アルメニア語 — アルメニア |
| az_az | アゼリ語 — アゼルバイジャン |
| be_by | ベラルーシ語 — ベラルーシ |
| bs_ba | ボスニア語 — ボスニア |
| bg_bg | ブルガリア語 — ブルガリア |
| ca_es | カタルーニャ語 — スペイン |
| zh_cn | 中国語（簡体字） — 中国 |
| zh_sg | 中国語（簡体字） — シンガポール |
| zh_hk | 中国語（繁体字） — 中国香港特別行政区 |
| zh_tw | 中国語（繁体字） — 台湾地域 |
| hr_hr | クロアチア語 — クロアチア |
| cs_cz | チェコ語 — チェコ |
| da_dk | デンマーク語 — デンマーク |
| nl_be | オランダ語 — ベルギー |
| nl_nl | オランダ語 — オランダ |
| en_au | 英語 — オーストラリア |
| en_bz | 英語 — ベリーズ |
| en_ca | 英語 — カナダ |
| en_in | 英語 — インド |
| en_ie | 英語 — アイルランド |
| en_jm | 英語 — ジャマイカ |
| en_nz | 英語 — ニュージーランド |
| en_ph | 英語 — フィリピン |
| en_za | 英語 — 南アフリカ |
| en_tt | 英語 — トリニダード・トバゴ |
| en_gb | 英語 — 英国 |
| en_us | 英語 — 米国 |
| en_zw | 英語 — ジンバブエ |
| et_ee | エストニア語 — エストニア |
| fi_fi | フィンランド語 — フィンランド |
| fr_be | フランス語 — ベルギー |
| fr_ca | フランス語 — カナダ |
| fr_fr | フランス語 — フランス |
| fr_lu | フランス語 — ルクセンブルク |
| fr_ch | フランス語 — スイス |
| de_at | ドイツ語 — オーストリア |
| de_de | ドイツ語 — ドイツ |
| de_lu | ドイツ語 — ルクセンブルグ |
| de_ch | ドイツ語 — スイス |
| el_cy | ギリシャ語 — キプロス |
| el_gr | ギリシャ語 — ギリシャ |
| gu_in | グジャラティ — インド |
| he_il | ヘブライ語 — イスラエル |
| hi_in | ヒンディー語 — インド |
| hu_hu | ハンガリー語 — ハンガリー |
| is_is | アイスランド語 — アイスランド |
| id_id | インドネシア語 — インドネシア |
| it_it | イタリア語 — イタリア |
| it_ch | イタリア語 — スイス |
| ja_jp | 日本語 — 日本 |
| kn_in | カンナダ語 — インド |
| kk_kz | カザフ語 — カザフスタン |
| ko_kr | 韓国語 — 韓国 |
| lv_lv | ラトビア語 — ラトビア |
| lt_lt | リトアニア語 — リトアニア |
| mk_mk | マケドニア語 — マケドニア |
| ms_my | マレー語 — マレーシア |
| mr_in | マラーティ語 — インド |
| no_no | ノルウェー語 — ノルウェー |
| pl_pl | ポーランド語 — ポーランド |
| pt_br | ポルトガル語 — ブラジル |
| pt_pt | ポルトガル語 — ポルトガル |
| pa_in | パンジャビ語 — インド |
| ro_md | ルーマニア語 — モルドバ |
| ro_ro | ルーマニア語 — ルーマニア |
| ru_kz | ロシア語 — カザフスタン |
| ru_ru | ロシア語 — ロシア |
| ru_ua | ロシア語 — ウクライナ |
| a_in | サンスクリット語 — インド |
| sr_ba | セルビア語 — ボスニア |
| sr_rs | セルビア語 — セルビア |
| sk_sk | スロバキア — スロバキア |
| sl_si | スロベニア語 — スロベニア |
| es_ar | スペイン語 — アルゼンチン |
| es_bo | スペイン語 — ボリビア |
| es_cl | スペイン語 — チリ |
| es_co | スペイン語 — コロンビア |
| es_cr | スペイン語 — コスタリカ |
| es_do | スペイン語 — ドミニカ共和国 |
| es_ec | スペイン語 — エクアドル |
| es_sv | スペイン語 — エルサルバドル |
| es_gt | スペイン語 — グアテマラ |
| es_hn | スペイン語 — ホンジュラス |
| es_mx | スペイン語 — メキシコ |
| es_ni | スペイン語 — ニカラグア |
| es_pa | スペイン語 — パナマ |
| es_py | スペイン語 — パラグアイ |
| es_pe | スペイン語 — ペルー |
| es_pr | スペイン語 — プエルトリコ |
| es_es | スペイン語 — スペイン |
| es_uy | スペイン語 — ウルグアイ |
| es_ve | スペイン語 — ベネズエラ |
| sw_ke | スワヒリ語 — ケニア |
| sv_fi | スウェーデン語 — フィンランド |
| sv_se | スウェーデン語 — スウェーデン |
| ta_in | タミル語 — インド |
| tt_ru | タタール語 — ロシア語 |
| te_in | テルグ語 — インド |
| th_th | タイ語 — タイ |
| tr_cy | トルコ語 — キプロス |
| tr_tr | トルコ語 — トルコ |
| uk_ua | ウクライナ語 — ウクレイン |
| ur_in | ウルドゥ語 — インド |
| ur_pk | ウルドゥ語 — パキスタン |
| vi_vn | ベトナム語 — ベトナム |