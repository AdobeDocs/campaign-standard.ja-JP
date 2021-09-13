---
title: DataModel
description: データモデルの詳細
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: Data Model
role: Developer
level: Experienced
exl-id: bd12a214-5998-4fb9-9f54-0c886067b58b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 7%

---

# landingPage (nms:landingPage)

## オブジェクトの説明

<table>
      <tr>
         <th>名前</th>
         <th>ラベル</th>
         <th>タイプ（長さ）</th>
         <th>列挙値</th>
      </tr>
      <tr>
         <td>PKey</td>
         <td>メインリソースID</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalData</td>
         <td>追加データ</td>
         <td>コレクション </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalLanguages</td>
         <td>その他の言語</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>識別されない訪問者を認証する</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>branding (brandingBase)</td>
         <td>ブランド</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>builtIn</td>
         <td>アプリケーションのビルトインオブジェクト</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>キャッシュ</td>
         <td>キャッシュ</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>キャンペーン(campaignBase)</td>
         <td>キャンペーン</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>closedLog</td>
         <td>「ランディングページが閉じられました」ログ</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>created</td>
         <td>作成日時</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>createdBy (userBase)</td>
         <td>作成者</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>cryptKey</td>
         <td>AES暗号化キー</td>
         <td>文字列(64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>デフォルト言語</td>
         <td>列挙（文字列） (255)</td>
         <td>
            <ul>
               <li>ギリシャ語 — el - el</li>
               <li>英語 — en - en</li>
               <li>中国語 — zh - zh</li>
               <li>フランス語（フランス） — fr_FR - fr_FR</li>
               <li>ベトナム語 — vi - vi</li>
               <li>ポルトガル語（ポルトガル） - pt_PT - pt_PT</li>
               <li>イタリア語（イタリア） - it_IT - it_IT</li>
               <li>イタリア語 — it - it</li>
               <li>オランダ語（ベルギー） - nl_BE - nl_BE</li>
               <li>ノルウェー語（ノルウェー） — no_NO - no_NO</li>
               <li>オランダ語（オランダ） — nl_NL - nl_NL</li>
               <li>アラビア語 — ar - ar</li>
               <li>英語（米国） — en_US - en_US</li>
               <li>アイルランド語 — ga - ga</li>
               <li>チェコ語 — cs - cs</li>
               <li>エストニア語 — et - et</li>
               <li>インドネシア語 — id - id</li>
               <li>スペイン語 — es - es</li>
               <li>ロシア語 — ru - ru</li>
               <li>オランダ語 — nl - nl</li>
               <li>ワロン — ワ — ワ</li>
               <li>ポルトガル語 — pt - pt</li>
               <li>フランス語（ベルギー） — fr_BE - fr_BE</li>
               <li>ラトビア語 — lv - lv</li>
               <li>リトアニア語 — lt - lt</li>
               <li>タイ語 — th - th</li>
               <li>英語（英国） — en_GB - en_GB</li>
               <li>フランス語 — fr - fr</li>
               <li>ポルトガル語（ブラジル） — pt_BR - pt_BR</li>
               <li>ドイツ語 — de - de</li>
               <li>デンマーク語 — da - da</li>
               <li>フィンランド語 — fi - fi</li>
               <li>ハンガリー語 — hu - hu</li>
               <li>スウェーデン語（フィンランド） - sv_FI - sv_FI</li>
               <li>日本語 — ja - ja</li>
               <li>ヘブライ語 — he - he</li>
               <li>韓国語 — ko - ko</li>
               <li>スウェーデン語 — sv - sv</li>
               <li>スウェーデン（スウェーデン語） — sv_SE - sv_SE</li>
               <li>スロバキア語 — sk - sk</li>
               <li>マルタ語 — mt - mt</li>
               <li>イタリア語（スイス） - it_CH - it_CH</li>
               <li>ポーランド語 — pl - pl</li>
               <li>スロベニア語 — sl - sl</li>
               <li>無効な値 — __無効な値__ - __無効な値__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin (delivery)</td>
         <td>トラフィックソース</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>desc</td>
         <td>説明</td>
         <td>文字列(512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>デザイン言語</td>
         <td>列挙（文字列） (255)</td>
         <td>
            <ul>
               <li>ギリシャ語 — el - el</li>
               <li>英語 — en - en</li>
               <li>中国語 — zh - zh</li>
               <li>フランス語（フランス） — fr_FR - fr_FR</li>
               <li>ベトナム語 — vi - vi</li>
               <li>ポルトガル語（ポルトガル） - pt_PT - pt_PT</li>
               <li>イタリア語（イタリア） - it_IT - it_IT</li>
               <li>イタリア語 — it - it</li>
               <li>オランダ語（ベルギー） - nl_BE - nl_BE</li>
               <li>ノルウェー語（ノルウェー） — no_NO - no_NO</li>
               <li>オランダ語（オランダ） — nl_NL - nl_NL</li>
               <li>アラビア語 — ar - ar</li>
               <li>英語（米国） — en_US - en_US</li>
               <li>アイルランド語 — ga - ga</li>
               <li>チェコ語 — cs - cs</li>
               <li>エストニア語 — et - et</li>
               <li>インドネシア語 — id - id</li>
               <li>スペイン語 — es - es</li>
               <li>ロシア語 — ru - ru</li>
               <li>オランダ語 — nl - nl</li>
               <li>ワロン — ワ — ワ</li>
               <li>ポルトガル語 — pt - pt</li>
               <li>フランス語（ベルギー） — fr_BE - fr_BE</li>
               <li>ラトビア語 — lv - lv</li>
               <li>リトアニア語 — lt - lt</li>
               <li>タイ語 — th - th</li>
               <li>英語（英国） — en_GB - en_GB</li>
               <li>フランス語 — fr - fr</li>
               <li>ポルトガル語（ブラジル） — pt_BR - pt_BR</li>
               <li>ドイツ語 — de - de</li>
               <li>デンマーク語 — da - da</li>
               <li>フィンランド語 — fi - fi</li>
               <li>ハンガリー語 — hu - hu</li>
               <li>スウェーデン語（フィンランド） - sv_FI - sv_FI</li>
               <li>日本語 — ja - ja</li>
               <li>ヘブライ語 — he - he</li>
               <li>韓国語 — ko - ko</li>
               <li>スウェーデン語 — sv - sv</li>
               <li>スウェーデン（スウェーデン語） — sv_SE - sv_SE</li>
               <li>スロバキア語 — sk - sk</li>
               <li>マルタ語 — mt - mt</li>
               <li>イタリア語（スイス） - it_CH - it_CH</li>
               <li>ポーランド語 — pl - pl</li>
               <li>スロベニア語 — sl - sl</li>
               <li>無効な値 — __無効な値__ - __無効な値__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>動的サービス</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>終了</td>
         <td>有効期限</td>
         <td>日付 </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>エラーページ</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>地理的単位</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>ページ</td>
         <td>コレクション </td>
         <td> </td>
      </tr>
      <tr>
         <td>identificationByUrlParam</td>
         <td>URLパラメーターによる識別</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>リダイレクト URL</td>
         <td>文字列(4096)</td>
         <td> </td>
      </tr>
      <tr>
         <td>isExternal</td>
         <td>外部リソース</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>isTemplate</td>
         <td>テンプレート</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>ジョブ</td>
         <td>ジョブ</td>
         <td>コレクション </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLogs</td>
         <td>ログ</td>
         <td>コレクション </td>
         <td> </td>
      </tr>
      <tr>
         <td>label</td>
         <td>ラベル</td>
         <td>文字列(128)</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>最終変更日時</td>
         <td>日付 </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter (queryFilterBase)</td>
         <td>キーの読み込み</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>読み込みキーのパラメーター</td>
         <td>コレクション </td>
         <td> </td>
      </tr>
      <tr>
         <td>logicalStatus</td>
         <td>実行ステータス</td>
         <td>列挙（文字列） (255)</td>
         <td>
            <ul>
               <li>処理中 — 開始済み — 開始済み</li>
               <li>編集 — 編集 — 編集</li>
               <li>終了 — 終了 — 終了</li>
               <li>警告 — 警告 — 警告</li>
               <li>エラー — エラー — エラー</li>
               <li>無効な値 — __無効な値__ - __無効な値__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>メッセージの送信を開始</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>トランザクションメッセージ</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>modifiedBy (userBase)</td>
         <td>変更者</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>name</td>
         <td>ID</td>
         <td>文字列(64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>組織単位</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>事前入力</td>
         <td>訪問者データのプリロード</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>program (programBase)</td>
         <td>プログラム</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>パブリックURL</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>公開日</td>
         <td>日付 </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationFilter (queryFilterBase)</td>
         <td>紐付けキー</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationFilterMapping</td>
         <td>紐付けキーパラメーター</td>
         <td>コレクション </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationUpdateStrategy</td>
         <td>更新方法</td>
         <td>列挙（バイト） </td>
         <td>
            <ul>
               <li>更新 — updateTarget - 1</li>
               <li>未承認 — 未承認 — 0</li>
               <li>無効な値 — __無効な値__ - __無効な値__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>購読サービス</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>特定のアクション</td>
         <td>列挙（バイト） </td>
         <td>
            <ul>
               <li>ブラックリスト — blackList - 3</li>
               <li>特定のアクションなし — なし — 0</li>
               <li>購読解除 — 購読解除 — 2</li>
               <li>無効な値 — __無効な値__ - __無効な値__</li>
               <li>Subscription - subscription - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>開始</td>
         <td>デプロイ日</td>
         <td>日付 </td>
         <td> </td>
      </tr>
      <tr>
         <td>state</td>
         <td>ステータス</td>
         <td>列挙（バイト） </td>
         <td>
            <ul>
               <li>編集 — 編集 — 0</li>
               <li>公開に失敗しました — 失敗 — 99</li>
               <li>閉 — 閉 — 20</li>
               <li>無効な値 — __無効な値__ - __無効な値__</li>
               <li>オンライン — 開封済み — 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>ターゲティングディメンション</td>
         <td>文字列(255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>template (landingPage)</td>
         <td>ランディングページテンプレート</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>テストURL</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>thumbnail</td>
         <td>サムネイル</td>
         <td>文字列(255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>timezone</td>
         <td>タイムゾーン</td>
         <td>列挙（文字列） (64)</td>
         <td>
            <ul>
               <li>(GMT-02:00)中央大西洋 — Atlantic_South_Georgia — 大西洋/南グルジア</li>
               <li>(GMT+02:00) Amman - Asia_Amman - Asia/Amman</li>
               <li>(GMT-03:00)ブラシ — America_Sao_Paulo - America/Sao_Paulo</li>
               <li>(GMT+06:00)アスタナ、ダッカ — Asia_Dhaka — アジア/ダッカ</li>
               <li>(GMT+06:00)ノボシビルスク — Asia_Novosibirsk — アジア/ノボシビルスク</li>
               <li>(GMT+02:00)ウィンドホーク — Africa_Windhoek - Africa/Windhoek</li>
               <li>(GMT+04:00)コーカサス、エレバン — Asia_Yerevan — アジア/エレバン</li>
               <li>(GMT-04:00)マナウス — America_Manaus - America/Manaus</li>
               <li>(GMT+03:30)テヘラン — アジア_テヘラン — アジア/テヘラン</li>
               <li>(GMT+12:00)オークランド、ウェリントン — Pacific_Auckland — 太平洋/オークランド</li>
               <li>(GMT+02:00)エルサレム — Asia_Jerusalem — アジア/エルサレム</li>
               <li>(GMT+03:00)モスクワ、サンクトペテルブルグ、ボルゴグラード — Europe_Moscow — ヨーロッパ/モスクワ</li>
               <li>(GMT+09:30) Adelaide - Australia_Adelaide - Australia/Adelaide</li>
               <li>(GMT+10:00)キャンベラ、メルボルン、シドニー — Australia_Canberra — オーストラリア/キャンベラ</li>
               <li>(GMT+08:00)パース — オーストラリア_パース — オーストラリア/パース</li>
               <li>(GMT+09:00)ヤクーツク — Asia_Yakutsk — アジア/ヤクーツク</li>
               <li>(GMT-10:00)ハワイ — Pacific_Honolulu — 太平洋/ホノルル</li>
               <li>(GMT+04:00)バク — アジア_バク — アジア/バク</li>
               <li>(GMT+10:00)ウラジオストク — Asia_Vladivostok — アジア/ウラジオストク</li>
               <li>(GMT+09:00)ソウル — アジア_ソウル — アジア/ソウル</li>
               <li>(GMT+01:00)サラエボ、スコプリエ、ソフィア、ワルシャワ、ワルシャワ、ザグレブ — Europe_Sarajevo - Europe/Sarajevo</li>
               <li>サーバーのタイムゾーン — _server_ - _server_</li>
               <li>(GMT+04:00)アブダビ、マスカット — Asia_Muscat — アジア/マスカット</li>
               <li>(GMT+08:00)クアラルンプール、シンガポール — Asia_Kuala_Lumpur - Asia/Kuala_Lumpur</li>
               <li>(GMT+09:00)大阪、札幌、東京 — Asia_Tokyo — アジア/東京</li>
               <li>(GMT+10:00)ブリスベン — Australia_Brisbane — オーストラリア/ブリスベン</li>
               <li>(GMT+05:30)スリジャヤワルデネプラ — Asia_Colombo — アジア/コロンボ</li>
               <li>(GMT+02:00)ハラレ、プレトリア — Africa_Harare - Africa/Harare</li>
               <li>(GMT+08:00) Oulan-Bator - Asia_Ulan_Bator - Asia/Ulan_Bator</li>
               <li>(GMT-02:00)グリニッジ標準時 — 2時間 — Gmt_m2 - Etc/GMT+2</li>
               <li>(GMT-03:00)グリニッジ標準時 — 3時間 — Gmt_m3 - Etc/GMT+3</li>
               <li>(GMT-01:00)グリニッジ標準時から1時間を引いた値 — Gmt_m1 - Etc/GMT+1</li>
               <li>(GMT-06:00)グリニッジ標準時 — 6時間 — Gmt_m6 - Etc/GMT+6</li>
               <li>(GMT-07:00)グリニッジ標準時から7時間 — Gmt_m7 - Etc/GMT+7</li>
               <li>(GMT-04:00)グリニッジ標準時 — 4時間 — Gmt_m4 - Etc/GMT+4</li>
               <li>(GMT)カサブランカ — Africa_Casablanca - Africa/Casablanca</li>
               <li>(GMT+05:30)コルカタ、チェンナイ、ムンバイ、ニューデリー — Asia_Kolkata - Asia/Kolkata</li>
               <li>(GMT-11:00)グリニッジ標準時 — 11時間 — Gmt_m11 - Etc/GMT+11</li>
               <li>(GMT-09:00)グリニッジ標準時 — 9時間 — Gmt_m9 - Etc/GMT+9</li>
               <li>(GMT-03:30)ニューファウンドランド — America_St_Johns — アメリカ/St_Johns</li>
               <li>デフォルト — _inherit_ - _inherit_</li>
               <li>(GMT+03:00)グリニッジ標準時+ 3時間 — Gmt_p3 - Etc/GMT-3</li>
               <li>(GMT-04:30)カラカス — America_Caracas - America/Caracas</li>
               <li>(GMT+01:00)アムステルダム、ベルリン、ベルン、ローマ、ストックホルム、ウィーン、ヨーロッパ_ベルリン — ヨーロッパ/ベルリン</li>
               <li>(GMT-07:00)チワワ、ラパス、マサトラン — America_Chihuahua - America/Chihuahua</li>
               <li>(GMT+03:00)ナイロビ — Africa_Nairobi - Africa/Nairobi</li>
               <li>(GMT-04:00)アスンシオン — America_Asuncion — アメリカ/アスンシオン</li>
               <li>(GMT+03:00)バグダッド — Asia_Baghdad — アジア/バグダッド</li>
               <li>(GMT-10:00)グリニッジ標準時から10時間を引いた値 — Gmt_m10 - Etc/GMT+10</li>
               <li>(GMT-03:00)グリーンランド — America_Godthab - America/Godthab</li>
               <li>(GMT+02:00)ダマス — Asia_Damascus — アジア/ダマスカス</li>
               <li>(GMT-11:00)サモア — Pacific_Samoa — 太平洋/サモア</li>
               <li>(GMT-05:00)ボゴタ、リマ、キト — America_Bogota — アメリカ/ボゴタ</li>
               <li>(GMT+01:00)ブリュッセル、コペンハーゲン、マドリード、パリ — Europe_Paris — ヨーロッパ/パリ</li>
               <li>(GMT+08:00)北京、重慶、香港、ウルムチ — Asia_Shanghai — アジア/上海</li>
               <li>(GMT+12:00)フィジー — 太平洋_フィジー — 太平洋/フィジー</li>
               <li>(GMT+02:00)アテネ、イスタンブール、ミンスク — Europe_Athens — ヨーロッパ/アテネ</li>
               <li>(GMT+04:00)トビリシ — アジア_トビリシ — アジア/トビリシ</li>
               <li>無効な値 — __無効な値__ - __無効な値__</li>
               <li>(GMT+05:45)カトマンズ — Asia_Katmandu — アジア/カトマンズ</li>
               <li>(GMT-05:00)インディアナ（東部） - America_Indianapolis — アメリカ/インディアナポリス</li>
               <li>(GMT-01:00)カーボベルデ諸島 — Atlantic_Cape_Verde - Atlantic/Cape_Verde</li>
               <li>(GMT+04:00)ポートルイス — Indian_Mauritius — インド/モーリシャス</li>
               <li>(GMT+08:00)台北 — Asia_Taipei - Asia/Taipei</li>
               <li>データベースのタイムゾーン — _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30)ラングーン — アジア_ラングーン — アジア/ラングーン</li>
               <li>(GMT+11:00)マガダン、ソロモン諸島、ニューカレドニア — Pacific_Guadalcanal — 太平洋/グアダルカナル</li>
               <li>(GMT+02:00)カイロ — Africa_Cairo — アフリカ/カイロ</li>
               <li>(GMT+05:00) Iekaterinburg - Asia_Yekaterinburg — アジア/Yekaterinburg</li>
               <li>(GMT+08:00)イルコーツク — Asia_Irkutsk — アジア/イルクーツク</li>
               <li>(GMT+10:00)グアム、ポートモレスビー — Pacific_Guam — 太平洋/グアム</li>
               <li>(GMT-04:00)大西洋標準時（カナダ） - America_Halifax — アメリカ/ハリファックス</li>
               <li>(GMT)グリニッジ標準時 — GMT - GMT</li>
               <li>(GMT-04:00)ラパス — アメリカ_ラ_パス — アメリカ/ラ_パス</li>
               <li>オペレーターのタイムゾーン — _login_ - _login_</li>
               <li>(GMT-06:00)グアダラハラ、メキシコ、モンテレイ — America_Mexico_City - America/Mexico_City</li>
               <li>(GMT+09:30) Darwin - Australia_Darwin - Australia/Darwin</li>
               <li>(GMT-05:00)東部（米国およびカナダ） - America_New_York — アメリカ/ニューヨーク</li>
               <li>(GMT-05:00)グリニッジ標準時 — 5時間 — Gmt_m5 - Etc/GMT+5</li>
               <li>(GMT+05:00)イスラマバード、カラチ、タッケント — Asia_Karachi — アジア/カラチ</li>
               <li>(GMT+03:00) Koweyut, Riyad - Asia_Riyadh — アジア/リヤド</li>
               <li>(GMT-08:00)グリニッジ標準時 — 8時間 — Gmt_m8 - Etc/GMT+8</li>
               <li>(GMT-01:00)アゾレス諸島 — Atlantic_Azores — 大西洋/アゾレス諸島</li>
               <li>(GMT+07:00)バンコク、ハノイ、ジャカルタ — Asia_Bangkok — アジア/バンコク</li>
               <li>(GMT)モンロビア — Africa_Monrovia — アフリカ/モンロビア</li>
               <li>(GMT-09:00)アラスカ — America_Anchorage — アメリカ/アンカレッジ</li>
               <li>(GMT+01:00)ベオグラード、ブラチスラバ、ブダペスト、リュブリャナ、プラハ — ヨーロッパ_ベオグラード — ヨーロッパ/ベオグラード</li>
               <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
               <li>(GMT+02:00)ブカレスト — Europe_Bucharest — ヨーロッパ/ブカレスト</li>
               <li>(GMT+05:00)グリニッジ標準時+ 5時間 — Gmt_p5 - Etc/GMT-5</li>
               <li>(GMT+04:00)グリニッジ標準時+ 4時間 — Gmt_p4 - Etc/GMT-4</li>
               <li>(GMT+07:00)グリニッジ標準時+ 7時間 — Gmt_p7 - Etc/GMT-7</li>
               <li>(GMT+06:00)グリニッジ標準時+ 6時間 — Gmt_p6 - Etc/GMT-6</li>
               <li>(GMT+01:00)グリニッジ標準時+ 1時間 — Gmt_p1 - Etc/GMT-1</li>
               <li>(GMT-08:00)太平洋（米国およびカナダ） — America_Los_Angeles — アメリカ/ロサンゼルス</li>
               <li>(GMT+02:00)グリニッジ標準時+ 2時間 — Gmt_p2 - Etc/GMT-2</li>
               <li>(GMT+07:00)クラスノヤルスク — Asia_Krasnoyarsk — アジア/クラスノヤルスク</li>
               <li>(GMT+09:00)グリニッジ標準時+ 9時間 — Gmt_p9 - Etc/GMT-9</li>
               <li>(GMT+08:00)グリニッジ標準時+ 8時間 — Gmt_p8 - Etc/GMT-8</li>
               <li>(GMT+10:00)ホバート — Australia_Hobart - Australia/Hobart</li>
               <li>(GMT+13:00)ヌクアロファ — Pacific_Tongatapu — 太平洋/トンガタプ</li>
               <li>(GMT-06:00)中米 — America_Regina — アメリカ/レジーナ</li>
               <li>(GMT-03:00)ブエノスアイレス、ケイエン、フォルタレザ — America_Buenos_Aires — アメリカ/ブエノス_アイレス</li>
               <li>(GMT-07:00)ロッキー山脈（米国およびカナダ） - America_Denver — アメリカ/デンバー</li>
               <li>(GMT+01:00)中央アフリカ — 西 — Africa_Luanda - Africa/Luanda</li>
               <li>(GMT+02:00)ヘルシンキ、キエフ、リガ、ソフィア、タリン、ビリニウス — Europe_Helsinki - Europe/Helsinki</li>
               <li>(GMT)グリニッジ標準時：ダブリン、エジンバラ、リスボン、ロンドン — Europe_London - Europe/London</li>
               <li>(GMT-07:00)アリゾナ — アメリカ_フェニックス — アメリカ/フェニックス</li>
               <li>(GMT+02:00)ベイルート — Asia_Beirut — アジア/ベイルート</li>
               <li>(GMT+04:30)カブール — Asia_Kabul — アジア/カブール</li>
               <li>(GMT-06:00)センター（米国およびカナダ） - America_Chicago — アメリカ/シカゴ</li>
               <li>(GMT+11:00)グリニッジ標準時+ 11時間 — Gmt_p11 - Etc/GMT-11</li>
               <li>(GMT+10:00)グリニッジ標準時+ 10時間 — Gmt_p10 - Etc/GMT-10</li>
               <li>(GMT+13:00)グリニッジ標準時+ 13時間 — Gmt_p13 - Etc/GMT-13</li>
               <li>(GMT+12:00)グリニッジ標準時+ 12時間 — Gmt_p12 - Etc/GMT-12</li>
               <li>(GMT-04:00)サンティアゴ — America_Santiago - America/Santiago</li>
               <li>(GMT-03:00)モンテビデオ — America_Montevideo — アメリカ/モンテビデオ</li>
               <li>(GMT-04:00)クイアバ — America_Cuiaba - America/Cuiaba</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>タイトル</td>
         <td>ランディングページ</td>
         <td>文字列(255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>応答をログに記録</td>
         <td>boolean </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>トラッキング URL 名</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>type</td>
         <td>タイプ</td>
         <td>列挙（バイト） </td>
         <td>
            <ul>
               <li>汎用 — 汎用 — 0</li>
               <li>サービスの購読解除 — 購読解除 — 3</li>
               <li>ブラックリスト — blackList - 4</li>
               <li>無効な値 — __無効な値__ - __無効な値__</li>
               <li>獲得 — 獲得 — 1</li>
               <li>サービスのサブスクリプション — サブスクリプション — 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>セキュリティ ID</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Web トラッキングを有効にする</td>
         <td>boolean </td>
         <td> </td>
      </tr>
   </table>

## フィルター

論理ステータス別(byLogicalStatus)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>state</td>
    <td>列挙</td>
    </tr>
</table>

名前またはラベル(byText)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>テキスト</td>
    <td>文字列</td>
    </tr>
</table>

ステータス別(byState)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>state</td>
    <td>列挙</td>
    </tr>
</table>

ターゲティングリソース(byTargetResource)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>targetResource</td>
<td>文字列</td>
</tr>
</table>

高度なランディングページを含める(Advanced)

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>advanced</td>
    <td>boolean</td>
    </tr>
</table>

異種のリストからの連続配信を含める(withContinuous)

<table>
        <tr>
        <th>名前</th>
        <th>タイプ</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>boolean</td>
        </tr>
    </table>

指定した期間(byCalendar)に存在する

<table>
        <tr>
        <th>名前</th>
        <th>タイプ</th>
        </tr>
        <tr>
        <td>startDate</td>
        <td>日付</td>
        </tr>
        <tr>
        <td>endDate</td>
        <td>日付</td>
        </tr>
    </table>

特定の期間(byPlanning)に公開される

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>日付</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>日付</td>
    </tr>
</table>
