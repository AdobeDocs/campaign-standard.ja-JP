---
title: DataModel
description: データモデルについて
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# プロファイル(nms:recipient)

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
                  <td>年齢</td>
                  <td>年齢</td>
                  <td>整数 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>appSubscription</td>
                  <td>アプリの購読</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>誕生日</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackList</td>
                  <td>今後の連絡は不要 (すべてのチャネル)</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>今後の E メールによる連絡は不要</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>今後の FAX による連絡は不要</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>今後の SMS による連絡は不要</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>今後の電話による連絡は不要</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>今後のダイレクトメールによる連絡は不要</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>プッシュ通知による連絡は不要になりました</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>国（国）</td>
                  <td>国</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>created</td>
                  <td>作成済み</td>
                  <td>日付 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>作成者</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cryptedId</td>
                  <td>暗号化されたID</td>
                  <td>文字列 </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink(cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>最終取引日</td>
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
                  <td>domain</td>
                  <td>E メールドメイン</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>E メール</td>
                  <td>文字列(128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>E メールフォーマット</td>
                  <td>列挙（バイト） </td>
                  <td>
                     <ul>
                        <li>テキスト — テキスト — 1</li>
                        <li>HTML - html - 2</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>不明 — 不明 — 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>emailStatus (addressStatus)</td>
                  <td>電子メールに関する情報</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>除外ログ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>FAX</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>名</td>
                  <td>文字列(30)</td>
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
                        <li>雌 — 雌 — 2</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>外部リソース</td>
                  <td>boolean </td>
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
                  <td>文字列(50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>場所</td>
                  <td>場所</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ログ</td>
                  <td>配信ログ</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>ミドルネーム</td>
                  <td>文字列(30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>モバイル</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>変更者</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>phone</td>
                  <td>電話</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>場所</td>
                  <td>場所</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>postalAddress</td>
                  <td>郵送先住所</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>salutation</td>
                  <td>タイトル</td>
                  <td>文字列(20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (state)</td>
                  <td>都道府県</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>購読履歴</td>
                  <td>購読履歴</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>購読</td>
                  <td>購読</td>
                  <td>コレクション </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>サムネイル</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>timeZone</td>
                  <td>タイムゾーン</td>
                  <td>列挙（文字列） (64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02:00)中央大西洋 — Atlantic_South_Georgia - Atlantic/South_Georgia</li>
                        <li>(GMT+02:00)アンマン — Asia_Amman - Asia/Amman</li>
                        <li>(GMT-03:00)ブラジ — America_Sao_Paulo - America/Sao_Paulo</li>
                        <li>(GMT+06:00)アスタナ、ダッカ — Asia_Dhaka - Asia/Dhaka</li>
                        <li>(GMT+06:00)ノボシビルスク — Asia_Novosibirsk - Asia/Novosibirsk</li>
                        <li>(GMT+02:00)ウィントホーク — Africa_Windhoek - Africa/Windhoek</li>
                        <li>(GMT+04:00)コーカサス、エレバン — Asia_Yerevan - Asia/Yerevan</li>
                        <li>(GMT-04:00)マナウス — America_Manaus - America/Manaus</li>
                        <li>(GMT+03:30)テヘラン — Asia_Tehran - Asia/Theran</li>
                        <li>(GMT+12:00)オークランド、ウェリントン — Pacific_Auckland - Pacific/Auckland</li>
                        <li>(GMT+02:00)エルサレム — Asia_Jerusalem - Asia/Jerusalem</li>
                        <li>(GMT+03:00)モスクワ、サンクトペテルブルグ、ボルゴグラード — Europe_Moscow - Europe/Moscow</li>
                        <li>(GMT+09:30)アデレード — Australia_Adelaide - Australia/Adelaide</li>
                        <li>(GMT+10:00)キャンベラ、メルボルン、シドニー — Australia_Canberra - Australia/Canberra</li>
                        <li>(GMT+08:00)パース — オーストラリア_パース — オーストラリア/パース</li>
                        <li>(GMT+09:00)ヤクーツク — Asia_Yakutsk — アジア/ヤクーツク</li>
                        <li>(GMT-10:00)ハワイ — Pacific_Honolulu - Pacific/Honolulu</li>
                        <li>(GMT+04:00)バクー — アジアバクー — アジア/バクー</li>
                        <li>(GMT+10:00)ウラジオストク — Asia_Vladivostok - Asia/Vladivostok</li>
                        <li>(GMT+09:00)ソウル — アジア_ソウル — アジア/ソウル</li>
                        <li>(GMT+01:00)サラエボ、スコプリエ、ソフィア、ワルシャワ、ザグレブ — Europe_Sarajevo - Europe/Sarajevo</li>
                        <li>(GMT+04:00)アブダビ、マスカット — Asia_Muscat - Asia/Muscat</li>
                        <li>(GMT+08:00)クアラルンプール、シンガポール — Asia_Kuala_Lumpur - Asia/Kuala_Lumpur</li>
                        <li>(GMT+09:00)大阪、札幌、東京 — Asia_Tokyo — アジア/東京</li>
                        <li>(GMT+10:00)ブリスベン — オーストラリア_ブリスベン — オーストラリア/ブリスベン</li>
                        <li>(GMT+05:30)スリジャヤワルデネプラ — Asia_Colombo - Asia/Colombo</li>
                        <li>(GMT+02:00)ハラレ、プレトリア — Africa_Harare - Africa/Harare</li>
                        <li>(GMT+08:00)ウランバトル — Asia_Ulan_Bator - Asia/Ulan_Bator</li>
                        <li>(GMT-02:00)グリニッジ標準時 — 2時間 — Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03:00)グリニッジ標準時 — 3時間 — Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-01:00)グリニッジ標準時 — 1時間 — Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06:00)グリニッジ標準時 — 6時間 — Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07:00)グリニッジ標準時 — 7時間 — Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04:00)グリニッジ標準時 — 4時間 — Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT)カサブランカ — Africa_Casablanca - Africa/Casablanca</li>
                        <li>(GMT+05:30)コルカタ、チェンナイ、ムンバイ、ニューデリー — Asia_Kolkata - Asia/Kolkata</li>
                        <li>(GMT-11:00)グリニッジ標準時 — 11時間 — Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09:00)グリニッジ標準時 — 9時間 — Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03:30)ニューファンドランド — America_St_Johns - America/St_Johns</li>
                        <li>(GMT+03:00)グリニッジ標準時+ 3時間 — Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04:30)カラカス — America_Caracas - America/Caracas</li>
                        <li>(GMT+01:00)アムステルダム、ベルリン、ベルン、ローマ、ストックホルム、ウィーン — Europe_Berlin - Europe/Berlin</li>
                        <li>(GMT-07:00)チワワ、ラパス、マサトラン — America_Chihuahua - America/Chihuahua</li>
                        <li>(GMT+03:00)ナイロビ — アフリカ_ナイロビ — アフリカ/ナイロビ</li>
                        <li>(GMT-04:00)アスンシオン — America_Asuncion - America/Asuncion</li>
                        <li>(GMT+03:00)バグダッド — Asia_Baghdad - Asia/Baghdad</li>
                        <li>(GMT-10:00)グリニッジ標準時 — 10時間 — Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03:00)グリーンランド — America_Godthab - America/Godthab</li>
                        <li>(GMT+02:00)ダマス — Asia_Damascus - Asia/Damascus</li>
                        <li>(GMT-11:00)サモア — Pacific_Samoa - Pacific/Samoa</li>
                        <li>(GMT-05:00)ボゴタ、リマ、キト — America_Bogota - America/Bogota</li>
                        <li>(GMT+01:00)ブリュッセル、コペンハーゲン、マドリッド、パリ — Europe_Paris - Europe/Paris</li>
                        <li>(GMT+08:00)北京、重慶、香港、ウルムチ — Asia_Shanghai - Asia/Shanghai</li>
                        <li>(GMT+12:00)フィジー — パシフィック_フィジ — 太平洋/フィジ</li>
                        <li>(GMT+02:00)アテネ、イスタンブール、ミンスク — ヨーロッパ_アテネ — ヨーロッパ/アテネ</li>
                        <li>(GMT+04:00)トビリシ — Asia_Tbilisi - Asia/Tbilisi</li>
                        <li>無効な値 — __Invalid_value__ - __Invalid_value__</li>
                        <li>(GMT+05:45)カトマンズ — Asia_Katmandu - Asia/Katmandu</li>
                        <li>(GMT-05:00)インディアナ（東部） - America_Indianapolis - America/Indianapolis</li>
                        <li>(GMT-01:00)カーボベルデ諸島 — Atlantic_Cape_Verde - Atlantic/Cape_Verde</li>
                        <li>(GMT+04:00)ポートルイス — Indian_Mauritius - Indian/Mauritius</li>
                        <li>(GMT+08:00)台北 — Asia_Taipei - Asia/Taipei</li>
                        <li>(GMT+06:30)ラングーン — Asia_Rangeon - Asia/Rangeon</li>
                        <li>(GMT+11:00)マガダン、ソロモン諸島、ニューカレドニア — Pacific_Guadalcanal - Pacific/Guadalcanal</li>
                        <li>(GMT+02:00)カイロ — Africa_Cairo - Africa/Cairo</li>
                        <li>(GMT+05:00)イーカテリンブルグ — Asia_Yekaterinburg - Asia/Yekaterinburg</li>
                        <li>(GMT+08:00)イルコーツク — Asia_Irkutsk - Asia/Irkutsk</li>
                        <li>(GMT+10:00)グアム、ポートモレスビー — パシフィック_グアム — パシフィック/グアム</li>
                        <li>(GMT-04:00)大西洋標準時（カナダ） — America_Halifax - America/Halifax</li>
                        <li>(GMT)グリニッジ標準時 — GMT - GMT</li>
                        <li>デフォルト — なし — なし</li>
                        <li>(GMT-04:00)ラパス — America_La_Paz - America/La_Paz</li>
                        <li>(GMT-06:00)グアダラハラ、メキシコ、モンテレイ — America_Mexico_City - America/Mexico_City</li>
                        <li>(GMT+09:30)ダーウィン — オーストラリア_ダーウィン — オーストラリア/ダーウィン</li>
                        <li>(GMT-05:00)東部（米国およびカナダ） — America_New_York - America/New_York</li>
                        <li>(GMT-05:00)グリニッジ標準時 — 5時間 — Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05:00)イスラマバード、カラチ、タケント — Asia_Karachi - Asia/Karachi</li>
                        <li>(GMT+03:00)Koweyt、Riyad - Asia_Riyadh - Asia/Riyadh</li>
                        <li>(GMT-08:00)グリニッジ標準時 — 8時間 — Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01:00)アゾレス諸島 — Atlantic_Azores - Atlantic/Azores</li>
                        <li>(GMT+07:00)バンコク、ハノイ、ジャカルタ — Asia_Bangkok - Asia/Bangkok</li>
                        <li>(GMT)モンロビア — Africa_Monrovia - Africa/Monrovia</li>
                        <li>(GMT-09:00)アラスカ — America_Anchorage - America/Anchorage</li>
                        <li>(GMT+01:00)ベオグラード、ブラチスラバ、ブダペスト、リュブリャナ、プラハ — ヨーロッパ_ベオグラード — ヨーロッパ/ベオグラード</li>
                        <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
                        <li>(GMT+02:00)ブカレスト — Europe_Bucharest - Europe/Bucharest</li>
                        <li>(GMT+05:00)グリニッジ標準時+ 5時間 — Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04:00)グリニッジ標準時+ 4時間 — Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07:00)グリニッジ標準時+ 7時間 — Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06:00)グリニッジ標準時+ 6時間 — Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01:00)グリニッジ標準時+ 1時間 — Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08:00)太平洋（米国およびカナダ） — America_Los_Angeles - America/Los_Angeles</li>
                        <li>(GMT+02:00)グリニッジ標準時+ 2時間 — Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07:00)クラスノヤルスク — Asia_Krasnoyarsk - Asia/Krasnoyarsk</li>
                        <li>(GMT+09:00)グリニッジ標準時+ 9時間 — Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08:00)グリニッジ標準時+ 8時間 — Gmt_p8 - Etc/GMT-8</li>
                        <li>(GMT+10:00)ホバート — オーストラリア_ホバート — オーストラリア/ホバート</li>
                        <li>(GMT+13:00)ヌクアロファ — Pacific_Tongatapu - Pacific/Tongatapu</li>
                        <li>(GMT-06:00)中央アメリカ — America_Regina - America/Regina</li>
                        <li>(GMT-03:00)ブエノスアイレス、ケイエン、フォルタレザ — America_Buenos_Aires - America/Buenos_Aires</li>
                        <li>(GMT-07:00)ロッキー山脈（米国およびカナダ） — America_Denver - America/Denver</li>
                        <li>(GMT+01:00)中央アフリカ — 西 — Africa_Luanda - Africa/Luanda</li>
                        <li>(GMT+02:00)ヘルシンキ、キエフ、リガ、ソフィア、タリン、ビリニウス — Europe_Helsinki - Europe/Helsinki</li>
                        <li>(GMT)グリニッジ標準時：ダブリン、エジンバラ、リスボン、ロンドン — Europe_London - Europe/London</li>
                        <li>(GMT-07:00)アリゾナ — America_Phoenix - America/Phoenix</li>
                        <li>(GMT+02:00)ベイルート — Asia_Beirut - Asia/Beirut</li>
                        <li>(GMT+04:30)カブール — Asia_Kabul — アジア/カブール</li>
                        <li>(GMT-06:00)センター（米国およびカナダ） — America_Chicago - America/Chicago</li>
                        <li>(GMT+11:00)グリニッジ標準時+ 11時間 — Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10:00)グリニッジ標準時+ 10時間 — Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13:00)グリニッジ標準時+ 13時間 — Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12:00)グリニッジ標準時+ 12時間 — Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04:00)サンティアゴ — America_Santiago - America/Santiago</li>
                        <li>(GMT-03:00)モンテビデオ — America_Montevideo - America/Montevideo</li>
                        <li>(GMT-04:00)クイアバ — アメリカ_クイアバ — アメリカ/クイアバ</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>タイトル</td>
                  <td>プロファイル</td>
                  <td>文字列(255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tracking</td>
                  <td>トラッキングログ</td>
                  <td>コレクション </td>
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
<td>boolean</td>
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
<td>boolean</td>
</tr>
<tr>
<td>endMonth</td>
<td>日付</td>
</tr>
<tr>
<td>type</td>
<td>列挙</td>
</tr>
<tr>
<td>day</td>
<td>日付</td>
</tr>
</table>

電子メール（電子メール）

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>email</td>
<td>文字列</td>
</tr>
</table>

キー別(byKeysProfile)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>email</td>
<td>文字列</td>
</tr>
</table>

名前または電子メール(byText)

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

静的オーディエンス別(byStaticAudience)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>オーディエンス</td>
<td>link</td>
</tr>
</table>

クリック済み(hasClickedDelivery)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>配信</td>
<td>link</td>
</tr>
</table>

Opened (hasOpenedDelivery)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>配信</td>
<td>link</td>
</tr>
</table>

プロファイル（プロファイル）

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>profile</td>
<td>link</td>
</tr>
</table>

受信済み(hasReceivedDelivery)

<table>
<tr>
<th>名前</th>
<th>タイプ</th>
</tr>
<tr>
<td>配信</td>
<td>link</td>
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
<td>link</td>
</tr>
</table>