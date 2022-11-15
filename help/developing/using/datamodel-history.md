---
title: DataModel マーケティング履歴
description: データモデルの詳細
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 7f2a3139-57eb-48ff-9b1a-ac2caad2f691
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 14%

---

# マーケティング履歴 (nms:history)

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
                  <td>メインリソース ID</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>年齢</td>
                  <td>年齢</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>誕生日</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackList</td>
                  <td>今後の連絡は不要 (すべてのチャネル)</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>今後の E メールによる連絡は不要</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>今後の FAX による連絡は不要</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>今後の SMS による連絡は不要</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>今後の電話による連絡は不要</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>今後のダイレクトメールによる連絡は不要</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>今後のプッシュ通知による連絡は不要</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countBroadLogEvents</td>
                  <td>CountBroadLogEvents</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countSubHistoEvents</td>
                  <td>CountSubHistoEvents</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>国（国）</td>
                  <td>国</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countryIsoA2</td>
                  <td>ISO A2 コード</td>
                  <td>文字列 (2)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>created</td>
                  <td>作成日時</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>作成者</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>最終トランザクション日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>トランザクション</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>電子メール</td>
                  <td>メール</td>
                  <td>文字列 (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>イベント</td>
                  <td>異種リソース</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>FAX</td>
                  <td>文字列 (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>名</td>
                  <td>文字列 (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>gender</td>
                  <td>性別</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>未指定 — 不明 — 0</li>
                        <li>男性 — 男性 — 1</li>
                        <li>女性 — 女性 — 2</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソースです</td>
                  <td>ブール値 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpisAndChart</td>
                  <td>KpisAndChart</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>最終変更日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastName</td>
                  <td>姓</td>
                  <td>文字列 (50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>場所</td>
                  <td>場所</td>
                  <td>項目 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>ミドルネーム</td>
                  <td>文字列 (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minBroadLogEvents</td>
                  <td>MinBroadLogEvents</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>minSubHistoEvents</td>
                  <td>MinSubHistoEvents</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>モバイル</td>
                  <td>文字列 (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>変更者</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>phone</td>
                  <td>電話</td>
                  <td>文字列 (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>salutation</td>
                  <td>タイトル</td>
                  <td>文字列 (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
                  <td>状態</td>
                  <td>リンク </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>サムネイル</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>timeZone</td>
                  <td>タイムゾーン</td>
                  <td>enumeration（文字列） (64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02:00) 中部大西洋 — 大西洋 — 大西洋南ジョージア — 大西洋/サウスジョージア</li>
                        <li>(GMT+02:00) アンマン — アジア_アンマン — アジア/アンマン</li>
                        <li>(GMT-03:00) ブラジ — アメリカ_サンパウロ — アメリカ/サンパウロ</li>
                        <li>(GMT+06:00) アスタナ、ダッカ — アジア_ダッカ — アジア/ダッカ</li>
                        <li>(GMT+06:00) ノボシビルスク — アジア_ノボシビルスク — アジア/ノボシビルスク</li>
                        <li>(GMT+02:00) ウィントフック — Africa_Winthoek — アフリカ/ウィントフック</li>
                        <li>(GMT+04:00) コーカサス、エレバン — アジア_エレバン — アジア/エレバン</li>
                        <li>(GMT-04:00) マナウス — アメリカ_マナウス — アメリカ/マナウス</li>
                        <li>(GMT+03:30) テヘラン — アジア_テヘラン — アジア/テヘラン</li>
                        <li>(GMT+12:00) オークランド、ウェリントン — 太平洋_オークランド — 太平洋/オークランド</li>
                        <li>(GMT+02:00) エルサレム — アジア_エルサレム — アジア/エルサレム</li>
                        <li>(GMT+03:00) モスクワ、サンクトペテルブルグ、ボルゴグラード — ヨーロッパ_モスクワ — ヨーロッパ/モスクワ</li>
                        <li>(GMT+09:30) アデレード — オーストラリア_アデレード — オーストラリア/アデレード</li>
                        <li>(GMT+10:00) キャンベラ、メルボルン、シドニー — オーストラリア_キャンベラ — オーストラリア/キャンベラ</li>
                        <li>(GMT+08:00) パース — オーストラリア_パース — オーストラリア/パース</li>
                        <li>(GMT+09:00) ヤクーツク — アジア_ヤクーツク — アジア/ヤクーツク</li>
                        <li>(GMT-10:00) ハワイ — 太平洋_ホノルル — 太平洋/ホノルル</li>
                        <li>(GMT+04:00) バクー — アジア_バクー — アジア/バクー</li>
                        <li>(GMT+10:00) ウラジオストク — アジア_ウラジオストク — アジア/ウラジオストク</li>
                        <li>(GMT+09:00) ソウル — アジアソウル — アジア/ソウル</li>
                        <li>(GMT+01:00) サラエボ、スコピエ、ソフィア、ワルシャワ、ザグレブ — ヨーロッパ_サラエボ — ヨーロッパ/サラエボ</li>
                        <li>(GMT+04:00) アブダビ、マスカット — アジア_マスカット — アジア/マスカット</li>
                        <li>(GMT+08:00) クアラルンプール、シンガポール — アジア_クアラルンプール — アジア/クアラルンプール</li>
                        <li>(GMT+09:00) 大阪、札幌、東京 — アジア_東京 — アジア/東京</li>
                        <li>(GMT+10:00) ブリスベン — オーストラリア_ブリスベン — オーストラリア/ブリスベン</li>
                        <li>(GMT+05:30) スリジャヤワルデネプラ — アジア_コロンボ — アジア/コロンボ</li>
                        <li>(GMT+02:00) ハラレ、プレトリア — アフリカハラレ — アフリカ/ハラレ</li>
                        <li>(GMT+08:00) Oulan-Bator - Asia_Ulan_Bator — アジア/Ulan_Bator</li>
                        <li>(GMT-02:00) グリニッジ標準時 — 2 時間 — Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03:00) グリニッジ標準時 — 3 時間 — Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-01:00) グリニッジ標準時 — 1 時間 — Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06:00) グリニッジ標準時 — 6 時間 — Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07:00) グリニッジ標準時 — 7 時間 — Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04:00) グリニッジ標準時 — 4 時間 — Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT) カサブランカ — アフリカ_カサブランカ — アフリカ/カサブランカ</li>
                        <li>(GMT+05:30) コルカタ、チェンナイ、ムンバイ、ニューデリー — Asia_Kolkata — アジア/コルカタ</li>
                        <li>(GMT-11:00) グリニッジ標準時 — 11 時間 — Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09:00) グリニッジ標準時 — 9 時間 — Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03:30) ニューファンドランド — アメリカ_セントジョンズ — アメリカ/セントジョンズ</li>
                        <li>(GMT+03:00) グリニッジ標準時+ 3 時間 — Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04:30) カラカス — アメリカ_カラカス — アメリカ/カラカス</li>
                        <li>(GMT+01:00) アムステルダム、ベルリン、ベルン、ローマ、ストックホルム、ウィーン — ヨーロッパ_ベルリン — ヨーロッパ/ベルリン</li>
                        <li>(GMT-07:00) チワワ、ラパス、マサトラン — アメリカ_チワワ — アメリカ/チワワ</li>
                        <li>(GMT+03:00) ナイロビ — アフリカ_ナイロビ — アフリカ/ナイロビ</li>
                        <li>(GMT-04:00) アスンシオン — アメリカ_アスンシオン — アメリカ/アスンシオン</li>
                        <li>(GMT+03:00) バグダッド — アジア_バグダッド — アジア/バグダッド</li>
                        <li>(GMT-10:00) グリニッジ標準時 — 10 時間 — Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03:00) グリーンランド — アメリカ_ゴットハブ — アメリカ/ゴットハブ</li>
                        <li>(GMT+02:00) ダマス — アジア_ダマスカス — アジア/ダマスカス</li>
                        <li>(GMT-11:00) サモア — 太平洋サモア — 太平洋/サモア</li>
                        <li>(GMT-05:00) ボゴタ、リマ、キト — アメリカ_ボゴタ — アメリカ/ボゴタ</li>
                        <li>(GMT+01:00) ブリュッセル、コペンハーゲン、マドリード、パリ — ヨーロッパ_パリ — ヨーロッパ/パリ</li>
                        <li>(GMT+08:00) 北京、重慶、香港、ウルムチ — アジア_上海 — アジア/上海</li>
                        <li>(GMT+12:00) フィジー — 太平洋_フィジー — 太平洋/フィジー</li>
                        <li>(GMT+02:00) アテネ、イスタンブール、ミンスク — ヨーロッパ_アテネ — ヨーロッパ/アテネ</li>
                        <li>(GMT+04:00) トビリシ — アジア_トビリシ — アジア/トビリシ</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>(GMT+05:45) カトマンズ — アジア_カトマンズ — アジア/カトマンズ</li>
                        <li>(GMT-05:00) インディアナ州（東部） - America_Indianapolis — アメリカ/インディアナポリス</li>
                        <li>(GMT-01:00) カーボベルデ諸島 — 大西洋_カーボベルデ — 大西洋/カーボベルデ</li>
                        <li>(GMT+04:00) ポートルイス — インド洋_モーリシャス — インド洋/モーリシャス</li>
                        <li>(GMT+08:00) 台北 — アジア_台北 — アジア/台北</li>
                        <li>(GMT+06:30) ラングーン — アジア_ラングーン — アジア/ラングーン</li>
                        <li>(GMT+11:00) マガダン、ソロモン諸島、ニューカレドニア — 太平洋_ガダルカナル — 太平洋/ガダルカナル</li>
                        <li>(GMT+02:00) カイロ — アフリカ_カイロ — アフリカ/カイロ</li>
                        <li>(GMT+05:00) エカテリンブルグ — アジア_エカテリンブルグ — アジア/エカテリンブルグ</li>
                        <li>(GMT+08:00) イルクーツク — アジア_イルクーツク — アジア/イルクーツク</li>
                        <li>(GMT+10:00) グアム、ポートモレスビー — 太平洋_グアム — 太平洋/グアム</li>
                        <li>(GMT-04:00) 大西洋標準時（カナダ） - America_Halifax — アメリカ/ハリファックス</li>
                        <li>(GMT) グリニッジ標準時 — GMT - GMT</li>
                        <li>デフォルト — なし — なし</li>
                        <li>(GMT-04:00) ラパス — アメリカ_ラ_パス — アメリカ/ラ_パス</li>
                        <li>(GMT-06:00) グアダラハラ、メキシコ、モンテレイ — アメリカ_メキシコシティ — アメリカ/メキシコシティ</li>
                        <li>(GMT+09:30) ダーウィン — オーストラリア_ダーウィン — オーストラリア/ダーウィン</li>
                        <li>(GMT-05:00) 東部標準時（米国およびカナダ） — アメリカ_ニューヨーク — アメリカ/ニューヨーク</li>
                        <li>(GMT-05:00) グリニッジ標準時 — 5 時間 — Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05:00) イスラマバード、カラチ、タシケント — アジア_カラチ — アジア/カラチ</li>
                        <li>(GMT+03:00) Koweyt, Riyad - Asia_Riyadh - Asia/Riyadh</li>
                        <li>(GMT-08:00) グリニッジ標準時 — 8 時間 — Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01:00) アゾレス諸島 — 大西洋アゾレス諸島 — 大西洋/アゾレス諸島</li>
                        <li>(GMT+07:00) バンコク、ハノイ、ジャカルタ — アジア_バンコク — アジア/バンコク</li>
                        <li>(GMT) モンロビア — アフリカ_モンロビア — アフリカ/モンロビア</li>
                        <li>(GMT-09:00) アラスカ — アメリカ_アンカレッジ — アメリカ/アンカレッジ</li>
                        <li>(GMT+01:00) ベオグラード、ブラチスラバ、ブダペスト、リュブリャナ、プラハ — ヨーロッパ_ベオグラード — ヨーロッパ/ベオグラード</li>
                        <li>(GMT) レイキャビク — Atlantic_Reykjavik — 大西洋/レイキャビク</li>
                        <li>(GMT+02:00) ブカレスト — ヨーロッパ_ブカレスト — ヨーロッパ/ブカレスト</li>
                        <li>(GMT+05:00) グリニッジ標準時+ 5 時間 — Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04:00) グリニッジ標準時+ 4 時間 — Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07:00) グリニッジ標準時+ 7 時間 — Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06:00) グリニッジ標準時+ 6 時間 — Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01:00) グリニッジ標準時+ 1 時間 — Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08:00) 太平洋（米国およびカナダ） — アメリカ_ロサンゼルス — アメリカ/ロサンゼルス</li>
                        <li>(GMT+02:00) グリニッジ標準時+ 2 時間 — Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07:00) クラスノヤルスク — アジア_クラスノヤルスク — アジア/クラスノヤルスク</li>
                        <li>(GMT+09:00) グリニッジ標準時+ 9 時間 — Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08:00) グリニッジ標準時+ 8 時間 — Gmt_p8 - Etc/GMT-8</li>
                        <li>(GMT+10:00) ホバート — オーストラリア_ホバート — オーストラリア/ホバート</li>
                        <li>(GMT+13:00) ヌクアロファ — 太平洋_トンガタプ — 太平洋/トンガタプ</li>
                        <li>(GMT-06:00) 中米 — アメリカ_レジーナ — アメリカ/レジナ</li>
                        <li>(GMT-03:00) ブエノスアイレス、カイエンヌ、フォルタレザ — アメリカ_ブエノスアイレス — アメリカ/ブエノスアイレス</li>
                        <li>(GMT-07:00) ロッキー山脈（米国およびカナダ） — アメリカ_デンバー — アメリカ/デンバー</li>
                        <li>(GMT+01:00) 中央アフリカ — 西 — アフリカ_ルアンダ — アフリカ/ルアンダ</li>
                        <li>(GMT+02:00) ヘルシンキ、キエフ、リガ、ソフィア、タリン、ヴィリニュス — ヨーロッパ_ヘルシンキ — ヨーロッパ/ヘルシンキ</li>
                        <li>(GMT) グリニッジ標準時：ダブリン、エジンバラ、リスボン、ロンドン — ヨーロッパ_ロンドン — ヨーロッパ/ロンドン</li>
                        <li>(GMT-07:00) アリゾナ — アメリカ_フェニックス — アメリカ/フェニックス</li>
                        <li>(GMT+02:00) ベイルート — アジア_ベイルート — アジア/ベイルート</li>
                        <li>(GMT+04:30) カブール — アジア_カブール — アジア/カブール</li>
                        <li>(GMT-06:00) 中央（米国およびカナダ） — アメリカ_シカゴ — アメリカ/シカゴ</li>
                        <li>(GMT+11:00) グリニッジ標準時+ 11 時間 — Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10:00) グリニッジ標準時+ 10 時間 — Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13:00) グリニッジ標準時+ 13 時間 — Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12:00) グリニッジ標準時+ 12 時間 — Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04:00) サンティアゴ — アメリカ_サンティアゴ — アメリカ/サンティアゴ</li>
                        <li>(GMT-03:00) モンテビデオ — アメリカ_モンテビデオ — アメリカ/モンテビデオ</li>
                        <li>(GMT-04:00) クイアバ — アメリカ_クイアバ — アメリカ/クイアバ</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>プロファイル</td>
                  <td>文字列 (255)</td>
                  <td> </td>
               </tr>
            </table>

## フィルター

誕生日（誕生日）

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>includeStart</td>
<td>ブール値</td>
</tr>
<tr>
<td>previousUnitsValue</td>
<td>整数</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>整数</td>
</tr>
<tr>
<td>endDay</td>
<td>日付</td>
</tr>
<tr>
<td>精度</td>
<td>列挙</td>
</tr>
<tr>
<td>relativeValue</td>
<td>文字列</td>
</tr>
<tr>
<td>ヶ月</td>
<td>日付</td>
</tr>
<tr>
<td>演算子</td>
<td>列挙</td>
</tr>
<tr>
<td>includeEnd</td>
<td>ブール値</td>
</tr>
<tr>
<td>endMonth</td>
<td>日付</td>
</tr>
<tr>
<td>タイプ</td>
<td>列挙</td>
</tr>
<tr>
<td>day</td>
<td>日付</td>
</tr>
</table>

E メール別（E メール別）

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>電子メール</td>
<td>文字列</td>
</tr>
</table>

キー別 (byKeysProfile)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>電子メール</td>
<td>文字列</td>
</tr>
</table>

名前別または E メール別（テキスト別）

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

静的オーディエンス (byStaticAudience)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>オーディエンス</td>
<td>リンク</td>
</tr>
</table>

クリック済み (hasClickedDelivery)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>配信</td>
<td>リンク</td>
</tr>
</table>

開封済み (hasOpenedDelivery)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>配信</td>
<td>リンク</td>
</tr>
</table>

プロファイル (profile)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>profile</td>
<td>リンク</td>
</tr>
</table>

受信済み (hasReceivedDelivery)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>配信</td>
<td>リンク</td>
</tr>
</table>

購読者（購読者）

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>サービス</td>
<td>リンク</td>
</tr>
</table>
