---
title: DataModel landingPage
description: データモデルについて説明します
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: Data Model
role: Developer
level: Experienced
exl-id: bd12a214-5998-4fb9-9f54-0c886067b58b
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1817'
ht-degree: 8%

---

# landingPage （nms:landingPage）

## オブジェクトの説明

<table>
      <tr>
         <th>名前</th>
         <th>ラベル</th>
         <th>タイプ （長さ）</th>
         <th>列挙値</th>
      </tr>
      <tr>
         <td>PKey</td>
         <td>メインリソース ID</td>
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
         <td>項目 </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>未識別の訪問者を許可</td>
         <td>ブール値 </td>
         <td> </td>
      </tr>
      <tr>
         <td>ブランディング （brandingBase）</td>
         <td>ブランド</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>builtIn</td>
         <td>アプリケーションのビルトインオブジェクト</td>
         <td>ブール値 </td>
         <td> </td>
      </tr>
      <tr>
         <td>キャッシュ</td>
         <td>キャッシュ</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>campaign （campaignBase）</td>
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
         <td>日付 </td>
         <td> </td>
      </tr>
      <tr>
         <td>createdBy （userBase）</td>
         <td>作成者</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>cryptKey</td>
         <td>AES 暗号化キー</td>
         <td>文字列（64）</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>デフォルト言語</td>
         <td>列挙（文字列） （255）</td>
         <td>
            <ul>
               <li>ギリシャ語 – el - el</li>
               <li>英語 – en - en</li>
               <li>中国語 – zh - zh</li>
               <li>フランス語（フランス） – fr_FR - fr_FR</li>
               <li>ベトナム語 – vi - vi</li>
               <li>ポルトガル語（ポルトガル） – pt_PT - pt_PT</li>
               <li>イタリア語（イタリア） – it_IT - it_IT</li>
               <li>イタリア語 – it</li>
               <li>オランダ語（ベルギー） - nl_BE - nl_BE</li>
               <li>ノルウェー語（ノルウェー） - no_NO - no_NO</li>
               <li>オランダ語（オランダ） - nl_NL - nl_NL</li>
               <li>アラビア語 – ar - ar</li>
               <li>英語（米国） – en_US - en_US</li>
               <li>アイルランド語 – ga - ga</li>
               <li>チェコ語 – cs - cs</li>
               <li>エストニア語 – et - et</li>
               <li>インドネシア語 – id - id</li>
               <li>スペイン語 – es - es</li>
               <li>ロシア語 – ru - ru</li>
               <li>オランダ語 – nl - nl</li>
               <li>ワロン ワ ワ ワ ワ</li>
               <li>ポルトガル語 – pt - pt</li>
               <li>フランス語（ベルギー） – fr_BE - fr_BE</li>
               <li>ラトビア語 – lv - lv</li>
               <li>リトアニア語 – lt - lt</li>
               <li>タイ語 – th - th</li>
               <li>英語（英国） – en_GB - en_GB</li>
               <li>フランス語 – fr - fr</li>
               <li>ポルトガル語（ブラジル） – pt_BR - pt_BR</li>
               <li>ドイツ語 – de - de</li>
               <li>デンマーク語 – da - da</li>
               <li>フィンランド語 – fi - fi</li>
               <li>ハンガリー語 – hu - hu</li>
               <li>スウェーデン語（フィンランド） - sv_FI - sv_FI</li>
               <li>日本語 – ja - ja</li>
               <li>ヘブライ語 – he - he</li>
               <li>韓国語 – ko - ko</li>
               <li>スウェーデン語 – sv - sv</li>
               <li>スウェーデン語（スウェーデン） - sv_SE - sv_SE</li>
               <li>スロバキア語 – sk - sk</li>
               <li>マルタ語 – mt - mt</li>
               <li>イタリア語（スイス） - it_CH - it_CH</li>
               <li>ポーランド語 – pl - pl</li>
               <li>スロベネ - sl - sl</li>
               <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin （配信）</td>
         <td>トラフィックソース</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>降順</td>
         <td>説明</td>
         <td>文字列（512）</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>デザイン言語</td>
         <td>列挙（文字列） （255）</td>
         <td>
            <ul>
               <li>ギリシャ語 – el - el</li>
               <li>英語 – en - en</li>
               <li>中国語 – zh - zh</li>
               <li>フランス語（フランス） – fr_FR - fr_FR</li>
               <li>ベトナム語 – vi - vi</li>
               <li>ポルトガル語（ポルトガル） – pt_PT - pt_PT</li>
               <li>イタリア語（イタリア） – it_IT - it_IT</li>
               <li>イタリア語 – it</li>
               <li>オランダ語（ベルギー） - nl_BE - nl_BE</li>
               <li>ノルウェー語（ノルウェー） - no_NO - no_NO</li>
               <li>オランダ語（オランダ） - nl_NL - nl_NL</li>
               <li>アラビア語 – ar - ar</li>
               <li>英語（米国） – en_US - en_US</li>
               <li>アイルランド語 – ga - ga</li>
               <li>チェコ語 – cs - cs</li>
               <li>エストニア語 – et - et</li>
               <li>インドネシア語 – id - id</li>
               <li>スペイン語 – es - es</li>
               <li>ロシア語 – ru - ru</li>
               <li>オランダ語 – nl - nl</li>
               <li>ワロン ワ ワ ワ ワ</li>
               <li>ポルトガル語 – pt - pt</li>
               <li>フランス語（ベルギー） – fr_BE - fr_BE</li>
               <li>ラトビア語 – lv - lv</li>
               <li>リトアニア語 – lt - lt</li>
               <li>タイ語 – th - th</li>
               <li>英語（英国） – en_GB - en_GB</li>
               <li>フランス語 – fr - fr</li>
               <li>ポルトガル語（ブラジル） – pt_BR - pt_BR</li>
               <li>ドイツ語 – de - de</li>
               <li>デンマーク語 – da - da</li>
               <li>フィンランド語 – fi - fi</li>
               <li>ハンガリー語 – hu - hu</li>
               <li>スウェーデン語（フィンランド） - sv_FI - sv_FI</li>
               <li>日本語 – ja - ja</li>
               <li>ヘブライ語 – he - he</li>
               <li>韓国語 – ko - ko</li>
               <li>スウェーデン語 – sv - sv</li>
               <li>スウェーデン語（スウェーデン） - sv_SE - sv_SE</li>
               <li>スロバキア語 – sk - sk</li>
               <li>マルタ語 – mt - mt</li>
               <li>イタリア語（スイス） - it_CH - it_CH</li>
               <li>ポーランド語 – pl - pl</li>
               <li>スロベネ - sl - sl</li>
               <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>動的サービス</td>
         <td>ブール値 </td>
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
         <td>項目 </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit （geoUnitBase）</td>
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
         <td>idByUrlParam</td>
         <td>URL パラメーターによる識別</td>
         <td>ブール値 </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>リダイレクト URL</td>
         <td>文字列（4096）</td>
         <td> </td>
      </tr>
      <tr>
         <td>isExternal</td>
         <td>外部リソース</td>
         <td>ブール値 </td>
         <td> </td>
      </tr>
      <tr>
         <td>isTemplate</td>
         <td>テンプレート</td>
         <td>ブール値 </td>
         <td> </td>
      </tr>
      <tr>
         <td>ジョブ</td>
         <td>ジョブ</td>
         <td>コレクション </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLog</td>
         <td>ログ</td>
         <td>コレクション </td>
         <td> </td>
      </tr>
      <tr>
         <td>ラベル</td>
         <td>ラベル</td>
         <td>文字列（128）</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>最終変更日</td>
         <td>日付 </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter （queryFilterBase）</td>
         <td>キーを読み込み中</td>
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
         <td>列挙（文字列） （255）</td>
         <td>
            <ul>
               <li>処理中 – 開始 – 開始</li>
               <li>編集 – エディション – エディション</li>
               <li>完了 – 完了 – 完了</li>
               <li>警告 – 警告 – 警告</li>
               <li>エラー – エラー – エラー</li>
               <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>メッセージの送信を開始</td>
         <td>ブール値 </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery （deliveryMCTemplateBase）</td>
         <td>トランザクションメッセージ</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>modifiedBy （userBase）</td>
         <td>変更者</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>name</td>
         <td>ID</td>
         <td>文字列（64）</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit （orgUnitBase）</td>
         <td>組織単位</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>事前入力</td>
         <td>訪問者データのプリロード</td>
         <td>ブール値 </td>
         <td> </td>
      </tr>
      <tr>
         <td>プログラム（programBase）</td>
         <td>プログラム</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>パブリック URL</td>
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
         <td>reconciliationFilter （queryFilterBase）</td>
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
         <td>戦略を更新</td>
         <td>列挙（バイト） </td>
         <td>
            <ul>
               <li>更新 – updateTarget - 1</li>
               <li>未認証 – 未認証 – 0</li>
               <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>サービス （serviceBase）</td>
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
               <li>ブラックリスト – ブラックリスト - 3</li>
               <li>特定のアクションなし – なし – 0</li>
               <li>購読解除 – 購読解除 – 2</li>
               <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
               <li>購読 – 購読 – 1</li>
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
         <td>都道府県</td>
         <td>ステータス</td>
         <td>列挙（バイト） </td>
         <td>
            <ul>
               <li>編集 – 編集 – 0</li>
               <li>公開に失敗しました – 失敗 – 99</li>
               <li>クローズド – クローズド - 20</li>
               <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
               <li>オンライン – 開封済み – 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>ターゲティングディメンション</td>
         <td>文字列（255）</td>
         <td> </td>
      </tr>
      <tr>
         <td>テンプレート（landingPage）</td>
         <td>ランディングページテンプレート</td>
         <td>リンク </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>テスト URL</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>thumbnail</td>
         <td>サムネイル</td>
         <td>文字列（255）</td>
         <td> </td>
      </tr>
      <tr>
         <td>タイムゾーン</td>
         <td>タイムゾーン</td>
         <td>列挙（文字列） （64）</td>
         <td>
            <ul>
               <li>（GMT-02:00）中部大西洋 – 大西洋_サウスジョージア – 大西洋/サウスジョージア</li>
               <li>（GMT+02:00） アンマン – アジア_アンマン – アジア/アンマン</li>
               <li>（GMT-03:00） ブラジ – アメリカ_サンパウロ – アメリカ/サンパウロ</li>
               <li>（GMT+06:00） アスタナ、ダッカ – アジア_ダッカ – アジア/ダッカ</li>
               <li>（GMT+06:00） ノボシビルスク – アジア_ノボシビルスク – アジア/ノボシビルスク</li>
               <li>（GMT+02:00） ウィントフック – アフリカ_ウィントフック – アフリカ/ウィントフック</li>
               <li>（GMT+04:00） コーカサス、エレバン – アジア_エレバン – アジア/エレバン</li>
               <li>（GMT-04:00） マナウス – アメリカマナウス – アメリカ/マナウス</li>
               <li>（GMT+03:30） テヘラン – アジア_テヘラン – アジア/テヘラン</li>
               <li>（GMT+12:00） オークランド、ウェリントン – 太平洋_オークランド – 太平洋/オークランド</li>
               <li>（GMT+02:00） エルサレム – アジア_エルサレム – アジア/エルサレム</li>
               <li>（GMT+03:00） モスクワ、サンクトペテルブルク、ボルゴグラード – ヨーロッパ_モスクワ – ヨーロッパ/モスクワ</li>
               <li>（GMT+09:30） アデレード – オーストラリア_アデレード – オーストラリア/アデレード</li>
               <li>（GMT+10:00） キャンベラ、メルボルン、シドニー – オーストラリア_キャンベラ – オーストラリア/キャンベラ</li>
               <li>（GMT+08:00） パース – オーストラリア_パース – オーストラリア/パース</li>
               <li>（GMT+09:00） ヤクーツク – アジア_ヤクーツク – アジア/ヤクーツク</li>
               <li>（GMT-10:00） ハワイ – 太平洋_ホノルル – 太平洋/ホノルル</li>
               <li>（GMT+04:00） バクー – アジア_バクー – アジア/バクー</li>
               <li>（GMT+10:00） ウラジオストック – アジア_ウラジオストック – アジア/ウラジオストック</li>
               <li>（GMT+09:00） ソウル – アジア_ソウル – アジア/ソウル</li>
               <li>（GMT+01:00） サラエボ、スコピエ、ソフィア、ワルシャワ、ザグレブ – ヨーロッパ_サラエボ – ヨーロッパ/サラエボ</li>
               <li>サーバーのタイムゾーン - _server_ - _server_</li>
               <li>（GMT+04:00） アブダビ、マスカット – アジア_マスカット – アジア/マスカット</li>
               <li>（GMT+08:00） クアラルンプール、シンガポール – アジア_クアラルンプール – アジア/クアラルンプール</li>
               <li>（GMT+09:00）大阪、札幌、東京 – アジア東京 – アジア/東京</li>
               <li>（GMT+10:00） ブリスベン – オーストラリア_ブリスベン – オーストラリア/ブリスベン</li>
               <li>（GMT+05:30） スリジャヤワルダナプラコッテ – アジア_コロンボ – アジア/コロンボ</li>
               <li>（GMT+02:00） ハラレ、プレトリア – アフリカ_ハラレ – アフリカ/ハラレ</li>
               <li>（GMT+08:00） ウランバートル – アジア_ウランバートル – アジア/ウランバートル</li>
               <li>（GMT-02:00） グリニッジ標準時 – 2 時間 – Gmt_m2 - Etc/GMT+2</li>
               <li>（GMT-03:00） グリニッジ標準時 – 3 時間 – Gmt_m3 - Etc/GMT+3</li>
               <li>（GMT-01:00） グリニッジ標準時 – 1 時間 – Gmt_m1 - Etc/GMT+1</li>
               <li>（GMT-06:00） グリニッジ標準時 – 6 時間 – Gmt_m6 - Etc/GMT+6</li>
               <li>（GMT-07:00） グリニッジ標準時 – 7 時間 – Gmt_m7 - Etc/GMT+7</li>
               <li>（GMT-04:00） グリニッジ標準時 – 4 時間 – Gmt_m4 - Etc/GMT+4</li>
               <li>（GMT） カサブランカ – アフリカ_カサブランカ – アフリカ/カサブランカ</li>
               <li>（GMT+05:30） コルカタ、チェンナイ、ムンバイ、ニューデリー – アジア_コルカタ – アジア/コルカタ</li>
               <li>（GMT-11:00） グリニッジ標準時 – 11 時間 – Gmt_m11 - Etc/GMT+11</li>
               <li>（GMT-09:00） グリニッジ標準時 – 9 時間 – Gmt_m9 - Etc/GMT+9</li>
               <li>（GMT-03:30） ニューファンドランド – アメリカ_セントジョンズ – アメリカ/セントジョンズ</li>
               <li>デフォルト - _inherit_ - _inherit_</li>
               <li>（GMT+03:00） グリニッジ標準時+ 3 時間 – Gmt_p3 - Etc/GMT-3</li>
               <li>（GMT-04:30） カラカス – アメリカ_カラカス – アメリカ/カラカス</li>
               <li>（GMT+01:00） アムステルダム、ベルリン、ベルン、ローマ、ストックホルム、ウィーン – ヨーロッパ_ベルリン – ヨーロッパ/ベルリン</li>
               <li>（GMT-07:00） チワワ、ラパス、マサトラン – アメリカ_チワワ – アメリカ/チワワ</li>
               <li>（GMT+03:00） ナイロビ – アフリカ_ナイロビ – アフリカ/ナイロビ</li>
               <li>（GMT-04:00） アスンシオン – アメリカ_アスンシオン – アメリカ/アスンシオン</li>
               <li>（GMT+03:00） バグダッド – アジア_バグダッド – アジア/バグダッド</li>
               <li>（GMT-10:00） グリニッジ標準時 – 10 時間 – Gmt_m10 - Etc/GMT+10</li>
               <li>（GMT-03:00） グリーンランド – アメリカ_ゴッドタブ – アメリカ/ゴッドタブ</li>
               <li>（GMT+02:00） ダマスカス – アジア_ダマスカス – アジア/ダマスカス</li>
               <li>（GMT-11:00） サモア – 太平洋_サモア – 太平洋/サモア</li>
               <li>（GMT-05:00） ボゴタ、リマ、キト – アメリカ_ボゴタ – アメリカ/ボゴタ</li>
               <li>（GMT+01:00） ブリュッセル、コペンハーゲン、マドリード、パリ – 欧州_パリ – 欧州/パリ</li>
               <li>（GMT+08:00）北京、重慶、香港、ウルムチ – アジア上海 – アジア/上海</li>
               <li>（GMT+12:00） フィジー – 太平洋_フィジー – 太平洋/フィジー</li>
               <li>（GMT+02:00） アテネ、イスタンブール、ミンスク – ヨーロッパ アテネ – ヨーロッパ/アテネ</li>
               <li>（GMT+04:00） トビリシ – アジア_トビリシ – アジア/トビリシ</li>
               <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
               <li>（GMT+05:45） カトマンズ – アジア_カトマンズ – アジア/カトマンズ</li>
               <li>（GMT-05:00） インディアナ州（東部） – アメリカ_インディアナポリス – アメリカ/インディアナポリス</li>
               <li>（GMT-01:00） カーボベルデ諸島 – 大西洋_カーボベルデ – 大西洋/カーボベルデ</li>
               <li>（GMT+04:00） ポートルイス – インド洋_モーリシャス – インド洋/モーリシャス</li>
               <li>（GMT+08:00）台北 – アジア_台北 – アジア/台北</li>
               <li>データベースのタイムゾーン - _wdbc_ - _wdbc_</li>
               <li>（GMT+06:30） ラングーン – アジア_ラングーン – アジア/ラングーン</li>
               <li>（GMT+11:00） マガダン、ソロモン諸島、ニューカレドニア – 太平洋_ガダルカナル – 太平洋/ガダルカナル</li>
               <li>（GMT+02:00） カイロ – アフリカ_カイロ – アフリカ/カイロ</li>
               <li>（GMT+05:00） エカテリンブルグ – アジア_エカテリンブルグ – アジア/エカテリンブルグ</li>
               <li>（GMT+08:00） イルクーツク – アジア_イルクーツク – アジア/イルクーツク</li>
               <li>（GMT+10:00） グアム、ポートモレスビー – 太平洋_グアム – 太平洋/グアム</li>
               <li>（GMT-04:00）大西洋標準時（カナダ） – アメリカ_ハリファックス – アメリカ/ハリファックス</li>
               <li>（GMT） グリニッジ標準時 – GMT - GMT</li>
               <li>（GMT-04:00） ラパス – アメリカ_ラパス – アメリカ/ラパス</li>
               <li>オペレーターのタイムゾーン - _login_ - _login_</li>
               <li>（GMT-06:00） グアダラハラ、メキシコ、モンテレー – アメリカ メキシコシティ – アメリカ/メキシコシティ</li>
               <li>（GMT+09:30） ダーウィン – オーストラリア_ダーウィン – オーストラリア/ダーウィン</li>
               <li>（GMT-05:00）東部標準時（米国およびカナダ） – アメリカ ニューヨーク – アメリカ/ニューヨーク</li>
               <li>（GMT-05:00） グリニッジ標準時 – 5 時間 – Gmt_m5 - Etc/GMT+5</li>
               <li>（GMT+05:00） イスラマバード、カラチ、タシケント – アジア_カラチ – アジア/カラチ</li>
               <li>（GMT+03:00） クウェート、リヤド – アジア_リヤド – アジア/リヤド</li>
               <li>（GMT-08:00） グリニッジ標準時 – 8 時間 – Gmt_m8 - Etc/GMT+8</li>
               <li>（GMT-01:00） アゾレス諸島 – 大西洋_アゾレス諸島 – 大西洋/アゾレス諸島</li>
               <li>（GMT+07:00） バンコク、ハノイ、ジャカルタ – アジア_バンコク – アジア/バンコク</li>
               <li>（GMT） モンロビア – アフリカ_モンロビア – アフリカ/モンロビア</li>
               <li>（GMT-09:00） アラスカ – アメリカ_アンカレッジ – アメリカ/アンカレッジ</li>
               <li>（GMT+01:00） ベオグラード、ブラチスラバ、ブダペスト、リュブリャナ、プラハ – ヨーロッパ_ベオグラード – ヨーロッパ/ベオグラード</li>
               <li>（GMT） レイキャビク – 大西洋_レイキャビク – 大西洋/レイキャビク</li>
               <li>（GMT+02:00） ブカレスト – ヨーロッパ_ブカレスト – ヨーロッパ/ブカレスト</li>
               <li>（GMT+05:00） グリニッジ標準時+ 5 時間 – Gmt_p5 - Etc/GMT-5</li>
               <li>（GMT+04:00） グリニッジ標準時+ 4 時間 – Gmt_p4 - Etc/GMT-4</li>
               <li>（GMT+07:00） グリニッジ標準時+ 7 時間 – Gmt_p7 - Etc/GMT-7</li>
               <li>（GMT+06:00） グリニッジ標準時+ 6 時間 – Gmt_p6 - Etc/GMT-6</li>
               <li>（GMT+01:00） グリニッジ標準時+ 1 時間 – Gmt_p1 - Etc/GMT-1</li>
               <li>（GMT-08:00）太平洋（米国およびカナダ） – アメリカ ロサンゼルス – アメリカ/ロサンゼルス</li>
               <li>（GMT+02:00） グリニッジ標準時+ 2 時間 – Gmt_p2 - Etc/GMT-2</li>
               <li>（GMT+07:00） クラスノヤルスク – アジア_クラスノヤルスク – アジア/クラスノヤルスク</li>
               <li>（GMT+09:00） グリニッジ標準時+ 9 時間 – Gmt_p9 - Etc/GMT-9</li>
               <li>（GMT+08:00） グリニッジ標準時+ 8 時間 – Gmt_p8 - Etc/GMT-8</li>
               <li>（GMT+10:00） ホバート – オーストラリア_ホバート – オーストラリア/ホバート</li>
               <li>（GMT+13:00） ヌクアロファ – 太平洋_トンガタプ – 太平洋/トンガタプ</li>
               <li>（GMT-06:00）中央アメリカ – アメリカ_レジーナ – アメリカ/レジーナ</li>
               <li>（GMT-03:00） ブエノスアイレス、カイエンヌ、フォルタレザ – アメリカ/ブエノスアイレス – アメリカ/ブエノスアイレス</li>
               <li>（GMT-07:00） ロッキー山脈（米国およびカナダ） – アメリカ_デンバー – アメリカ/デンバー</li>
               <li>（GMT+01:00）中央アフリカ – 西部 – アフリカ_ルアンダ – アフリカ/ルアンダ</li>
               <li>（GMT+02:00） ヘルシンキ、キエフ、リガ、ソフィア、タリン、ビリニュス – ヨーロッパ_ヘルシンキ – ヨーロッパ/ヘルシンキ</li>
               <li>（GMT） グリニッジ標準時：ダブリン、エジンバラ、リスボン、ロンドン – ヨーロッパ_ロンドン – ヨーロッパ/ロンドン</li>
               <li>（GMT-07:00） アリゾナ – アメリカ_フェニックス – アメリカ/フェニックス</li>
               <li>（GMT+02:00） ベイルート – アジア_ベイルート – アジア/ベイルート</li>
               <li>（GMT+04:30） カブール – アジア_カブール – アジア/カブール</li>
               <li>（GMT-06:00）中央（米国およびカナダ） – アメリカ シカゴ – アメリカ/シカゴ</li>
               <li>（GMT+11:00） グリニッジ標準時+ 11 時間 – Gmt_p11 - Etc/GMT-11</li>
               <li>（GMT+10:00） グリニッジ標準時+ 10 時間 – Gmt_p10 - Etc/GMT-10</li>
               <li>（GMT+13:00） グリニッジ標準時+ 13 時間 – Gmt_p13 - Etc/GMT-13</li>
               <li>（GMT+12:00） グリニッジ標準時+ 12 時間 – Gmt_p12 - Etc/GMT-12</li>
               <li>（GMT-04:00） サンティアゴ – アメリカ_サンティアゴ – アメリカ/サンティアゴ</li>
               <li>（GMT-03:00） モンテビデオ – アメリカ_モンテビデオ – アメリカ/モンテビデオ</li>
               <li>（GMT-04:00） クイアバ – アメリカ_クイアバ – アメリカ/クイアバ</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>タイトル</td>
         <td>ランディングページ</td>
         <td>文字列（255）</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>応答をログに記録</td>
         <td>ブール値 </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>トラッキング URL 名</td>
         <td>文字列 </td>
         <td> </td>
      </tr>
      <tr>
         <td>タイプ</td>
         <td>タイプ</td>
         <td>列挙（バイト） </td>
         <td>
            <ul>
               <li>汎用 – 汎用 – 0</li>
               <li>サービスの購読解除 – 購読解除 – 3</li>
               <li>ブラックリスト – ブラックリスト - 4</li>
               <li>無効な値 – __Invalid_value__ - __Invalid_value__</li>
               <li>買収 – 買収 – 1</li>
               <li>サービスの購読 – 購読 – 2</li>
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
         <td>ブール値 </td>
         <td> </td>
      </tr>
   </table>

## フィルター

論理ステータス別（byLogicalStatus）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>都道府県</td>
    <td>定義済みリスト</td>
    </tr>
</table>

名前またはラベル （byText）

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

ステータス別（byState）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>都道府県</td>
    <td>定義済みリスト</td>
    </tr>
</table>

ターゲティングリソースによる（byTargetResource）

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

詳細ランディングページを含める（詳細を含む）

<table>
    <tr>
    <th>名前</th>
    <th>タイプ</th>
    </tr>
    <tr>
    <td>詳細</td>
    <td>ブール値</td>
    </tr>
</table>

異機種リストからの連続配信を含める（withContinuous）

<table>
        <tr>
        <th>名前</th>
        <th>タイプ</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>ブール値</td>
        </tr>
    </table>

指定された期間に存在（byCalendar）

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

指定された期間に公開（byPlanning）

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
